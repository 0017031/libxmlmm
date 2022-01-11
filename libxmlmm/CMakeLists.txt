add_library(libxmlmm)

if(BUILD_SHARED_LIBS)
  message("BUILD_SHARED_LIBS")
else()
  message("BUILD_STATic")
  target_link_directories(
    libxmlmm PUBLIC
    D:/2vcpkg/installed/x86-windows-static/$<$<CONFIG:Debug>:debug/>lib)
endif()

target_include_directories(libxmlmm
                           PUBLIC D:/2vcpkg/installed/x86-windows/include/)

target_link_libraries(libxmlmm PUBLIC libxml2.lib)

target_sources(
  libxmlmm
  PRIVATE Attribute.cpp
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
