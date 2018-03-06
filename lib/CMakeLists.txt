set(PRINT_HELLO_SRC print_hello.cpp)
add_library(print_hello SHARED ${PRINT_HELLO_SRC})
set_target_properties(print_hello PROPERTIES VERSION 1.1 SOVERSION 1)
add_library(print_hello_static STATIC ${PRINT_HELLO_SRC})
set_target_properties(print_hello_static PROPERTIES OUTPUT_NAME "print_hello")
install(TARGETS print_hello print_hello_static 
    LIBRARY DESTINATION lib
    ARCHIVE DESTINATION lib
)
install(FILES print_hello.h DESTINATION include/print_hello)
