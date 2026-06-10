
# multirobot_competitive_simulation

 Simulating Competitive Setpoints Navigation for Twin TurtleBots in Environment with obstacles

## Project Structure

```
.
├── docker_ws/             # Docker workspace for building the container
├── ros_ws/                # Main ROS 2 workspace containing all packages
├── chown_me.sh            # Script to change ownership of files created as root user
├── run.sh                 # Script to run the Docker container 
├── exec.sh                # Script to open a running container
```

## How to Run the Simulation

### 1. **Build the Docker Image**

```bash
cd docker_ws
chmod +x build.sh
./build.sh
```

Ensure scripts are executable:
```bash
cd ..
chmod +x run.sh exec.sh chown_me.sh
```

### 2. **Run the Docker Container**

```bash
./run.sh
```

### 3. **Inside the Container**

Run the following commands:

```bash
source /opt/ros/jazzy/setup.bash
export TURTLEBOT3_MODEL=burger
cd /root/ros_workspace
colcon build
source install/setup.bash
ros2 launch turtlebot3_gazebo custom_world.launch.py
```
