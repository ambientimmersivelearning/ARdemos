---
layout: default
---

# Welcome to Ambient Immersive Learning

Documentation for an EE296 and EE 496 project focusing on the implementation of an immersive learning solution based on Augmented Reality and QR codes.

Augmented Reality (AR) refers to technology that overlays information or virtual objects on real-world scenes in real-time.  Education is a major field that is currently being affected by AR.  AR can introduce new methods of teaching, change the location and timing of studying, and make the learning process more engaging.  Smartphones are the ideal platform for AR in education due to portability, size, and availability.  Our team is interested in exploring ways to create a more immersive and engaging learning experience using smartphone AR technology.

# A-Frame Examples

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