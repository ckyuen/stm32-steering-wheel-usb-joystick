# stm32-steering-wheel-usb-joystick
This is the electronic part of my DIY steering wheel for sim racing using STM32. Featuring 8 front-facing buttons, 2 pedal shifters and 2 rotary encoders.

## Materials
1. Generic STM32F103 Blue-Pill Board https://stm32-base.org/boards/STM32F103C8T6-Blue-Pill.html
2. 8 momentary switches of any kind
3. 2 incremental rotary encoders (Module form with pull-up resistors and low-pass filters is perferred.)

## Peripheral Mappings
### 1. Momentary switches
All buttons are connected to GPIO with Active-Low configuration. Internal pull-up needs to be enabled fo all pins.
### 2. Rotary Encoders
Two rotary encoders are connected to TIM2 and TIM3 in Encoder Mode respectively. TI1 and TI2 are used for both Timer to capture the rotational direction. 
Software Input Filter for all timer channels are enabled. Both Interrupt for TIM2 and TIM3 needs to be enabled as well.

## USB HID Joystick Device
A custom HID report Descriptor is used with 14 binary inputs enabled which can be modified to support a maximum of 32 binary inputs(buttons) for a single HID Device. 
