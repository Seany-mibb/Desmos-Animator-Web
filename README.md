# Desmos Image Tracer

#### 🎥 Demo: <URL HERE>

## 📖 Description
**Desmos Image Tracer** is a Flask web app that converts a single uploaded image into **Desmos parametric equations** and displays them inside an embedded [Desmos Graphing Calculator](https://www.desmos.com/calculator).  

It works by:
1. Converting the image to edges with **OpenCV**.
2. Vectorizing the edges into **SVG paths** using **Potrace**.
3. Translating the SVG paths into **parametric equations**.
4. Rendering the equations in **Desmos**, inside a browser.

This lets you turn any image into math-based art without touching the Desmos editor manually.

---

## ⚡ Features
- Upload an image → instantly see it drawn in Desmos.
- Adjustable **quality levels** (low → super high).
- Choose output **color** (or randomize it).
- Automatic cleanup of old uploads for efficiency.

---

---

## ⚠️ Limitations
The main bottleneck in this project is **Desmos itself**.  

While the app can generate tens of thousands of equations from an image, the Desmos Graphing Calculator becomes **slow when rendering too many parametric curves at once**.  

- Higher quality settings (`High` or `Super High`) can produce extremely detailed outputs, but you’ll notice:
  - Slower loading times
  - Lag when panning/zooming
  - Gradual rendering instead of instant display

This isn’t a limitation of the conversion process — it’s simply because Desmos isn’t optimized for such large datasets.  

## 🛠️ Installation
Clone the repo and install dependencies:

```bash
git clone https://github.com/<your-username>/desmos-image-tracer.git
cd desmos-image-tracer
pip install -r requirements.txt
