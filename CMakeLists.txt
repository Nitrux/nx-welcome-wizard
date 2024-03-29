cmake_minimum_required(VERSION 3.1)

project(nx-welcome-wizard LANGUAGES CXX)

set(CMAKE_INCLUDE_CURRENT_DIR ON)
set(CMAKE_AUTOMOC ON)
set(CMAKE_AUTORCC ON)
set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

find_package(
  Qt5

  COMPONENTS
    Core
    Quick
    Concurrent

  REQUIRED
)

add_executable(
  ${PROJECT_NAME}

  Helper.h
  Helper.cpp
  ShellHelper.h
  ShellHelper.cpp
  main.cpp

  qml.qrc
)

target_link_libraries(
  ${PROJECT_NAME}

  Qt5::Core
  Qt5::Quick
  Qt5::Concurrent
)

install(
  TARGETS ${PROJECT_NAME}
  RUNTIME DESTINATION bin
)

install(DIRECTORY applications DESTINATION ${CMAKE_INSTALL_PREFIX}/share)
