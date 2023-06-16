# MobileRobot-Openloopcontrol
## Aim:

To develop a python control code to move the mobilerobot along the predefined path.

## Equipments Required:
1. RoboMaster EP core
2. Python 3.7

## Procedure

Step1:

 Import the necessary modules and classes.

Step2:

Check if the code is being run as the main module.

Step3:

Initialize the robot and establish a connection.

Step4:

 Get the necessary robot components.

Step5:

Start the video streaming.

Step6:

 Set LED color, move the chassis, and repeat.

## Program
```
from robomaster import robot
import time
from robomaster import camera

if _name_ == '_main_':
    ep_robot = robot.Robot()
    ep_robot.initialize(conn_type="ap")

    ep_chassis = ep_robot.chassis
    ep_led = ep_robot.led
    ep_camera = ep_robot.camera
          
    print("Video streaming started.....")
    ep_camera.start_video_stream(display=True, resolution = camera.STREAM_360P)
    ''' 
    x = x-axis movement distance,( meters) [-5,5]
    y = y-axis movement distance,( meters) [-5,5] 
    z = rotation about z axis ( degree)[-180,180]
    xy_speed = xy axis movement speed,( unit meter/second)  [0.5,2]

    '''
    ep_led.set_led(comp="all",r=255,g=100,b=0,effect="on") 
    ep_chassis.move(x=3, y=0, z=0, xy_speed=1).wait_for_completed()
    time.sleep(1)
    ep_led.set_led(comp="all",r=0,g=0,b=255,effect="on") 
    ep_chassis.move(x=0, y=0, z=90, xy_speed=1).wait_for_completed()
    time.sleep(1)
  


    ep_led.set_led(comp="all",r=255,g=0,b=20,effect="on") 
    ep_chassis.move(x=2, y=0, z=0, xy_speed=1).wait_for_completed()
    time.sleep(1)
    ep_led.set_led(comp="all",r=255,g=170,b=20,effect="on") 
    ep_chassis.move(x=0, y=0, z=90, xy_speed=1).wait_for_completed()
    time.sleep(1)
    ep_chassis.move(x=2, y=0, z=0, xy_speed=1).wait_for_completed()
    ep_led.set_led(comp="all",r=100,g=170,b=20,effect="on") 
    ep_chassis.move(x=0, y=0, z=90, xy_speed=1).wait_for_completed()
    ep_led.set_led(comp="all",r=100,g=70,b=20,effect="on") 
    ep_chassis.move(x=2, y=0, z=0, xy_speed=1).wait_for_completed()

    


 

    

    ep_camera.stop_video_stream()
    print("Stopped video streaming.....")

    ep_robot.close()

```

## MobileRobot Movement Image:

![robo](./img/robomaster.png)

![image](https://github.com/Vasanthpushpa/mobilerobot-openloopcontrol/assets/119291100/b9ddb521-d07c-472e-90ae-3b26b076d8ad)


## MobileRobot Movement Video:

Upload your video in Youtube and paste your video-id here

[![IMAGE ALT TEXT HERE](https://img.youtube.com/vi/YOUTUBE_VIDEO_ID_HERE/0.jpg)](https://www.youtube.com/watch?v=YOUTUBE_VIDEO_ID_HERE)

<br/>
<br/>
<br/>
<br/>

## Result:
Thus the python program code is developed to move the mobilerobot in the predefined path.


<br/>
<br/>

```
Mobile Robotics Laboratory
Department of Artificial Intelligence and Data Science/ Machine Learning
Saveetha Engineering College
```
