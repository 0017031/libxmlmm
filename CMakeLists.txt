cmake_minimum_required(VERSION 3.20)
project(libxmlmm VERSION 0.6.0 LANGUAGES CXX)
set(CMAKE_CXX_STANDARD 23)

if (MSVC)
    add_compile_options(/sdl $<$<CONFIG:Debug>:/GS> /wd4068 /nologo) # /diagnostics:caret  /utf-8
    add_compile_definitions($<$<CONFIG:Debug>:_DEBUG>)
endif ()

# include(CTest) enable_testing()
set(BUILD_SHARED_LIBS 1)

add_subdirectory(libxmlmm)

# set(CPACK_PROJECT_NAME ${PROJECT_NAME}) set(CPACK_PROJECT_VERSION
# ${PROJECT_VERSION}) include(CPack)

add_subdirectory(libxmlmm-test)

