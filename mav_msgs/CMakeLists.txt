cmake_minimum_required(VERSION 2.8.3)

set(PROJECT_NAME mav_msgs)
project(${PROJECT_NAME})

# Set the build type.  Options are:
#  Coverage       : w/ debug symbols, w/o optimization, w/ code-coverage
#  Debug          : w/ debug symbols, w/o optimization
#  Release        : w/o debug symbols, w/ optimization
#  RelWithDebInfo : w/ debug symbols, w/ optimization
#  MinSizeRel     : w/o debug symbols, w/ optimization, stripped binaries
#set(ROS_BUILD_TYPE MinSizeRel)



find_package(catkin REQUIRED
                COMPONENTS message_generation std_msgs)



add_message_files(
    DIRECTORY
        msg
    FILES
	Height.msg
	Pitch.msg
	RC.msg
	Roll.msg
	Status.msg
	Thrust.msg
	YawRate.msg


)





generate_messages(DEPENDENCIES std_msgs)




catkin_package(
        CATKIN_DEPENDS message_runtime std_msgs
	)


include_directories(${catkin_INCLUDE_DIRS})

