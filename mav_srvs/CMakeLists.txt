cmake_minimum_required(VERSION 2.4.6)

set(PROJECT_NAME mav_srvs)
project(${PROJECT_NAME})

# Set the build type.  Options are:
#  Coverage       : w/ debug symbols, w/o optimization, w/ code-coverage
#  Debug          : w/ debug symbols, w/o optimization
#  Release        : w/o debug symbols, w/ optimization
#  RelWithDebInfo : w/ debug symbols, w/ optimization
#  MinSizeRel     : w/o debug symbols, w/ optimization, stripped binaries
#set(ROS_BUILD_TYPE RelWithDebInfo)

#rosbuild_init()

#set the default path for built executables to the "bin" directory
#set(EXECUTABLE_OUTPUT_PATH ${PROJECT_SOURCE_DIR}/bin)
#set the default path for built libraries to the "lib" directory
#set(LIBRARY_OUTPUT_PATH ${PROJECT_SOURCE_DIR}/lib)

#uncomment if you have defined messages
#rosbuild_genmsg()
#uncomment if you have defined services
#rosbuild_gensrv()




find_package(catkin REQUIRED
                COMPONENTS message_generation std_srvs)



add_service_files(FILES
	AdvanceState.srv
	ChangeDesPose.srv
	ESTOP.srv
	GetFlightState.srv
	GetMotorsOnOff.srv
	Land.srv
	PositionHold.srv
	RetreatState.srv
	SetCtrlType.srv
	SetMotorsOnOff.srv
	Takeoff.srv
	ToggleEngage.srv
	VelocityHold.srv


)





generate_messages(DEPENDENCIES std_srvs)




catkin_package(
        CATKIN_DEPENDS message_runtime std_srvs
	)





