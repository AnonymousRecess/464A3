****************
* Simple Modeling
* CS 464
* 10th Oct, 2021
* Jeff Kahn
**************** 

# PROJECT OVERVIEW:

In this WebGL assignment, the goal was to create a textured height map with simple ambient and directional lighting calculated from normals.
Functionality for scaling and rotating the image was also required.


## INCLUDED FILES:

* README.md - This file
* box.png - Texture loaded for the terrain generation
* example1.png - Example of site with model slightly titled
* example2.png - Example of site with model viewed from above and zoomed out a bit
* A2 Modeling.html - Javascript code that initializes shaders, calculates vectors and implements other required functionality before drawing the scene
* Utilities
  * glMatrix_utils.js - Javascript matrix utilities
  * webgl-utils.js - Javascript WebGl utilities

## How to Use:
When interacting with the rendered image, the left click can be held in order to rotate the image with the movement of the mouse. Scaling in regard
to vertical mouse movement is also possible when holding the right mouse button down.


## PROJECT DESIGN NOTES:
_The overall strategy used for this assignment was to implement each feature one at a time, beginning with the Grid, until finishing with the lighting._

### Grid Geometry:
Implementation of the grid geometry was the first element that I tackled. Given that I began here, the first struggle was understanding the given skeleton code.
Since the skeleton code was pseudocode, I initially had to determine what syntax was necessary to change to prevent compiler errors.

Initially, debugging proved difficult in my chosen IDE of IntelliJ, as the grid did not appear on the live-preview of the html. However, the in-built
debugger for IntelliJ, upon specifically requesting debugging, output more specific information that helped with debugging. For example, the format for
vector color assignment given by the pseudo-code was incorrect and the debugger helped with the diagnosis of this.


### User Interaction:
Again, useful skeleton code was provided that made implementing this feature fairly straightforward. One of the mistakes I initially made, was using the 
'Mouse Rotate Y' Code Example instead of the 'Trackball' example. This lead to a lot of confusion over variables such as gAngle. However, after the lecture
clarified this mistake, I was able to make sense of the 'trackball' code and implement it without much issue. I decided to use the mouse handler event
'which' functionality to distinguish between mouse button clicks. The only other struggle was finding out which values to scale the scale matrix by, which
was mainly trial and error


### Add simple WebGL lights - direction and ambient:
This feature, as expected, was the most difficult to implement. Understanding how to initialize the shader to properly deal with lighting, then 
assigning the properties of the light in the draw scene function took looking up examples online to understand. The changes to the texture and lighting that I
made compared to the class example was minimal in an effort to more easily determine if the functionality was correct. While vec4's could have been used for the lighting,
I saw more examples using vec3 to denote lighting as the alpha value didn't seem necessary for most applications of vector colors.

## RESOURCES USED:

* [WebGL Lighting Example] https://developer.mozilla.org/en-US/docs/Web/API/WebGL_API/Tutorial/Lighting_in_WebGL
* [A2 Provided Skeleton Code] http://cs.boisestate.edu/~scutchin/cs464/codesnips/a2skeleton.html
* [Mouse balll handler] http://cs.boisestate.edu/~scutchin/cs464/codesnips/mouse_ball.html
* [MouseEvent Object Properties and Methods] https://www.w3schools.com/jsref/obj_mouseevent.asp
* [Jackson Edwards] - Student in this class that I talked about how to implement features with such as the mouse interaction