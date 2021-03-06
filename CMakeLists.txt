cmake_minimum_required(VERSION 3.10)

project(LearnOpenGL)

set(CMAKE_CXX_STANDARD 17)

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -v -stdlib=libc++ -framework AppKit -framework CoreVideo -framework IOKit -framework CoreGraphics -framework CoreFoundation")

include_directories(/usr/include)

include_directories(extern/glad/include)

include_directories("${PROJECT_SOURCE_DIR}/include/")

LINK_DIRECTORIES( /usr/local/lib ${PROJECT_SOURCE_DIR}/lib/)

# Tutorial 1[入门-第一个窗口]
add_executable(tutorial01_first_window
        glad.c getting_started/first_window/tutorial01_first_window.cpp)
target_link_libraries(tutorial01_first_window libglfw3.a)

# Tutorial 2[入门-三角形]
set(SOURCE_FILES_RED_TRIANGLE
        glad.c getting_started/shader/getting_started_shader.cpp std_image.cpp)
add_executable(tutorial02_red_triangle ${SOURCE_FILES_RED_TRIANGLE})
target_link_libraries(tutorial02_red_triangle libglfw3.a)

# getting_started_shader[入门-着色器]
set(SOURCE_FILES_GETTING_STARTED_SHADER
        glad.c getting_started/shader/getting_started_shader.cpp std_image.cpp)
add_executable(getting_started_shader ${SOURCE_FILES_GETTING_STARTED_SHADER})
target_link_libraries(getting_started_shader libglfw3.a)


# getting_started_textures_combined[入门-纹理]
set(SOURCE_FILES_GETTING_STARTED_TEXTURES_COMBINED
        glad.c getting_started/textures_combined/getting_started_textures_combined.cpp std_image.cpp)
add_executable(getting_started_textures_combined ${SOURCE_FILES_GETTING_STARTED_TEXTURES_COMBINED})
target_link_libraries(getting_started_textures_combined libglfw3.a)

# getting_started_transformation[入门-变换]
set(SOURCE_FILES_GETTING_STARTED_TRANSFORMATION
        glad.c getting_started/transformation/getting_started_transformation.cpp std_image.cpp)
add_executable(getting_started_transformation ${SOURCE_FILES_GETTING_STARTED_TRANSFORMATION})
target_link_libraries(getting_started_transformation libglfw3.a)

# getting_started_coordinate_systems[入门-坐标系]
set(SOURCE_FILES_GETTING_STARTED_COORDINATE_SYSTEMS
        glad.c getting_started/coordinate_systems/getting_started_coordinate_systems.cpp std_image.cpp)
add_executable(getting_started_coordinate_systems ${SOURCE_FILES_GETTING_STARTED_COORDINATE_SYSTEMS})
target_link_libraries(getting_started_coordinate_systems libglfw3.a)

# getting_started_camera_class[入门-摄像机]
set(SOURCE_FILES_GETTING_STARTED_CAMERA_CLASS
        glad.c getting_started/camera_class/getting_started_camera_class.cpp std_image.cpp)
add_executable(getting_started_camera_class ${SOURCE_FILES_GETTING_STARTED_CAMERA_CLASS})
target_link_libraries(getting_started_camera_class libglfw3.a)



# lighting_colors[光照-颜色]
set(SOURCE_FILES_LIGHTING_COLORS
        glad.c lighting/colors/lighting_colors.cpp std_image.cpp)
add_executable(lighting_colors ${SOURCE_FILES_LIGHTING_COLORS})
target_link_libraries(lighting_colors libglfw3.a)

# lighting_colors[光照-基础光照]
set(SOURCE_FILES_BASIC_LIGHTING_SPECULAR
        glad.c lighting/basic_lighting_specular/lighting_basic_lighting_specular.cpp std_image.cpp)
add_executable(lighting_basic_lighting_specular ${SOURCE_FILES_BASIC_LIGHTING_SPECULAR})
target_link_libraries(lighting_basic_lighting_specular libglfw3.a)

# lighting_colors[光照-材质]
set(SOURCE_FILES_MATERIALS
        glad.c lighting/materials/lighting_materials.cpp std_image.cpp)
add_executable(lighting_materials ${SOURCE_FILES_MATERIALS})
target_link_libraries(lighting_materials libglfw3.a)

# lighting_colors[光照-光照贴图]
set(SOURCE_FILES_LIGHTING_MAPS_SPECULAR_MAP
        glad.c lighting/lighting_maps_specular_map/lighting_lighting_maps_specular_map.cpp std_image.cpp)
add_executable(lighting_lighting_maps_specular_map ${SOURCE_FILES_LIGHTING_MAPS_SPECULAR_MAP})
target_link_libraries(lighting_lighting_maps_specular_map libglfw3.a libboost_filesystem.a libboost_system.a)

# lighting_colors[光照-透光物]
set(SOURCE_FILES_CASTERS_SPOT_SOFT
        glad.c lighting/casters_spot_soft/lighting_casters_spot_soft.cpp std_image.cpp)
add_executable(lighting_casters_spot_soft ${SOURCE_FILES_CASTERS_SPOT_SOFT})
target_link_libraries(lighting_casters_spot_soft libglfw3.a libboost_filesystem.a libboost_system.a)

# lighting_colors[光照-多光源]
set(SOURCE_FILES_MULTIPLE_LIGHTS
        glad.c lighting/multiple_lights/lighting_multiple_lights.cpp std_image.cpp)
add_executable(lighting_multiple_lights ${SOURCE_FILES_MULTIPLE_LIGHTS})
target_link_libraries(lighting_multiple_lights libglfw3.a libboost_filesystem.a libboost_system.a)

# demo_tesselation_shader[Demo-细分着色器]
set(SOURCE_FILES_TESSELATION_SHADER
        glad.c tesselation_shader/demo_tesselation_shader.cpp)
add_executable(demo_tesselation_shader ${SOURCE_FILES_TESSELATION_SHADER})
target_link_libraries(demo_tesselation_shader libglfw3.a)

# model_loading[模型加载-模型]
set(SOURCE_FILES_MODEL_LOADING
        glad.c model_loading/model_loading.cpp std_image.cpp)
add_executable(model_loading ${SOURCE_FILES_MODEL_LOADING})
target_link_libraries(model_loading libglfw3.a libboost_filesystem.a libboost_system.a libassimp.a)


# stencil_testing[高级OpenGL-模板测试]
set(SOURCE_FILES_STENCIL_TESTING
        glad.c advanced_opengl/stencil_testing/stencil_testing.cpp std_image.cpp)
add_executable(stencil_testing ${SOURCE_FILES_STENCIL_TESTING})
target_link_libraries(stencil_testing libglfw3.a libboost_filesystem.a libboost_system.a)
