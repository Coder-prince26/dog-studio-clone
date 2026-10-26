# Dog Studio Clone

An interactive 3D website inspired by [Dog Studio](https://dogstudio.co/), built with React, Three.js and GSAP. An animated 3D dog stays fixed in the center of the screen and reacts to scrolling and to hovering over project titles, with smooth shader-based material transitions.

**Live Demo:** _add your deployed link here_

## Features

- **Animated 3D model:** a Draco-compressed `.glb` dog model with its built-in animation playing in a loop
- **Full-screen fixed 3D canvas:** the dog stays on screen while the page sections scroll over it
- **Scroll-driven animation:** GSAP ScrollTrigger moves and rotates the dog from the first section to the third, while the third section's heading and text scale in sync
- **Hover material transitions:** hovering over a project title smoothly blends the dog's matcap material to a new look using a custom shader (`onBeforeCompile`), and leaving the list resets it
- **Matcap materials:** 20 matcap textures plus a normal map give the model a stylized look without complex lighting
- **Fast tooling:** built with Vite for instant dev server start and quick builds

## Page Sections

1. **Hero:** navigation bar with the Dogstudio logo (inline SVG) and the headline "We Make Good Shit"
2. **Projects:** a list of 7 project titles (Tomorrowland, Navy Pier, MSI Chicago, This Was Louises Phone, KIKK Festival 2018, The Kennedy Center, Royal Opera Of Wallonia). Hovering each one changes the dog's look
3. **About:** "We Build Digital Stories" with short text about the studio, animated on scroll

## Tech Stack

- [React](https://react.dev/): UI library
- [Vite](https://vitejs.dev/): build tool and dev server
- [Three.js](https://threejs.org/): 3D rendering
- [@react-three/fiber](https://docs.pmnd.rs/react-three-fiber): React renderer for Three.js
- [@react-three/drei](https://github.com/pmndrs/drei): helpers (`useGLTF`, `useTexture`, `useAnimations`)
- [GSAP](https://gsap.com/) with `@gsap/react` and `ScrollTrigger`: animations and scroll effects

## Getting Started

### Prerequisites

- [Node.js](https://nodejs.org/) (v18 or higher)
- npm (comes with Node.js)

### Installation

```bash
# Clone the repository
git clone https://github.com/<your-username>/dog-studio-clone.git

# Go to the project folder
cd dog-studio-clone

# Install dependencies
npm install
```

### Run Locally

```bash
npm run dev
```

Open [http://localhost:5173](http://localhost:5173) in your browser.

### Build for Production

```bash
npm run build
```

The production files are generated in the `dist` folder. To preview the build locally:

```bash
npm run preview
```

## Project Structure

```
app/
├── public/
│   ├── models/              # 3D model (dog.drc.glb)
│   ├── matcap/              # Matcap textures (mat-1.png to mat-20.png)
│   ├── dog_normals.jpg      # Normal map for the dog
│   ├── branches_diffuse.jpg # Texture for the branches
│   └── *.png                # Project images (tomorrowland, kikk, etc.)
├── src/
│   ├── components/
│   │   └── Dog.jsx          # 3D dog (model, materials, shader, GSAP animations)
│   ├── App.jsx              # Page layout, sections and canvas
│   ├── App.css              # Styles
│   └── main.jsx             # React entry point
├── index.html               # HTML entry point
├── vite.config.js           # Vite configuration
└── package.json
```

## How It Works

1. `App.jsx` renders a fixed full-screen `Canvas` containing the `Dog` component, with the three page sections scrolling above it.
2. `Dog.jsx` loads the model with `useGLTF` and plays its animation using `useAnimations`.
3. The dog uses a matcap material with a custom shader that blends between two matcap textures, and the branches use a separate textured matcap material.
4. On scroll, a GSAP timeline linked to `ScrollTrigger` changes the dog's position and rotation between the first and third sections.
5. On hovering a project title, the shader blends from the current matcap texture to a new one, so the dog's look changes smoothly.

## Deployment

This project can be deployed on [Vercel](https://vercel.com) or [Netlify](https://netlify.com):

- **Build command:** `npm run build`
- **Output directory:** `dist`

## Credits

This is a learning project created to practice 3D web development with React Three Fiber and GSAP. The design and concept are inspired by [Dog Studio](https://dogstudio.co/). All rights to the original design, logo and project images belong to their respective owners.

## Author

Made by **<Prince-Singh>**

- GitHub: [@Coder-prince26](https://github.com/<Coder-prince26>)