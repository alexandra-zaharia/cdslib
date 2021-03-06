cmake_minimum_required(VERSION 3.5)
project(libgcds)

set(CMAKE_C_STANDARD 11)
set(GCC_COVERAGE_COMPILE_FLAGS "-g -Wall -Wextra -Wpedantic -Wconversion")
set(CMAKE_C_FLAGS "${CMAKE_C_FLAGS} ${GCC_COVERAGE_COMPILE_FLAGS}")

include_directories(
        include
        include/CircularLinkedList
        include/LinkedList
        include/Queue
        include/Stack
        include/Vector
)

add_library(gcds STATIC
        src/node.c
        src/CircularLinkedList/circular_linked_list.c
        src/LinkedList/linked_list.c
        src/Queue/queue.c
        src/Stack/stack.c
        src/Vector/vector.c)

install(TARGETS gcds DESTINATION lib)
install(FILES
        include/node.h
        include/CircularLinkedList/circular_linked_list.h
        include/LinkedList/linked_list.h
        include/Queue/queue.h
        include/Stack/stack.h
        include/Vector/vector.h
        DESTINATION include)
