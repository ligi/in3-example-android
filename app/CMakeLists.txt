# Sets the minimum version of CMake required to build your native library.
# This ensures that a certain set of CMake features is available to
# your build.

cmake_minimum_required(VERSION 3.4.1)

OPTION(FAST_MATH "Math optimizations" OFF)
IF(FAST_MATH)
  MESSAGE ( STATUS "Enable math optimizations (excutable size may increase)" )
  ADD_DEFINITIONS(-DIN3_MATH_FAST)
ELSE()
  MESSAGE ( STATUS "Disable math optimizations (optimised for executable size)" )
  ADD_DEFINITIONS(-DIN3_MATH_LITE)
ENDIF(FAST_MATH)



# Specifies a library name, specifies whether the library is STATIC or
# SHARED, and provides relative paths to the source code. You can
# define multiple libraries by adding multiple add_library() commands,
# and CMake builds them for you. When you build your app, Gradle
# automatically packages shared libraries with your APK.

# Sets lib_src_DIR to the path of the target CMake project.
set( core_src_DIR src/main/core )

# Sets lib_build_DIR to the path of the desired output directory.
set( core_build_DIR src/main/core/outputs )
file(MAKE_DIRECTORY ${core_build_DIR})


# Sets lib_src_DIR to the path of the target CMake project.
set( eth_api_src_DIR src/main/eth_api )
# Sets lib_build_DIR to the path of the desired output directory.
set( eth_api_build_DIR src/main/eth_api/outputs )
file(MAKE_DIRECTORY ${eth_api_build_DIR})

# Sets lib_src_DIR to the path of the target CMake project.
set( eth_basic_src_DIR src/main/eth_basic )
# Sets lib_build_DIR to the path of the desired output directory.
set( eth_basic_build_DIR src/main/eth_basic/outputs )
file(MAKE_DIRECTORY ${eth_basic_build_DIR})


# Sets lib_src_DIR to the path of the target CMake project.
set( eth_nano_src_DIR src/main/eth_nano )
# Sets lib_build_DIR to the path of the desired output directory.
set( eth_nano_build_DIR src/main/eth_nano/outputs )
file(MAKE_DIRECTORY ${eth_nano_build_DIR})

# Sets lib_src_DIR to the path of the target CMake project.
set( libin3_src_DIR src/main/libin3 )
# Sets lib_build_DIR to the path of the desired output directory.
set( libin3_build_DIR src/main/libin3/outputs )
file(MAKE_DIRECTORY ${libin3_build_DIR})


# Sets lib_src_DIR to the path of the target CMake project.
set( eth_full_src_DIR src/main/eth_full )
# Sets lib_build_DIR to the path of the desired output directory.
set( eth_full_build_DIR src/main/eth_full/outputs )
file(MAKE_DIRECTORY ${eth_full_build_DIR})


add_subdirectory( # Specifies the directory of the CMakeLists.txt file.
        ${core_src_DIR}
        # Specifies the directory for the build outputs.
        ${core_build_DIR})


add_subdirectory( # Specifies the directory of the CMakeLists.txt file.
        ${eth_api_src_DIR}
        # Specifies the directory for the build outputs.
        ${eth_api_build_DIR})

add_subdirectory( # Specifies the directory of the CMakeLists.txt file.
        ${eth_basic_src_DIR}
        # Specifies the directory for the build outputs.
        ${eth_basic_build_DIR})

add_subdirectory( # Specifies the directory of the CMakeLists.txt file.
        ${eth_nano_src_DIR}
        # Specifies the directory for the build outputs.
        ${eth_nano_build_DIR})

add_subdirectory( # Specifies the directory of the CMakeLists.txt file.
        ${libin3_src_DIR}
        # Specifies the directory for the build outputs.
        ${libin3_build_DIR})


add_subdirectory( # Specifies the directory of the CMakeLists.txt file.
        ${eth_full_src_DIR}
        # Specifies the directory for the build outputs.
        ${eth_full_build_DIR})