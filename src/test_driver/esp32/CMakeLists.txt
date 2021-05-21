#
# This is project CMakeLists.txt
#

cmake_minimum_required(VERSION 3.5)
include($ENV{IDF_PATH}/tools/cmake/project.cmake)

project(chip-tests)
idf_build_set_property(CXX_COMPILE_OPTIONS "-DCHIP_SUPPORT_FOREIGN_TEST_DRIVERS;-DCHIP_TARGET_STYLE_EMBEDDED;-Wno-deprecated-declarations;-std=gnu++14;-Os;-DLWIP_IPV6_SCOPES=0;-DCHIP_HAVE_CONFIG_H" APPEND)
idf_build_set_property(C_COMPILE_OPTIONS "-DLWIP_IPV6_SCOPES=0;-std=gnu11" APPEND)

# The list of extra component dirs must be in sync with that in all-clusters-app/esp32/Makefile
set(EXTRA_COMPONENT_DIRS
    "${CMAKE_CURRENT_LIST_DIR}/third_party/connectedhomeip/config/esp32/components"
)


