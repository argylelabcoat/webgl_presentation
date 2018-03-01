# WebGL

### Subtitle

---

## Key Goals:

* Basic understanding of what WebGL is
* Basic knowledge of how *things* get drawn
* We'll draw in WebGL using a Vertex Buffer
* Learn a little bit about matrices and how they relate
* Possibly someone will make something move in 3D

---

## What is WebGL?

* Can draw 2D and 3D shapes
* Integrates with `<canvas/>`
* GPU Accelerated
* Based on OpenGL ES (mobile)
* Works in Modern/Current Browsers

---

## WebGL basics: GPU?

* Composition
   * Lists of things we want displayed
   * Hardware sorting and ordering these
* Rasterization
   * Understood shapes become pixels
   * Triangles, Bitmaps
* Programmable
   * "Shaders"
   * GPGPU ;)

---

## WebGL basics: Triangles

* Triangles create shapes
* Easy to rasterize
* Rasterize: "Draw"
![triangle rasterization][tri-raster]

---

## WebGL basics: Polygon Soup

* List of Polygons
* Typically list(s) of Vertices
  * 3 vertices = 1 triangle
* Vertex Format
  * Position
  * Color
  * Texture Coordinates (2D)
  * Normal
  * Tangent
  * Binormal/bitangent 
    * cross product of normal/tangent

---

### FIDDLE
[JS-Fiddle]

---

### Vectors

 * For us, essentially a collection of associated numbers
 * But, yes, usually a mathematical vector (direction with magnitude)
 * Sometimes people use vectors to store related values
 
 X | Y | Z | (W)===1

---

### Matrices:

 * Projection (perspective)
 * Model (object position, orientation, scale)
   * essentially a Transform or SRT Matrix
 * View (world/camera)

---

### Matrix Math!

 * Matrix concatenation
   * Order Matters!
   * transform = S * R * T
 * glMatrix is helpful
   * [glMatrix]
   * Typed out in Row Major
   * Documentation for Graphics often Column Major
 * Rotation from Euler Angles...
   * Bad! Gimbal-Lock
   * But, that's how I'll show you

--- 

### Matrix Composition

 Identity

 1 | 0 | 0 | 0 
 0 | 1 | 0 | 0
 0 | 0 | 1 | 0
 0 | 0 | 0 | 1

--- 

### Matrix Composition

 Scaling

 X | 0 | 0 | 0 
 0 | Y | 0 | 0
 0 | 0 | Z | 0
 0 | 0 | 0 | 1

 --- 

### Matrix Composition

 Translation

 1 | 0 | 0 | X 
 0 | 1 | 0 | Y
 0 | 0 | 1 | Z
 0 | 0 | 0 | 1

 --- 

### Matrix Composition

 Rotation X

 1 | 0 | 0 | 0 
 0 | cos | -sin | 0
 0 | sin | cos | 0
 0 | 0 | 0 | 1

  --- 

### Matrix Composition

 Rotation Y

 cos | 0 | sin | 0 
 0 | 0 | 0 | 0
 -sin | 0 | cos | 0
 0 | 0 | 0 | 1

   --- 

### Matrix Composition

 Rotation Z

 cos | -sin | 0 | 0 
 sin | cos | 0 | 0
 0 | 0 | 0 | 0
 0 | 0 | 0 | 1

---
[tri-raster]: images/Voxelization_blog_fig_9.png
[JS-Fiddle]: https://jsfiddle.net/argylelabcoat/xd70q5fr/16/
[glMatrix]: http://glmatrix.net/