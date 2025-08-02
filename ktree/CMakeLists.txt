cmake_minimum_required(VERSION 3.10)

project(KTree VERSION 1.0)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED True)

find_package(Threads)

if(THREADS_FOUND)
	message(STATUS "Threads found")
	add_definitions(-DMULTITHREADED_ENABLED)
endif()


set(CMAKE_CXX_FLAGS_DEBUG "${CMAKE_CXX_FLAGS_DEBUG} -DENABLE_DEBUG_MACRO")

add_compile_definitions(TOP_DOWN_SEARCH_PRUNING)

add_subdirectory(ktreelib)
add_executable(ktree main.cpp)

target_include_directories(ktree PUBLIC
	"${PROJECT_BINARY_DIR}"
	"${PROJECT_SOURCE_DIR}/ktreelib"
)

target_link_libraries(ktree PUBLIC KTree)

if(THREADS_FOUND)
target_link_libraries(ktree PUBLIC Threads::Threads)
endif()

configure_file(KTreeConfig.h.in KTreeConfig.h)


