cmake_minimum_required(VERSION 2.8.8)

set(DSN_ROOT "$ENV{DSN_ROOT}")
set(DSN_THIRDPARTY_ROOT "$ENV{DSN_THIRDPARTY_ROOT}")
if((DSN_ROOT STREQUAL "") OR (NOT EXISTS "${DSN_ROOT}/"))
    message(FATAL_ERROR "Please make sure that DSN_ROOT is defined and does exists.")
endif()

include("${DSN_ROOT}/bin/dsn.cmake")

set(DSN_BUILD_RUNTIME FALSE)

dsn_common_setup()

add_subdirectory(base)
add_subdirectory(client_lib)
add_subdirectory(server)
add_subdirectory(shell)
add_subdirectory(redis_protocol)
add_subdirectory(test/function_test)
add_subdirectory(test/kill_test)
add_subdirectory(test/pressure_test)
