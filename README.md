<!-- ═════════════════════ HERO ═════════════════════ -->
<div align="center">

<img src="https://img.shields.io/badge/AI-IMAGE%20ENHANCER-6D28D9?style=for-the-badge&labelColor=111827" alt="AI Image Enhancer" />

# ✨ AI Image Enhancer

### Give your images a sharper, higher-resolution look.

A React-powered interface for uploading an image, requesting AI image scaling through an external API, and previewing the original and returned result.

<br />

<a href="https://ai-image-enhancer-pi-eight.vercel.app/">
  <img src="https://img.shields.io/badge/🚀%20TRY%20THE%20LIVE%20DEMO-Open%20App-6D28D9?style=for-the-badge" alt="Open live demo" />
</a>

<br /><br />

<img src="https://img.shields.io/badge/React-19-61DAFB?style=flat-square&logo=react&logoColor=black" alt="React" />
<img src="https://img.shields.io/badge/Vite-6-646CFF?style=flat-square&logo=vite&logoColor=white" alt="Vite" />
<img src="https://img.shields.io/badge/Tailwind%20CSS-4-06B6D4?style=flat-square&logo=tailwindcss&logoColor=white" alt="Tailwind CSS" />
<img src="https://img.shields.io/badge/Axios-HTTP%20Requests-5A29E4?style=flat-square&logo=axios&logoColor=white" alt="Axios" />
<img src="https://img.shields.io/badge/Hosted%20on-Vercel-black?style=flat-square&logo=vercel&logoColor=white" alt="Vercel" />

</div>

---

## 🖼️ The Idea

**AI Image Enhancer** is a web application built with **React and Vite**. A user selects an image, the application sends it to an external image-scaling API, and the interface presents the original image alongside the result returned by the service.

The project separates the page, upload control, image preview, loading indicator, and API communication into small React components.

> **How enhancement works:** The repository calls an external API; it does not include or host its own AI model or backend.

## ⚡ How It Works

<div align="center">

| 01 · SELECT | 02 · ENHANCE | 03 · REVIEW |
|:---:|:---:|:---:|
| 🗂️ Choose an image | 🤖 Upload and poll the API task | 🔍 View the original and API result |

</div>

1. Select an image using the upload control.
2. The browser creates a local preview for the selected file.
3. The API utility uploads the image to the external scaling service.
4. The application checks task status until a result is available or the retry limit is reached.
5. The preview component displays the original image and the returned enhanced-image URL.

## 💎 Current Features

- 🗂️ **Image selection** through a dedicated upload component.
- 🖼️ **Original-image preview** using a browser-created object URL.
- 🤖 **External image scaling** through the API integration in `src/utils/enhanceImageApi.js`.
- ⏳ **Loading indicator** while an enhancement request is processing.
- 🔄 **Task-status polling** with a configured retry limit.
- 🧩 **Component-based architecture** for the upload control, preview areas, and loading UI.
- ⚡ **Vite dev server and production build** for quick development.
- 🎨 **Tailwind CSS styling** integrated through the Vite plugin.

*This list describes the current code, not planned features.*

## 🧰 Technology Stack

| Tool | What it does |
|:--|:--|
| ⚛️ **React 19** | UI components and state |
| ⚡ **Vite 6** | Development server and production build |
| 🎨 **Tailwind CSS 4** | Utility-first styling |
| 📡 **Axios** | HTTP requests to the enhancement service |
| 🟨 **JavaScript / JSX** | Application and component logic |
| 🧹 **ESLint** | Code linting |
| ▲ **Vercel** | Live demo hosting |

## 🗺️ Project Structure

```text
AI-Image-Enhancer/
├── index.html
├── package.json
├── package-lock.json
├── vite.config.js
├── eslint.config.js
└── src/
    ├── main.jsx
    ├── App.jsx
    ├── index.css
    ├── components/
    │   ├── Home.jsx
    │   ├── ImageUpload.jsx
    │   ├── ImagePreview.jsx
    │   └── Loading.jsx
    └── utils/
        └── enhanceImageApi.js
```

