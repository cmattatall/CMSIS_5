cmake_minimum_required(VERSION 3.20)

project(CMSIS
    VERSION 5.0.0
    LANGUAGES C ASM
)

set(CMSIS_CORTEX_BRINGUP_TARGETS "") # empty list

add_library(ARMCM0)
list(APPEND CMSIS_CORTEX_BRINGUP_TARGETS ARMCM0)
target_include_directories(ARMCM0 
    PUBLIC 
        $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/Device/ARM/ARMCM0/Include>
        $<INSTALL_INTERFACE:CMSIS/Device/ARM/ARMCM0/Include>
    PRIVATE
        $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/CMSIS/Core/Include>
        $<INSTALL_INTERFACE:CMSIS/Core/Include>
)
target_sources(ARMCM0 
    PRIVATE
        Device/ARM/ARMCM0/Source/startup_ARMCM0.c
        Device/ARM/ARMCM0/Source/system_ARMCM0.c
)
target_compile_definitions(ARMCM0 PUBLIC ARMCM0)



add_library(ARMCM0plus)
list(APPEND CMSIS_CORTEX_BRINGUP_TARGETS ARMCM0plus)
target_include_directories(ARMCM0plus 
    PUBLIC 
        $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/Device/ARM/ARMCM0plus/Include>
        $<INSTALL_INTERFACE:CMSIS/Device/ARM/ARMCM0plus/Include>
    PRIVATE
        $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/CMSIS/Core/Include>
        $<INSTALL_INTERFACE:CMSIS/Core/Include>
)
target_sources(ARMCM0plus 
    PRIVATE
        Device/ARM/ARMCM0plus/Source/startup_ARMCM0plus.c
        Device/ARM/ARMCM0plus/Source/system_ARMCM0plus.c
)
target_compile_definitions(ARMCM0plus PUBLIC ARMCM0P)


add_library(ARMCM0plusMpu)
list(APPEND CMSIS_CORTEX_BRINGUP_TARGETS ARMCM0plusMpu)
target_include_directories(ARMCM0plusMpu
    PUBLIC 
        $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/Device/ARM/ARMCM0plus/Include>
        $<INSTALL_INTERFACE:CMSIS/Device/ARM/ARMCM0plus/Include>
    PRIVATE
        $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/CMSIS/Core/Include>
        $<INSTALL_INTERFACE:CMSIS/Core/Include>
)
target_sources(ARMCM0plusMpu 
    PRIVATE
        Device/ARM/ARMCM0plus/Source/startup_ARMCM0plus.c
        Device/ARM/ARMCM0plus/Source/system_ARMCM0plus.c
)
target_compile_definitions(ARMCM0plusMpu PUBLIC ARMCM0P_MPU)


add_library(ARMCM1)
list(APPEND CMSIS_CORTEX_BRINGUP_TARGETS ARMCM1)
target_include_directories(ARMCM1 
    PUBLIC 
        $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/Device/ARM/ARMCM1/Include>
        $<INSTALL_INTERFACE:CMSIS/Device/ARM/ARMCM1/Include>
    PRIVATE
        $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/CMSIS/Core/Include>
        $<INSTALL_INTERFACE:CMSIS/Core/Include>
)
target_sources(ARMCM1 
    PRIVATE
        Device/ARM/ARMCM1/Source/startup_ARMCM1.c
        Device/ARM/ARMCM1/Source/system_ARMCM1.c
)
target_compile_definitions(ARMCM1 PUBLIC ARMCM1)


add_library(ARMCM3)
list(APPEND CMSIS_CORTEX_BRINGUP_TARGETS ARMCM3)
target_include_directories(ARMCM3 
    PUBLIC 
        $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/Device/ARM/ARMCM3/Include>
        $<INSTALL_INTERFACE:CMSIS/Device/ARM/ARMCM3/Include>
    PRIVATE
        $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/CMSIS/Core/Include>
        $<INSTALL_INTERFACE:CMSIS/Core/Include>
)
target_sources(ARMCM3 
    PRIVATE
        Device/ARM/ARMCM3/Source/startup_ARMCM3.c
        Device/ARM/ARMCM3/Source/system_ARMCM3.c
)
target_compile_definitions(ARMCM3 PUBLIC ARMCM3)


