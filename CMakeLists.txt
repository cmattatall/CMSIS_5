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
target_compile_options(ARMCM0 
    PRIVATE 
        -Wno-int-to-pointer-cast
        -Wno-pointer-to-int-cast
    PUBLIC
        -mthumb
        -mcpu=cortex-m0
)





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
target_compile_options(ARMCM0plus
    PRIVATE 
        -Wno-int-to-pointer-cast
        -Wno-pointer-to-int-cast
    PUBLIC
        -mthumb
        -mcpu=cortex-m0plus
)


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
target_compile_options(ARMCM0plusMpu 
    PRIVATE 
        -Wno-int-to-pointer-cast
        -Wno-pointer-to-int-cast
    PUBLIC
        -mthumb
        -mcpu=cortex-m0plus
)

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
target_compile_options(ARMCM1 
    PRIVATE 
        -Wno-int-to-pointer-cast
        -Wno-pointer-to-int-cast
    PUBLIC
        -mthumb
        -mcpu=cortex-m1
)

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
target_compile_options(ARMCM3
    PRIVATE 
        -Wno-int-to-pointer-cast
        -Wno-pointer-to-int-cast
    PUBLIC
        -mthumb
        -mcpu=cortex-m3
)


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
target_compile_options(ARMCM4
    PRIVATE 
        -Wno-int-to-pointer-cast
        -Wno-pointer-to-int-cast
    PUBLIC
        -mthumb
        -mcpu=cortex-m4
)


add_library(ARMCM4_SOFT_FP)
list(APPEND CMSIS_CORTEX_BRINGUP_TARGETS ARMCM4_SOFT_FP)
target_include_directories(ARMCM4_SOFT_FP 
    PUBLIC 
        $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/Device/ARM/ARMCM4/Include>
        $<INSTALL_INTERFACE:CMSIS/Device/ARM/ARMCM4/Include>
    PRIVATE
        $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/CMSIS/Core/Include>
        $<INSTALL_INTERFACE:CMSIS/Core/Include>
)
target_sources(ARMCM4_SOFT_FP 
    PRIVATE
        Device/ARM/ARMCM4/Source/startup_ARMCM4.c
        Device/ARM/ARMCM4/Source/system_ARMCM4.c
)
target_compile_definitions(ARMCM4_SOFT_FP PUBLIC ARMCM4_FP)
target_compile_options(ARMCM4_SOFT_FP
    PRIVATE 
        -Wno-int-to-pointer-cast
        -Wno-pointer-to-int-cast
    PUBLIC
        -mthumb
        -mcpu=cortex-m4
        -mfloat-abi=softfp
        -mfpu=fpv4-sp-d16
)


add_library(ARMCM4_HARD_FP)
list(APPEND CMSIS_CORTEX_BRINGUP_TARGETS ARMCM4_HARD_FP)
target_include_directories(ARMCM4_HARD_FP 
    PUBLIC 
        $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/Device/ARM/ARMCM4/Include>
        $<INSTALL_INTERFACE:CMSIS/Device/ARM/ARMCM4/Include>
    PRIVATE
        $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/CMSIS/Core/Include>
        $<INSTALL_INTERFACE:CMSIS/Core/Include>
)
target_sources(ARMCM4_HARD_FP 
    PRIVATE
        Device/ARM/ARMCM4/Source/startup_ARMCM4.c
        Device/ARM/ARMCM4/Source/system_ARMCM4.c
)
target_compile_definitions(ARMCM4_HARD_FP PUBLIC ARMCM4_FP)
target_compile_options(ARMCM4_HARD_FP
    PRIVATE 
        -Wno-int-to-pointer-cast
        -Wno-pointer-to-int-cast
    PUBLIC
        -mthumb
        -mcpu=cortex-m4
        -mfloat-abi=hard
        -mfpu=fpv4-sp-d16
)

#Permissible names are: ‘armv4t’, ‘armv5t’, ‘armv5te’, ‘armv6’, ‘armv6j’, ‘armv6k’, ‘armv6kz’, ‘armv6t2’, ‘armv6z’, ‘armv6zk’, ‘armv7’, ‘armv7-a’, ‘armv7ve’, ‘armv8-a’, ‘armv8.1-a’, ‘armv8.2-a’, ‘armv8.3-a’, ‘armv8.4-a’, ‘armv8.5-a’, ‘armv8.6-a’, ‘armv7-r’, ‘armv8-r’, ‘armv6-m’, ‘armv6s-m’, ‘armv7-m’, ‘armv7e-m’, ‘armv8-m.base’, ‘armv8-m.main’, ‘armv8.1-m.main’, ‘iwmmxt’ and ‘iwmmxt2’.

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
target_compile_options(ARMCM4_HARD_FP
    PRIVATE 
        -Wno-int-to-pointer-cast
        -Wno-pointer-to-int-cast
    PUBLIC
        -mthumb
        -mcpu=cortex-m7
        -march=armv7e-m
)


