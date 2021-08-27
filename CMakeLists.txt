cmake_minimum_required(VERSION 3.20)

project(CMSIS
    VERSION 5.0.0
    LANGUAGES C ASM
)


set(CMSIS_CORTEX_TARGETS "") # empty list

add_library(ARMCM0)
list(APPEND CMSIS_CORTEX_TARGETS ARMCM0)
target_include_directories(ARMCM0 
    PUBLIC 
        $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/Device/ARM/ARMCM0/Include>
        $<INSTALL_INTERFACE:CMSIS/Device/ARM/ARMCM0/Include>
        $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/CMSIS/Core/Include>
        $<INSTALL_INTERFACE:CMSIS/Core/Include>
)
target_sources(ARMCM0 
    PUBLIC
        Device/ARM/ARMCM0/Source/startup_ARMCM0.c
        Device/ARM/ARMCM0/Source/system_ARMCM0.c
)
target_compile_definitions(ARMCM0 PUBLIC ARMCM0)
target_compile_options(ARMCM0 
    PUBLIC 
        -Wno-int-to-pointer-cast
        -Wno-pointer-to-int-cast
        -mthumb
        -mcpu=cortex-m0
)


add_library(ARMCM0plus)
list(APPEND CMSIS_CORTEX_TARGETS ARMCM0plus)
target_include_directories(ARMCM0plus 
    PUBLIC 
        $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/Device/ARM/ARMCM0plus/Include>
        $<INSTALL_INTERFACE:CMSIS/Device/ARM/ARMCM0plus/Include>
        $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/CMSIS/Core/Include>
        $<INSTALL_INTERFACE:CMSIS/Core/Include>
)
target_sources(ARMCM0plus 
    PUBLIC
        Device/ARM/ARMCM0plus/Source/startup_ARMCM0plus.c
        Device/ARM/ARMCM0plus/Source/system_ARMCM0plus.c
)
target_compile_definitions(ARMCM0plus PUBLIC ARMCM0P)
target_compile_options(ARMCM0plus
    PUBLIC 
        -Wno-int-to-pointer-cast
        -Wno-pointer-to-int-cast
        -mthumb
        -mcpu=cortex-m0plus
)


add_library(ARMCM0plusMpu)
list(APPEND CMSIS_CORTEX_TARGETS ARMCM0plusMpu)
target_include_directories(ARMCM0plusMpu
    PUBLIC 
        $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/Device/ARM/ARMCM0plus/Include>
        $<INSTALL_INTERFACE:CMSIS/Device/ARM/ARMCM0plus/Include>
        $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/CMSIS/Core/Include>
        $<INSTALL_INTERFACE:CMSIS/Core/Include>
)
target_sources(ARMCM0plusMpu 
    PUBLIC
        Device/ARM/ARMCM0plus/Source/startup_ARMCM0plus.c
        Device/ARM/ARMCM0plus/Source/system_ARMCM0plus.c
)
target_compile_definitions(ARMCM0plusMpu PUBLIC ARMCM0P_MPU)
target_compile_options(ARMCM0plusMpu 
    PUBLIC 
        -Wno-int-to-pointer-cast
        -Wno-pointer-to-int-cast
        -mthumb
        -mcpu=cortex-m0plus
)

add_library(ARMCM1)
list(APPEND CMSIS_CORTEX_TARGETS ARMCM1)
target_include_directories(ARMCM1 
    PUBLIC 
        $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/Device/ARM/ARMCM1/Include>
        $<INSTALL_INTERFACE:CMSIS/Device/ARM/ARMCM1/Include>
        $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/CMSIS/Core/Include>
        $<INSTALL_INTERFACE:CMSIS/Core/Include>
)
target_sources(ARMCM1 
    PUBLIC
        Device/ARM/ARMCM1/Source/startup_ARMCM1.c
        Device/ARM/ARMCM1/Source/system_ARMCM1.c
)
target_compile_definitions(ARMCM1 PUBLIC ARMCM1)
target_compile_options(ARMCM1 
    PUBLIC 
        -Wno-int-to-pointer-cast
        -Wno-pointer-to-int-cast
        -mthumb
        -mcpu=cortex-m1
)

