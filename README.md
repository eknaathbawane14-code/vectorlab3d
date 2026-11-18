# VectorLab — Interactive NLP & Word Embeddings Visualizer

An interactive, single-file educational web application that visually explains how machines transform human language into mathematical vectors:

**Tokenization → Vocabulary → Word Embeddings → 3D Embedding Space → Cosine Similarity (Closest Pairs) → Custom Sentence Experiments**

---

## 🌐 Local Website Links

- **Local HTTP Server:** [http://localhost:8080](http://localhost:8080)
- **Direct File Link:** [index.html](file:///Users/eknaath/new/index.html) (`file:///Users/eknaath/new/index.html`)

### Starting the Local Server Manually
If you ever stop the server and want to restart it from `/Users/eknaath/new`:
```bash
python3 -m http.server 8080
```
Then open [http://localhost:8080](http://localhost:8080) in any modern browser. You can also double-click `index.html` directly—no build tools or dependencies are required.

---

## ✨ Features & Learning Modules

1. **Home (`From Words to Vectors`)**
   - Interactive 5-stage animated pipeline: `TEXT → TOKENS → NUMBERS → VECTORS → MEANING`.
   - Live overview metrics for tokenization modes, dynamic vocabulary size, vector dimensions, and cosine similarity.

2. **Tokenization Playground**
   - Compare **Word-level**, **Subword-level (Educational BPE-style approximation)**, and **Character-level** tokenization in real time.
   - Color-coded token blocks by token type (`Word`, `Subword Root`, `Subword Affix`, `Punctuation`, `Number`, `Character`), Token IDs array, token counts, and characters-per-token compression ratio.

3. **Vocabulary Explorer**
   - Pre-loaded with **56 base tokens** (including `"I love AI"` $\rightarrow$ `["I", "love", "AI"]` $\rightarrow$ `[1, 24, 37]`) that automatically expands as you tokenize new words.
   - Interactive **"How Vocabulary Works"** visual mapping diagram, real-time token/ID search, token-type filtering, and sorting.

4. **Word Embeddings Inspector**
   - Explores the relationship `Word → Token ID → Embedding Vector` across 36 curated words (`King`, `Queen`, `Man`, `Woman`, `Apple`, `Orange`, `Car`, `Vehicle`, `Dog`, `Cat`, `Computer`, `Laptop`, etc.).
   - Switch between **3 Dimensions (XYZ)**, **2D Projection (Canvas Scatter Plot)**, and **Full Vector (8D Semantic Feature Breakdown)** with live nearest-neighbor similarity bars.

5. **Interactive 3D Embedding Space**
   - Powered by **Three.js WebGL** with a synchronized 2D HUD label overlay and an automatic offline 3D Canvas projection fallback.
   - Rotate (`Drag`), Zoom (`Scroll` or `+`/`-`), Pan (`Shift + Drag` or `Right-Click Drag`), hover for coordinate tooltips, click spheres to inspect, filter by category (`People`, `Animals`, `Food`, `Technology`, `Transportation`, `Other`), toggle labels/neighbor lines, and search words with smooth camera focus.

6. **Closest Pairs & Cosine Similarity**
   - Explains $\text{Cosine Similarity} = \frac{A \cdot B}{\|A\| \times \|B\|}$ with a live **2D Vector Angle Visualizer** showing $\theta$, $A \cdot B$, $\|A\|$, and $\|B\|$.
   - Includes a searchable/sortable **Closest Word Pairs** table with `"View in 3D"` links and a **5 Closest Neighbors** finder.

7. **Try Your Own Word or Sentence**
   - End-to-end 6-step pipeline analyzer (`Input Text` $\rightarrow$ `Tokenization` $\rightarrow$ `Vocabulary Lookup` $\rightarrow$ `Embeddings` $\rightarrow$ `Similarity` $\rightarrow$ `3D Visualization`).
   - Transparently distinguishes words present in the 36-word demonstration embedding dataset from out-of-dataset tokens without inventing fake semantic vectors.

---

## 🛠️ Tech Stack & 3D Theme Architecture

- **Architecture:** Single-file (`index.html`) with zero build step.
- **3D Spatial Theme & Tactile UI:**
  - **3 Switchable 3D Themes** in the sidebar (`Emerald 3D` Holographic Teal/Gold, `Solaris 3D` Cyber-Magenta/Sky, and `Quantum 3D` Cobalt/Violet).
  - **Interactive 3D Card Tilt & Glare Physics:** Cards respond to cursor position in 3D perspective (`rotateX` / `rotateY`) with a toggleable `3D Tilt: ON/OFF` switch.
  - **3D Tactile Extruded Controls & Token Cubes:** Physical 3D bevels and push-button depth ledges across buttons, token blocks, and isometric pipeline stages.
  - **Ambient 3D Neural Lattice Background:** Full-viewport 3D background constellation with mouse parallax (`#ambient-3d-bg`).
  - **3D Holodeck Bounding Cube & Auto-Orbit:** The 3D Embedding Space includes a 3D wireframe bounding cube and a toggleable `3D Orbit: ON/OFF` mode alongside manual drag rotation, zoom, and pan.
- **3D & 2D Graphics:** Three.js (`r128` via CDN) + HTML5 Canvas 2D/3D projection engine.
