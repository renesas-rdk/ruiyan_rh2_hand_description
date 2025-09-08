# ruiyan_rh2_hand_description

ROS2 package containing URDF description files for the Ruiyan RH2 dexterous hand.

## Overview

This package provides the robot description for the Ruiyan RH2 dexterous hand, including URDF/XACRO files, 3D meshes, and visualization launch files for RViz and Foxglove Studio. Supports both left and right hand configurations.

## Usage

### RViz Visualization

Launch with GUI (local):
```bash
ros2 launch ruiyan_rh2_hand_description display_rviz.launch.py run_rviz:=true
```

Launch for remote visualization:
```bash
ros2 launch ruiyan_rh2_hand_description display_rviz.launch.py run_rviz:=false
```

### Foxglove Studio Visualization

```bash
ros2 launch ruiyan_rh2_hand_description display_foxglove.launch.py
ros2 launch ruiyan_rh2_hand_description display_foxglove.launch.py hand_side:=right
```

Connect Foxglove Studio to `ws://<foxglove_bridge_ip>:8765`.

### Using the XACRO Macro

For left hand:
```xml
<xacro:include filename="$(find ruiyan_rh2_hand_description)/urdf/ruiyan_hand_left_macro.xacro" />

<xacro:ruiyan_hand_left prefix="left_hand_" parent="tool0">
  <origin xyz="0 0 0" rpy="0 0 0" />
</xacro:ruiyan_hand_left>
```

For right hand:
```xml
<xacro:include filename="$(find ruiyan_rh2_hand_description)/urdf/ruiyan_hand_right_macro.xacro" />

<xacro:ruiyan_hand_right prefix="right_hand_" parent="tool0">
  <origin xyz="0 0 0" rpy="0 0 0" />
</xacro:ruiyan_hand_right>
```

## Hand Specifications

- **Type:** Dexterous anthropomorphic hand
- **Configurations:** Left and right hand variants
- **DOF:** Multiple articulated fingers with independent joint control
- **Coordinate frames:** base → hand links → finger links → TCP

## License

Apache-2.0. URDF model for Ruiyan RH2 dexterous hand.