add_library(ARMCM3)
list(APPEND CMSIS_CORTEX_TARGETS ARMCM3)
target_include_directories(ARMCM3 
    PUBLIC 
        $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/Device/ARM/ARMCM3/Include>
        $<INSTALL_INTERFACE:CMSIS/Device/ARM/ARMCM3/Include>
        $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/CMSIS/Core/Include>
        $<INSTALL_INTERFACE:CMSIS/Core/Include>
)
target_sources(ARMCM3 
    PUBLIC
        Device/ARM/ARMCM3/Source/startup_ARMCM3.c
        Device/ARM/ARMCM3/Source/system_ARMCM3.c
)
target_compile_definitions(ARMCM3 PUBLIC ARMCM3)
target_compile_options(ARMCM3
    PUBLIC 
        -Wno-int-to-pointer-cast
        -Wno-pointer-to-int-cast
        -mthumb
        -mcpu=cortex-m3
)


add_library(ARMCM4)
list(APPEND CMSIS_CORTEX_TARGETS ARMCM4)
target_include_directories(ARMCM4 
    PUBLIC 
        $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/Device/ARM/ARMCM4/Include>
        $<INSTALL_INTERFACE:CMSIS/Device/ARM/ARMCM4/Include>
        $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/CMSIS/Core/Include>
        $<INSTALL_INTERFACE:CMSIS/Core/Include>
)
target_sources(ARMCM4 
    PUBLIC
        Device/ARM/ARMCM4/Source/startup_ARMCM4.c
        Device/ARM/ARMCM4/Source/system_ARMCM4.c
)
target_compile_definitions(ARMCM4 PUBLIC ARMCM4)
target_compile_options(ARMCM4
    PUBLIC 
        -Wno-int-to-pointer-cast
        -Wno-pointer-to-int-cast
        -mthumb
        -mcpu=cortex-m4
)


add_library(ARMCM4_SOFT_FP)
list(APPEND CMSIS_CORTEX_TARGETS ARMCM4_SOFT_FP)
target_include_directories(ARMCM4_SOFT_FP 
    PUBLIC 
        $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/Device/ARM/ARMCM4/Include>
        $<INSTALL_INTERFACE:CMSIS/Device/ARM/ARMCM4/Include>
        $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/CMSIS/Core/Include>
        $<INSTALL_INTERFACE:CMSIS/Core/Include>
)
target_sources(ARMCM4_SOFT_FP 
    PUBLIC
        Device/ARM/ARMCM4/Source/startup_ARMCM4.c
        Device/ARM/ARMCM4/Source/system_ARMCM4.c
)
target_compile_definitions(ARMCM4_SOFT_FP PUBLIC ARMCM4_FP)
target_compile_options(ARMCM4_SOFT_FP
    PUBLIC 
        -Wno-int-to-pointer-cast
        -Wno-pointer-to-int-cast
        -mthumb
        -mcpu=cortex-m4
        -mfloat-abi=softfp
        -mfpu=fpv4-sp-d16
)


add_library(ARMCM4_HARD_FP)
list(APPEND CMSIS_CORTEX_TARGETS ARMCM4_HARD_FP)
target_include_directories(ARMCM4_HARD_FP 
    PUBLIC 
        $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/Device/ARM/ARMCM4/Include>
        $<INSTALL_INTERFACE:CMSIS/Device/ARM/ARMCM4/Include>
        $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/CMSIS/Core/Include>
        $<INSTALL_INTERFACE:CMSIS/Core/Include>
)
target_sources(ARMCM4_HARD_FP 
    PUBLIC
        Device/ARM/ARMCM4/Source/startup_ARMCM4.c
        Device/ARM/ARMCM4/Source/system_ARMCM4.c
)
target_compile_definitions(ARMCM4_HARD_FP PUBLIC ARMCM4_FP)
target_compile_options(ARMCM4_HARD_FP
    PUBLIC 
        -Wno-int-to-pointer-cast
        -Wno-pointer-to-int-cast
        -mthumb
        -mcpu=cortex-m4
        -mfloat-abi=hard
        -mfpu=fpv4-sp-d16
)


set(CPU_TARGET ARMCM7)
set(CPU_CMSIS_DIR ARMCM7)
add_library(${CPU_TARGET})
list(APPEND CMSIS_CORTEX_TARGETS ${CPU_TARGET})
target_include_directories(${CPU_TARGET}
    PUBLIC 
        $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/Device/ARM/${CPU_CMSIS_DIR}/Include>
        $<INSTALL_INTERFACE:CMSIS/Device/ARM/${CPU_CMSIS_DIR}/Include>
        $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/CMSIS/Core/Include>
        $<INSTALL_INTERFACE:CMSIS/Core/Include>
)
target_sources(${CPU_TARGET} 
    PUBLIC
        Device/ARM/${CPU_CMSIS_DIR}/Source/startup_${CPU_CMSIS_DIR}.c
        Device/ARM/${CPU_CMSIS_DIR}/Source/system_${CPU_CMSIS_DIR}.c
)
target_compile_definitions(${CPU_TARGET} PUBLIC ARMCM7)
target_compile_options(${CPU_TARGET}
    PUBLIC 
        -Wno-int-to-pointer-cast
        -Wno-pointer-to-int-cast
        -mthumb
        -mcpu=cortex-m7
        -march=armv7e-m
)


