# Start with a minimal Ubuntu base image
FROM ubuntu:22.04

# Upgrade and update the terminal
RUN apt update -y
RUN apt upgrade -y

# Install Gedit which is a useful text editor 
RUN apt-get install gedit -y

# Make sure Colcon in installed (this is the build package for ROS2 humble)
#       Use 'source /usr/share/colcon_argcomplete/hook/colcon-argcomplete.bash' to enable colcon autocomplete
RUN apt update -y
RUN apt-get -y install python3-colcon-common-extensions

# Install Gazebo-Harmonic (The most recent version of Gazebo)
RUN apt-get update -y
RUN apt-get install lsb-release wget gnupg -y

RUN apt-get update -y
RUN wget https://packages.osrfoundation.org/gazebo.gpg -O /usr/share/keyrings/pkgs-osrf-archive-keyring.gpg
RUN echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/pkgs-osrf-archive-keyring.gpg] http://packages.osrfoundation.org/gazebo/ubuntu-stable $(lsb_release -cs) main" | sudo tee /etc/apt/sources.list.d/gazebo-stable.list > /dev/null
RUN apt-get update -y
RUN apt-get upgrade -y
RUN apt-get update -y -qq && apt-get install -y -qq gz-harmonic