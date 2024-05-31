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
![Screenshot 2024-05-30 154913](https://github.com/leokrahn/robot-arm/assets/143544783/23e00094-1121-47da-a101-3dc395635ffb)

## physical evidence
![ezgif-6-0f4c220a4b](https://github.com/leokrahn/robot-arm/assets/143544783/3136c8ab-a7e5-4794-8706-51a40df1295d)
![WIN_20240531_15_23_00_Pro](https://github.com/leokrahn/robot-arm/assets/143544783/3910183b-0732-4b6d-a43d-ffe059e7c37d)
![WIN_20240531_15_23_53_Pro](https://github.com/leokrahn/robot-arm/assets/143544783/3619ef9b-1437-4c67-9a85-0c7738ec87eb)

## schedule

## reflection
Week 1 (March 11-15)-----------: Planned, researched, started drawings and designs.

Week 2 (March 18-22)-----------: 

Week 3 (March 25-29)-----------: 

Week 5 (April 8-12)------------: 

Week 6 (April 15-19)-----------: 

Week 7 (April 22-26)-----------: 

Week 8 (April 29-May 3)--------:

Week 9 (May 6-10)--------------: 

Week 10 (May 13-17)-------------:

Week 10 (May 19-24)-------------: Code got to the point where it would need to be printed before we could finish it, wiring finished

Week 10 (May 26-31)-------------: Documented, printed newer designs

##obituary :(
