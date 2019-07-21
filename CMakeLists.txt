cmake_minimum_required(VERSION 3.14)
project(SAPI_Wrapper)

set(CMAKE_CXX_STANDARD 14)

add_library(SAPI_Wrapper STATIC
        src/SpeechEngine.cpp
        src/SpeechEngine.h
        src/Voice.cpp
        src/Voice.h
        )
