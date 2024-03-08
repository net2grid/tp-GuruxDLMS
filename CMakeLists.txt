file(GLOB srcs_gurux ${CMAKE_CURRENT_LIST_DIR}/development/src/*.c)
set(incl_gurux       ${CMAKE_CURRENT_LIST_DIR}/development/include)

set(opts_gurux -w)
set(defs_gurux
  "DLMS_IGNORE_IP6_SETUP"
  "DLMS_IGNORE_SERVER")

if(NOT CMAKE_SCRIPT_MODE_FILE OR CMAKE_PARENT_LIST_FILE)
  add_library(gurux ${srcs_gurux})
  target_include_directories(gurux PUBLIC ${incl_gurux})
  target_compile_definitions(gurux PRIVATE ${defs_gurux})
  target_compile_options(gurux PRIVATE ${opts_gurux})
endif()
