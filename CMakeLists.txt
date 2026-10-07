cmake_minimum_required(VERSION 3.14)
project(TeletextUI VERSION 1.0.0 LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED True)
set(CMAKE_EXPORT_COMPILE_COMMANDS ON)

find_package(CURL REQUIRED)
find_package(SQLite3 REQUIRED)
find_package(pugixml REQUIRED)

include(FetchContent)
FetchContent_Declare(
  ftxui
  GIT_REPOSITORY https://github.com/ArthurSonzogni/FTXUI
  GIT_TAG main # Můžeš nahradit konkrétní verzí, např. v5.0.0
)
FetchContent_MakeAvailable(ftxui)

file(GLOB_RECURSE SOURCES "src/*.cpp")

add_executable(teletextui ${SOURCES})

target_include_directories(teletextui PRIVATE src)

target_link_libraries(teletextui
  PRIVATE
  ftxui::screen
  ftxui::dom
  ftxui::component
  CURL::libcurl
  SQLite::SQLite3
  pugixml
)
