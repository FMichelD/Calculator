#file CMakeLists.txt

# esta primeira linha não é obrigatória. Mas o CMake às vezes reclama da
#ausência dela
cmake_minimum_required(VERSION 2.6)

# definição do nome do project. Não precisa ser obrigatoriamente o nome
#do diretório
PROJECT(Calculator)

FIND_PACKAGE(Qt4 REQUIRED)

SET(Calculator_SOURCES
    src/main.cpp
    src/calculator.cpp
    src/button.cpp
)

SET(Calculator_HEADERS
    src/include/calculator.h
    src/include/button.h
)

QT4_WRAP_CPP(Calculator_HEADERS_MOC ${Calculator_HEADERS})

INCLUDE(${QT_USE_FILE})

ADD_DEFINITIONS(${QT_DEFINITIONS})

ADD_EXECUTABLE(Calculator ${Calculator_SOURCES} ${Calculator_HEADERS_MOC})

TARGET_LINK_LIBRARIES(Calculator ${QT_LIBRARIES})
