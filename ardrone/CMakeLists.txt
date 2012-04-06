SET (
	FLY_SRC
	fly/controlthread.c	
	fly/controlthread.h
	fly/pid.c			
	fly/pid.h
)

SET (
	MOTORBOARD_SRC
	motorboard/motorboard.c	
	motorboard/motorboard.h
	motorboard/mot.c			
	motorboard/mot.h
)

SET (
	NAVBOARD_SRC
	navboard/navboard.c
	navboard/navboard.h
)

SET (
	UDP_SRC
	udp/udp.c
	udp/udp.h
)

SET (
	UTIL_SRC
	util/type.h
	util/util.c
	util/util.h
)

SET (
	VBAT_SRC
	vbat/i2c-dev.h
	vbat/vbat.c
	vbat/vbat.h
)

SET (
	VIDEO_SRC
	video/video.c
	video/video.h
)

SET (
	GPIO_SRC
	gpio/gpio.c
	gpio/gpio.h
)

SET ( 
	ATTITUDE_SRC
	attitude/ars.c		
	attitude/ars.h
	attitude/attitude.c	
	attitude/attitude.h
)

SET( 
	SRC
	${FLY_SRC} ${MOTORBOARD_SRC} ${NAVBOARD_SRC}
	${UDP_SRC} ${UTIL_SRC} ${VBAT_SRC} ${VIDEO_SRC}
	${GPIO_SRC} ${ATTITUDE_SRC}
)

add_library( ardrone ${SRC} )

add_executable( fly fly/main_fly.c )
target_link_libraries(fly ardrone pthread)

add_executable( attitude attitude/main_attitude.c )
target_link_libraries( attitude ardrone pthread)

add_executable( gpio gpio/main_gpio.c )
target_link_libraries( gpio ardrone pthread)

add_executable( motorboard motorboard/main_motorboard.c )
target_link_libraries( motorboard ardrone pthread)

add_executable( navboard navboard/main_navboard.c )
target_link_libraries( navboard ardrone pthread)

add_executable( udpclient udp/main_udpclient.c )
target_link_libraries( udpclient ardrone pthread)

add_executable( udpserver udp/main_udpserver.c )
target_link_libraries( udpserver ardrone pthread)

add_executable( vbat vbat/main_vbat.c )
target_link_libraries( vbat ardrone pthread)

add_executable( video video/main_video.c )
target_link_libraries( video ardrone pthread)























