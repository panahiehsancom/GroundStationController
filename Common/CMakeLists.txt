CMAKE_MINIMUM_REQUIRED(VERSION 2.8)
#include main files
add_subdirectory(doc)
add_subdirectory(include)
add_subdirectory(src)
add_subdirectory(resources)
add_subdirectory(test)

set(MODULE_NAME Common )

set(INC_LIST_APPDX )
foreach(LOOP_VAR ${Inc_Files})
   set(INC_LIST_APPDX ${INC_LIST_APPDX}; include/${LOOP_VAR})
endforeach(LOOP_VAR)

set(SRC_LIST_APPDX )
foreach(LOOP_VAR ${Src_Files})
   set(SRC_LIST_APPDX ${SRC_LIST_APPDX}; src/${LOOP_VAR})
endforeach(LOOP_VAR)

add_library(CommonLib SHARED ${INC_LIST_APPDX} ${SRC_LIST_APPDX})
target_include_directories(CommonLib PUBLIC ${CMAKE_CURRENT_SOURCE_DIR})


#set(Inc_Files ${MODULE_NAME}/${INC_LIST_APPDX} PARENT_SCOPE)