add_library(ARMCM23)
list(APPEND CMSIS_CORTEX_BRINGUP_TARGETS ARMCM23)
target_include_directories(ARMCM23
    PUBLIC 
        $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/Device/ARM/ARMCM23/Include>
        $<INSTALL_INTERFACE:CMSIS/Device/ARM/ARMCM23/Include>
    PRIVATE
        $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/CMSIS/Core/Include>
        $<INSTALL_INTERFACE:CMSIS/Core/Include>
)
target_sources(ARMCM23 
    PRIVATE
        Device/ARM/ARMCM23/Source/startup_ARMCM23.c
        Device/ARM/ARMCM23/Source/system_ARMCM23.c
)
target_compile_definitions(ARMCM23 PUBLIC ARMCM23)
target_compile_options(ARMCM23
    PRIVATE 
        -Wno-int-to-pointer-cast
        -Wno-pointer-to-int-cast
    PUBLIC
        -mthumb
        -mcpu=cortex-m23
        -march=armv8-m.main
        # Pretty uncertain on this one, there seems to have been a divergence
        # in the ISA betwen for armv7 and armv8. One of several compiler
        # options may be needed to make this work. 
        # - armv7e-m <-- this one is pretty unlikely
        # - armv8-m.base 
        # - armv8-m.main <-- I've use this one for now
)



add_library(ARMCM33)
list(APPEND CMSIS_CORTEX_BRINGUP_TARGETS ARMCM33)
target_include_directories(ARMCM33
    PUBLIC 
        $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/Device/ARM/ARMCM33/Include>
        $<INSTALL_INTERFACE:CMSIS/Device/ARM/ARMCM33/Include>
    PRIVATE
        $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/CMSIS/Core/Include>
        $<INSTALL_INTERFACE:CMSIS/Core/Include>
)
target_sources(ARMCM33 
    PRIVATE
        Device/ARM/ARMCM33/Source/startup_ARMCM33.c
        Device/ARM/ARMCM33/Source/system_ARMCM33.c
)
target_compile_definitions(ARMCM33 PUBLIC ARMCM33)
target_compile_options(ARMCM33
    PRIVATE 
        -Wno-int-to-pointer-cast
        -Wno-pointer-to-int-cast
    PUBLIC
        -mthumb
        -mcpu=cortex-m33
        -march=armv8-m.main
)

add_library(ARMCM35P)
list(APPEND CMSIS_CORTEX_BRINGUP_TARGETS ARMCM35P)
target_include_directories(ARMCM35P
    PUBLIC 
        $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/Device/ARM/ARMCM35P/Include>
        $<INSTALL_INTERFACE:CMSIS/Device/ARM/ARMCM35P/Include>
    PRIVATE
        $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/CMSIS/Core/Include>
        $<INSTALL_INTERFACE:CMSIS/Core/Include>
)
target_sources(ARMCM35P 
    PRIVATE
        Device/ARM/ARMCM35P/Source/startup_ARMCM35P.c
        Device/ARM/ARMCM35P/Source/system_ARMCM35P.c
)
target_compile_definitions(ARMCM35P PUBLIC ARMCM35P)
target_compile_options(ARMCM35P
    PRIVATE 
        -Wno-int-to-pointer-cast
        -Wno-pointer-to-int-cast
    PUBLIC
        -mthumb
        #-mcpu=cortex-m35p # seems that not all versions of arm-none-eabi-gcc toolchain support this flag for mcpu
        -march=armv8-m.main
        -mfpu=fpv5-sp-d16
)

