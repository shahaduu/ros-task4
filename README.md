# Turtlesim Square Motion - ROS 2

## Overview

This project implements a simple **ROS 2 Python node** that controls the `turtlesim` simulation. The turtle moves forward and turns 90 degrees four times to draw a square path.

The node publishes linear and angular velocity commands to the `/turtle1/cmd_vel` topic.

---

## Prerequisites

* **Operating System:** Ubuntu 24.04 LTS or WSL2 with GUI support
* **ROS 2:** Jazzy
* **Python 3**
* **Package:** `turtlesim`

---

## Installation

First, update the package list and install `turtlesim`:

```bash
sudo apt update
sudo apt install -y ros-jazzy-turtlesim
```

Then, source the ROS 2 environment:

```bash
source /opt/ros/jazzy/setup.bash
```

---

## How to Run

### Step 1: Start Turtlesim

Open a terminal and run:

```bash
ros2 run turtlesim turtlesim_node
```

This starts the Turtlesim simulation and displays the turtle.

> **WSL2 Note:** If the Turtlesim window does not appear, configure the display before running the simulator:
>
> ```bash
> export DISPLAY=:0
> export LIBGL_ALWAYS_INDIRECT=1
> ```

---

### Step 2: Run the Square Movement Script

Open a second terminal and run:

```bash
python3 turtle_square.py
```

The turtle will move forward and turn 90 degrees. This sequence is repeated four times to create a square path.

---

## Code Logic

The program uses the following steps:

1. Creates a ROS 2 publisher for the `/turtle1/cmd_vel` topic.
2. Publishes a linear velocity to move the turtle forward.
3. Stops the turtle briefly.
4. Publishes an angular velocity to rotate the turtle by 90 degrees.
5. Stops the turtle briefly.
6. Repeats the movement and rotation four times.

### Main Parameters

* **Linear velocity:** `2.0 m/s`
* **Forward movement time:** `2.0 seconds`
* **Angular velocity:** `1.5708 rad/s`
* **Rotation time:** `1.0 second`
* **Number of sides:** `4`

---

## Expected Output

After completing the movement, the terminal displays:

```text
[INFO] [turtle_square]: Finished drawing the square!
```

The Turtlesim window should show the turtle following a square-shaped path.

---

## Conclusion

The project demonstrates basic ROS 2 communication using a Python node and the `geometry_msgs/Twist` message. It shows how velocity commands can be published to control a simulated robot and create a predefined movement pattern.


