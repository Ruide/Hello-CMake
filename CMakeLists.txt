cmake_minimum_required(VERSION "3.5.1")

project("HelloWorld") # give us couple of variables. e.g. PROJECT_NAME


add_executable("${PROJECT_NAME}" "Main.cpp") # add an executable into cmake, needs 2 params (name and source) # deref the string variable


# need sudo to install: /usr/local/ <=> {CMAKE_INSTALL_PREFIX/CMAKE_INSTALL_PREFIX}
install(TARGETS "${PROJECT_NAME}" DESTINATION bin) # bin is relative path to cmake install prefix.<-- ${CMAKE_INSTALL_PREFIX}/bin
install(FILES "Main.cpp" DESTINATION src) # src is relative path to cmake src prefix.<-- ${CMAKE_INSTALL_PREFIX}/src

include(CTest)

add_test("test1" "${CMAKE_CURRENT_BINARY_DIR}/${PROJECT_NAME}") # test1 passes if process return 0. CMAKE_CURRENT_BINARY_DIR points to current build dir
# add_test("test2" "${CMAKE_CURRENT_BINARY_DIR}/${PROJECT_NAME}" "someparameter") 

