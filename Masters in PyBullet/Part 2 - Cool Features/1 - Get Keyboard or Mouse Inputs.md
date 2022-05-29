Before starting with the main functions of PyBullet, let's play with some cool features in it.
# Get KeyBoard or Mouse inputs
Taking a real world analogy, suppose you wish that on pressing a specific button, the robot does some particular tasks, and on pressing some other button, another set of tasks should be done. Although, we won't be making an actual button-signal system over here, but the idea is to command the robot based on the given inputs..
<br>
<p align="center">
  <img width=500 src="https://user-images.githubusercontent.com/77807055/170840626-6cd4c50c-d81d-4143-9e4e-2728d5b33c1f.gif">
  <br><i>Let me give command to the robot</i>
  </p>
  
This can be done by giving inputs using keyboard or mouse, and let the robot react accordingly.
#### How to implement it?
## getKeyboardEvents
#### Follow the words of the bible...
> You can receive all keyboard events that happened since the last time you called 'getKeyboardEvents'. Each event has a keycode and a state. The state is a bit flag combination of KEY_IS_DOWN, KEY_WAS_TRIGGERED and KEY_WAS_RELEASED. If a key is going from 'up' to 'down' state, you receive the KEY_IS_DOWN state, as well as the KEY_WAS_TRIGGERED state. If a key was pressed and released, the state will be KEY_IS_DOWN and KEY_WAS_RELEASED.

> Some special keys are defined: B3G_F1 … B3G_F12, B3G_LEFT_ARROW, B3G_RIGHT_ARROW, B3G_UP_ARROW, B3G_DOWN_ARROW, B3G_PAGE_UP, B3G_PAGE_DOWN, B3G_PAGE_END, B3G_HOME, B3G_DELETE, B3G_INSERT, B3G_ALT, B3G_SHIFT, B3G_CONTROL, B3G_RETURN.

> The input of getKeyboardEvents is an optional physicsClientId:

> |optional|physicsClientId|int|if you are connected to multiple servers, you can pick one|
> |---|---|---|---|

> The output is a dictionary of keycode 'key' and keyboard state 'value'.

#### Check out [this code - KeyboardInputs.py](KeyboardInputs.py) to test the above function, where spheres are spawned at locations depending on the pressed keys. URDF of the sphere can be accessed from [here](https://github.com/Robotics-Club-IIT-BHU/Summer-Camp-2022-Phase-1/blob/main/Masters%20in%20PyBullet/Part%201%20-%20Installation/sphere.urdf). Make sure that the pybullet window is selected while giving inputs
## getMouseEvents
Mouse events include the movements of the pointer as well as triggering of any mouse button. Let's look what bible has to say for that...
> Similar to getKeyboardEvents, you can get the mouse events that happened since the last callto getMouseEvents. All the mouse move events are merged into a single mouse move eventwith the most up-to-date position. In addition, all mouse button events for a given button aremerged. If a button went down and up, the state will be 'KEY_WAS_TRIGGERED '. We reuse the KEY_WAS_TRIGGERED /KEY_IS_DOWN /KEY_WAS_RELEASED for the mouse button states.

> Input arguments to getMouseEvents are:

> |optional|physicsClientId|int|if you are connected to multiple servers, you can pick one|
> |---|---|---|---|

> The output is a list of mouse events in the following format:

> |eventType|int|MOUSE_MOVE_EVENT=1, MOUSE_BUTTON_EVENT=2|
> |:---:|:---:|:---:|
> |**mousePosX**|**float**|**x-coordinates of the mouse pointer**|
> |**mousePosY**|**float**|**y-coordinates of the mouse pointer**|
> |**buttonIndex**|**int**|**button index for left/middle/right mouse button**|
> |**buttonState**|**int**|**flag KEY_WAS_TRIGGERED /KEY_IS_DOWN /KEY_WAS_RELEASED**|

#### Check out [this kool implementation - MouseInputs.py](MouseInputs.py) of the above function and watch the spheres being spawned as you move the pointer. Again, this will work only when your pointer will hover over the simulation window.
<br>
<p align="center">
  <img width="500" src="https://user-images.githubusercontent.com/77807055/170861742-00286866-183b-4934-8ca2-c31f9b9a2963.gif"><br>
  <i>Inputs...Inputs everywhere!!!</i>
</p>
