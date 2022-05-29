#### Now that you know, how to give inputs to the system, it's time to fill it with colors🎨🖌
# Draw Lines (Function - addUserDebugLine)
Sometimes, it is useful to draw lines in 3D space of the simulation world for visualization purpose, and pybullet surely provides the utility. You can add a 3d line specified by a 3d starting point (from) and end point (to), a color [red,green,blue], a line width and a duration in seconds. The arguments to addUserDebugline are:

|optional/required|parameter name|data type|description|
|:---------------:|:----------:|:------:|:---------:|
|required|lineFromXYZ|vec3, list of 3 floats|starting point of the line in Cartesian world coordinates|
|required|lineToXYZ|vec3, list of 3 floats|end point of the line in Cartesian world coordinates|
|optional|lineColorRGB|vec3, list of 3 floats|RGB color [Red, Green, Blue] each component in range [0..1]|
|optional|lineWidth|float|line width (limited by OpenGL implementation)|
|optional|lifeTime|float|use 0 for permanent line, or positive time in seconds (afterwards the line with be removed automatically)|
|optional|parentObjectUniqueId|int|draw line in local coordinates of a parent object/link|
|optional|parentLinkIndex|int|draw line in local coordinates of a parent object/link|
|optional|replaceItemUniqueId|int|replace an existing line (to improve performance and to avoid flickering of remove/add)|
|optional|physicsClientId|int|if you are connected to multiple servers, you can pick one|

addUserDebugLine will return a non-negative unique id, that lets you remove the line using removeUserDebugItem.

    LineID = p.addUserDebugLine([0,0,0], [1,1,1], [0,0,1], 2, 0) # This will draw a permanent blue line from origin to (1,1,1)

# Add Text (Function - addUserDebugText)
You can add some 3d text at a specific location using a color and size. The input arguments are:

|optional/required|parameter name|data type|description|
|:---------------:|:----------:|:------:|:---------:|
|required|text|string|text represented as a string (array of characters)|
|required|textPosition|vec3, list of 3 floats|3d position of the text in Cartesian world coordinates [x,y,z]|
|optional|textColorRGB|vec3, list of 3 floats|RGB color [Red, Green, Blue] each component in range [0..1]|
|optional|textSize|float|Text size|
|optional|lifeTime|float|use 0 for permanent text, or positive time in seconds (afterwards the text with be removed automatically)|
|optional|textOrientation|vec4, list of 4 floats|By default, debug text will always face the camera, automatically rotation. By specifying a text orientation (quaternion), the orientation will be fixed in world space or local space (when parent is specified). Note that a different implementation/shader is used for camera facing text, with different appearance: camera facing text uses bitmap fonts, text with specified orientation uses TrueType fonts..|
|optional|parentObjectUniqueId|int|draw line in local coordinates of a parent object/link|
|optional|parentLinkIndex|int|draw line in local coordinates of a parent object/link|
|optional|replaceItemUniqueId|int|replace an existing text item (to avoid flickering of remove/add)|
|optional|physicsClientId|int|if you are connected to multiple servers, you can pick one|

addUserDebugText will return a non-negative unique id, that lets you remove the line using removeUserDebugItem.

    TextID = p.addUserDebugText("Hello", [1,1,1], [0,0,1], 1, 0, p.getQuaternionFromEuler([1.57,0,0])) # Play with it to get familiar with the features
    
# Creating trackbars (Function - addUserDebugParameter)
Sometimes, you need to tune some parameters to their optimal values. Changing the parameter manually everytime can be tedious, but if there is a trackbar where you can slide the button and change the values, it will be more handy. Here is how you can create one:<br>
addUserDebugParameter lets you add custom sliders and buttons to tune parameters. It will return a unique id. This lets you read the value of the parameter using readUserDebugParameter. The input parameters of addUserDebugParameter are:

|required/optional|parameter name|data type|description|
|:---------------:|:------------:|:-------:|:---------:|
|required|paramName|string|name of the parameter|
|required|rangeMin|float|minimum value. If Minimum value > maximum value a button instead of slider will appear|
|required|rangeMax|float|maximum value|
|required|startValue|float|starting value|
|optional|physicsClientId|int|if you are connected to multiple servers, you can pick one|

The input parameters of readUserDebugParameter are:

|required|itemUniqueId|int|the unique id returned by addUserDebugParameter|
|:---:|:---:|:---:|:---:|
|**optional**|**physicsClientId**|**int**|**if you are connected to multiple servers, you can pick one**|

Return value is the most up-to-date reading of the parameter, for a slider. For a button, the value of getUserDebugParameter for a button increases 1 at each button press.

Check out this implementation of [slider.py](slider.py) where the slider value is the x coordinate. If you change the value of slider, a new sphere will be spawned at that new x position.
<br>
<p align="center">
  <img width=500 src="https://media2.giphy.com/media/3oriO1ZZCvLseIxbTa/200w.webp?cid=ecf05e4746mt2f00zl2bv62hvx135ae7oaihtvw4sv5cf5t5&rid=200w.webp&ct=g"><br>
  <i>Slide! Slide! Slide!</i>
  </p>
  
