CMAKE_MINIMUM_REQUIRED(VERSION 2.8)
#the GCS Project Name defined here
PROJECT(GroundControlStation)

set (MAJOR 1)
set (MINOR 0)

#include main directories
add_subdirectory(doc)
add_subdirectory(include)
add_subdirectory(src)
add_subdirectory(resources)
add_subdirectory(test)


#include Modules
add_subdirectory(Common)
add_subdirectory(Gui)
add_subdirectory(Peripheral)
add_subdirectory(PlayRecord)
add_subdirectory(UAVSimulator)

set(SRC_LIST_APPDX )
foreach(LoopVar ${SrcFiles})
   set(SRC_LIST_APPDX ${SRC_LIST_APPDX}; src/${LOOP_VAR})
endforeach(LoopVar)

add_executable(${CMAKE_PROJECT_NAME} src/${SrcFiles})

