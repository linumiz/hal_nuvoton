# SPDX-License-Identifier: Apache-2.0
#
# Copyright (c) 2020 Linumiz
# Author: Saravanan Sekar <saravanan@linumiz.com>

if(CONFIG_CPU_HAS_FPU)
  zephyr_compile_definitions( -D__FPU_PRESENT )
  zephyr_compile_definitions( -D__FPU_USED )
endif()

zephyr_include_directories(StdDriver/inc)
zephyr_include_directories(Devices/M480/Include)

zephyr_sources_ifdef(CONFIG_SOC_SERIES_M48X Devices/M480/Source/system_M480.c)

add_subdirectory(StdDriver)
