# Getting Started

## Overview
This module provides a ready-to-use starter template for rapidly building interactive 3D web applications with [Three.js](https://threejs.org/) using the modern Vite development environment. It handles project bootstrapping, development server management, and streamlined production builds, allowing developers to focus on 3D rendering and application logic.

## Key Features
- **Vite-Powered Development Server**: Quickly start a local server on `localhost:8080` with hot module reloading for instantaneous feedback during development.
- **Production Build Output**: Seamlessly produce optimized output assets in the `dist/` directory for deployment.
- **Three.js Integration**: Ships with Three.js as a dependency, enabling advanced 3D rendering out-of-the-box.
- **HTML & Canvas Boilerplate**: Includes a starter HTML file with a canvas and script pre-wired for immediate 3D rendering.
- **Static Asset Management**: Supports serving static files from a dedicated public directory.
- **Cross-Platform Accessibility**: Vite server is exposed to your local network for convenient device testing.

## System Errors
- **Missing Dependencies**:  
  Occurs if dependencies are not installed before running scripts.  
  _Resolution_: Run `npm install` before any other commands.
- **Port In Use/Error Starting Dev Server**:  
  Attempts to launch on a port already in use, or failed server initialization.  
  _Resolution_: Stop conflicting processes or change the default port in the Vite config.
- **Build Directory Permissions**:  
  Errors writing to the `dist/` directory (usually due to file permissions).  
  _Resolution_: Ensure correct permissions or remove any locks on the directory.
- **Static Asset Not Found**:  
  When referencing files that aren't in the static directory.  
  _Resolution_: Place all necessary assets in the designated static directory (`static/`).

## Usage Examples

```bash
# 1. Install Node.js if not already present
# 2. Install dependencies
npm install

# 3. Start the development server (open at http://localhost:8080)
npm run dev

# 4. Build for production (output in dist/)
npm run build
```

**Project Structure:**
```
Starter/
  ├── src/
  │   ├── index.html        # HTML template with <canvas>
  │   ├── script.js         # Entry point for Three.js logic (create/edit)
  │   └── style.css         # (Optional) Custom styles
  ├── static/               # Place static assets here (served at runtime)
  ├── dist/                 # Built files (auto-generated)
  ├── package.json
  └── vite.config.js
```

**Editing the 3D Scene:**
- Update `src/script.js` to add your Three.js code (scene, camera, objects, etc.).
- The `<canvas class="webgl"></canvas>` element in `index.html` is used as the Three.js rendering surface.

## System Integration

```mermaid
flowchart LR
  node[Node.js]
  vite[Vite]
  threejs[Three.js]
  devDeps["package.json (vite, scripts)"]
  html["index.html (Canvas, Script Link)"]
  static[Static Directory]
  script[script.js]
  devServer["Vite Dev Server"]
  dist[dist/ (Build Output)]
  browser[Browser/Consumer]

  node --> vite
  vite --> devServer
  devDeps --> devServer
  threejs --> script
  html --> devServer
  static --> devServer
  devServer --> browser
  browser --> html
  script --> html
  devServer --> dist
```
