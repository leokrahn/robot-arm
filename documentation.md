## planning
Our plan was to make a robot arm that can play a song on piano. Originally the song idea was Bohemian Rhapsody but we changed it to Runaway by kanye. I (Leo K) planned on bringing in a midi keyboard to hook up to the computer, which it would play the song on.
Here is what was our main planning drawing
![fbih](https://github.com/leokrahn/robot-arm/assets/143544783/f9f3237e-c6ae-4ec0-ac60-ef824218075b)
In the image you can see the idea was to use tracks and wheels kinda like how a drawer works. The arm extends from inside the box where the tracks are and plays on the piano from there. We later changed this to a rack and pinion instead of tracks and wheels. Leo W designed the rack and pinion and then added walls on the side of the gear to keep it from falling off. The gear has a plate on top of it which the metro board and arm would sit on.
##bom

## wiring diagram
![Screenshot 2024-05-30 153955](https://github.com/leokrahn/robot-arm/assets/143544783/63e48458-646d-408b-95b3-a1c6656e5308)

## code
```python
import board
import time
import pwmio
from adafruit_motor import servo
from digitalio import DigitalInOut, Direction, Pull

# create a PWMOut object on the control pin.
pwm1 = pwmio.PWMOut(board.D5, duty_cycle=0, frequency=50)
pwm2 = pwmio.PWMOut(board.D4, duty_cycle=0, frequency=50)
pwm3 = pwmio.PWMOut(board.D3, duty_cycle=0, frequency=50)

servo1 = servo.ContinuousServo(pwm1)
servo2 = servo.ContinuousServo(pwm2)
servo3 = servo.ContinuousServo(pwm3)

button = DigitalInOut(board.D12)

while True:
    if button.value:
        ##note 1
        servo2.throttle = 1.0
        time.sleep(1.0)
        servo2.throttle = -1.0
        time.sleep(1.0)
        servo2.throttle = 0.0
        time.sleep(1.0)
        ##note 2R
        servo2.throttle = 1.0
        time.sleep(1.0)
        servo2.throttle = -1.0
        time.sleep(1.0)
        servo2.throttle = 0.0
        time.sleep(1.0)
        ##note 3
        servo2.throttle = 1.0
        time.sleep(1.0)
        servo2.throttle = -1.0
        time.sleep(1.0)
        servo2.throttle = 0.0
        servo1.throttle = 1.0
        time.sleep(2.0)
        ##stop
        servo1.throttle = 0.0
        time.sleep(1.0)
        ##note 4
```
## cad
![Screenshot 2024-05-30 154836](https://github.com/leokrahn/robot-arm/assets/143544783/85eaf7d2-d714-4026-982b-2110c074d28c)
the rack and pinion
![Screenshot 2024-05-30 154913](https://github.com/leokrahn/robot-arm/assets/143544783/23e00094-1121-47da-a101-3dc395635ffb)
the robot arm
## physical evidence
![ezgif-6-0f4c220a4b](https://github.com/leokrahn/robot-arm/assets/143544783/3136c8ab-a7e5-4794-8706-51a40df1295d)
![WIN_20240531_15_23_00_Pro](https://github.com/leokrahn/robot-arm/assets/143544783/3910183b-0732-4b6d-a43d-ffe059e7c37d)
![WIN_20240531_15_23_53_Pro](https://github.com/leokrahn/robot-arm/assets/143544783/3619ef9b-1437-4c67-9a85-0c7738ec87eb)
![IMG_0646](https://github.com/leokrahn/robot-arm/assets/143544783/9de413c5-29a4-471d-bd8b-94e7abe38434)

## schedule
Week 1 (March 11-15)-----------: Planned, researched, started drawings and designs.

Week 2 (March 18-22)-----------: Onshape started, code started

Week 3 (March 25-29)-----------: Wiring started, rack created

Week 5 (April 8-12)------------: Pinion created, wiring updated to include a second motor, plate added

Week 6 (April 15-19)-----------: Sizes of the parts updated to fit real life

Week 7 (April 22-26)-----------: Walls added to the side of the pinion to prevent it from falling off

Week 8 (April 29-May 3)--------: Screws and hex bolts added

Week 9 (May 6-10)--------------: Walls cut so the motor can spin the gear

Week 10 (May 13-17)-------------: First version of the pinion, pinion walls, and pinion plate printed, onshape updated so that the problems with what was printed were fixed

Week 10 (May 19-24)-------------: Code got to the point where it would need to be printed before we could finish it, wiring finished, pinion plate, pinion, and pinion walls printed

Week 10 (May 26-31)-------------: Documented, printed rack and rack walls

## reflection
The project could have been a lot better in my opinion, if we had spent more time doing work I think we could have finished so. So I advise as a "nugget of wisdom" to not goof off just because you think you have a lot of time to work on it. The project idea itself was ambitious but at the same time we got pretty close. If we had time to assemble the whole thing together, the only major thing that would be left would be to measure how fast the servo moves the pinion along the rack, and then to write each individual note. I also advise to make sure both partners have something they can be working at all times, to maximize efficiency. 

There were a couple things that were obstacles for us along the way when making this project. The first problem we came across was making the pinion gear be able to smoothly move along the rack. It some math to figure out but eventually Leo W was able to design the rack so that the pinion could mooth smoothly along it. From there to the point we got was pretty straightfoward, we came up with the idea to put walls on the side of it to prevent it from falling off, but it was a lot of trial and error since we kept printing things that had one minor things wrong with it. The version that we have right now works, it just needs to be assembled fully. The other major issue we had was calculating how fast the motor will move the pinion along the rack, so we know how long it has to spin for in order to hit the right notes. As it turns out it's not possible to do that as the weight of the pinion and whats on top of it affects the rpm (rotation speed) of the motor. So as I already stated that would have been the next step after assembling the whole thing.

## obituary :(
It is very unfortunate that we were unable to finish the project because I think it would have been great. If I could pick it back up I would make sure to really lock in and not goof off. But seriously the first thing I would do would be to assemble it. Then I would print the arm part, assemble that, make sure it all works properly, put the servos in the right place, measure how fast the servos move the pinion, and then code each individual note so that it works properly.

The number one thing I'd do differently would be to work harder. I would also not waste time trying to calculate the speed of pinion.
