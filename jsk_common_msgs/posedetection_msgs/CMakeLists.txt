# http://ros.org/doc/groovy/api/catkin/html/user_guide/supposed.html
cmake_minimum_required(VERSION 3.5)
project(posedetection_msgs)

find_package(rosidl_default_generators REQUIRED)
find_package(std_msgs REQUIRED)
find_package(sensor_msgs REQUIRED)
find_package(geometry_msgs REQUIRED)

rosidl_generate_interfaces(${PROJECT_NAME}
  msg/Curve1D.msg
  msg/Feature0D.msg
  msg/Feature1D.msg
  msg/ImageFeature0D.msg
  msg/ImageFeature1D.msg
  msg/Object6DPose.msg
  msg/ObjectDetection.msg

  srv/Detect.srv
  srv/Feature0DDetect.srv
  srv/Feature1DDetect.srv
  srv/TargetObj.srv

  DEPENDENCIES std_msgs geometry_msgs sensor_msgs)

ament_export_dependencies(rosidl_default_runtime)

if(BUILD_TESTING)
  find_package(ament_lint_auto REQUIRED)
  # the following line skips the linter which checks for copyrights
  # uncomment the line when a copyright and license is not present in all source files
  #set(ament_cmake_copyright_FOUND TRUE)
  # the following line skips cpplint (only works in a git repo)
  # uncomment the line when this package is not in a git repo
  #set(ament_cmake_cpplint_FOUND TRUE)
  ament_lint_auto_find_test_dependencies()
endif()

ament_package()
