cmake_minimum_required(VERSION 3.8)

project(
    GoldFishBC
    VERSION 0.1
)

enable_language(C)
enable_language(CXX)

if(MSVC)
    enable_language(ASM_MASM)
else()
    enable_language(ASM_NASM)
    set( CMAKE_CXX_FLAGS "-DNDEBUG -g2 -O3 -fPIC -pthread -pipe -msse4.1 -msse4.2 -maes -msha -mssse3 -mpclmul" )
    set( CMAKE_ASM_NASM_FLAGS " -DX64 -g -f elf64 ")
endif()

add_executable(
    main
    main.cpp
)

target_link_libraries(
    main
    
)

set_target_properties(
    main 
    PROPERTIES CXX_STANDARD 11
)

add_subdirectory(
    deps
)