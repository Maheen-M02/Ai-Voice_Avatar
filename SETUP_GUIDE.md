# 🚀 Advanced AI Avatar System Setup Guide

## 📁 File Placement for Custom Avatar

### Step 1: Create Directory Structure
```
public/
  assets/
    models/
      avatar.glb  ← Place your GLB file here
```

### Step 2: GLB Model Requirements
- **Format**: GLB (Binary glTF)  
- **Morph Targets**: For best results, include these morph targets:
  - `jawOpen` - For mouth opening
  - `smile` - For happy expressions  
  - `mouthFunnel` or `pucker` - For "oo" sounds
  - `eyeBlinkLeft`, `eyeBlinkRight` - For blinking
  - `browsUp`, `browsDown` - For emotions

## 🤖 Ollama Setup (Local AI)

### Step 1: Install Ollama
```bash
# macOS/Linux
curl -fsSL https://ollama.ai/install.sh | sh

# Windows - Download from https://ollama.ai/download
```

### Step 2: Start Ollama Service
```bash
ollama serve
```

### Step 3: Pull Recommended Models
```bash
# Lightweight, fast model (recommended)
ollama pull llama3.2

# More capable model (if you have more RAM)  
ollama pull llama3.1

# Multilingual model for better Hindi support
ollama pull llama2  # Has better multilingual training
```

### Step 4: Test Connection
```bash
# Test if Ollama is running
curl http://localhost:11434/api/tags
```

## 🎤 ElevenLabs Setup (Premium Voice)

### Step 1: Get API Key
1. Sign up at [ElevenLabs](https://elevenlabs.io)
2. Go to Profile → API Keys
3. Create a new API key

### Step 2: Configure in App
The system will automatically detect if ElevenLabs is available and fall back to browser TTS if not.

## 🌍 Supported Languages

### Voice Input Languages
- **English (US)**: `en-US` 🇺🇸
- **Hindi (India)**: `hi-IN` 🇮🇳  
- **English (India)**: `en-IN` 🇮🇳

### How Language Detection Works
- **Automatic**: System detects language from script (Devanagari = Hindi)
- **Manual**: Select language in dropdown before speaking
- **Mixed Languages**: System handles English-Hindi code-switching

## 🎯 Usage Instructions

### Voice Interaction Flow
1. **Select Language** - Choose from dropdown
2. **Click "Start Listening"** - Red button indicates active listening
3. **Speak Naturally** - System shows live transcript
4. **AI Processing** - Ollama generates contextual response
5. **Avatar Response** - Speaks back with facial animations

### Text Input Alternative
- Use the text input panel if voice isn't working
- Supports the same multilingual responses
- Click "Speak" or use quick phrases

### Avatar Customization
- Drop your `.glb` file in `public/assets/models/avatar.glb`
- System auto-detects and loads custom avatar
- Falls back to geometric avatar if file not found
- Real-time morph target mapping for lip sync

## 🛠️ Troubleshooting

### Ollama Connection Issues
```bash
# Check if Ollama is running
ps aux | grep ollama

# Restart Ollama service
ollama serve

# Check available models
ollama list
```

### Voice Input Not Working
- **Chrome/Edge**: Usually works best
- **Safari**: Limited support
- **Firefox**: May need manual permissions
- **Mobile**: Limited speech recognition support

### Avatar Not Loading
1. Check file path: `public/assets/models/avatar.glb`
2. Verify GLB format (not GLTF + bin)
3. Check browser console for loading errors
4. Ensure model has proper morph targets

### ElevenLabs Issues
- Check API key is valid
- Verify account has credits
- Monitor rate limits
- System falls back to browser TTS automatically

## 🎨 Customization Options

### Change Ollama Model
```javascript
// In src/lib/ollamaClient.ts
const ollamaRef = useRef(new OllamaClient("http://localhost:11434", "llama3.2"));
```

### Add Custom Voices (ElevenLabs)
```javascript
// In src/lib/elevenLabsTTS.ts - add to ELEVENLABS_VOICES
"custom-lang": [
  { voice_id: "your-voice-id", name: "Custom Voice", language: "Custom" }
]
```

### Modify Avatar Behavior
```javascript
// In src/components/Avatar3DCustom.tsx
// Adjust animation parameters in useFrame hook
meshRef.current.rotation.y = Math.sin(state.clock.elapsedTime * 2) * 0.1;
```

## 🚀 Performance Tips

### For Best Performance
1. **Use Llama 3.2** - Fastest local model
2. **Enable Hardware Acceleration** - GPU support in Ollama
3. **Optimize GLB Model** - Keep under 10MB for smooth loading
4. **Browser Choice** - Chrome/Edge perform best

### Memory Requirements
- **Llama 3.2**: ~4GB RAM
- **Llama 3.1**: ~8GB RAM  
- **Browser**: ~500MB for 3D rendering

## 🎭 Advanced Features

### Context Memory
- Keeps last 4 conversation messages
- Maintains language consistency
- Emotional state tracking

### Real-time Sync
- Audio-visual synchronization
- Morph target interpolation  
- Emotion-based expressions
- Live transcription display

### Desktop Integration Ready
- Website opening controls
- Folder access buttons
- Cross-platform compatibility

---

## 🎉 You're Ready!

Your advanced AI avatar system supports:
✅ **Voice Input** (Hindi + English)  
✅ **Local AI** (Ollama integration)  
✅ **Premium TTS** (ElevenLabs + fallback)  
✅ **Custom Avatars** (GLB model support)  
✅ **Real-time Sync** (Audio + visuals)  
✅ **Multilingual** (Seamless language switching)

Perfect for hackathons, demos, and production use! 🚀