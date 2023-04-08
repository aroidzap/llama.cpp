set(TARGET main)

# nlohmann json library
set(JSON_BuildTests OFF CACHE INTERNAL "")
add_subdirectory(../../3rdparty/nlohmann_json 3rdparty/nlohmann_json)

add_executable(${TARGET} main.cpp)
target_link_libraries(${TARGET} PRIVATE 
    common llama ${CMAKE_THREAD_LIBS_INIT}
    nlohmann_json::nlohmann_json)
target_compile_features(${TARGET} PRIVATE cxx_std_11)
