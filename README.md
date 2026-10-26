<div align="center">

# 🐶 Dog Studio Clone

### An interactive 3D website where an animated dog reacts to your scroll and hover

A creative-studio style landing page inspired by [Dogstudio](https://dogstudio.co/), built with **React**, **Three.js** and **GSAP**.

<br />

[![Live Demo](https://img.shields.io/badge/🚀_Live_Demo-Visit_Site-000000?style=for-the-badge&logo=vercel&logoColor=white)](https://dog-studio-clone-pied.vercel.app/)
[![GitHub Repo](https://img.shields.io/badge/GitHub-Source_Code-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/Coder-prince26/dog-studio-clone)

<br />

![React](https://img.shields.io/badge/React-20232A?style=flat-square&logo=react&logoColor=61DAFB)
![Vite](https://img.shields.io/badge/Vite-646CFF?style=flat-square&logo=vite&logoColor=white)
![Three.js](https://img.shields.io/badge/Three.js-000000?style=flat-square&logo=threedotjs&logoColor=white)
![GSAP](https://img.shields.io/badge/GSAP-88CE02?style=flat-square&logo=greensock&logoColor=black)
![WebGL](https://img.shields.io/badge/WebGL-990000?style=flat-square&logo=webgl&logoColor=white)
![Vercel](https://img.shields.io/badge/Vercel-000000?style=flat-square&logo=vercel&logoColor=white)

</div>

<br />

---

## ✨ Highlights

| | Feature | Description |
|---|---|---|
| 🐕 | **Animated 3D model** | A Draco-compressed `.glb` dog with its built-in animation looping in real time |
| 📜 | **Scroll-driven motion** | GSAP ScrollTrigger moves and rotates the dog as you scroll, while text scales in sync |
| 🎨 | **Hover material transitions** | Hover over a project title and the dog smoothly blends to a new look using a custom shader |
| 🖼️ | **Matcap styling** | 20 matcap textures and a normal map give a stylized look without heavy lighting |
| 🖥️ | **Fixed full-screen canvas** | The 3D scene stays on screen while the page sections scroll over it |
| ⚡ | **Fast tooling** | Powered by Vite for instant dev start and quick production builds |

---

## 📄 Page Sections

1. **Hero:** navigation bar with the Dogstudio logo (inline SVG) and the headline *"We Make Good Shit"*
2. **Projects:** 7 project titles (Tomorrowland, Navy Pier, MSI Chicago, This Was Louises Phone, KIKK Festival 2018, The Kennedy Center, Royal Opera Of Wallonia). Each hover changes the dog's look
3. **About:** *"We Build Digital Stories"* with short studio text, animated on scroll

---

## 🛠️ Tech Stack

| Category | Technology |
|---|---|
| UI | [React](https://react.dev/) |
| Build tool | [Vite](https://vitejs.dev/) |
| 3D rendering | [Three.js](https://threejs.org/), [@react-three/fiber](https://docs.pmnd.rs/react-three-fiber) |
| 3D helpers | [@react-three/drei](https://github.com/pmndrs/drei) (`useGLTF`, `useTexture`, `useAnimations`) |
| Animation | [GSAP](https://gsap.com/), `@gsap/react`, `ScrollTrigger` |
| Deployment | [Vercel](https://vercel.com/) |

---

## ⚙️ How It Works

```
App.jsx ──► fixed full-screen <Canvas> ──► <Dog /> component
                                              │
        ┌─────────────────────────────────────┼─────────────────────────────┐
        ▼                                     ▼                             ▼
  useGLTF + useAnimations            Matcap material with           GSAP ScrollTrigger
  load model, play animation         custom shader (two textures    timeline moves and rotates
                                     blended by a progress value)   the dog while scrolling
```

1. `App.jsx` renders a fixed full-screen `Canvas` with the `Dog` component, and the three sections scroll above it.
2. `Dog.jsx` loads the model with `useGLTF` and plays its animation using `useAnimations`.
3. The dog uses a matcap material patched with `onBeforeCompile`, so a shader can blend between two matcap textures.
4. A GSAP timeline linked to `ScrollTrigger` changes the dog's position and rotation between the first and third sections.
5. Hovering a project title animates the shader's progress value, so the dog's look changes smoothly instead of snapping.

---

## 🚀 Getting Started

### Prerequisites

- [Node.js](https://nodejs.org/) v18 or higher
- npm (comes with Node.js)

### Installation

```bash
# Clone the repository
git clone https://github.com/Coder-prince26/dog-studio-clone.git

# Go to the project folder
cd dog-studio-clone

# Install dependencies
npm install

# Start the development server
npm run dev
```

Open [http://localhost:5173](http://localhost:5173) in your browser.

### Available Scripts

| Command | What it does |
|---|---|
| `npm run dev` | Starts the development server |
| `npm run build` | Creates a production build in the `dist` folder |
| `npm run preview` | Previews the production build locally |

---

## 📁 Project Structure

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

---

## 🎯 Concepts Practiced

- Rendering 3D scenes in React with React Three Fiber
- Loading and animating compressed GLTF models
- Writing custom shader logic with `onBeforeCompile`
- Scroll-linked animations using GSAP timelines and `ScrollTrigger`
- Connecting DOM interactions (hover) to a 3D scene
- Deploying a Vite app to Vercel with GitHub auto-deploys

---

## 🌐 Deployment

The site is deployed on **Vercel**, and every push to `main` triggers a new deployment automatically.

| Setting | Value |
|---|---|
| Framework preset | Vite |
| Build command | `npm run build` |
| Output directory | `dist` |

---

## 🙌 Credits

This is a learning project created to practice 3D web development. The design and concept are inspired by [Dogstudio](https://dogstudio.co/). All rights to the original design, logo and project images belong to their respective owners.

---

<div align="center">

### ⭐ If you liked this project, consider giving it a star!

Made with ❤️ by [Coder-prince26](https://github.com/Coder-prince26)

</div>