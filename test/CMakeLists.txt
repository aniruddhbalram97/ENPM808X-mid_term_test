set(GTEST_SHUFFLE 1)
FIND_PACKAGE( OpenCV REQUIRED )   
add_executable(
    cpp-test
    main.cpp
    test.cpp
    ./../app/human_object_detector.cpp
)

INCLUDE_DIRECTORIES( ${OpenCV_INCLUDE_DIRS} )
target_include_directories(cpp-test PUBLIC ../vendor/googletest/googletest/include 
                                           ${CMAKE_SOURCE_DIR}/include )

target_link_libraries(cpp-test PUBLIC gtest ${OpenCV_LIBS})
