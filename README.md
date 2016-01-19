# Marlin #

**A Digital Light Processing 3D printer driver**

---

### Project structure

- **Planner.cpp** 
	- ```plan_buffer()``` 
- **Marlin_main.cpp**
	- ```GCode Praser```
G1 -> 1. ```get_coordinates()```  2. ```prepare_move()```


### Known Issues

- In ```plan_buffer()``` function, controller prevents dangerous extrude by defining ``PREVENT_DANGEROUS_EXTRUDE``. Printer would ignore E part when extrusion reach the ``extrude_min_temp`` temperature.
