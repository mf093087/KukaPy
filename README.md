```markdown
# kukapy

## Overview
**kukapy** is a Python package designed to control KUKA robots by interfacing with the KUKA Controller via the `kukadriver` module. The package provides functionalities for calibration, motion control, and transformation handling.

### Project Structure

- **kukadriver** (KRL scripts for the KUKA robot controller):
  - `mappdk_kuka_cmd.src` – Handles robot commands.
  - `mappdk_kuka_comm.src` – Manages communication between the robot and the external system.
  - `mappdk_kuka_logger.src` – Logs system and command activities.
  - `mappdk_kuka_server.src` – Serves as the main interface server for the robot.
  - `mappdk_kuka_utils.src` – Provides utility functions for robot operations.

- **kukapy** (Python API for KUKA robot interaction):
  - `calibration.py` – Handles robot calibration.
  - `robot.py` – Core module for robot control.
  - `robotapp.py` – Application-level control logic.
  - `transformations.py` – Utilities for handling transformations (e.g., quaternions, Euler angles).

## Installation

1. Ensure Python 3.x is installed.
2. Clone the repository:
   ```bash
   git clone https://github.com/your-username/kukapy.git
   cd kukapy
   ```
3. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

## Deploy to KUKA Controller

1. Transfer the `.src` files from `kukadriver` onto the KUKA controller.
2. Configure network communication between the controller and your computer (e.g., set IP addresses, verify connectivity).
3. Start the relevant KUKA programs (like `mappdk_kuka_server.src`) on the robot to enable commands.

## Usage

```python
from kukapy.robot import Robot

# Initialize the robot connection
robot = Robot(ip="192.168.1.100", port=12345)

# Move the robot to a position (XYZ + Quaternion)
robot.move_to([500, 0, 300], [0, 1, 0, 0])

# Retrieve the current position
pos = robot.get_position()
print("Current Position:", pos)

# Disconnect
robot.disconnect()
```

## Contributing

Contributions are welcome! Please open an issue or submit a pull request. For larger changes, discuss your ideas in an issue first.

## License

This project is licensed under the [MIT License](LICENSE).

## Contact

For any inquiries, please open an issue on this repository or contact the maintainers directly.
```
