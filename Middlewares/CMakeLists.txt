

file(GLOB_RECURSE SOURCES "${CMAKE_CURRENT_SOURCE_DIR}/*.c")

add_library(middleware STATIC ${SOURCES})
target_include_directories( middleware PUBLIC
        "${CMAKE_CURRENT_SOURCE_DIR}/Third_Party/FreeRTOS/Source/CMSIS_RTOS_V2"
        "${CMAKE_CURRENT_SOURCE_DIR}/Third_Party/FreeRTOS/Source/include"
        "${CMAKE_CURRENT_SOURCE_DIR}/Third_Party/FreeRTOS/Source/portable/GCC/ARM_CM4F"
        "${CMAKE_SOURCE_DIR}/Core/Inc"
        "${CMAKE_SOURCE_DIR}/Drivers/CMSIS/Include"
        "${CMAKE_SOURCE_DIR}/Drivers/CMSIS/Device/ST/STM32F4xx/Include/"
        "${CMAKE_SOURCE_DIR}/Drivers/STM32F4xx_HAL_Driver/Inc/"

)
add_library(middleware::middleware ALIAS middleware)
