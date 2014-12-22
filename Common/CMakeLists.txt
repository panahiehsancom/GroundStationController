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

#set(Inc_Files ${MODULE_NAME}/${INC_LIST_APPDX})
#message("${Inc_Files}")
#add_library(${MODULE_NAME} SHARED ${INC_LIST_APPDX})


