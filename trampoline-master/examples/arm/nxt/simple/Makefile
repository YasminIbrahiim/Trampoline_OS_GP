#
# @file Makefile
#
# @section desc File description
#
# Makefile for application test
# automatically generated by goil on Thu Jun 20 18:34:40 2019
# from root OIL file nxt_simple.oil
#
# @section copyright Copyright
#
# Trampoline OS
#
# Trampoline is copyright (c) IRCCyN 2005-2012
# Trampoline is protected by the French intellectual property law.
#
# This software is distributed under the Lesser GNU Public Licence
#
# @section infos File informations
#
# Do not modify directly this file, it can be overwritten by goil
# Instead, you can update your .oil file description.
#
# $Date$
# $Rev$
# $Author$
# $URL$
#
# make          : build application test
# make doc      : extract both dev and user docs from trampoline sources 
#                 (doxygen and dot required).
# make clean    : remove everything except the Makefile.
# 
# NOTE: dependancies are set by default (to recompile the needed files)
#       if your compiler does not support it (-MF -MD) you can turn it off:
#       use the NODEP symbol, i.e. : make clean NODEP=1
#

#############################################################################
# USER APPLICATION CONFIGURATION
#############################################################################

# Name of the generated executable
# it should be declared as APP_NAME in the OS section of the .oil file.
# if not, it defaults to 'trampoline'
EXEC = nxt_simple_exe

# Name of the source OIL file
OIL_FILE = nxt_simple.oil

# Source files of the application.
# it should be declared as APP_SRC in the OS section of the .oil file
# (many times allowed).
SOURCES = nxt_simple.c

OIL_GENERATED_FILES += tpl_dispatch_table.c
OIL_GENERATED_FILES += tpl_invoque.S

WITH_IOC = false

# Trampoline generation flags
WITH_TRACE = false
WITH_MEMMAP = true
WITH_LINKSCRIPT = true
WITH_MEMORY_PROTECTION = false


# CFLAGS: flags used for the C compilation process
# it should be declared as CFLAGS in the OS section of the .oil file
# (many times allowed).
override CFLAGS += -g -c -ffreestanding -fsigned-char -mcpu=arm7tdmi -Os -Winline -Wall -Werror-implicit-function-declaration --param max-inline-insns-single=1000 -ffunction-sections -fdata-sections -std=gnu99 -I/trampoline/machines/arm/nxt/drivers/lejos_nxj/src/nxtvm/platform/nxt -I/trampoline/machines/arm/nxt/drivers/ecrobot/c  -I/trampoline/machines/arm/nxt/drivers -I/trampoline/machines/arm/nxt/drivers/ecrobot/bios -I/trampoline/machines/arm/nxt/drivers/lejos_nxj/src/nxtvm/javavm -I/trampoline/os -DTRUE=1 -DFALSE=0 -Du8=uint8 -Du32=uint32 -Du16=uint16


# LDFLAGS: flags used for the link process
# it should be declared as LDFLAGS in the OS section of the .oil file
# (many times allowed).
LDFLAGS = -g --allow-multiple-definition --gc-sections -L/usr/arm-none-eabi/lib -L/usr/lib/gcc/arm-none-eabi/7.3.1 -lc -lm -lgcc

LDFLAGS += -T nxt_simple/script.ld
# ASFLAGS: flags used for the assembly process (if required)
# it should be declared as AS_FLAGS in the OS section of the .oil file
# (many times allowed).
ASFLAGS = -g -mcpu=arm7tdmi-s --fatal-warnings 

# Default build directory
BUILD_DIR = build

# Autosar extension
# If 'true', Autosar extension are compiled in (schedule tables, ...)
AUTOSAR = false
AUTOSAR_SC = 0
AUTOSAR_OSAPPLICATIONS = false

# Scheduler
SCHEDULER = osek

#############################################################################
# COMPILER CONFIGURATION
#############################################################################
# Program used to compile files.
# it should be declared as COMPILER in the OS section of the .oil file.
# default is 'gcc'
CC = arm-none-eabi-gcc

# Program used to link files during compilation process.
# it should be declared as LINKER in the OS section of the .oil file.
# default is 'gcc'

LD = arm-none-eabi-ld

# Program used to link files during compilation process.
# it should be declared as ASSEMBLER in the OS section of the .oil file.
# default is 'gcc'
AS = arm-none-eabi-as

#############################################################################
# TRAMPOLINE CONFIGURATION
#############################################################################

# Trampoline root path to source code.
# it should be declared as TRAMPOLINE_BASE_PATH
# in the OS section of the .oil file.
TPL_BASE_PATH = /trampoline

# Target is given in goil command line when generating the Makefile. 
# If you update the target here, it will be taken into account, and 
# a new Makefile will be generated with the new target.
TARGET = arm/nxt
ARCH = arm
CHIP = nxt
MACHINE_INCLUDE_PATH = -I/trampoline/machines/arm -I/trampoline/machines/arm/nxt
MACHINE_INCLUDE_MAKEFILE = /trampoline/machines/arm/Makefile /trampoline/machines/arm/nxt/Makefile
MACHINE_ALL_PATHS = /trampoline/machines/arm /trampoline/machines/arm/nxt

# WITH_USECOM is true if COM is used
WITH_USECOM = false

# WITH_USEDEBUG is true if DEBUG is used
WITH_USEDEBUG = false

# WITH_SYSTEM_CALL is true when compiling trampoline
# with system call support. It is false otherwise
WITH_SYSTEM_CALL = true

#############################################################################
# OIL COMPILER CONFIGURATION
#############################################################################
# Goil OIL compiler tool configuration.
# If the GOIL_TEMPLATE_PATH is commented, the default template path is used
# (it can be saved in the .profile file).
GOIL_COMPILER = goil
GOIL_TEMPLATE_PATH = /trampoline/goil/templates

#############################################################################
# DOCUMENTATION GENERATION
#############################################################################
# The doxygen tool is used to extract both user and developpment 
# documentation from the source code. 
# See http://www.stack.nl/~dimitri/doxygen/
# You should also install Graphviz dot tool to build dependancy graph in
# the documentation:
# see http://www.graphviz.org/
DOXYGEN = doxygen

#############################################################################
# TARGET SPECIFIC STUFF
#############################################################################
#add the 'hex' rule for avr
hex: $(EXEC)
	@arm-none-eabi-objcopy -O binary $(EXEC)  $(EXEC).rxe

EXTRA_FILES_CLEAN += $(EXEC).rxe



#############################################################################
# KERNEL FILE LIST
#############################################################################

SOURCES += tpl_os_kernel.c
SOURCES += tpl_os_timeobj_kernel.c
SOURCES += tpl_os_action.c
SOURCES += tpl_os_error.c

#############################################################################
# SYSTEM CALL FILE LIST
#############################################################################

SOURCES += tpl_os_os_kernel.c
SOURCES += tpl_os_os.c
SOURCES += tpl_os_interrupt_kernel.c
SOURCES += tpl_os_task_kernel.c
SOURCES += tpl_os_resource_kernel.c
SOURCES += tpl_os_alarm_kernel.c

#############################################################################
# call Trampoline makefile rules.
#############################################################################

# Call main Trampoline Makefile
OS_MAKE_PATH = $(TPL_BASE_PATH)/make
include $(OS_MAKE_PATH)/Makefile

# vim:ft=make
