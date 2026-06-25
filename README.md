# Turtle Speed Monitoring Service + Motion Control (ROS)

Robotic System & Programming Lab, Open Ended Lab Task. Simulates a turtle moving
on screen using Turtlesim, monitors its speed/direction in real time using a ROS
service, and auto-controls motion if speed crosses a threshold.

**Bahria University Karachi Campus**
Class: BS RIS-5A, Fall 2025

Team:
- Malahima Adeel (02-239232-043)
- Urooj Khan (02-239232-052)
- Shayan Ali (02-239232-068)

Submitted to: Sir Hamza

## Objectives
- Turtle moves in a pattern
- Implement a ROS service that returns turtle's (x, y) position
- Client calls service repeatedly to compute speed and direction
- If speed > 3.0, client sends cmd_vel to slow it down
- Demonstrate ROS service-topic integration

## System Design

**Turtle Motion Node**
- Moves turtle in circular pattern with slight speed variation (sine function)
- Maximum speed capped to prevent excessive velocity

**Service Server Node**
- Subscribes to `/turtle1/pose` for live coordinates
- Implements `/get_turtle_state` service, returns turtle's current (x, y)

**Client Node**
- Repeatedly calls the service for latest position
- Calculates speed and direction between consecutive positions
- Logs data to terminal for monitoring
- Publishes `cmd_vel` message if speed exceeds 3.0
- Warning triggered only once per speed crossing (no spam)

## Tools Used
- ROS (Robot Operating System)
- Turtlesim
- ROS Services and Topics

## Files
- `Turtle_Speed_Monitoring_Report.pdf` — full project report
- `demo_video.mp4` — working demo
