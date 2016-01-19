# Marlin #

**A Digital Light Processing 3D printer driver**

### Project structure

- **Planner.cpp** 
	- ```plan_buffer()``` 
- **Marlin_main.cpp**
	- ```GCode Praser```
G1 -> 1. ```get_coordinates()```  2. ```prepare_move()```

	- ```manage_inactivity``` 1. execute ``kill()`` when exceed ``max_inactive_time`` 2. disable x/y/z/e0/e1/e2 when exceed ``stepper_inactive_time``
	- ```kill()``` 1. stop interrupts 2. disable heater 3. disable x/y/z/e0/e1/e2 serial 4. show/send feedbacks to user
### Known Issues

- In ```plan_buffer()``` function, controller prevents dangerous extrude by defining ``PREVENT_DANGEROUS_EXTRUDE``. Printer would ignore E part when extrusion reach the ``extrude_min_temp`` temperature.

- **URGENT** The sepration force for liquid resin with/without curing is too high, the model platform cannot seperate from PDMS film. To address this issue, we plan to make following changes to our hardware also software:
	- Slower the speed of x/y/z stepping motors
	- Move platform inside XY plane to relief the force
	- Fix the connection between platform and rotating motor