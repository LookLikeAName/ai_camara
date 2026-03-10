# AI_CAMARA // V.0.1

AI_CAMARA is a technical "image-to-text-to-image" reconstruction experiment. It uses Gemini's advanced multimodal capabilities to analyze a real-world image, describe it in exhaustive detail, and then "dream" a new version based strictly on that description.

![AI_CAMARA UI](https://github.com/LookLikeAName/ai_camara/raw/main/public/vite.svg) *Placeholder - App uses a dark camera-inspired interface*

## 📸 Core Features

-   **Dual Input Modes**: 
    -   **Upload**: Select any image from your device for analysis.
    -   **Live Camera**: Capture the world directly through your browser's viewfinder (optimized for mobile rear cameras).
-   **Intelligent Reconstruction Pipeline**:
    -   **Analysis**: Uses `gemini-3.1-flash-lite-preview` to translate pixels into a high-fidelity textual prompt.
    -   **Generation**: Uses `gemini-3.1-flash-image-preview` (Imagen 3) to reconstruct the scene from the generated text.
-   **Technical Interface**:
    -   **Adaptive Viewfinder**: Real-time JavaScript calculation ensures the lens fits perfectly on any screen size (PC or Mobile) while maintaining chosen aspect ratios.
    -   **System Settings**: Directly toggle between **Aspect Ratios** (1:1, 16:9, 9:16, etc.) and **Image Quality** (1K, 2K, 4K).
    -   **Dynamic UI Scaling**: All interface elements scale gracefully based on your browser window size.
-   **Security First**: API keys are stored only in your browser's `localStorage`. No server-side storage.
-   **One-Click Export**: Download your favorite AI reconstructions instantly.

## 🛠️ Tech Stack

-   **Framework**: React 19 (TypeScript)
-   **Build Tool**: Vite
-   **API**: Google Gemini API (v1beta)
-   **Styling**: Vanilla CSS (Modern Flexbox/Grid + CSS Variables)
-   **Deployment**: GitHub Pages via GitHub Actions

## 🚀 Getting Started

### Prerequisites
-   A **Google AI Studio API Key**. Get one for free at [aistudio.google.com](https://aistudio.google.com/).

### Installation
1.  Clone the repository:
    ```bash
    git clone https://github.com/LookLikeAName/ai_camara.git
    cd ai_camara
    ```
2.  Install dependencies:
    ```bash
    npm install
    ```
3.  Run the development server:
    ```bash
    npm run dev
    ```
4.  Open `http://localhost:5173` in your browser.

### Usage
1.  Open **[ API KEY MGMT ]** at the bottom and add your Gemini API Key.
2.  Select your preferred mode (**UPLOAD** or **CAMERA**).
3.  Adjust settings in the **[ SETTINGS ]** menu (top header).
4.  Press the **Shutter Button** to start the reconstruction.
5.  Wait for the AI to analyze and generate (10-30s).
6.  Hit **DOWNLOAD** if you like the result, or **NEW** to try again.

## ⚙️ Advanced Configuration
You can change the underlying AI models directly from the browser console:
```javascript
window.AiCamaraConfig.setVisionModel('your-model-id');
window.AiCamaraConfig.setImageModel('your-model-id');
window.AiCamaraConfig.config; // View current settings
```

## 📄 License
MIT