set(CPU_TARGET ARMCM23)
set(CPU_CMSIS_DIR ARMCM23)
add_library(${CPU_TARGET})
list(APPEND CMSIS_CORTEX_TARGETS ${CPU_TARGET})
target_include_directories(${CPU_TARGET}
    PUBLIC 
        $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/Device/ARM/${CPU_CMSIS_DIR}/Include>
        $<INSTALL_INTERFACE:CMSIS/Device/ARM/${CPU_CMSIS_DIR}/Include>
        $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/CMSIS/Core/Include>
        $<INSTALL_INTERFACE:CMSIS/Core/Include>
)
target_sources(${CPU_TARGET} 
    PUBLIC
        Device/ARM/${CPU_CMSIS_DIR}/Source/startup_${CPU_CMSIS_DIR}.c
        Device/ARM/${CPU_CMSIS_DIR}/Source/system_${CPU_CMSIS_DIR}.c
)
target_compile_definitions(${CPU_TARGET} PUBLIC ARMCM23)
target_compile_options(${CPU_TARGET}
    PUBLIC 
        -Wno-int-to-pointer-cast
        -Wno-pointer-to-int-cast
        -mthumb
        -mcpu=cortex-m23
)



set(CPU_TARGET ARMCM33)
set(CPU_CMSIS_DIR ARMCM33)
add_library(${CPU_TARGET})
list(APPEND CMSIS_CORTEX_TARGETS ${CPU_TARGET})
target_include_directories(${CPU_TARGET}
    PUBLIC 
        $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/Device/ARM/${CPU_CMSIS_DIR}/Include>
        $<INSTALL_INTERFACE:CMSIS/Device/ARM/${CPU_CMSIS_DIR}/Include>
        $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/CMSIS/Core/Include>
        $<INSTALL_INTERFACE:CMSIS/Core/Include>
)
target_sources(${CPU_TARGET} 
    PUBLIC
        Device/ARM/${CPU_CMSIS_DIR}/Source/startup_${CPU_CMSIS_DIR}.c
        Device/ARM/${CPU_CMSIS_DIR}/Source/system_${CPU_CMSIS_DIR}.c
)
target_compile_definitions(${CPU_TARGET} PUBLIC ARMCM33)
target_compile_options(${CPU_TARGET}
    PUBLIC 
        -Wno-int-to-pointer-cast
        -Wno-pointer-to-int-cast
        -mthumb
        -mcpu=cortex-m33
        -march=armv8-m.main+nodsp+nofp # THE nodsp and nofp parts are IMPORTANT
)


set(CPU_TARGET ARMCM33_DSP_FP)
set(CPU_CMSIS_DIR ARMCM33)
add_library(${CPU_TARGET})
list(APPEND CMSIS_CORTEX_TARGETS ${CPU_TARGET})
target_include_directories(${CPU_TARGET}
    PUBLIC 
        $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/Device/ARM/${CPU_CMSIS_DIR}/Include>
        $<INSTALL_INTERFACE:CMSIS/Device/ARM/${CPU_CMSIS_DIR}/Include>
        $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/CMSIS/Core/Include>
        $<INSTALL_INTERFACE:CMSIS/Core/Include>
)
target_sources(${CPU_TARGET} 
    PUBLIC
        Device/ARM/${CPU_CMSIS_DIR}/Source/startup_${CPU_CMSIS_DIR}.c
        Device/ARM/${CPU_CMSIS_DIR}/Source/system_${CPU_CMSIS_DIR}.c
)
target_compile_definitions(${CPU_TARGET} PUBLIC ARMCM33_DSP_FP)
target_compile_options(${CPU_TARGET}
    PUBLIC 
        -Wno-int-to-pointer-cast
        -Wno-pointer-to-int-cast
        -mthumb
        -mcpu=cortex-m33
        -march=armv8-m.main # THE nodsp and nofp parts are IMPORTANT
)



