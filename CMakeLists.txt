cmake_minimum_required(VERSION 3.10.2 FATAL_ERROR)

#============================================================================
# Initialize the project
#============================================================================
project(ignition-edifice VERSION 1.0.3)

#============================================================================
# Find ignition-cmake
#============================================================================
# If you get an error at this line, you need to install ignition-cmake
find_package(ignition-cmake2 2.11.0 REQUIRED)

#============================================================================
# Configure the project
#============================================================================
ign_configure_project(VERSION_SUFFIX)

# all list of edifice packages

ign_find_package(ignition-common4 REQUIRED VERSION 4.5)
ign_find_package(ignition-fuel_tools6 REQUIRED VERSION 6.2)
ign_find_package(ignition-gazebo5 REQUIRED VERSION 5.4)
ign_find_package(ignition-gui5 REQUIRED VERSION 5.5)
ign_find_package(ignition-launch4 REQUIRED VERSION 4.1)
ign_find_package(ignition-math6 REQUIRED COMPONENTS eigen3 VERSION 6.10)
ign_find_package(ignition-msgs7 REQUIRED VERSION 7.3)
ign_find_package(ignition-physics4 REQUIRED VERSION 4.3)
ign_find_package(ignition-plugin1 REQUIRED VERSION 1.2.1)
ign_find_package(ignition-rendering5 REQUIRED VERSION 5.2.1)
ign_find_package(ignition-sensors5 REQUIRED VERSION 5.1.1)
ign_find_package(ignition-transport10 REQUIRED VERSION 10.2)
ign_find_package(ignition-utils1 REQUIRED VERSION 1.3)
ign_find_package(sdformat11 REQUIRED VERSION 11.4.1)

if(build_warnings)
  set(all_warnings " CONFIGURATION WARNINGS:")
  foreach (msg ${build_warnings})
    ign_string_append(all_warnings " -- ${msg}" DELIM "\n")
  endforeach ()
  message(WARNING "${all_warnings}")
endif (build_warnings)

if(build_errors)
  message(SEND_ERROR "-- BUILD ERRORS: These must be resolved before compiling.")
  foreach(msg ${build_errors})
    message(SEND_ERROR "-- ${msg}")
  endforeach()
  message(SEND_ERROR "-- END BUILD ERRORS\n")

  set(error_str "Errors encountered in build. Please see BUILD ERRORS above.")

  message(FATAL_ERROR "${error_str}")

endif()

install(DIRECTORY gazebodistro DESTINATION ${IGN_DATA_INSTALL_DIR})
