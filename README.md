# owl
Hackathon Challenge for Edge Compute Vision and Coordinate Interaction.

<img src="https://user-images.githubusercontent.com/1065118/189431025-5d172308-b586-4c7d-925a-eb0ef591daa3.png" width=400>


## Challenge

### Standard
Can you, given the coordinates and direction of a camera, determine the rotation and elevation needed to pan and tilt that camera to look at an arbitrary latitude/longitude/elevation coordinate.

### Bonus
* Can you deal with a camera that is moving so it would track a point... like an owl.
* Can you deal with a rotating camera?
* Can you main tracking even if gps is intermittent?
* A test harness UI where points can be dropped in the geographic area around the camera is highly encouraged.


### Ultra Bonus
Given a bounding box in the camera's view, can you determine the coordinates of that rough location in latitude / longitude / altitude in the real world.

## Constraints
* Camera Coordinates will be in latitude / longitude / altitude
* Camera direction is not known but will need to be determined. How? Can you?
* Target coordinates will be in latitude / longitude / altitude
* Camera can only be controlled in roughly degrees off local center pan and tilt.
* GPS coordinates of camera will be provided
  * Will be live (if our test harness is working right.)
* Target coordinates will be provided
* Coordinates are limited to earth
* Only one pan/tilt camera available, write you code and then we will copy it over to the Pi4 with the cam. We could also enable ssh so everyone can "timeshare" on it.

## Hints
* Assume static GPS location / rotation of camera base first.
  * Ahem... yes we have a GPS unit but it's very hard to get to work indoors, even in a window.
* Simulation is fine if you would rather do that first.
* If you want to visualize a target coordinate, something like this might be helpful https://towardsdatascience.com/simple-gps-data-visualization-using-python-and-open-street-maps-50f992e9b676
* Maybe 3d plotting might help if you create a simulator for the camera and target? https://jakevdp.github.io/PythonDataScienceHandbook/04.12-three-dimensional-plotting.html
* More visulization / simulation possibilities: https://towardsdatascience.com/visualizing-geospatial-data-in-python-e070374fe621
* Common issues with GPS https://raspberrypi.stackexchange.com/questions/68816/how-can-i-set-up-my-g-mouse-usb-gps-for-use-with-raspbian
* The Rpi4 is using libcamera right now. That's the new open source camera stack for Rpis. But if you really need to use something that is only compatible with raspicam, we can make that happen.
* There is a large battery available if you wish to take the project outside for gps signal and/or testing.
* If you are good with game engines, perhaps you could do a simulation with this? https://www.panda3d.org/
* GPS spec, https://gpsd.gitlab.io/gpsd/gpsd_json.html

## Final Requirements
* An algorithm implementation that given a camera latitude / longitude / alt, and a target latitude / longitude / altitude determines the azimuth and elevation of the camera
* Implementation should be compatible with the pan/tilt control api. In other words, the azimuth / elevation should be passable to the `pantilthat` api.



