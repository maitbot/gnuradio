# Copyright 2011 Free Software Foundation, Inc.
#
# This file is part of GNU Radio
#
# SPDX-License-Identifier: GPL-3.0-or-later
#

########################################################################
# Setup dependencies
########################################################################
find_package(Doxygen)
find_package(MathJax2)

########################################################################
# Register components
########################################################################
include(GrComponent)

########################################################################
# Begin conditional configuration
########################################################################
gr_register_component("doxygen" ENABLE_DOXYGEN DOXYGEN_FOUND)
if(ENABLE_DOXYGEN)
    add_subdirectory(doxygen)
endif(ENABLE_DOXYGEN)

gr_register_component("man-pages" ENABLE_MANPAGES)
if(ENABLE_MANPAGES)
    add_subdirectory(man)
endif(ENABLE_MANPAGES)
