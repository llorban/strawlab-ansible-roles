# strawlab-ansible-roles - recipes to install strawlab software

Tested on Ubuntu xenial (16.04) amd64.

# Installation

To install prerequisites:

    sudo apt-get install ansible

Clone this repository to your desired location

    mkdir whatever
    cd whatever
    git clone https://github.com/strawlab/strawlab-ansible-roles.git

To run the playbook (installs flydra and freemoovr):

    sudo ansible-playbook -i "localhost," -c local playbook.yml

# Now, to create a ROS workspace for FreemooVR

    # Do this as a normal user
    /opt/ros/workspace-installers/kinetic/make-freemoovr-workspace.sh

    # Now you should have new directories in `~/ros` with everything installed.
    # The top-level workspace is at `~/ros/freemoovr-kinetic`.
    # You can initiate your ROS environment with
    source ~/ros/freemoovr-kinetic/devel/setup.bash

    # After this, you can run commands such as
    roslaunch freemoovr_engine demo_display_server.launch
