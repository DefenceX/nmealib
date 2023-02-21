
project(nmea C)

cmake_minimum_required(VERSION 3.18)
set(CMAKE_C_FLAGS "-Wall -fPIC -D_POSIX_C_SOURCE")

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

add_library(nmea STATIC ${SOURCES})
target_include_directories(nmea PUBLIC ${CMAKE_CURRENT_SOURCE_DIR}/include)

target_link_libraries(nmea m)

install(TARGETS nmea DESTINATION lib)