#[[
cc1: note: valid arguments are: arm8 arm810 strongarm strongarm110 fa526 fa626 arm7tdmi arm7tdmi-s arm710t arm720t arm740t arm9 arm9tdmi arm920t arm920 arm922t arm940t ep9312 arm10tdmi arm1020t arm9e arm946e-s arm966e-s arm968e-s arm10e arm1020e arm1022e xscale iwmmxt iwmmxt2 fa606te fa626te fmp626 fa726te arm926ej-s arm1026ej-s arm1136j-s arm1136jf-s arm1176jz-s arm1176jzf-s mpcorenovfp mpcore arm1156t2-s arm1156t2f-s cortex-m1 cortex-m0 cortex-m0plus cortex-m1.small-multiply cortex-m0.small-multiply cortex-m0plus.small-multiply generic-armv7-a cortex-a5 cortex-a7 cortex-a8 cortex-a9 cortex-a12 cortex-a15 cortex-a17 cortex-r4 cortex-r4f cortex-r5 cortex-r7 cortex-r8 cortex-m7 cortex-m4 cortex-m3 marvell-pj4 cortex-a15.cortex-a7 cortex-a17.cortex-a7 cortex-a32 cortex-a35 cortex-a53 cortex-a57 cortex-a72 cortex-a73 exynos-m1 xgene1 cortex-a57.cortex-a53 cortex-a72.cortex-a53 cortex-a73.cortex-a35 cortex-a73.cortex-a53 cortex-a55 cortex-a75 cortex-a76 neoverse-n1 cortex-a75.cortex-a55 cortex-a76.cortex-a55 cortex-m23 cortex-m33 cortex-r52; did you mean 'cortex-m3'?
make[2]: *** [CMakeFiles/ARMCM35P.dir/build.make:76: CMakeFiles/ARMCM35P.dir/Device/ARM/ARMCM35P/Source/startup_ARMCM35P.c.obj] Error 1
make[1]: *** [CMakeFiles/Makefile2:391: CMakeFiles/ARMCM35P.dir/all] Error 2




#]]


if(NOT CPACK_PACKAGING_INSTALL_PREFIX)
    set(CPACK_PACKAGING_INSTALL_PREFIX ${PROJECT_SOURCE_DIR}/install/)
endif(NOT CPACK_PACKAGING_INSTALL_PREFIX)


set(INSTALL_LIBDIR lib)
set(INSTALL_INCLUDEDIR include)
set(INSTALL_BINDIR bin)

set(INSTALL_CONFIGDIR ${INSTALL_LIBDIR}/cmake/CMSIS)

install(
    TARGETS     ${CMSIS_CORTEX_BRINGUP_TARGETS}
    EXPORT      CMSIS
    LIBRARY     DESTINATION ${INSTALL_LIBDIR}/CMSIS/
    ARCHIVE     DESTINATION ${INSTALL_LIBDIR}/CMSIS/
    COMPONENT   lib
)

install(
    DIRECTORY       ${CMAKE_CURRENT_SOURCE_DIR}/CMSIS/Core/Include/
    DESTINATION     ${INSTALL_INCLUDEDIR}/CMSIS/Core/
    FILES_MATCHING  PATTERN "*.h"
)

file(GLOB DEVICE_IDIRS "${CMAKE_CURRENT_LIST_DIR}/Device/ARM/*/Include")
foreach(DIR ${DEVICE_IDIRS})
    get_filename_component(DEVICE_PATH ${DIR} DIRECTORY)
    get_filename_component(DEVICE ${DEVICE_PATH} NAME)
    install(
        DIRECTORY       ${CMAKE_CURRENT_SOURCE_DIR}/Device/ARM/${DEVICE}/Include/
        DESTINATION     ${INSTALL_INCLUDEDIR}/CMSIS/Device/${DEVICE}/
        FILES_MATCHING  PATTERN "*.h"
    )

    install(
        DIRECTORY       ${CMAKE_CURRENT_SOURCE_DIR}/Device/ARM/${DEVICE}/Config/
        DESTINATION     ${INSTALL_INCLUDEDIR}/CMSIS/Device/${DEVICE}/
        FILES_MATCHING  PATTERN "*.h"
    )

    install(
        DIRECTORY       ${CMAKE_CURRENT_SOURCE_DIR}/Device/ARM/${DEVICE}/Source/GCC/
        DESTINATION     ${INSTALL_INCLUDEDIR}/CMSIS/Device/${DEVICE}/
        FILES_MATCHING  PATTERN "*.ld"
    )

endforeach(DIR ${DEVICE_IDIRS})


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


################################################################################
## CPACK STUFF
################################################################################


if(NOT CPACK_PACKAGING_INSTALL_PREFIX)
    set(CPACK_PACKAGING_INSTALL_PREFIX "/usr/local/CMSIS/")
endif(NOT CPACK_PACKAGING_INSTALL_PREFIX)

# Write and set permissions for postinst
file(WRITE
    ${CMAKE_CURRENT_BINARY_DIR}/tmp/postinst
    "#!/bin/bash\n                                                                                        \
    ldconfig\n                                                                                            \
    chown $(whoami):$(whoami) -R ${CPACK_PACKAGING_INSTALL_PREFIX}/${INSTALL_INCLUDEDIR}/CMSIS\n    \
    chown $(whoami):$(whoami) -R ${CPACK_PACKAGING_INSTALL_PREFIX}/${INSTALL_LIBDIR}/CMSIS\n        \  
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