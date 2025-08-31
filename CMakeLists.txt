cmake_minimum_required(VERSION 3.16)
project(VulkanTutorial)

add_executable(Main main.cpp)

set(CMAKE_CXX_STANDRD 17)
set(CMAKE_CXX_STANDARD_REQUIRED TRUE)

find_package(Vulkan REQUIRED) # CONFIG HINTS "C:/VulkanSDK/1.4.321.1/Lib/cmake"
find_package(glfw3 REQUIRED)

target_link_directories(${PROJECT_NAME} PRIVATE ${Vulkan_INCLUDE_DIRECTORIES} ${GLM_INCLUDE_DIRECTORIES})
target_link_libaries(${PROJECT_NAME} PRIVATE ${Vulkan_LIBRARIES} glfw glm::glm)