| File | Responsibility |
|:--|:--|
| `src/App.jsx` | Main heading and page layout |
| `src/components/Home.jsx` | Selected-image state, loading state, and enhancement request |
| `src/components/ImageUpload.jsx` | Image file input and upload callback |
| `src/components/ImagePreview.jsx` | Original and result preview areas |
| `src/components/Loading.jsx` | Processing indicator |
| `src/utils/enhanceImageApi.js` | Uploads the file, polls the task, and retrieves API data |
| `vite.config.js` | Vite, React, and Tailwind CSS plugin configuration |

## 🚀 Get Started

### Prerequisites

- [Node.js](https://nodejs.org/) with npm
- Internet access for the external API and other remotely loaded resources
- A valid API configuration for the enhancement provider

### 1. Clone the repository

```bash
git clone https://github.com/Krishnendu1910/AI-Image-Enhancer.git
cd AI-Image-Enhancer
```

### 2. Install dependencies

```bash
npm install
```

### 3. Start the development server

```bash
npm run dev
```

Open the local URL printed by Vite in your terminal.

### 4. Build for production

```bash
npm run build
```

### 5. Preview the production build

```bash
npm run preview
```

### 6. Run lint checks

```bash
npm run lint
```

## 🔐 API Setup & Security

API integration lives in:

```text
src/utils/enhanceImageApi.js
```

The current implementation sends requests to the TechHK/AOS CDN API host and includes an `X-API-KEY` header.

**Security warning:** the current source contains an API key in frontend JavaScript. Any key included in client-side code can be inspected by visitors, so it should not be treated as a secret. If this key is active, revoke or rotate it, then move authenticated requests behind a backend or serverless function and keep the replacement key in server-side environment variables.

For a production deployment, verify the provider's current documentation, endpoint, request format, quotas, and terms before using your own credentials. Do not commit private keys to the repository or expose them through a `VITE_*` browser environment variable.

## ⚠️ Known Gaps to Address

This README is based on the source currently in the repository. The following items deserve attention before the app is considered production-ready:

- 🔑 **Client-side API key:** move the key to a protected server-side integration and rotate it if it's still valid.
- 🧯 **Error handling:** the API helper catches errors and logs them without rethrowing; the UI may not reliably detect failure or reset its loading state.
- 📁 **Upload validation:** validate MIME type, file size, and empty or unsupported files before submitting.
- 🧹 **Object URL cleanup:** revoke browser-created object URLs when replacing an image and when the component unmounts.
- 📥 **Download action:** the current UI source includes image previews, but no dedicated result-download control is implemented in the visible components.
- 🧩 **Preview state:** review the result/empty-state conditions so a successful result doesn't appear alongside the “No Enhanced Image” message.
- 🔁 **Task polling:** add cancellation, a timeout, clearer failure states, and a more resilient delay strategy.
- ♿ **Accessibility:** add descriptive image alt text, keyboard-friendly upload behavior, and clearer status announcements.

## 🛣️ Roadmap

- [ ] Secure the API integration behind a server-side endpoint.
- [ ] Validate image type and size before upload.
- [ ] Improve API failure and timeout handling.
- [ ] Prevent duplicate or overlapping enhancement requests.
- [ ] Add a before/after comparison slider.
- [ ] Add an explicit download button for the returned image.
- [ ] Clean up object URLs safely.
- [ ] Improve accessibility and mobile behavior.
- [ ] Add tests for upload, task polling, errors, and result rendering.

## 🔗 Links

<div align="center">

<a href="https://ai-image-enhancer-pi-eight.vercel.app/">
  <img src="https://img.shields.io/badge/🌐%20LIVE%20DEMO-Open%20Application-6D28D9?style=for-the-badge" alt="Open the live application" />
</a>
<a href="https://github.com/Krishnendu1910/AI-Image-Enhancer">
  <img src="https://img.shields.io/badge/💻%20GITHUB-View%20Source-24292e?style=for-the-badge&logo=github&logoColor=white" alt="View source on GitHub" />
</a>

<br /><br />

**React × Vite × External Image Enhancement API** ✨

</div>
