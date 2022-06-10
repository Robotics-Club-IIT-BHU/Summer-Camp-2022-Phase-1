# Master Task!!!
After learning various functions of PyBullet, now it's time to test how much you have grasped!! So, here is a major task for you...

## Part 1: Loading the World
Create a door.urdf file, and load various doors in the pybullet world. Constrain these doors with the world, so that they can be rotated about their hinges when an external torque is applied on them. 5 Pairs of doors (10 doors in total) should be loaded as shown in the following figure...
<br>
<p align="center">
  <img width=500 src="https://user-images.githubusercontent.com/77807055/173033247-db0894f9-7cee-4644-b6e3-5e4098757be0.png">
  <br><i>Top View: These red lines are the doors, load the doors in the world roughly at the above mentioned positions</i>
</p>

Next, you have to load pairs of wedges in front of the doors. For that, [the URDF of the wedge](wedge.urdf) is given that makes use of [the ramp.stl](ramp.stl). Download both of these files in the same directory as your python file. The pair should be such that, both the wedges in it should be facing opposite to each other. Now load a husky at the following position...
<br>
<p align="center">
  <img width=500 src="https://user-images.githubusercontent.com/77807055/173032425-bc8c0726-1dbe-44e1-835a-2cf563ac0390.png">
  <img width=500 src="https://user-images.githubusercontent.com/77807055/173032445-98cbd232-b4d9-4fc8-a147-e89fe30190fe.png">
  <img width=500 src="https://user-images.githubusercontent.com/77807055/173032446-f5247638-171c-4fa7-a534-bf6d0b32d7cc.png">
</p>

Look for "globalScaling" attribute in the loadURDF function.

## Part 2: The Motion
Now, when you press 1 on the keyboard, first pair of doors should open, press 2 for second pair, 3, 4 and 5...
Now, the husky should pass through each pair of door one by one and then climb over the wedges, if any. To control the husky, you need to again press the arrow keys on keyboard. UP and DOWN arrows should move the husky forward and backward, RIGHT and LEFT arrow keys should turn it right and left.<br>
You can look at the [car.py](car.py) file for the starter code. Run this file and you will see the husky moving according to your controls. Implement the same thing for this task.

Here, I have demonstrated the passing of the husky through one pair of doors. You need to do it for all the doors.
<br>
<p align="center">
  <img width=500 src="sample.gif">
  <img width-500 src="husky_door_system.gif">
  </p>
  
Try to make the husky follow a path roughly similar to this 👇
<br>
<p align="center">
  <img width=500 src="https://user-images.githubusercontent.com/77807055/173035414-9997c3eb-1cc7-4138-abea-3a9037a31a3f.png">
  </p>
  
Submit your python file, door.urdf and a video of the simulation on the following link:
- [Here!! Here!!](https://forms.gle/XhPvdYha7G98Ngr49)  
