project(meshup-ogl CXX)

add_library(${PROJECT_NAME}
        include/meshup/ogl/Camera.h
        include/meshup/ogl/Model.h
        include/meshup/ogl/Shader.h
        src/meshup/ogl/Camera.cpp
        src/meshup/ogl/Model.cpp
        src/meshup/ogl/Shader.cpp
)

target_compile_features(${PROJECT_NAME}
        PUBLIC
            cxx_std_17
)

target_include_directories(${PROJECT_NAME}
        PUBLIC
            include
        PRIVATE
            src
)

target_link_libraries(${PROJECT_NAME}
        glad
        glm
        spdlog
        meshup-geom
)

add_subdirectory(test)