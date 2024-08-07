cmake_minimum_required(VERSION 3.30.1)

set(PROJECT_NAME BattleCity)

project(${PROJECT_NAME} CXX)
set(CMAKE_CXX_STANDARD 17)

# Добавление исходных файлов вашего проекта
add_executable(${PROJECT_NAME} src/main.cpp)

# Установка путей к заголовочным файлам GLFW
include_directories(${CMAKE_SOURCE_DIR}/external/glfw/include)

# Добавление библиотеки GLFW
add_subdirectory(external/glfw)

# Линковка с библиотекой GLFW
target_link_libraries(${PROJECT_NAME} glfw)

# Добавление библиотеки glad
add_subdirectory(external/glad)

# Линковка с библиотекой glad
target_link_libraries(${PROJECT_NAME} glad)