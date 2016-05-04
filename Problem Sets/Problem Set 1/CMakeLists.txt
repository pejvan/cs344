cmake_minimum_required( VERSION 3.5 )

find_package( OpenCV REQUIRED )

file( GLOB  hdr *.hpp *.h )
file( GLOB  cu  *.cu)
SET ( HW1_files main.cpp reference_calc.cpp compare.cpp )

find_package( CUDA )
CUDA_ADD_EXECUTABLE( HW1 ${HW1_files} ${hdr} ${cu} )
target_link_libraries( HW1 ${OpenCV_LIBS} )

file( GLOB inputfile cinque_terre_small.jpg )
file( COPY ${inputfile} DESTINATION ${CMAKE_BINARY_DIR} )