################################################################################
# CROSS COMPILING OVERRIDES
#    Uncomment the following lines and edit the necessary paths, if you are
#	 compiling on a host platform different than the target platform
################################################################################
PLATFORM_OS=Linux
PLATFORM_ARCH=armv6l
PLATFORM_VARIANT=cross
TOOLCHAIN_BIN=/Volumes/raspberrypidev/tools/arm-unknown-linux-gnueabi/bin
TOOLCHAIN_PREFIX=arm-unknown-linux-gnueabi-
ROOTFS=/Volumes/raspberrypidev/rootfs

# Attempt to load a config.make file.
# If none is found, project defaults in config.project.make will be used.
ifneq ($(wildcard config.make),)
	include config.make
endif

# make sure the the OF_ROOT location is defined
ifndef OF_ROOT
    OF_ROOT=../../..
endif

# call the project makefile!
include $(OF_ROOT)/libs/openFrameworksCompiled/project/makefileCommon/compile.project.mk
