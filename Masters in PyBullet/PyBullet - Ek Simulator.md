# PyBullet - Ek Simulator
#### You must have heard about driving and flight simulators, what purpose do they serve?
Obviously, to do the task in a virtual environment, without using the actual hardware. Or to imitate the real world conditions in a virtual environment to check how things might go (for example, when scientists try to simulate the earth conditions of very old times). The conditions are simulated in a virtual environment but the user feels it to be real. The main goal is to make the user learn, try and test various functions without causing loss to the actual hardware. Suppose, in some case, the user inputs a wrong function, the whole simulation can be restarted.<br>
<p align="center">
  <img width=500 src="https://media0.giphy.com/media/YvhvOTwXQDQ3ctcAPs/giphy.gif?cid=ecf05e477mhk21mwpcl3hvzerihl6v8yktb4iakqh416ocg6&rid=giphy.gif&ct=g">
  </p>

> A simulation is the imitation of the operation of a real-world process or system over time.

This is precisely why we need simulators in robotics as well. Robot simulators let you replicate the robot in a virtual environment, and imitate its functions. You can try and test various ideas on robot without actually building one. We need to program various joints of the robot and then, test it. But what if there was some bug in the program? You don't want your bot to run into a pit and go crash itself, right? Also debugging codes directly in hardware takes a lot of time.<br>
#### So, to save time, money and effort, we need...
<br>
<p align="center">
  <img width=500 src="https://media2.giphy.com/media/26tk09AMq9Bh01cxW/200w.webp?cid=ecf05e47eakk7v6m3d7cgosn7mapuh22os19lwmvziduhp40&rid=200w.webp&ct=g">
  <br><i>Just a Simulation</i>
  </p>
  
Different tools are used for the analysis of kinematics(does not include the cause of motion), dynamics(includes the cause of motion) of robotic manipulators, for off-line programming, to design different control algorithms, to design mechanical structure of robots, to design robotic cells and production lines, etc. Given that simulation is the way to go, there are plenty of options available for robotics namely Bullet, Gazebo, V-Rep, Webots, Open Dynamics Engine, MujoCo, etc.

# PyBullet
#### Now, if you have attended the introductory session on the camp (which I am sure u have 😌), you must know that we have a very beginner-friendly simulator for robotics i.e., PyBullet.
Bullet is a physics engine that simulates collision detection, soft and rigid body dynamics. It has been used in video games as well as for visual effects in movies.PyBullet is an easy to use Python module for physics simulation, robotics, and deep reinforcement learning based on the Bullet Physics SDK.<br><br>
While PyBullet is a python module to work on Bullet. It is an easy to use and light-weight simulator that works on python. It can be used in robots involving advanced deep reinforcement learning.<br>
#### Here are some cool simulations in PyBullet:
<br>
<p align="center">
  <img width=500 src="gif03.gif">
  </p>
  
  <p align="center">
  <img width=500 src="gif01.gif">
  </p>

#### Okay...okay...okay...I don't wanna give you a feeling of existential crisis 😔, but you can also be in a simulation controlled by some higher dimensional creatures...forget it🙂
