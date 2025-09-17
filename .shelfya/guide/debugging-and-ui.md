# Debug UI Module

## Overview
The Debug UI module provides an interactive user interface for inspecting and manipulating 3D scene properties in real-time within a Three.js application. By integrating lil-gui controls, this module empowers developers and technical artists to rapidly iterate on visual aspects, debug scenes, and tune parameters (like geometry, material, and visibility), all during runtime—without code changes or reloads.

## Key Features
- **Toggleable Debug UI Panel**: Offers an adjustable lil-gui panel that can be shown/hidden with a keyboard shortcut, reducing visual clutter while developing.
- **Live Object Controls**: Enables real-time manipulation of object position, visibility, material wireframe mode, color, and geometry subdivision directly from the UI.
- **Animation Triggering**: Provides interface buttons to trigger predefined object behaviors (e.g., spinning the cube).
- **Geometry Update**: Supports changing mesh subdivisions interactively, allowing live updates to object geometry for performance or quality testing.
- **Responsive Handling**: Listens to window resize events to update camera and renderer, maintaining correct aspect ratio and rendering precision.
- **Seamless Orbit Controls**: Integrates Three.js OrbitControls for intuitive camera movement and scene exploration, alongside debug controls.

## System Errors
It's important to document common errors and troubleshooting specify :
- **Canvas Not Found**: If `.webgl` canvas is missing in the HTML, the 3D scene and debug UI will not be initialized.  
  *Resolution*: Ensure a `<canvas class="webgl"></canvas>` is present in your HTML.
- **GUI Not Visible**: If the debug UI is not showing, it may be in hidden mode.  
  *Resolution*: Press **'h'** to toggle the visibility of the debug UI.
- **Mesh Geometry Issues**: Changing subdivision could produce a blank or deformed mesh if the operation is interrupted or invalid number is provided.  
  *Resolution*: Use only positive integer subdivisions within the supported range (1–20).

## Usage Examples
Practical code examples showing how to use the module:

```js
// Ensure HTML has: <canvas class="webgl"></canvas>
import './script.js' // Debug UI script sets up scene and controls

// Toggle Debug UI with the 'h' key
// Adjust cube elevation, color, visibility via the 'Nice debug UI' panel

// Programmatically trigger a spin:
const gui = /* obtain reference if you modify the script */;
gui.show()
const debugObject = /* obtain reference if you modify the script */;
debugObject.spin() // Spins the cube via GSAP tween
```

## System Integration

```mermaid
flowchart LR
  dependencies["Three.js<br>lil-gui<br>gsap<br>OrbitControls<br>Browser DOM"]
    --> thisModule["Debug UI Module"]
    --> details["- Expects '<canvas class=\"webgl\">'<br>- Imports external libraries"]
  thisModule --> process["- Manages 3D scene and camera<br>- Displays debug controls"]
  thisModule --> usedBy["App Developers/Technical Artists"]
  usedBy --> consumers["- Use runtime UI for live tuning<br>- Debug rendering and scene properties"]
```
