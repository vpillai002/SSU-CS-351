# Project 3: Procedural WebGL Shapes

This project builds a sequence of WebGL programs that procedurally generate geometry and shaders.

## Table of Contents

- [Wireframe Triangle](triangle.html)
- [Filled 10-Sided Polygon](decagon.html)
- [Five-Pointed Star](star.html)
- [Rotating Five-Pointed Star](star-rotating.html)
- [Rotating Star with Interpolated Color (Extra Credit)](star-rotating-color.html)

## Version Notes

### 1) Wireframe Triangle (`triangle.html`)
- Uses `gl.LINE_LOOP` with three procedurally generated vertices in the vertex shader.
- Fragment shader outputs a flat white color.

### 2) Filled 10-Sided Polygon (`decagon.html`)
- Switches to `gl.TRIANGLE_FAN`.
- Uses uniform `N` to control vertex count and angle spacing.
- Generates center vertex plus 10 perimeter segments (12 total vertices).

### 3) Five-Pointed Star (`star.html`)
- Keeps triangle fan geometry.
- Alternates radius by `gl_VertexID` parity to create star points.
- Keeps vertex 0 fixed at the origin as the shared fan center.

### 4) Rotating Star (`star-rotating.html`)
- Adds uniform `t` and updates it each frame.
- Adds `t` into angular computation so the star rotates continuously.

### 5) Rotating Star with Color (`star-rotating-color.html`)
- Exports `radius` from vertex shader to fragment shader.
- Uses interpolated `radius` in fragment shader to mix between cyan and gold.
- Produces a rotating star with radial color variation.

## How To Run

1. Open any HTML file directly in a WebGL2-capable browser.
2. Or run a local server from this directory:

```bash
python -m http.server
```

Then open `http://localhost:8000/` and select one of the HTML files.
