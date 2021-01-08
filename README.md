# Homework 3 - Navigation and FSM

The command

```sh
$ roslaunch robin_arena robin_bringup.launch simulation:=true gripper_enable:=true spawn_marrtino:=true arena_name:=robin_arena_simplified
```

spawns a simulated setup equipped with both a manipulator robot, i.e., the Universal Robot UR5, and a mobile robot, i.e., Marrtino. Moreover, an arena with fixed walls (fixed obstacles) surrounds these robots. Inside it, some orange cylinders (movable obstacles) obstruct the navigation of the mobile robot.

Let *Init* be the initial pose of Marrtino and *Goal* its final location, where *Init* is the robot pose at the simulation bring up, and *Goal* is an arbitrarily chosen robot pose in front of the manipulator table.

Students have to implement a routine that lets Martino move from *Init* to *Goal* while avoiding fixed and movable obstacles. Once Martino reaches *Goal*, students should employ the routines solving Homework 1 and Homework 2 to recognize two objects on the table in front of the manipulator robot, pick them, and place them on the tray above the mobile robot. As for Homework 2, the two objects are arbitrarily selected by the students who input their frame_id from the command shell.

When the two selected objects are on the tray, Marrtino should navigate back to *Goal*.

In detail:
- exploit the ROS Navigation Stack - with appropriately tuned navigation parameters - to make Marrtino navigate inside the arena while avoiding obstacles. Try different movable obstacles configurations to prove the correct tuning of these parameters;
- implement a simple Finite State Machine guaranteeing the correct sequence of robot actions.
