# Kinect
Kinect has an infrared projector, infrared camera, and colour camera - which makes it one of the cheapest high-quality 3d scanners available on a market.

## Converting Kinect for Xbox One into standalone.
The Xbox One Kinect Sensor requires a [Kinect adapter](https://support.xbox.com/en-US/xbox-one/accessories/kinect-adapter), which acts as a convert from proprietary type B to A USB + 12V power cable. 
![Kinect adapter picture](https://www.dhresource.com/0x0s/f2-albu-g9-M01-3B-B5-rBVaWFxeH3qAFFStAAEG5qTGsGA820.jpg/for-kinect-2-0-sensor-adapter-usb-3-0-kinect.jpg)

The use of a Kinect adapter can be eliminated by soldering the external power supply of 12V directly on Kinect's board (pin 10 (+12V)) and B to A USB v3.0 cable.
![kinect_pinout](https://user-images.githubusercontent.com/1571406/77344717-ddca3e00-6d33-11ea-9ccb-bfff50d5a661.png)

### Required items: 
 1. wire with female DC connector 5.5 x 2.1 mm
 2. DC power plug with 5.5 x 2.1 mm connector, 12V/2A or 12v/2.5A.
 3. A to B type USB v3.0 with a guaranteed speed of **5Gbps** if lower Kinect won't work.

Excellent step by step video with English subtitles by [Tat'ka](https://www.youtube.com/watch?v=vQYZABBNBqA).

### Final result
Here how looks my Kinect after modifications: 
![IMG_8234](https://user-images.githubusercontent.com/1571406/77346558-b9239580-6d36-11ea-8f82-91cadeecbe54.JPG)
For step 3. I chose to use B to B USB extension cable to have it compact in storage and extensible in use.
![Cablecc-Super-Speed-USB-3-0-Back-Panel-Mount-Female-to-Male-B-Type-Extension-Cable](https://user-images.githubusercontent.com/1571406/77345029-5c26e000-6d34-11ea-89ed-c7f0b5814a5e.jpg)

## Using multiple Kinect at once
By using multiple Kinect in the same room, one should be aware of [Interference between multiple Kinects](https://github.com/OpenKinect/libfreenect2/issues/424) - the sensors might pick up light from the other emitters.

### One machine with multiple Kinect
Kinect2 uses a lot of bandwidth on the USB v3.0 port and requires a separate USB bus to connect multiple Kinect to one machine.
As well requires using [libfreenect2](https://github.com/OpenKinect/libfreenect2) by [OpenKinect](https://openkinect.org/wiki/Main_Page) instead of Microsoft [Kinect SDK v2](https://www.microsoft.com/en-us/download/details.aspx?id=44561). 
Here, a very descriptive [article](http://docs.ipisoft.com/Multiple_Kinects_v2_on_a_Single_PC) on how to "replace" Microsoft drivers with OpenKinect one.

### Multiple machines with multiple Kinect
Alternative a client/server solution where additional Kinects are connected to client computers. The [Project RoomAlive](https://github.com/Microsoft/RoomAliveToolkit) utilizes multiple K4W sensors and requires each Kinect v2 must be hosted on a separate computer.

## Materials
[MIT OpenCourseWare](https://ocw.mit.edu): RES.3-003 [Learn to Build Your Own Videogame with the Unity Game Engine and Microsoft Kinect](https://ocw.mit.edu/resources/res-3-003-learn-to-build-your-own-videogame-with-the-unity-game-engine-and-microsoft-kinect-january-iap-2017/). By Kyle Keane PhD, Andrew Ringler MFA, Abhinav Gandhi, and Mark Vrablic. January IAP 2017. License: Creative Commons BY-NC-SA.

[iPi Recorder](http://docs.ipisoft.com/iPi_Recorder) - an easy way to get started with Kinect.
[OpenFrameworks Forum](https://forum.openframeworks.cc/t/multiple-kinect-setup-for-real-time-volumetric-reconstruction-and-tracking-of-people/15271) - discussion about physical setups with multiple Kinect.

[The Kinect distance sensor as human-machine-interface in audio-visual art projects](http://www.matthiaskronlachner.com/wp-content/uploads/2013/01/2013-01-07-Kronlachner-Kinect.pdf)
[Intelligent Sensor-Scheduling for Multi-Kinect-Tracking](https://isas.iar.kit.edu/pdf/IROS12_Faion.pdf)