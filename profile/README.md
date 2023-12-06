# Cal Poly Automated Drone Charging Project

## Overview

Exploratory project attempting to guide a drone to land on a dedicated charging pad, identified with a QR code.

## Methodology

The automatic charging sequence is divided into 3 phases:
1. Getting close to the charging pad via GPS waypoint navigation
2. Finding the target visually and navigating to above the target
3. Orienting correctly and making a controlled landing onto the target

### Phase 1: GPS Waypoint Navigation

The GPS coordinates of the charging pad will be saved prior to initiating the charge sequence. During this process, images will be captured periodically to look for the target. If the target is spotted, the drone will shift into phase 2. The gimbal position for the forward camera will be 15 degrees below horizontal.

- [ ] We must be able to automatically fly the drone to GPS coordinates
- [x] We must find a way to gather images from the camera
- [x] We must create a method to identify the target in the image

### Phase 2: Visual Target Spotting and Navigation

The drone will search for the target visually, and if targets are spotted it will attempt to navigate to an altitude of 20 feet, keeping the QR code near the center-bottom of the image.

- [x] We must find a way to gather images from the front camera
- [x] We must create a method to identify the corner points of the target in the image
- [ ] We must implement a search strategy to investigate potential targets, check targetsm and continue searching
- [x] Using the points in the image, the focal length, and the gimbal pitch, we must find the cylindrical position of the QR code relative to the drone
- [ ] With the cylindrical coordinates, navigate to the desired location before shifting to pahse 3.

### Phase 3: Orientation and Landing

The gimbal pitch will be set to 90 degrees below horizontal and the drone will rotate to the proper orientation then descend to land.

- [x] We must create a method to **uniquely** identify the corner points of the QR code in the image
- [ ] We must create a method to keep the target oriented correctly and positioned directly below the battery
- [ ] We must initiate a land at a low altiude when confident the landing will be correct

## Target

The scope of the project does not include creating a charging pad, but an ideal charging pad would have an inductive charging pad and the drone batteries would support inductive charging. For the sake of this project, the drone is tasked with landing accurately on the charging pad with the correect orientation. The target itself is the QR code pictured below.

![qrcode](https://github.com/cal-poly-auto-drone-charging/.github/assets/114958111/d475b3de-6ffa-4a95-88f0-cf977f3fee2d)
