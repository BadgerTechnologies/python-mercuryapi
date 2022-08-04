cmake_minimum_required(VERSION 3.0.2)
project(mercury_api)

include(GNUInstallDirs)

execute_process(COMMAND python3 setup.py build
                WORKING_DIRECTORY ${PROJECT_SOURCE_DIR})

file(GLOB so ${PROJECT_SOURCE_DIR}/build/lib.linux-x86_64-3.8/mercury.cpython-38-x86_64-linux-gnu.so)

install(
  FILES ${so}
  DESTINATION ${CMAKE_INSTALL_LIBDIR}/python3.8/site-packages/
)
