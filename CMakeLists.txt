CMAKE_MINIMUM_REQUIRED(VERSION 2.8)
#the GCS Project Name defined here
PROJECT(GroundControlStation CXX)

set (MAJOR 1)
set (MINOR 0)

#configure_file(
#        "${PROJECT_SOURCE_DIR}/ladderConfig.h.in"
#        "${PROJECT_BINARY_DIR}/ladderConfig.h"
#)

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
foreach(LOOP_VAR ${Src_Files})
   set(SRC_LIST_APPDX ${SRC_LIST_APPDX}; src/${LOOP_VAR})
endforeach(LOOP_VAR)

add_executable(GroundControlStation  ${SRC_LIST_APPDX}  )
target_link_libraries(GroundControlStation LINK_PUBLIC CommonLib)