add_library(ARMCM4)
list(APPEND CMSIS_CORTEX_BRINGUP_TARGETS ARMCM4)
target_include_directories(ARMCM4 
    PUBLIC 
        $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/Device/ARM/ARMCM4/Include>
        $<INSTALL_INTERFACE:CMSIS/Device/ARM/ARMCM4/Include>
    PRIVATE
        $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/CMSIS/Core/Include>
        $<INSTALL_INTERFACE:CMSIS/Core/Include>
)
target_sources(ARMCM4 
    PRIVATE
        Device/ARM/ARMCM4/Source/startup_ARMCM4.c
        Device/ARM/ARMCM4/Source/system_ARMCM4.c
)
target_compile_definitions(ARMCM4 PUBLIC ARMCM4)


add_library(ARMCM7)
list(APPEND CMSIS_CORTEX_BRINGUP_TARGETS ARMCM7)
target_include_directories(ARMCM7
    PUBLIC 
        $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/Device/ARM/ARMCM7/Include>
        $<INSTALL_INTERFACE:CMSIS/Device/ARM/ARMCM7/Include>
    PRIVATE
        $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/CMSIS/Core/Include>
        $<INSTALL_INTERFACE:CMSIS/Core/Include>
)
target_sources(ARMCM7 
    PRIVATE
        Device/ARM/ARMCM7/Source/startup_ARMCM7.c
        Device/ARM/ARMCM7/Source/system_ARMCM7.c
)
target_compile_definitions(ARMCM7 PUBLIC ARMCM7)


include(GNUInstallDirs)
set(INSTALL_CONFIGDIR ${CMAKE_INSTALL_LIBDIR}/cmake/CMSIS)

install(
    TARGETS     ${CMSIS_CORTEX_BRINGUP_TARGETS}
    EXPORT      CMSIS
    LIBRARY     DESTINATION ${CMAKE_INSTALL_LIBDIR}/CMSIS/
    ARCHIVE     DESTINATION ${CMAKE_INSTALL_LIBDIR}/CMSIS/
    COMPONENT   lib
)

install(
    DIRECTORY       ${CMAKE_CURRENT_SOURCE_DIR}/CMSIS/Core/Include/
    DESTINATION     ${CMAKE_INSTALL_INCLUDEDIR}/CMSIS/Core/
    FILES_MATCHING  PATTERN "*.h"
)

file(GLOB DEVICE_IDIRS "${CMAKE_CURRENT_LIST_DIR}/Device/ARM/*/Include")
foreach(DIR ${DEVICE_IDIRS})
    get_filename_component(DEVICE_PATH ${DIR} DIRECTORY)
    get_filename_component(DEVICE ${DEVICE_PATH} NAME)
    message("${DEVICE}")
    install(
        DIRECTORY       ${CMAKE_CURRENT_SOURCE_DIR}/CMSIS/Device/ARM/${DEVICE}/Include/
        DESTINATION     ${CMAKE_INSTALL_INCLUDEDIR}/CMSIS/Device/${DEVICE}/
        FILES_MATCHING  PATTERN "*.h"
    )
endforeach(DIR ${DEVICE_IDIRS})

#[[
install(
    DIRECTORY       ${CMAKE_CURRENT_SOURCE_DIR}/CMSIS/Device/ARM/
    DESTINATION     ${CMAKE_INSTALL_INCLUDEDIR}/CMSIS/Device/
    FILES_MATCHING  PATTERN "*/Include/*.h"
)
#]]

install(
    EXPORT      CMSIS
    FILE        CMSISTargets.cmake
    NAMESPACE   CMSIS::
    DESTINATION ${INSTALL_CONFIGDIR}
)


#Create a ConfigVersion.cmake file
include(CMakePackageConfigHelpers)
write_basic_package_version_file(
    ${CMAKE_CURRENT_BINARY_DIR}/CMSISConfigVersion.cmake
    VERSION ${PROJECT_VERSION}
    COMPATIBILITY AnyNewerVersion
)

configure_package_config_file(
    ${CMAKE_CURRENT_LIST_DIR}/cmake/CMSISconfig.cmake.in
    ${CMAKE_CURRENT_BINARY_DIR}/CMSISConfig.cmake
    INSTALL_DESTINATION ${INSTALL_CONFIGDIR}
)

configure_file(
    ${CMAKE_CURRENT_SOURCE_DIR}/cmake/FindCMSIS.cmake.in
    ${CMAKE_CURRENT_SOURCE_DIR}/cmake/FindCMSIS.cmake
    @ONLY
)

