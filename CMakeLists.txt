cmake_minimum_required(VERSION 3.10.2 FATAL_ERROR)

#============================================================================
# Initialize the project
#============================================================================
project(ignition-edifice VERSION 1.0.1)

#============================================================================
# Find ignition-cmake
#============================================================================
# If you get an error at this line, you need to install ignition-cmake
find_package(ignition-cmake2 2.9.0 REQUIRED)

#============================================================================
# Configure the project
#============================================================================
ign_configure_project(VERSION_SUFFIX)

# all list of edifice packages

ign_find_package(ignition-common4 REQUIRED VERSION 4.4)
ign_find_package(ignition-fuel_tools6 REQUIRED VERSION 6.1)
ign_find_package(ignition-gazebo5 REQUIRED VERSION 5.2)
ign_find_package(ignition-gui5 REQUIRED VERSION 5.3)
ign_find_package(ignition-launch4 REQUIRED VERSION 4.1)
ign_find_package(ignition-math6 REQUIRED COMPONENTS eigen3 VERSION 6.9.2)
ign_find_package(ignition-msgs7 REQUIRED VERSION 7.2)
ign_find_package(ignition-physics4 REQUIRED VERSION 4.2)
ign_find_package(ignition-plugin1 REQUIRED VERSION 1.2.1)
ign_find_package(ignition-rendering5 REQUIRED VERSION 5.1)
ign_find_package(ignition-sensors5 REQUIRED VERSION 5.1)
ign_find_package(ignition-tools REQUIRED VERSION 1.4)
ign_find_package(ignition-transport10 REQUIRED VERSION 10.1)
ign_find_package(ignition-utils1 REQUIRED VERSION 1.1)
ign_find_package(sdformat11 REQUIRED VERSION 11.3)

install(DIRECTORY gazebodistro DESTINATION ${IGN_DATA_INSTALL_DIR})
