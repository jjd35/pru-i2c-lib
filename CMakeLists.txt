

project(pru_i2c LANGUAGES C)

add_library(${PROJECT_NAME} STATIC ${CMAKE_CURRENT_SOURCE_DIR}/pru_i2c_driver.c)

target_include_directories(${PROJECT_NAME} PUBLIC 
"$ENV{PRU_SDK_PATH}/include/"
"$ENV{AM335X_INCLUDE_PATH}"
"$ENV{ARM_INCLUDE_PATH}"
"$<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}>/include/"
)


#set_target_properties(${PROJECT_NAME} PROPERTIES IMPORTED_LOCATION ${CMAKE_CURRENT_SOURCE_DIR}/../)
#target_link_libraries(${PROJECT_NAME} $ENV{PRU_LIBRARY_PATH}/libc.a ${CMAKE_CURRENT_SOURCE_DIR}/../librobotcontrol/pru_firmware/src/AM335x_PRU.cmd )
#install(TARGETS ${PROJECT_NAME}
 #    DESTINATION ${CMAKE_LIBRARY_OUTPUT_DIRECTORY})
#install(FILES "include/pru_i2c_driver.h" "include/pru_i2c.h" DESTINATION include/$PROJECT_NAME)