file(COPY_FILE ${CMAKE_CURRENT_SOURCE_DIR}/cmake/FindCMSIS.cmake ${CMAKE_CURRENT_BINARY_DIR}/FindCMSIS.cmake)
file(REMOVE ${CMAKE_CURRENT_SOURCE_DIR}/cmake/FindCMSIS.cmake)


#Install the config, configversion and custom find modules
install(
    FILES
        ${CMAKE_CURRENT_BINARY_DIR}/FindCMSIS.cmake
        ${CMAKE_CURRENT_BINARY_DIR}/CMSISConfig.cmake
        ${CMAKE_CURRENT_BINARY_DIR}/CMSISConfigVersion.cmake
    
    DESTINATION 
        ${INSTALL_CONFIGDIR}
)

# Register package in the User Package Registry
export(PACKAGE CMSIS)


set(CPACK_PACKAGING_INSTALL_PREFIX "${CMAKE_CURRENT_SOURCE_DIR}/install_prefix")

# Write and set permissions for postinst

message("CPACK_PACKAGING_INSTALL_PREFIX = ${CPACK_PACKAGING_INSTALL_PREFIX}")

if(NOT CPACK_PACKAGING_INSTALL_PREFIX)
    set(CPACK_PACKAGING_INSTALL_PREFIX "/usr/local/")
endif(NOT CPACK_PACKAGING_INSTALL_PREFIX)

file(WRITE
    ${CMAKE_CURRENT_BINARY_DIR}/tmp/postinst
    "#!/bin/bash\n                                                                                        \
    ldconfig\n                                                                                            \
    chown $(whoami):$(whoami) -R ${CPACK_PACKAGING_INSTALL_PREFIX}/${CMAKE_INSTALL_INCLUDEDIR}/CMSIS\n    \
    chown $(whoami):$(whoami) -R ${CPACK_PACKAGING_INSTALL_PREFIX}/${CMAKE_INSTALL_LIBDIR}/CMSIS\n        \  
    "
)

file(COPY ${CMAKE_CURRENT_BINARY_DIR}/tmp/postinst
    DESTINATION ${CMAKE_CURRENT_BINARY_DIR}/configFiles
    FILE_PERMISSIONS
        OWNER_READ OWNER_WRITE OWNER_EXECUTE
        GROUP_READ GROUP_EXECUTE
        WORLD_READ WORLD_EXECUTE
)

# Remove temp directory
file(REMOVE_RECURSE ${CMAKE_CURRENT_BINARY_DIR}/tmp/)

set(PKG_ARCH amd64)

set(CPACK_PACKAGE_CONTACT "cmattatall2@gmail.com")
set(CPACK_DEBIAN_PACKAGE_MAINTAINER "cmattatall2@gmail.com")
set(CPACK_DEBIAN_PACKAGE_DESCRIPTION "Debian package for ARM cortex bringup targets using cmake")
set(CPACK_DEBIAN_PACKAGE_ARCHITECTURE ${PKG_ARCH})
set(CPACK_PACKAGE_VERSION ${PROJECT_VERSION_MAJOR}.${PROJECT_VERSION_MINOR}.${PROJECT_VERSION_PATCH})
set(CPACK_PACKAGE_FILE_NAME ${PROJECT_NAME}_${CPACK_PACKAGE_VERSION}-${CPACK_DEBIAN_PACKAGE_ARCHITECTURE})
set(CPACK_DEBIAN_PACKAGE_NAME lib${PROJECT_NAME}${PROJECT_VERSION_MAJOR})
set(CPACK_GENERATOR "DEB")

# generate dependencies
set(CPACK_DEBIAN_PACKAGE_SHLIBDEPS ON)
set(CPACK_DEBIAN_PACKAGE_SECTION libs)

# generate dependencies for upstream packages
set(CPACK_DEBIAN_PACKAGE_GENERATE_SHLIBS ON)
set(CPACK_DEBIAN_PACKAGE_GENERATE_SHLIBS_POLICY ">=")

set(CPACK_DEBIAN_PACKAGE_CONTROL_EXTRA ${CMAKE_CURRENT_BINARY_DIR}/configFiles/postinst)
set(CPACK_LIB_STRIP_FILES TRUE)

message(STATUS 
  "Debian Package: ${CPACK_DEBIAN_PACKAGE_NAME} (${CPACK_PACKAGE_VERSION}) [${CPACK_PACKAGE_FILE_NAME}.deb]"
)

include(CPack)