cmake_minimum_required(VERSION 3.20)
project(libxmlmm VERSION 0.6.0)
set(CMAKE_CXX_STANDARD 23)

if(MSVC)
  add_compile_options(/diagnostics:caret /sdl /utf-8 $<$<CONFIG:Debug>:/GS>)
  add_compile_definitions($<$<CONFIG:Debug>:_DEBUG>)
endif()

# include(CTest) enable_testing()

if(BUILD_SHARED_LIBS)
  message("BUILD_SHARED_LIBS1")
else()
  message("BUILD_STATic1")
endif()

add_subdirectory(libxmlmm)

# set(CPACK_PROJECT_NAME ${PROJECT_NAME}) set(CPACK_PROJECT_VERSION
# ${PROJECT_VERSION}) include(CPack)
