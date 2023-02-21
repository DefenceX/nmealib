
project(libnmea C)

cmake_minimum_required(VERSION 3.18)
set(CFLAGS "CCFLAGS = -Wall -fPIC -D_POSIX_C_SOURCE")

set(SOURCES
    ./src/context.c
    ./src/generate.c
    ./src/generator.c
    ./src/info.c
    ./src/parse.c
    ./src/parser.c
    ./src/sentence.c
    ./src/time.c
    ./src/gmath.c
    ./src/tok.c
    ./src/util.c
)

add_library(libnmea STATIC ${SOURCES})
target_include_directories(libnmea PUBLIC ${CMAKE_CURRENT_SOURCE_DIR}/include)

Target_link_libraries(libnmea m)

install(TARGETS libnmea DESTINATION lib)