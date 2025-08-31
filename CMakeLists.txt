cmake_minimum_required(VERSION 3.16)
project(VulkanTutorial)

add_executable(VulkanTutorial src/main.cpp)

set(CMAKE_CXX_STANDRD 17)
set(CMAKE_CXX_STANDARD_REQUIRED TRUE)

include(cmake/CPM.cmake)

set(Vulkan_DIR "C:/VulkanSDK/1.4.321.1/Lib/cmake")
find_package(Vulkan REQUIRED) # CONFIG HINTS "C:/VulkanSDK/1.4.321.1/Lib/cmake"

set(glfw3_DIR "C:/Program Files (x86)/GLFW/lib/cmake/glfw3")
find_package(glfw3 REQUIRED)

include_directories(C:/VulkanSDK/1.4.321.1/Include/glm)

target_link_directories(${PROJECT_NAME} PUBLIC ${Vulkan_INCLUDE_DIRECTORIES} ${GLM_INCLUDE_DIRECTORIES})
target_link_libraries(${PROJECT_NAME} PUBLIC ${Vulkan_LIBRARIES} glfw glm)

