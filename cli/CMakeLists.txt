cmake_minimum_required(VERSION 2.8)


project(dice)
# Find includes in corresponding build directories
set(CMAKE_INCLUDE_CURRENT_DIR ON)
# Instruct CMake to run moc automatically when needed.
set(CMAKE_AUTOMOC ON)

# Find the QtWidgets library
find_package(Qt5Core)

set(EXECUTABLE_OUTPUT_PATH bin/)


include_directories(${Qt5Core_INCLUDES} ../)
add_definitions(${Qt5Core_DEFINITIONS})

set(MODE "cli")


ADD_DEFINITIONS(
    -std=c++11 # Or -std=c++0x
    # Other flags
)
add_executable(
    dice     
   ../diceparser.cpp
   ../range.cpp
   ../booleancondition.cpp
   ../validator.cpp
   ../compositevalidator.cpp
   ../operationcondition.cpp
   ../die.cpp
   ../parsingtoolbox.cpp
   ../dicealias.cpp
   ../result/result.cpp
   ../result/scalarresult.cpp
   ../result/stringresult.cpp
   ../result/diceresult.cpp
   ../node/countexecutenode.cpp
   ../node/dicerollernode.cpp
   ../node/executionnode.cpp
   ../node/explosedicenode.cpp
   ../node/helpnode.cpp
   ../node/mergenode.cpp
   ../node/jumpbackwardnode.cpp
   ../node/keepdiceexecnode.cpp
   ../node/listaliasnode.cpp
   ../node/listsetrollnode.cpp
   ../node/numbernode.cpp
   ../node/parenthesesnode.cpp
   ../node/paintnode.cpp
   ../node/rerolldicenode.cpp
   ../node/scalaroperatornode.cpp
   ../node/sortresult.cpp
   ../node/startingnode.cpp
    ../node/ifnode.cpp
    main.cpp
    ../highlightdice.cpp
    )

target_link_libraries(dice ${Qt5Core_LIBRARIES})
INSTALL_TARGETS(/bin dice)

#qt5_use_modules()
