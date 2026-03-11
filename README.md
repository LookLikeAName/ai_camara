# AI_CAMERA // V.0.1

AI_CAMERA is a high-fidelity "image-to-text-to-image" reconstruction experiment. It leverages Google Gemini's multimodal power to translate visual reality into technical descriptions, which are then used as prompts to "dream" a new, stylistically controlled version of the original scene.

![AI_CAMERA UI](https://github.com/LookLikeAName/ai_camera/raw/main/public/ai_camera.svg)

## 📸 Core Features

### 1. Dual-Input Vision System
-   **Live Viewfinder**: Capture the world directly using your device's camera (optimized for mobile rear-facing lenses).
-   **Static Upload**: Process any existing image file (JPG, PNG, WebP) from your local storage.
-   **Token-Efficient Processing**: All inputs are automatically downscaled to 768px and compressed (JPEG 80%) to maximize description detail while minimizing API token usage.

### 2. Stylistic Inception Filters
-   **Integrated Pipeline**: Unlike standard filters, AI_CAMERA instructs the **Vision Model** to describe the scene *through the lens* of the selected style.
-   **Presets**: Choose from **Cyberpunk**, **Oil Painting**, **Sketch**, **Pixel Art**, and **Watercolor**.
-   **Custom Engine**: Define your own stylistic rules via natural language descriptions.

### 3. Technical EXIF Integration
-   **GPS Tagging**: Enable Geolocation in settings to capture the exact coordinates at the moment of the shutter press.
-   **Metadata Injection**: Location data is embedded directly into the header of your downloaded JPEG reconstructions using the EXIF standard.

### 4. Adaptive & Robust Interface
-   **Dynamic Scaling**: Real-time JavaScript calculations ensure the UI and viewfinder maximize every pixel of your screen, whether on a 4K monitor or a mobile device.
-   **Cinematic Controls**: Toggle between modern aspect ratios (**16:9**, **1:1**, **9:16**, **4:3**, **3:4**) and generation qualities (**1K**, **2K**, **4K**).
-   **Abort Protection**: State-machine logic prevents race conditions by allowing you to cancel and reset active AI generations if settings are changed mid-process.

## 🛠️ Tech Stack

-   **Frontend**: React 19 + TypeScript 5
-   **API**: Google Gemini REST API (v1beta)
-   **Metadata**: piexifjs (EXIF injection)
-   **Deployment**: Static site via GitHub Pages + GitHub Actions

## 🚀 Quick Start

### Prerequisites
-   A **Google AI Studio API Key**. [Get one here](https://aistudio.google.com/).

### Installation
1.  Clone & Install:
    ```bash
    git clone https://github.com/LookLikeAName/ai_camera.git
    cd ai_camera
    npm install
    ```
2.  Launch:
    ```bash
    npm run dev
    ```

### Basic Workflow
1.  **Configure**: Click **[ API KEY MGMT ]** and add your key.
2.  **Compose**: Choose your Mode (**CAMERA/UPLOAD**) and **Aspect Ratio**.
3.  **Capture**: Hit the **Shutter**. View the detailed AI analysis in the browser console (`F12`).
4.  **Export**: Use **DOWNLOAD (GPS+)** to save your result with embedded location data.

## ⚙️ Advanced Developer Console
Use `window.AiCameraConfig` to manipulate the engine in real-time:
-   `setVisionModel(id)`: Switch the analysis model (e.g., `gemini-3.1-flash`).
-   `setImageModel(id)`: Switch the generation model (e.g., `gemini-3.1-flash-image`).
-   `setVisionPrompt(text)`: Overwrite the system analysis prompt for the current session.
-   `config`: Inspect all persistent engine settings.

## 📄 License
MIT