set(CPU_TARGET ARMCM35P)
set(CPU_CMSIS_DIR ARMCM35P)
add_library(${CPU_TARGET})
list(APPEND CMSIS_CORTEX_TARGETS ${CPU_TARGET})
target_include_directories(${CPU_TARGET}
    PUBLIC 
        $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/Device/ARM/${CPU_CMSIS_DIR}/Include>
        $<INSTALL_INTERFACE:CMSIS/Device/ARM/${CPU_CMSIS_DIR}/Include>
        $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/CMSIS/Core/Include>
        $<INSTALL_INTERFACE:CMSIS/Core/Include>
)
target_sources(${CPU_TARGET} 
    PUBLIC
        Device/ARM/${CPU_CMSIS_DIR}/Source/startup_${CPU_CMSIS_DIR}.c
        Device/ARM/${CPU_CMSIS_DIR}/Source/system_${CPU_CMSIS_DIR}.c
)
target_compile_definitions(${CPU_TARGET} PUBLIC ARMCM35P)
target_compile_options(${CPU_TARGET}
    PUBLIC 
        -Wno-int-to-pointer-cast
        -Wno-pointer-to-int-cast
        -mthumb
        -mcpu=cortex-m35p+nodsp+nofp
)


set(CPU_TARGET ARMCM35P_DSP_FP)
set(CPU_CMSIS_DIR ARMCM35P)
add_library(${CPU_TARGET})
list(APPEND CMSIS_CORTEX_TARGETS ${CPU_TARGET})
target_include_directories(${CPU_TARGET}
    PUBLIC 
        $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/Device/ARM/${CPU_CMSIS_DIR}/Include>
        $<INSTALL_INTERFACE:CMSIS/Device/ARM/${CPU_CMSIS_DIR}/Include>
        $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/CMSIS/Core/Include>
        $<INSTALL_INTERFACE:CMSIS/Core/Include>
)
target_sources(${CPU_TARGET} 
    PUBLIC
        Device/ARM/${CPU_CMSIS_DIR}/Source/startup_${CPU_CMSIS_DIR}.c
        Device/ARM/${CPU_CMSIS_DIR}/Source/system_${CPU_CMSIS_DIR}.c
)
target_compile_definitions(${CPU_TARGET} PUBLIC ARMCM35P_DSP_FP)
target_compile_options(${CPU_TARGET}
    PUBLIC 
        -Wno-int-to-pointer-cast
        -Wno-pointer-to-int-cast
        -mthumb
        -mcpu=cortex-m35p
)


add_library(ARMCM55)
list(APPEND CMSIS_CORTEX_TARGETS ARMCM55)
target_include_directories(ARMCM55
    PUBLIC 
        $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/Device/ARM/ARMCM55/Include>
        $<INSTALL_INTERFACE:CMSIS/Device/ARM/ARMCM55/Include>
        $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/CMSIS/Core/Include>
        $<INSTALL_INTERFACE:CMSIS/Core/Include>
)
target_sources(ARMCM55 
    PUBLIC
        Device/ARM/ARMCM55/Source/startup_ARMCM55.c
        Device/ARM/ARMCM55/Source/system_ARMCM55.c
)
target_compile_definitions(ARMCM55 PUBLIC ARMCM55)
target_compile_options(ARMCM55
    PUBLIC 
        -Wno-int-to-pointer-cast
        -Wno-pointer-to-int-cast
        -mthumb
        -mcpu=cortex-m55 # seems that not all versions of arm-none-eabi-gcc toolchain support this flag for mcpu
        -mfpu=fpv5-sp-d16
)



#[[


if(NOT CPACK_PACKAGING_INSTALL_PREFIX)
    set(CPACK_PACKAGING_INSTALL_PREFIX ${PROJECT_SOURCE_DIR}/install/)
endif(NOT CPACK_PACKAGING_INSTALL_PREFIX)


set(INSTALL_LIBDIR lib)
set(INSTALL_INCLUDEDIR include)
set(INSTALL_BINDIR bin)

set(INSTALL_CONFIGDIR ${INSTALL_LIBDIR}/cmake/CMSIS)

install(
    TARGETS     ${CMSIS_CORTEX_TARGETS}
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

#]]


message("Listing CMSIS targets ...")
foreach(target ${CMSIS_CORTEX_TARGETS})
    message(" - ${target}")
endforeach(target ${CMSIS_CORTEX_TARGETS})
message("")
