CMAKE_MINIMUM_REQUIRED	( VERSION 2.8 )
PROJECT		  	( time-test )

FIND_PACKAGE ( ArtikBase )

SET ( CMAKE_C_FLAGS "${CMAKE_C_FLAGS} -Wno-unused-parameter" )

SET ( EXE_TIME_TEST time-test )

SET ( SRC_TEST_TIME	artik_time_test.c
    )

ADD_EXECUTABLE		( ${EXE_TIME_TEST} ${SRC_TEST_TIME} )

TARGET_INCLUDE_DIRECTORIES ( ${EXE_TIME_TEST}
								PUBLIC ${ARTIK_BASE_INCLUDE_DIR}
)

TARGET_LINK_LIBRARIES	( ${EXE_TIME_TEST}
								${ARTIK_BASE_LIBRARIES}
)

INSTALL ( TARGETS ${EXE_TIME_TEST} RUNTIME DESTINATION "${CMAKE_INSTALL_LIBDIR}/artik-sdk/tests" )
