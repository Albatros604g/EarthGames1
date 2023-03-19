cmake_minimum_required(VERSION 3.24)
project(EarthGames)

set(CMAKE_CXX_STANDARD 23)

add_executable(EarthGames main.cpp)

find_package(OpenGL REQUIRED)
target_link_libraries(EarthGames ${OPENGL_LIBRARIES})

set(GLFW_DIR D:/Prog/Games/EarthGames/Library/glfw-3.3.8)

set(GLM_INCLUDE_DIR D:/Prog/Games/EarthGames/Library/glm)

set(GLEW_DIR D:/Prog/Games/EarthGames/Library/glew-2.1.0)

include_directories(${GLFW_DIR}/include)

include_directories(${GLM_INCLUDE_DIR})
include_directories(${GLEW_DIR}/include)

link_directories(${GLFW_DIR}/lib-mingw-w64)
link_directories(${GLEW_DIR}/lib/Release/x64)

target_link_libraries(EarthGames -L"${GLFW_DIR}/lib-mingw-w64" glfw3)

target_link_libraries(EarthGames -L"${GLEW_DIR}/lib/Release/x64" glew32)