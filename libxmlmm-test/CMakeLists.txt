add_executable(test_app)
target_sources(test_app PRIVATE CDataTest.cpp DocumentTest.cpp ElementTest.cpp main.cpp)
target_include_directories(test_app PRIVATE ${CMAKE_CURRENT_SOURCE_DIR})
target_link_libraries(test_app PRIVATE
        libxmlmm
        GTest::GTest)

if (BUILD_SHARED_LIBS)
    message("test_app: BUILD_SHARED_LIBS")
    target_compile_definitions(test_app PRIVATE _WINDLL)

    #    target_include_directories(test_app PRIVATE libxmlmm-test D:/2vcpkg/installed/$<IF:$<EQUAL:4,${CMAKE_SIZEOF_VOID_P}>,x86,x64>-windows/include/)
    #    target_link_directories(test_app PRIVATE D:/2vcpkg/installed/$<IF:$<EQUAL:4,${CMAKE_SIZEOF_VOID_P}>,x86,x64>-windows/$<$<CONFIG:Debug>:debug/>lib)

else ()
    message("test_app: BUILD_STATic")
    #    target_include_directories(test_app PRIVATE libxmlmm-test D:/2vcpkg/installed/$<IF:$<EQUAL:4,${CMAKE_SIZEOF_VOID_P}>,x86,x64>-windows-static/include)
    #    target_link_directories(test_app PRIVATE D:/2vcpkg/installed/$<IF:$<EQUAL:4,${CMAKE_SIZEOF_VOID_P}>,x86,x64>-windows-static-md/$<$<CONFIG:Debug>:debug/>lib)
endif ()


#target_include_directories(test_app PRIVATE D:/2vcpkg/installed/x86-windows-static/include/)
#target_link_directories(test_app PRIVATE D:/2vcpkg/installed/x86-windows-static/$<$<CONFIG:Debug>:debug/>lib)

find_package(GTest)