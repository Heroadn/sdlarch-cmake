# CMakeList.txt: projeto de CMake para Database_hello, incluir origem e definir
# lógica específica a um projeto aqui.
#
cmake_minimum_required (VERSION 3.8)
project (
	"sdlarch"
	LANGUAGES CXX C
    VERSION 0.0.0.0)

#
set(CMAKE_CXX_STANDARD 20)
add_definitions("-std=c++11 -Wall -g")

#parkages
find_package(SDL2 CONFIG REQUIRED)

# Adicione a origem ao executável deste projeto.
add_executable (sdlarch
	"glad.c"
	"sdlarch.c")


target_link_libraries(sdlarch PRIVATE
	PRIVATE
        $<TARGET_NAME_IF_EXISTS:SDL2::SDL2main>
        $<IF:$<TARGET_EXISTS:SDL2::SDL2>,SDL2::SDL2,SDL2::SDL2-static>
)

# TODO: Adicione testes e instale destinos, se necessário.
