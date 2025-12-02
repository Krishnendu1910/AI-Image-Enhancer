

# 🌟 **AI Image Enhancer — Super Resolution & Image Quality Booster**

Elevate your images with AI-powered enhancement. This project improves image quality using a high-performance external enhancement API integrated with a modern React + Vite frontend. Drag, drop, enhance — all in seconds.

---

## 🚀 **Live Demo**

https://ai-image-enhancer-pi-eight.vercel.app/

---

## 🧠 **What This Project Does**

This application allows users to upload an image and instantly enhance it using an AI image-enhancement API.
It:
✔ Increases resolution
✔ Sharpens details
✔ Enhances color & clarity
✔ Works with JPG/PNG/WebP
✔ Gives real-time preview + output download

All inside a clean, fast UI built using **React + Vite**.

---

# 🏗️ **Tech Stack**

### **Frontend**

* ⚛️ **React.js** — component-based UI
* ⚡ **Vite** — fast dev server & build tool
* 🎨 **CSS** — custom styling
* 📜 **JavaScript (ES6+)**

### **Backend**

* ❌ **No internal backend**
* ✔ Uses **external AI Image Enhancement API** (from `src/utils/enhanceImageApi.js`)

### **Build Tools**

* **Node.js**
* **npm**

---

# 📁 Folder Structure

```
AI-Image-Enhancer/
│
├── index.html
├── package.json
├── vite.config.js
├── src/
│   ├── App.jsx
│   ├── main.jsx
│   ├── index.css
│   │
│   ├── components/
│   │   ├── Home.jsx
│   │   ├── ImageUpload.jsx
│   │   ├── ImagePreview.jsx
│   │   └── Loading.jsx
│   │
│   └── utils/
│       └── enhanceImageApi.js
│
└── public/
```

---

# ⚙️ **How It Works (Architecture)**

### **Step-by-step Flow**

1. **User uploads an image** in the UI
2. `ImageUpload.jsx` reads & displays preview
3. API call is triggered (`enhanceImageApi.js`)
4. External AI model processes the image
5. Enhanced image is returned
6. `ImagePreview.jsx` displays before/after
7. User can **download** the improved image

---

# 🎯 Features

### 🖼️ **Drag & Drop Uploads**

Upload any JPG, PNG, or WebP file.

### ⚡ **AI Super-Resolution**

Sharpens quality using advanced ML algorithms.

### 🔄 **Before/After Preview**

See transformation instantly.

### ⏳ **Loading UI**

Beautiful loader using `Loading.jsx`.

### 📥 **One-click Download**

Download the enhanced image instantly.

### 📱 **Fully Responsive**

Works on all mobile & desktop screens.

---

# 🛠️ Installation & Setup

### **1️⃣ Clone the repo**

```bash
git clone https://github.com/your-username/AI-Image-Enhancer.git
cd AI-Image-Enhancer
```

### **2️⃣ Install dependencies**

```bash
npm install
```

### **3️⃣ Run dev server**

```bash
npm run dev
```

### **4️⃣ Build for production**

```bash
npm run build
```

---

# 🔑 Configure Your API (Important)

Open:

```
src/utils/enhanceImageApi.js
```

Replace API URL / API Key with your own:

```js
const API_URL = "https://your-enhance-api.com/enhance";
const API_KEY = "your-key";
```

This connects your frontend to the actual AI enhancement engine.

---

# 🤖 Future Improvements

* Add multiple enhancement modes (HDR, Sharpness, Face Cleanup)
* Add real-time slider for comparison
* Build a self-hosted backend model
* Add user authentication & cloud storage

---


