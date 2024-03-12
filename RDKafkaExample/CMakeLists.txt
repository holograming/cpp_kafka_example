SET(CMAKE_TOOLCHAIN_FILE "vcpkg.cmake not found" CACHE FILEPATH "${CMAKE_CURRENT_LIST_DIR}/../cmake/scripts/buildsystems/vcpkg.cmake")
SET(VCPKG_TARGET_TRIPLET "vcpkg_target_triplet need define!" CACHE STRING "x64-windows;x64-windows-static;") #x64-windows / x64-windows-static

cmake_minimum_required(VERSION 3.16)

project(RDKafkaExample
    LANGUAGES CXX
    VERSION 0.0.1.0
    DESCRIPTION "kafka RDKafkaExample project."
)

find_package(RdKafka CONFIG REQUIRED)

add_executable(RDKafkaConsumner RDKafkaConsumner.cpp)
target_link_libraries(RDKafkaConsumner PRIVATE RdKafka::rdkafka RdKafka::rdkafka++)

add_executable(RDKafkaProducer RDKafkaProducer.cpp)
target_link_libraries(RDKafkaProducer PRIVATE RdKafka::rdkafka RdKafka::rdkafka++)