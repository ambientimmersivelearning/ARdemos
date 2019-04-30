---
layout: default
---

# Welcome to Ambient Immersive Learning

Documentation for an EE296 and EE 496 project focusing on the implementation of an immersive learning solution based on Augmented Reality and QR codes.

Augmented Reality (AR) refers to technology that overlays information or virtual objects on real-world scenes in real-time.  Education is a major field that is currently being affected by AR.  AR can introduce new methods of teaching, change the location and timing of studying, and make the learning process more engaging.  Smartphones are the ideal platform for AR in education due to portability, size, and availability.  Our team is interested in exploring ways to create a more immersive and engaging learning experience using smartphone AR technology.

# Examples

## Introductory Examples and Setting Up The Environment
The following examples were completed to get accustomed to using AR.js, A-Frame, and the environment.  These examples taught us how to use the special html tags, ordering, and components of each tag.  These examples proved to be useful exercises for team members who were not so familiar with html.

### 1. Basic Cube
A basic example using A-Frame and AR.js to render a red box directly on the Hiro marker.  The box is rendered with the code:

```html
 <a-box position='0 0.5 0' material='opacity: 0.5; side:double; color:red;'> </a-box>
```
where position indicates the x, y, z components of the cube.  The "side: double" variable also tells A-Frame to render more than one face.  This gives the 3-D effect in the cube. 

  *  Webpage: [Basic Cube Example](./aframe/examples/basic.html)
  *  [Source Code](https://github.com/ambientimmersivelearning/ARdemos/blob/master/aframe/examples/basic.html)
  <p align="center">
  <img src="./images/QR-basic.png" alt="QR-basic" height="400" width="400"/>
  </p>
  
### 2. Basic Sphere
Another example to render a green sphere slightly away from the Hiro marker. We call the html tag `a-sphere` and changed `position='0 2 0'` so that the sphere hovers 2 units in the y axis above the marker.  If we edit the x or z axis, the sphere will appear off center of the marker.

  *  Webpage: [Basic Sphere Example](./aframe/examples/sphere.html)
  *  [Source Code](https://github.com/ambientimmersivelearning/ARdemos/blob/master/aframe/examples/sphere.html)
   <p align="center">
  <img src="./images/QR-sphere.png" alt="QR-sphere" height="400" width="400"/>
</p>

### 3. Basic Scene
This example sets up a basic scene using multiple objects, a plane, and text.  A cylinder, cone, and octahedron are layered within each other, and hover above a plane.  The text "Hello World!" is shown in front of the these objects.  Each object is rendered using an A-Frame html tag such as `a-cylinder`, `a-cone`, or `a-octahedron`.  The text is rendered using `a-text`.  This example is helpful in moving towards more complicated scenes.

We also see how layered objects interact with one another with different opacity.  The cylinder and cone show graininess at points of intersection.

  *  Webpage: [Basic Scene Example](./aframe/examples/scene.html)
  *  [Source Code](https://github.com/ambientimmersivelearning/ARdemos/blob/master/aframe/examples/scene.html)
   <p align="center">
  <img src="./images/QR-scene.png" alt="QR-scene" height="400" width="400"/>
</p>

## Testing Interactivity
These next few examples are building and understanding the limits of interactivity for mobile browser AR.  Our main goals were to explore tapping, scaling, dragging, and animation.

### 1. Tapping (MouseClick)
Our team realized that any object interactivity would require JavaScript scripts to handle mouse events.  We did some research and found that A-Frame has it's own cursor feature that became available in v0.6.1 by setting `<a-scene cursor="rayOrigin: mouse">`.  Unfortunately according to the API there are no `hovering`/`hovered` or `mouseenter`/`mouseexit` states for mobile.  This vastly limits how the user can interact with the object on a smartphone.  Our team will have to think more creatively about interactivity when coming up with the larger demo.

In this example we anchored a purple box at a 30 degree angle to the marker.  Using `<a-animation>` we included two different animations when the box is tapped, it will spin and change color.  The `fill` component in animation determines the effect of animation when not actively in plan.  We ran into problems with the color animation but realized we needed to change `fill = backwards` to `fill = forwards` so that after the animation the color would not immediately get set to NULL.  

The following code defines the mouse cursor.  Fuse is set to `false` for mobile.
```html
  <a-entity position='0 0.1 4'>
    <a-entity camera look-controls mouse-cursor>
      <a-cursor fuse='false' opacity = '0'></a-cursor>
    </a-entity>
  </a-entity>
```

  *  Webpage: [Tapping Example](./aframe/examples/tapping.html)
  *  [Source Code](https://github.com/ambientimmersivelearning/ARdemos/blob/tapping-optimization/aframe/examples/tapping.html)
   <p align="center">
  <img src="./images/QR-tapping.png" alt="QR-tapping" height="400" width="400"/>
</p>
