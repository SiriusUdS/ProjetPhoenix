file(GLOB_RECURSE SOURCES
        "${CMAKE_CURRENT_SOURCE_DIR}/*.c"
)

add_library(drivers STATIC ${SOURCES})

target_include_directories(drivers PUBLIC
        "${CMAKE_CURRENT_SOURCE_DIR}/STM32F4xx_HAL_Driver/Inc"
        "${CMAKE_CURRENT_SOURCE_DIR}/STM32F4xx_HAL_Driver/Inc/Legacy"
        "${CMAKE_CURRENT_SOURCE_DIR}/CMSIS/Device/ST/STM32F4xx/Include"
        "${CMAKE_CURRENT_SOURCE_DIR}/CMSIS/Include"
        "${CMAKE_SOURCE_DIR}/Core/Inc"
)

add_library(drivers::drivers ALIAS drivers)
