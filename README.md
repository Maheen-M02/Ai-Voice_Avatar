
# 🧑‍🚀 3D AI Avatar Project

An interactive **3D AI-powered avatar** built with **React + Three.js + Express + Python TTS**.  
This project brings an animated digital human to life with facial expressions, lip-sync, and voice responses. 🚀

---

## ✨ Features

- 🎭 **3D Avatar Rendering** (React Three Fiber + Drei)  
- 👄 **Lip-Sync & Facial Animations** (Morph Targets for visemes + emotions)  
- 👁 **Realistic Blinking** (randomized natural blinking)  
- 🎤 **Voice Interaction** (Text-to-Speech using Python TTS / Mimic3)  
- ⚡ **Real-time WebSocket Backend** (Node.js + Express + WS)  
- 🔊 **Sound Engine** (Howler.js for smooth audio playback)  
- 🌈 **Emotion System** (happy, sad, angry, neutral, excited)  
- 💫 **Speaking Glow Effect** (pulses when avatar talks)  

---

## 🏗️ Project Structure

```
📦 3d-ai-avatar
 ┣ 📂 server                # Backend (Node.js + Express + WS)
 ┃ ┣ 📜 index.js            # Entry point for backend
 ┃ ┗ 📜 package.json
 ┣ 📂 apps
 ┃ ┗ 📂 web                 # Frontend (React + Vite + Three.js)
 ┃   ┣ 📂 public
 ┃   ┃ ┗ avatar.glb         # 3D model of avatar
 ┃   ┣ 📂 src
 ┃   ┃ ┣ components         # React components
 ┃   ┃ ┣ App.tsx
 ┃   ┃ ┗ main.tsx
 ┃   ┗ 📜 package.json
 ┣ 📜 setup.bat             # Windows setup script
 ┣ 📜 README.md             # You’re here 😎
```

---

## ⚡ Quick Start

### 1️⃣ Prerequisites

Make sure you have installed:

- [Node.js](https://nodejs.org/) (>= 18)  
- [Python 3](https://www.python.org/downloads/)  
- [Git](https://git-scm.com/)  

---

### 2️⃣ One-Step Setup (Windows)

Run the setup script:

```bash
setup.bat
```

This will:  
✅ Check for Node.js, Python, Git  
✅ Install backend dependencies  
✅ Install frontend dependencies  
✅ Install Python TTS libs  
✅ Setup utils (socket.io, etc.)  

---

### 3️⃣ Manual Setup

If you prefer:

**Backend:**

```bash
cd server
npm install
node index.js
```

**Frontend:**

```bash
cd apps/web
npm install
npm run dev
```

**Python deps:**

```bash
pip install mimic3 TTS
```

---

## 🚀 Usage

1. Start backend:  

   ```bash
   cd server && node index.js
   ```

2. Start frontend:  

   ```bash
   cd apps/web && npm run dev
   ```

3. Place your avatar model in:  

   ```
   apps/web/public/avatar.glb
   ```

4. Open browser at:  
   ```
   http://localhost:5173/
   ```

---

## 🎮 Controls

- Avatar automatically blinks & moves lips with speech.  
- Emotions can be triggered programmatically (`happy`, `sad`, `angry`, etc.).  
- Speaking glow pulses based on jawOpen intensity.  

---

## 🛠️ Tech Stack

- **Frontend:** React, Vite, Three.js, @react-three/fiber, @react-three/drei, Zustand, Howler  
- **Backend:** Node.js, Express, WebSocket, Socket.io  
- **AI/TTS:** Python, Mimic3, Coqui TTS  
- **Utils:** Git, npm  

---

## 📌 Next Steps

- 🔥 Add speech recognition (STT)  
- 🎥 Webcam-based emotion detection  
- 🧠 Integrate LLMs (OpenAI/Groq/Gemini) for smarter convos  
- 🎨 Improve shaders & lighting for realism  

---

## 📜 License

MIT License – free to use & modify.  
