
SET(CMAKE_TOOLCHAIN_FILE "vcpkg.cmake not found" CACHE FILEPATH "${CMAKE_CURRENT_LIST_DIR}/../cmake/scripts/buildsystems/vcpkg.cmake")
SET(VCPKG_TARGET_TRIPLET "vcpkg_target_triplet need define!" CACHE STRING "x64-windows;x64-windows-static;") #x64-windows / x64-windows-static

set(CMAKE_CXX_STANDARD 17)

cmake_minimum_required(VERSION 3.16)

project(ModernCppKafkaExample
    LANGUAGES CXX
    VERSION 0.0.1.0
    DESCRIPTION "kafka ModernCppKafkaExample project."
)

find_package(unofficial-modern-cpp-kafka CONFIG REQUIRED)

add_executable(ModernCppKafkaConsumer ModernCppKafkaConsumer.cpp)
target_link_libraries(ModernCppKafkaConsumer PRIVATE unofficial::modern-cpp-kafka::modern-cpp-kafka)

add_executable(ModernCppKafkaProducer ModernCppKafkaProducer.cpp)
target_link_libraries(ModernCppKafkaProducer PRIVATE unofficial::modern-cpp-kafka::modern-cpp-kafka)