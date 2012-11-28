################################################################################
# OPENFRAMEWORKS MAKEFILE
#   The openFrameworks makefile system is desiged for ease of use, and 
#   particularly for straight-forward platform-based configurations.
#
#   Read the documentation or simply execute :
#
#   make help 
#
#   for a brief help file.
#
################################################################################

# define the OF_SHARED_MAKEFILES location
OF_SHARED_MAKEFILES_PATH=./makefileCommon

# do all of the core cofiguration work.
# configuration work basically means creating lots of
# lists of source files, search paths, libraries, etc.
#
ifndef OF_ROOT
    OF_ROOT=../../..
endif

ifndef SHELL
    SHELL := /bin/sh
endif

# if the user has not specified a special variant, then use the default variant
ifndef PLATFORM_VARIANT
	PLATFORM_VARIANT=default
endif


include makefileCommon/config.make


################################ FLAGS #########################################
# define the location of the core path
#TODO: make sure all of the right checks are here.
ifndef PLATFORM_CORE_EXCLUSIONS
    $(error PLATFORM_CORE_EXCLUSIONS not defined)
endif

ifndef OF_LIBS_OPENFRAMEWORKS_PATH
    $(error OF_LIBS_OPENFRAMEWORKS_PATH not defined)
endif


################################################################################
# CORE SOURCE FILES
################################################################################

# search the directories in the source folders for all .cpp files
# filter out all excluded files / folders that were defined above
# grep -v "/\.[^\.]" will exclude all .hidden folders and files
OF_CORE_SOURCE_FILES=$(filter-out $(CORE_EXCLUSIONS),$(shell find $(OF_CORE_SOURCE_PATHS) -name "*.cpp" | grep -v "/\.[^\.]"))


################################################################################
# DEBUG INFO
################################################################################
ifdef MAKEFILE_DEBUG
    $(info =============================configure.core.flags.make========================)

    $(info ---OF_CORE_SOURCE_FILES---)
    $(foreach v, $(OF_CORE_SOURCE_FILES),$(info $(v)))
endif



# compile core openFrameworks library
# check for platform specific compile rules
# if there's none use common ones
ifeq ($(wildcard $(OF_PLATFORM_MAKEFILES)/compile.core.make),) 
    include $(OF_SHARED_MAKEFILES_PATH)/compile.core.make
else 
    include $(OF_PLATFORM_MAKEFILES)/compile.core.make
endif




