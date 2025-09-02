cmake_minimum_required(VERSION 3.16)
project(VulkanTutorial)

include(cmake/CPM.cmake)

find_package(Vulkan REQUIRED)

set(glfw3_DIR "C:/Program Files (x86)/GLFW/lib/cmake/glfw3")
find_package(glfw3 REQUIRED)

#this includes glm headers im p sure
include_directories("C:/VulkanSDK/1.4.321.1/Include/glm")


add_executable(VulkanTutorial src/main.cpp)



target_include_directories(${PROJECT_NAME} PUBLIC ${Vulkan_INCLUDE_DIRS} ${GLM_INCLUDE_DIRS})
target_link_libraries(${PROJECT_NAME} PUBLIC ${Vulkan_LIBRARIES} glfw legacy_stdio_definitions.lib)

