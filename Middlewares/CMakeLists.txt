

file(GLOB_RECURSE SOURCES "${CMAKE_CURRENT_SOURCE_DIR}/*.c" "${CMAKE_SOURCE_DIR}/USB_HOST/*.c")

add_library(middleware STATIC ${SOURCES})
target_include_directories( middleware PUBLIC
        "${CMAKE_CURRENT_SOURCE_DIR}/Third_Party/FreeRTOS/Source/CMSIS_RTOS_V2"
        "${CMAKE_CURRENT_SOURCE_DIR}/Third_Party/FreeRTOS/Source/include"
        "${CMAKE_CURRENT_SOURCE_DIR}/Third_Party/FreeRTOS/Source/portable/GCC/ARM_CM4F"
        "${CMAKE_SOURCE_DIR}/Core/Inc"
        "${CMAKE_SOURCE_DIR}/Drivers/CMSIS/Include"
        "${CMAKE_SOURCE_DIR}/Drivers/CMSIS/Device/ST/STM32F4xx/Include/"
        "${CMAKE_SOURCE_DIR}/Drivers/STM32F4xx_HAL_Driver/Inc/"
        "${CMAKE_SOURCE_DIR}/USB_HOST/App"
        "${CMAKE_SOURCE_DIR}/USB_HOST/Target"
        "${CMAKE_SOURCE_DIR}/Drivers/CMSIS/Device/ST/STM32F4xx/Include/"
        "${CMAKE_CURRENT_SOURCE_DIR}/ST/STM32_USB_Host_Library/Class/CDC/Inc"
        "${CMAKE_CURRENT_SOURCE_DIR}/ST/STM32_USB_Host_Library/Core/Inc"



)
add_library(middleware::middleware ALIAS middleware)
