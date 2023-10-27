import board
import pwmio
import digitalio

#Define Left Motor
motor1_pwm = pwmio.PWMOut(board.GP13)
motor1_direction1 = digitalio.DigitalInOut(board.GP14)
motor1_direction1.direction = digitalio.Direction.OUTPUT
motor1_direction2 = digitalio.DigitalInOut(board.GP15)
motor1_direction2.direction = digitalio.Direction.OUTPUT

#Define Right Motor
motor2_pwm = pwmio.PWMOut(board.GP16)
motor2_direction1 = digitalio.DigitalInOut(board.GP17)
motor2_direction1.direction = digitalio.Direction.OUTPUT
motor2_direction2 = digitalio.DigitalInOut(board.GP18)
motor2_direction2.direction = digitalio.Direction.OUTPUT

#Function to control motor 1 speed
def motor1_speed(speed):
    if speed > 0:
        motor1_direction1.value = True
        motor1_direction2.value = False
    elif speed < 0:
        motor1_direction1.value = False
        motor1_direction2.value = True
    else:
        motor1_direction1.value = False
        motor1_direction2.value = False
    motor1_pwm.duty_cycle = int(abs(speed) * 65535)

#Function to control motor 2 speed
def motor2_speed(speed):
    if speed > 0:
        motor2_direction1.value = True
        motor2_direction2.value = False
    elif speed < 0:
        motor2_direction1.value = False
        motor2_direction2.value = True
    else:
        motor2_direction1.value = False
        motor2_direction2.value = False
    motor2_pwm.duty_cycle = int(abs(speed) * 65535)
    
    
#Function to control both motor speeds
def speed(speedleft, speedright):
    motor1_speed(speedleft)
    motor2_speed(speedright)

#Function to make both motors traverse forward
def forward(speed):
    if speed > 0:
        motor1_direction1.value = True
        motor1_direction2.value = False
        motor2_direction1.value = True
        motor2_direction2.value = False
        motor1_pwm.duty_cycle = int(abs(speed) * 65535)
        motor2_pwm.duty_cycle = int(abs(speed) * 65535)

#Function to make both motors traverse backward
def backward(speed):
    if speed > 0:
        motor1_direction1.value = False
        motor1_direction2.value = True
        motor2_direction1.value = False
        motor2_direction2.value = True
        motor1_pwm.duty_cycle = int(abs(speed) * 65535)
        motor2_pwm.duty_cycle = int(abs(speed) * 65535)

#Function to make both motors stop
def stop():
    motor1_direction1.value = False
    motor1_direction2.value = False
    motor2_direction1.value = False
    motor2_direction2.value = False
