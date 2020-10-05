cmake_minimum_required(VERSION 3.10.2 FATAL_ERROR)

#============================================================================
# Initialize the project
#============================================================================
project(ignition-edifice VERSION 1.0.0)

#============================================================================
# Find ignition-cmake
#============================================================================
# If you get an error at this line, you need to install ignition-cmake
find_package(ignition-cmake2 2.0.0 REQUIRED)

#============================================================================
# Configure the project
#============================================================================
ign_configure_project(VERSION_SUFFIX pre1)

# all list of edifice packages

ign_find_package(ignition-common3 REQUIRED)
ign_find_package(ignition-fuel_tools5 REQUIRED)
ign_find_package(ignition-gazebo4 REQUIRED)
ign_find_package(ignition-gui4 REQUIRED)
ign_find_package(ignition-launch3 REQUIRED)
ign_find_package(ignition-math6 REQUIRED)
ign_find_package(ignition-msgs6 REQUIRED)
ign_find_package(ignition-physics3 REQUIRED)
ign_find_package(ignition-plugin1 REQUIRED)
ign_find_package(ignition-rendering4 REQUIRED)
ign_find_package(ignition-sensors4 REQUIRED)
ign_find_package(ignition-tools REQUIRED)
ign_find_package(ignition-transport9 REQUIRED)
ign_find_package(sdformat10 REQUIRED)

install(DIRECTORY gazebodistro DESTINATION ${IGN_DATA_INSTALL_DIR})
