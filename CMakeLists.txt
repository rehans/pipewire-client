cmake_minimum_required(VERSION 3.20.0)

include(FetchContent)

project("PipeWire Client")

find_package(PkgConfig REQUIRED)
pkg_check_modules(PIPEWIRE REQUIRED libpipewire-0.3)

message(STATUS "PIPEWIRE_INCLUDE_DIRS: ${PIPEWIRE_INCLUDE_DIRS}")
message(STATUS "PIPEWIRE_LIBRARIES: ${PIPEWIRE_LIBRARIES}")
message(STATUS "PIPEWIRE_CFLAGS_OTHER: ${PIPEWIRE_CFLAGS_OTHER}")

add_executable(pipewire_client 
    src/audio-dsp-src.cpp
)

target_link_libraries(pipewire_client 
    ${PIPEWIRE_LIBRARIES}
    m # Math library
)

target_include_directories(pipewire_client 
    PUBLIC
        ${PIPEWIRE_INCLUDE_DIRS}
)

target_compile_options(pipewire_client 
    PUBLIC
        ${PIPEWIRE_CFLAGS_OTHER}
        -fpermissive
)
