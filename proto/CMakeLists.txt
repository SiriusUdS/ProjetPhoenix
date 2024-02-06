set(NANOPB_SRC_ROOT_FOLDER "${CMAKE_CURRENT_SOURCE_DIR}/nanopb")
# Define the command to be executed
set(COMMAND_TO_RUN python3 ${NANOPB_SRC_ROOT_FOLDER}/generator/nanopb_generator.py  simple.proto)

# Run the command using execute_process
execute_process(
        COMMAND ${COMMAND_TO_RUN}
        WORKING_DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR}
        RESULT_VARIABLE COMMAND_RESULT
        OUTPUT_VARIABLE COMMAND_OUTPUT
        ERROR_VARIABLE COMMAND_ERROR
)

# Check the result of the command
if(COMMAND_RESULT EQUAL 0)
    message(STATUS "Code generated successfully")
else()
    message(FATAL_ERROR "Failed to generate code")
endif()

set( SOURCES
        "${NANOPB_SRC_ROOT_FOLDER}/pb_common.c"
        "${NANOPB_SRC_ROOT_FOLDER}/pb_decode.c"
        "${NANOPB_SRC_ROOT_FOLDER}/pb_encode.c"
        "${CMAKE_CURRENT_SOURCE_DIR}/simple.pb.c"

)

add_library(proto STATIC ${SOURCES})

target_include_directories(proto PUBLIC
        "${NANOPB_SRC_ROOT_FOLDER}"
        "${CMAKE_CURRENT_SOURCE_DIR}"
)


add_library(proto::proto ALIAS proto)