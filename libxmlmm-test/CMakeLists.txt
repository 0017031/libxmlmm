add_library(test)


target_include_directories(
  test PUBLIC D:/2vcpkg/installed/x86-windows-static/include/)

target_link_directories(
  test PUBLIC
  D:/2vcpkg/installed/x86-windows-static/$<$<CONFIG:Debug>:debug/>lib)

target_link_libraries(test PUBLIC libxml2.lib)

target_sources(
  test
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

