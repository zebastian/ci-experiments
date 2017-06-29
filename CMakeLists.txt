## CMAKE BUILD SYSTEM SPECIFICATION ##
cmake_minimum_required(VERSION 3.2)
project(dummy)

# Detect Compilation System.
if ("${CMAKE_CXX_COMPILER_ID}" STREQUAL "Clang")
	set(USING_CLANG TRUE)
	message(STATUS "Clang Compiler Detected")
elseif ("${CMAKE_CXX_COMPILER_ID}" STREQUAL "GNU")
	set(USING_GNU TRUE)
	message(STATUS "GNU Compiler Detected")
elseif ("${CMAKE_CXX_COMPILER_ID}" STREQUAL "Intel")
	set(USING_INTEL TRUE)
	message(STATUS "Intel Compiler Detected")
elseif ("${CMAKE_CXX_COMPILER_ID}" STREQUAL "MSVC")
	set(USING_MSVC TRUE)
	message(STATUS "MSVC Compiler Detected")
endif()

# Find includes in corresponding build directories.
set(CMAKE_INCLUDE_CURRENT_DIR ON)

# Find all sources.
file(GLOB srcHeader "src/*.h" "src/*.hpp")
file(GLOB srcDef "src/*.c" "src/*.cpp")
set(SOURCE_FILES ${srcHeader} ${srcDef})

include_directories(src)

# Add source files to the build target.
add_executable(dummy ${SOURCE_FILES})

# mark win32 application as a console application
IF(WIN32 AND MSVC)
	add_definitions(-D_CRT_SECURE_NO_WARNINGS=1)
	set_target_properties(${PROJECT_NAME} PROPERTIES
		WIN32_EXECUTABLE YES
		LINK_FLAGS "/SUBSYSTEM:CONSOLE"
	)
ENDIF()

##########################
# Installation
##########################

install(TARGETS ${PROJECT_NAME}
	ARCHIVE DESTINATION ${CMAKE_INSTALL_PREFIX}
	LIBRARY DESTINATION ${CMAKE_INSTALL_PREFIX}
	RUNTIME DESTINATION ${CMAKE_INSTALL_PREFIX}
)

