# servo_as

A small asynchronous MicroPython servo library for conrolling SG90 servos with a Raspberry Pi Pico.

**Note:** This is a very incomplete WIP project. It may run, and your welcome to browse but please don't depend on it as everything about it is subject to change!

Example Usage :
```python
import uasyncio as asyncio
from servo_as import Servo_SG90 as Servo

async def main():
    servo1 =  Servo('Servo 1',0,Servo.CENTER) 
    
    while True:
        asyncio.create_task(servo1.move_to_poistion(Servo.PLUS_NINETY))
        await asyncio.sleep(20)
        asyncio.create_task(servo1.move_to_poistion(Servo.MINUS_NINETY))
        await asyncio.sleep(20)
        

asyncio.run(main())
```
