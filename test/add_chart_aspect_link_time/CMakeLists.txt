# Copyright Louis Dionne 2017
# Distributed under the Boost Software License, Version 1.0.
# (See accompanying file LICENSE.md or copy at http://boost.org/LICENSE_1_0.txt)

# This test makes sure that using the LINK_TIME aspect with metabench_add_chart
# produces a graph of the link time. The test does not actually check anything;
# this must be done by manual inspection.

cmake_minimum_required(VERSION 3.1)
list(APPEND CMAKE_MODULE_PATH "${CMAKE_CURRENT_SOURCE_DIR}/../..")
include(metabench)

metabench_add_dataset(dummy "dummy.cpp.erb" "[1, 2, 3]")
metabench_add_chart(check ASPECT LINK_TIME DATASETS dummy)
