cmake_minimum_required(VERSION 2.6)

set(APP_NAME luaprotoc)
project (${APP_NAME})

set(CMAKE_C_FLAGS "${CMAKE_C_FLAGS} -O3 -shared -fPIC -std=c99")
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++11")

set(GAME_SRC
  pb.c
)

include_directories(
    external/lua-5.1.5/src
)

link_directories(
)

# lua 
add_subdirectory(external/lua-5.1.5/src)

# add the executable
add_executable(${APP_NAME}
  ${GAME_SRC}
)

target_link_libraries(${APP_NAME}
  lua
  )

set(APP_BIN_DIR "${CMAKE_BINARY_DIR}/bin")

set_target_properties(${APP_NAME} PROPERTIES
     RUNTIME_OUTPUT_DIRECTORY  "${APP_BIN_DIR}")

