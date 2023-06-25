

project(openGJKdemo)

message( "[${CMAKE_PROJECT_NAME}] Compiling the executable ..")

# Set source file
set(SOURCE_FILES main.c )

# Create the executable
add_executable(${PROJECT_NAME} ${SOURCE_FILES})

# Link to openGJK
target_link_libraries(${PROJECT_NAME} openGJKlib )

set (EXECUTABLE_OUTPUT_PATH ${CMAKE_SOURCE_DIR}/bin)

# Copy input files for this example after build
add_custom_command(
    TARGET ${PROJECT_NAME} POST_BUILD
#     COMMAND ${CMAKE_COMMAND} -E copy
#             ${CMAKE_CURRENT_SOURCE_DIR}/userP.dat
#             ${CMAKE_CURRENT_BINARY_DIR}/userP.dat 
    COMMAND ${CMAKE_COMMAND} -E copy
            ${CMAKE_CURRENT_SOURCE_DIR}/userP.dat
            ${CMAKE_SOURCE_DIR}/bin/userP.dat        
#     COMMAND ${CMAKE_COMMAND} -E copy
#             ${CMAKE_CURRENT_SOURCE_DIR}/userQ.dat
#             ${CMAKE_CURRENT_BINARY_DIR}/userQ.dat 
    COMMAND ${CMAKE_COMMAND} -E copy
            ${CMAKE_CURRENT_SOURCE_DIR}/userQ.dat
            ${CMAKE_SOURCE_DIR}/bin/userQ.dat
)



# Report
message( ".. executable DONE!")
