

<pre>
sudo apt-get install python3-rosdep python3-rosinstall-generator python3-vcstool build-essential

sudo pip3 install -U rosdep rosinstall_generator vcstool

sudo pip3 install --upgrade setuptools

mkdir -p ~/ros_noetic/src

cd  ~/ros_noetic

rosinstall_generator desktop --rosdistro noetic --deps --tar > noetic-desktop.rosinstall

vcs import --input noetic-desktop.rosinstall ./src

rosdep install --from-paths ./src --ignore-packages-from-source --rosdistro noetic -y

./src/catkin/bin/catkin_make_isolated --install -DCMAKE_BUILD_TYPE=Release

</pre>