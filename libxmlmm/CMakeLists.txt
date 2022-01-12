add_library(libxmlmm)
target_link_libraries(libxmlmm PRIVATE LibXml2::LibXml2 Iconv::Iconv)

if (BUILD_SHARED_LIBS)
    message("libxmlmm: BUILD_SHARED_LIBS")
    #    target_compile_definitions(libxmlmm PRIVATE _WINDLL LIB_COMPILE)
    #    target_include_directories(libxmlmm PRIVATE D:/2vcpkg/installed/$<IF:$<EQUAL:4,${CMAKE_SIZEOF_VOID_P}>,x86,x64>-windows/include/)
    #    target_link_directories(libxmlmm PRIVATE D:/2vcpkg/installed/$<IF:$<EQUAL:4,${CMAKE_SIZEOF_VOID_P}>,x86,x64>-windows/$<$<CONFIG:Debug>:debug/>lib)

else ()
    message("libxmlmm: BUILD_STATic")
    #    #    target_link_directories(libxmlmm INTERFACE D:/2vcpkg/installed/$<IF:$<EQUAL:4,${CMAKE_SIZEOF_VOID_P}>,x86,x64>-windows-static/$<$<CONFIG:Debug>:debug/>lib)
    #    target_include_directories(libxmlmm PRIVATE D:/2vcpkg/installed/$<IF:$<EQUAL:4,${CMAKE_SIZEOF_VOID_P}>,x86,x64>-windows-static/include/)
    #    target_link_directories(libxmlmm PUBLIC D:/2vcpkg/installed/$<IF:$<EQUAL:4,${CMAKE_SIZEOF_VOID_P}>,x86,x64>-windows-static/$<$<CONFIG:Debug>:debug/>lib)
    #    target_link_libraries(libxmlmm PUBLIC libxml2 iconv zlib$<$<CONFIG:Debug>:d>)
    #
endif ()

target_sources(libxmlmm PRIVATE
        Attribute.cpp
        CData.cpp
        Comment.cpp
        Content.cpp
        Document.cpp
        Element.cpp
        LibXmlSentry.cpp
        Node.cpp
        ProcessingInstruction.cpp
        Text.cpp
        utils.cpp)

find_package(LibXml2 REQUIRED)
find_package(Iconv)


#$<$<EQUAL:4,${CMAKE_SIZEOF_VOID_P}>:...>    # 32-bit build
#$<$<EQUAL:8,${CMAKE_SIZEOF_VOID_P}>:...>
#
#$<IF:$<CONFIG:Debug>,cppzmq,cppzmq-static>
#
#$<IF:$<EQUAL:4,${CMAKE_SIZEOF_VOID_P}>,cppzmq,cppzmq-static>