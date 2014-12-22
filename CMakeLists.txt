CMAKE_MINIMUM_REQUIRED(VERSION 2.8)
#the GCS Project Name defined here
PROJECT(GroundControlStation CXX)

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
foreach(LOOP_VAR ${Src_Files})
   set(SRC_LIST_APPDX ${SRC_LIST_APPDX}; src/${LOOP_VAR})
endforeach(LOOP_VAR)


add_executable(${CMAKE_PROJECT_NAME}  ${SRC_LIST_APPDX}  )



#add_library(mylib   ${Inc_Files})
