set(CMAKE_CXX_FLAGS "-fpermissive")
cmake_minimum_required(VERSION 2.8.12)
set(CMAKE_CXX_FLAGS "-fpermissive")
if (CMAKE_VERSION VERSION_LESS "3.1")
  if (CMAKE_CXX_COMPILER_ID STREQUAL "GNU")
    set (CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++11")
  endif ()
else ()
  set (CMAKE_CXX_STANDARD 11)
endif ()
project(tda)
# Set source directory
set(SOURCE_DIR "algorithms/")
# Tell CMake that headers are also in SOURCE_DIR
include_directories(${SOURCE_DIR})
set(SOURCES "${SOURCE_DIR}/CubicalRipser_2dim/src/cubicalripser_2dim.cpp" "${SOURCE_DIR}/CubicalRipser_2dim/src/dense_cubical_grids.cpp" "${SOURCE_DIR}/CubicalRipser_2dim/src/birthday_index.cpp" "${SOURCE_DIR}/CubicalRipser_2dim/src/columns_to_reduce.cpp" "${SOURCE_DIR}/CubicalRipser_2dim/src/simplex_coboundary_enumerator.cpp" "${SOURCE_DIR}/CubicalRipser_2dim/src/union_find.cpp" "${SOURCE_DIR}/CubicalRipser_2dim/src/write_pairs.cpp" "${SOURCE_DIR}/CubicalRipser_2dim/src/compute_pairs.cpp" "${SOURCE_DIR}/Ripser/ripser.cpp" "src/Filter.cpp")
include_directories("${SOURCE_DIR}/include") 

#	fpermissive flag for perseus


# Generate Python module
add_subdirectory(lib/pybind11)
pybind11_add_module(tda ${SOURCES} "src/bindings.cpp")
