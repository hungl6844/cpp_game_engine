cmake_minimum_required(VERSION 3.28)
project(cpp_game_engine)

set(CMAKE_CXX_STANDARD 17)

# Notes from hayden :>
# OLD: If you receive process finished with exit code -1073741515 you need to take the SDL2.dll in x64 or x86 (depending on your machine's stuff) and copy it to your System32 folder

# you no longer need to put it into System32, just make sure your IDE is set up to run out of this repository
# additionally, make sure when you ship the executable, SDL2.dll is included, because if it can't find it, it will be mad

set(SDL2_INCLUDE_DIR ${CMAKE_SOURCE_DIR}/SDL/include)
set(SDL2_LIB_DIR ${CMAKE_SOURCE_DIR}/SDL/lib/x64) # If something messes up try switching this to x86 on your machine

include_directories(${SDL2_INCLUDE_DIR})
link_directories(${SDL2_LIB_DIR})

add_executable(cpp_game_engine main.cpp)

target_link_libraries(
        ${PROJECT_NAME}
        SDL2main
        SDL2
)