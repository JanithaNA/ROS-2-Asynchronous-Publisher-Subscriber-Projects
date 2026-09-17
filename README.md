# ROS-2-Asynchronous-Publisher-Subscriber-Projects
A collection of two ROS 2 C++ projects demonstrating asynchronous communication between nodes using the ROS 2 Publisher–Subscriber architecture.
# ROS 2 Asynchronous Publisher–Subscriber Projects

A collection of two ROS 2 C++ projects demonstrating asynchronous communication between nodes using the ROS 2 Publisher–Subscriber architecture.

These projects explore fundamental robotics concepts such as topic-based communication, sensor data processing, digital output control, distance monitoring, and collision warning logic. They are designed as practical exercises for understanding how ROS 2 can be used in robotics and embedded systems.

## 🎥 Project Introduction

This video demonstrates both ROS 2 projects running in separate terminals, showing the communication between publishers and subscribers.

[Screencast from 2026-07-16 13-24-14.webm](https://github.com/user-attachments/assets/09e3b14e-8127-4df9-b52f-2c8d12d767a4)


[Screencast from 2026-07-16 14-51-10.webm](https://github.com/user-attachments/assets/70f847b1-add7-44c1-a223-c739d923139e)


> To display the video directly on GitHub, upload it to a supported hosting platform or add a link to a GitHub-hosted video. GitHub may not render every uploaded video format directly inside a README.

---

## 📁 Projects

### 1. LED State Controller — `ledcontroller`

A ROS 2 C++ project that demonstrates controlling an LED state through asynchronous topic-based communication.

#### Architecture

```text
┌──────────────────────┐
│   led_publisher      │
│                      │
│ Publishes "ON"/"OFF" │
│ using a timer loop   │
└──────────┬───────────┘
           │
           │ ROS 2 Topic
           ▼
┌──────────────────────┐
│   led_subscriber     │
│                      │
│ Receives LED commands│
│ and updates the state│
└──────────────────────┘
```

#### Features

* Publishes alternating `"ON"` and `"OFF"` string commands.
* Uses a timer-based publishing loop.
* Subscribes to LED state messages through a ROS 2 topic.
* Simulates digital GPIO output using `HIGH` and `LOW` states.
* Demonstrates inter-process communication between ROS 2 nodes.
* Provides a foundation for controlling physical LEDs or embedded hardware.

#### Example Output

```text
[GPIO HIGH] LED is now turned ON
[GPIO LOW] LED is now turned OFF
[GPIO HIGH] LED is now turned ON
```

#### Key Concepts

* ROS 2 Publishers and Subscribers
* ROS 2 Topics
* Timer-based callbacks
* String message handling
* Digital output control
* Embedded systems integration

---

### 2. Collision Safety & Distance Monitor — `collisionwarning`

A ROS 2 C++ project that simulates distance sensor data and monitors obstacle proximity using threshold-based safety logic.

#### Architecture

```text
┌────────────────────────┐
│    sensor_publisher    │
│                        │
│ Simulates distance     │
│ sensor measurements    │
└───────────┬────────────┘
            │
            │ ROS 2 Topic
            ▼
┌────────────────────────┐
│   collision_monitor    │
│                        │
│ Evaluates distance     │
│ and generates alerts   │
└────────────────────────┘
```

#### Distance Monitoring Logic

| Distance           | Status   | Alert                |
| ------------------ | -------- | -------------------- |
| Greater than 1.0 m | Safe     | Clear path ahead     |
| 0.4 m–1.0 m        | Warning  | Approaching obstacle |
| 0.4 m or less      | Critical | Collision warning    |

#### Features

* Simulates continuous distance measurements from 3.0 m to 0.1 m.
* Publishes sensor data through a ROS 2 topic.
* Processes incoming distance measurements asynchronously.
* Classifies obstacle proximity using threshold conditions.
* Uses ROS 2 logging levels: `INFO`, `WARN`, and `ERROR`.
* Demonstrates safety monitoring logic for mobile robots and automated systems.


## 🛠️ Technologies Used

* **ROS 2**
* **C++**
* **rclcpp**
* ROS 2 Topics
* Asynchronous Publisher–Subscriber communication
* Timer callbacks
* Distance threshold evaluation
* ROS 2 logging
* Linux / Ubuntu

## 🚀 Getting Started

### Prerequisites

* Ubuntu Linux
* ROS 2 installed and configured
* C++ compiler
* `colcon` build system
  

## 📚 Learning Outcomes

Through these projects, the following concepts are explored:

* Creating and running ROS 2 nodes using C++.
* Understanding asynchronous topic-based communication.
* Publishing and subscribing to sensor and control messages.
* Processing incoming data using callback functions.
* Implementing digital output logic.
* Designing threshold-based safety monitoring.
* Using ROS 2 logging for system feedback and diagnostics.
* Connecting robotics software concepts with embedded systems applications.

## 🔮 Future Improvements

* Connect the LED controller to a physical GPIO device.
* Replace simulated distance data with real ultrasonic or LiDAR sensor readings.
* Integrate the collision monitor with a robot's motor controller.
* Implement a physical emergency-stop mechanism with appropriate safety validation.
* Add launch files for running nodes together.
* Use custom ROS 2 message types for structured sensor data.
* Add unit tests and automated build workflows.


⭐ If you find these projects useful for learning ROS 2 and robotics, consider giving this repository a star.
