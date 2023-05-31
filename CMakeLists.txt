cmake_minimum_required(VERSION 2.8.3)
project(ttlidar_demo)

set(TTLIDAR_SDK_PATH "./sdk/")

#SET(CMAKE_BUILD_TYPE "Debug")  
#SET(CMAKE_CXX_FLAGS_DEBUG "$ENV{CXXFLAGS} -O0 -Wall -g2 -ggdb")  
#SET(CMAKE_CXX_FLAGS_RELEASE "$ENV{CXXFLAGS} -O3 -Wall") 

include_directories(
  ${TTLIDAR_SDK_PATH}/include
  ${TTLIDAR_SDK_PATH}/src
  ${TTLIDAR_SDK_PATH}/src/arch
  ${TTLIDAR_SDK_PATH}/src/arch/linux
)

file(GLOB TTLIDAR_SDK_SRC 
  "${TTLIDAR_SDK_PATH}/src/*.cpp"
  "${TTLIDAR_SDK_PATH}/src/arch/*.cpp" 
  "${TTLIDAR_SDK_PATH}/src/arch/linux/*.cpp"
)



add_executable(ttlidar_demo app/demo_main.cpp ${TTLIDAR_SDK_SRC})

target_link_libraries(ttlidar_demo -lrt -lpthread)


