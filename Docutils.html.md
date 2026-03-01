## G1
# 🤖 LAMIS — LARGE MULTIMODAL SYSTEM  
### Real-Time Voice + Vision AI for Physical Robots

[![License](https://img.shields.io/badge/license-MIT-green)](LICENSE) [![Python Version](https://img.shields.io/badge/python-3.11-blue)](https://www.python.org/) [![Build Status](https://img.shields.io/badge/build-passing-brightgreen)](#lasmi.ai)

> Giving robots perception, conversation, and autonomous social response — in real time.

---

## 🌍 Vision

Most robots today are mechanical.  
Some are programmable.  
Very few are intelligent in context.

LAMIS transforms the **Unitree G1** into a real-time multimodal agent that:

- 🎙️ Listens
- 👀 Sees
- 🧠 Understands
- 🦾 Acts
- 🔁 Continues the loop


---

## 🧠 Core Innovation

This is not simple speech recognition.  
This is not camera streaming.

This is continuous multimodal cognition.

### Features

- 🎙️ Streaming voice input & output
- 🎥 Periodic visual context ingestion
- 🦾 AI-triggered physical actuation
- 👀 Autonomous visual-only reactions
- ⚡ Fully async, non-blocking architecture
- 💰 Real-time token cost awareness

Operational loop:

```m4a

Observe → Interpret → Decide → Act → Continue

```

---

## 🏗 System Architecture

```m4a

Audio In  ─┐
├──► LAMIS Multimodal Engine ───► Audio Out
Vision In ─┘               │
▼
Decision Layer
│
▼
Physical Actuation

```
### Layer Breakdown

```
| Layer | Responsibility |
|-------|---------------|
| Perception | USB Mic + RealSense D435i |
| Cognition | LAMIS Realtime Multimodal |
| Decision | Function-calling + gesture classification |
| Actuation | Unitree G1 Arm SDK |
| Feedback | Voice + gesture + continued dialogue |
```
---

## 🖥 Hardware Specs
```
| Component | Specification |
|-----------|---------------|
| Robot Base | Unitree G1 Quadruped |
| CPU | Intel i7-12700H / Jetson Orin |
| GPU | RTX 3070 / Orin GPU |
| Vision Sensor | Intel RealSense D435i |
| Microphone | USB Omnidirectional Mic |
| Connectivity | Wi-Fi 6, Ethernet |
| Power | 12V Li-ion Battery Pack |
| Actuation | 12 Servos + Arm SDK |
```
---

## 👁️ Modes of Operation

### 1️⃣ Conversational Mode
Voice + periodic visual awareness.

Use Cases:
- Interactive demo robot
- Lab assistant
- Reception robot

---

### 2️⃣ Gesture Command Mode
Voice-triggered gestures.

Example:
> "Say hello."

Robot:
- Speaks
- Waves
- Automatically releases arm (0.5s safety release)

---

### 3️⃣ Autonomous Social Mode (V2)

No voice command required.

Recognized gestures:
- 🤝 Handshake
- ❤️ Heart gesture
- 👋 Greeting wave

If uncertain → no movement.

**Confidence-based actuation ensures safety and prevents awkward behavior.**

---

## 💰 Cost Profile (2025 Estimate)

Approximate runtime cost:

~$120/hour (continuous operation)

Breakdown:
- Audio streaming = majority of cost
- Vision input = minor contribution

### Cost Optimization

- Increase image interval (10s → 20s)
- Reduce JPEG quality
- Dynamically disable vision
- Silence-aware audio throttling (future)

---

## 🛡 Safety Principles

- Gesture execution requires high confidence
- Automatic arm release mechanism
- No ambiguous actuation
- External USB audio prevents echo feedback

In robotics: safety > aesthetics.

---

## 🧩 Strategic Applications

- AI receptionists
- Retail robotics assistants
- Hospital robotic aides
- Museum interactive guides
- Research platforms for HRI
- Companion robotics

---

## 🔮 Product Roadmap

### Phase 1 — Stable Multimodal Loop
✅ Complete

### Phase 2 — Adaptive Cost Control
- Dynamic image streaming
- Silence-based audio optimization

### Phase 3 — Depth-Aware Interaction
- RealSense depth integration
- Spatial reasoning layer

### Phase 4 — Persistent Memory
- Long-term contextual memory

### Phase 5 — Multi-Robot Coordination
- Fleet behavior synchronization

---

## 🎯 Target Audience

- Robotics startups
- AI + hardware integrators
- Research labs
- Human-Robot Interaction researchers
- Advanced robotics developers

---

## 🚀 Positioning Statement

LAMIS is not a chatbot.

LAMIS is embodied intelligence.

And embodied intelligence changes everything.
```

```
# GPT Vision + RealSense Integration

Real-time scene analysis using OpenAI's GPT Vision models with Intel RealSense D435i camera for robotics applications.

## Overview

This project integrates OpenAI's GPT Vision models (GPT-4o, GPT-4o-mini, GPT-5) with the RealSense D435i RGB-D camera to provide intelligent scene understanding for robots. The system captures RGB and depth data, analyzes scenes using GPT Vision API, and provides actionable insights for navigation, object detection, and safety assessment.

## Features

- **Real-time Vision Analysis**: Process RealSense camera feeds with GPT Vision API
- **Depth Image Support**: Optional depth map visualization for enhanced spatial understanding
- **Multiple Model Support**: Choose from gpt-4o, gpt-4o-mini, or gpt-5-chat-latest
- **Korean/English Prompts**: Bilingual prompt templates (_KR versions available)
- **Customizable Prompts**: 8+ prompt templates for different robotics tasks
- **Token Cost Tracking**: Monitor and estimate API costs in real-time
- **Async Processing**: Non-blocking API calls for continuous operation
- **Comprehensive Logging**: Save images and analysis results with timestamps
- **Continuous Analysis**: No artificial rate limiting, runs as fast as API allows

## Project Structure

```bash
gpt-vlm/
├── gpt_realsense_analyzer.py  # Main application
├── config.py                   # Configuration settings
├── prompts.py                  # Prompt templates (EN + KR)
├── requirements.txt            # Python dependencies
├── README.md                   # This file
└── logs/                       # Analysis results (created at runtime)
    ├── frame_*.jpg             # Captured images
    └── analysis_*.json         # GPT responses
```

## Prerequisites

### Hardware

- Intel RealSense D435i camera
- NVIDIA Jetson Orin NX (or compatible device)
- Stable internet connection

### Software

**Python Packages:**
```bash
pip3 install openai pyrealsense2 opencv-python numpy python-dotenv
```

Or use the provided requirements file:
```bash
pip3 install -r requirements.txt
```

**OpenAI API Key:**
- Get your API key from [OpenAI Platform](https://platform.openai.com/api-keys)
- Ensure you have credits or billing set up

## Setup

### 1. Configure API Key

Create a `.env` file in the project directory:

```bash
cd /home/unitree/AIM-Robotics/gpt-vlm
cp .env.example .env
nano .env
```

Add your OpenAI API key:
```
OPENAI_API_KEY=sk-your-actual-api-key-here
```

### 2. Verify RealSense Camera

Check that your RealSense camera is connected:

```bash
lsusb | grep -i intel
# Should show: 8086:0b3a Intel Corp. RealSense D435i
```

### 3. Install Dependencies

```bash
pip3 install -r requirements.txt
```

## Configuration

Edit `config.py` to customize behavior:

### Model Selection
```python
OPENAI_MODEL = "gpt-5-chat-latest"  # Options:
                                     # "gpt-4o" - High accuracy
                                     # "gpt-4o-mini" - Cost-effective
                                     # "gpt-5-chat-latest" - Latest GPT-5
```

### Depth Image Option
```python
SEND_DEPTH_IMAGE = True   # Send RGB + depth colormap (2x tokens)
                          # False = RGB only (cheaper)
```

When enabled, GPT receives:
1. **RGB image**: Standard camera view
2. **Depth colormap**: Blue=close, green=mid, red=far
3. **Instruction**: Analyze depth map to estimate object distances

### Image Quality Settings
```python
IMAGE_DETAIL = "low"      # "low" saves ~65% tokens vs "high"
JPEG_QUALITY = 75         # 0-100, compression quality
```

### Other Options
```python
MAX_TOKENS = 300          # Maximum response tokens
TEMPERATURE = 0.7         # 0.0-2.0, creativity level
SAVE_IMAGES = True        # Save analyzed frames to disk
SAVE_RESPONSES = True     # Save GPT responses to JSON
```

## Usage

### Basic Usage

Run the analyzer:

```bash
cd /home/unitree/AIM-Robotics/gpt-vlm
python3 gpt_realsense_analyzer.py
```

**Expected Output:**
```llv
🎥 Initializing RealSense D435i...
  - Depth stream: 640x480 @ 30fps
  - Color stream: 640x480 @ 30fps
  - Waiting for device to be ready...
  ✓ Pipeline started
  - Warming up camera (30 frames)...
  ✓ Camera ready

============================================================
🎥 GPT VISION + REALSENSE ANALYZER
============================================================

Configuration:
  Model:         gpt-5-chat-latest
  Detail:        low
  JPEG Quality:  75%
  Resolution:    640x480
  Depth Image:   Enabled (2x tokens)

============================================================
Press Ctrl+C to stop
============================================================

============================================================
Analysis #1 | 4523.1ms
============================================================

📍 Depth: 1.25m

🤖 GPT Analysis:

1. 보이는 물체들
   - 의자 2개 (깊이맵 초록색, 약 1.3-1.5m)
   - 탁자 다리 (깊이맵 노란색, 약 2.0m)
   - 가방 (깊이맵 파란색, 약 0.8-0.9m)
   - 전원 케이블 (깊이맵 파란색, 약 0.8m)

2. 공간 배치
   - 왼쪽: 가방, 바닥 가까움
   - 오른쪽: 의자, 다리 공간 있음
   - 중앙: 케이블이 바닥을 가로지름

3. 장애물 / 위험 요소
   - 바닥의 케이블: 걸림 및 감김 위험
   - 의자 다리: 충돌 가능

4. 주행 제안 행동
   - 전방 케이블을 피하기 위해 우측으로 우회 이동
   - 속도 저속 유지 (0.2 m/s 이하)

📊 Tokens: 1247 in / 152 out
============================================================
```

### Available Prompts

**English Versions:**
- `SCENE_UNDERSTANDING` - General scene description (default)
- `OBJECT_DETECTION` - List objects with locations
- `OBSTACLE_DETECTION` - Identify navigation hazards
- `PERSON_TRACKING` - Detect and locate people
- `ROOM_CLASSIFICATION` - Identify room type
- `SAFETY_CHECK` - Safety assessment (SAFE/CAUTION/STOP)
- `DIRECTION_RECOMMENDATION` - Navigation direction advice
- `PATH_DESCRIPTION` - Describe navigable paths

**Korean Versions (_KR suffix):**
- `SCENE_UNDERSTANDING_KR` - 장면 이해 (기본값)
- `OBJECT_DETECTION_KR` - 물체 탐지
- `OBSTACLE_DETECTION_KR` - 장애물 탐지
- And all others with `_KR` suffix

**Switching Prompts:**
Edit `gpt_realsense_analyzer.py` line ~144:
```python
async def analyze_frame(self, ..., prompt_template=prompts.OBSTACLE_DETECTION_KR):
```

## Cost Estimation

### Token Usage

**RGB only (SEND_DEPTH_IMAGE = False):**
- Image: ~600 tokens
- Prompt: ~50 tokens
- Response: ~100-150 tokens
- **Total: ~750-800 tokens/analysis**

**RGB + Depth (SEND_DEPTH_IMAGE = True):**
- Images: ~1200 tokens (2 images)
- Prompt: ~100 tokens (includes depth instructions)
- Response: ~150-200 tokens
- **Total: ~1450-1500 tokens/analysis**

### Pricing

Varies by model (check [OpenAI Pricing](https://openai.com/api/pricing/)):

| Model | Input (per 1M tokens) | Output (per 1M tokens) |
|-------|----------------------|------------------------|
| gpt-4o-mini | $0.150 | $0.600 |
| gpt-4o | $2.50 | $10.00 |
| gpt-5-chat | ~$5.00 | ~$15.00 |

### Cost Examples (Continuous Analysis)

**Assuming 4-5 second API response time = ~0.2 fps effective rate**

**gpt-4o-mini + RGB only:**
- ~720 analyses/hour × 800 tokens = ~0.58M tokens/hour
- Input: $0.09/hour, Output: $0.03/hour
- **Total: ~$0.12/hour (~$3/day)**

**gpt-5-chat + RGB + Depth:**
- ~720 analyses/hour × 1500 tokens = ~1.08M tokens/hour
- Input: ~$5.40/hour, Output: ~$1.62/hour
- **Total: ~$7/hour (~$168/day)**

**Cost Reduction Tips:**
1. Use `gpt-4o-mini` instead of gpt-4o or gpt-5
2. Set `SEND_DEPTH_IMAGE = False` (saves 50% tokens)
3. Use `IMAGE_DETAIL = "low"` (already default)
4. Add conditional analysis (skip frames when robot is stopped)

## Performance

**Typical Analysis Time:**
- API latency: 2-5 seconds (varies by model and load)
- Continuous operation: Analyzes immediately after each completion
- Effective rate: ~0.2-0.5 fps depending on API response time

**The system runs continuously without artificial delays:**
- Frame received → Analyze → Complete → Next frame immediately
- No fixed FPS limit, depends only on API speed

## Output Examples

### Saved Files

**RGB Image**: `logs/frame_20250105_143022_123.jpg`

**Depth Colormap** (if enabled): Saved alongside RGB

**Analysis JSON**: `logs/analysis_20250105_143022_123.json`
```json
{
  "timestamp": "20250105_143022_123",
  "analysis_count": 42,
  "success": true,
  "analysis": "1. 보이는 물체들\n- 의자 2개 (깊이맵 초록색, 약 1.3-1.5m)...",
  "prompt": "로봇 관점에서 이 장면을 분석하세요...",
  "depth_m": 1.25,
  "tokens": {
    "input": 1247,
    "output": 152
  }
}
```

## Troubleshooting

### Camera Not Detected

```bash
# Check USB connection
lsusb | grep -i intel

# Test RealSense
cd /home/unitree/AIM-Robotics/RealSense/examples
python3 00_check_camera.py
```

### "Device or resource busy" Error

**Cause**: Unitree's `videohub_pc4` service uses the camera

**Solution:**
```bash
# Check if videohub is running
ps aux | grep videohub

# Kill it (will auto-restart, but gives brief window)
sudo kill -9 <PID>

# Immediately run your script
python3 gpt_realsense_analyzer.py
```

**Permanent solution:**
```bash
# Rename binary to disable auto-restart
sudo mv /unitree/module/video_hub_pc4/videohub_pc4 \
        /unitree/module/video_hub_pc4/videohub_pc4.disabled

# Restore later if needed
sudo mv /unitree/module/video_hub_pc4/videohub_pc4.disabled \
        /unitree/module/video_hub_pc4/videohub_pc4
```

### API Key Issues

```
❌ Error: OPENAI_API_KEY not found
```

**Solution:**
- Verify `.env` file exists in `/home/unitree/AIM-Robotics/gpt-vlm/`
- Check key starts with `sk-`
- Ensure no extra spaces or quotes

### Slow API Response

**If analysis takes >10 seconds:**
- Check internet connection
- Try switching to `gpt-4o-mini` (faster than gpt-5)
- Verify OpenAI API status

## Depth Map Analysis

When `SEND_DEPTH_IMAGE = True`, GPT receives depth visualization with instructions:

**Depth Colormap Scale:**
- 🔵 Blue: 0.5-1.0m (close)
- 🟢 Green: 1.0-2.0m (medium)
- 🟡 Yellow/🔴 Red: 2.0m+ (far)

**GPT is instructed to:**
1. Look at each object in RGB image
2. Check corresponding area in depth map
3. Estimate distance based on color
4. Report as: "의자 (깊이맵 초록색, 약 1.3-1.5m)"

This enables spatial awareness without complex depth processing.

## Comparison with YOLO

| Feature | GPT Vision | YOLOv8 |
|---------|------------|--------|
| **Speed** | ~0.2-0.5 fps | ~30 fps |
| **Cost** | $3-168/day | Free |
| **Understanding** | Scene reasoning, distance estimation | Bounding boxes only |
| **Output** | Natural language | Class + coordinates |
| **Depth** | Analyzes depth map | No depth awareness |
| **Use Case** | High-level decisions | Real-time tracking |

**Recommendation**: Use both together:
- **YOLO**: Real-time object tracking (30 fps, local)
- **GPT Vision**: Scene understanding and planning (0.5 fps, cloud)

## Advanced Usage

### Custom Prompts

Add to `prompts.py`:

```python
MY_CUSTOM_PROMPT_KR = """사용자 정의 프롬프트.
중앙 거리: {depth_m}m
[지시사항]"""

# Use in analyzer:
# Line ~144: prompt_template=prompts.MY_CUSTOM_PROMPT_KR
```

### Robot Control Integration

```python
# After receiving analysis result:
analysis_text = result["analysis"]

if "STOP" in analysis_text or "정지" in analysis_text:
    robot.stop()
elif "FORWARD" in analysis_text or "전진" in analysis_text:
    robot.move_forward()
```

### Conditional Analysis

Add logic to skip frames:

```python
# Only analyze if robot is moving
if robot.is_moving():
    result = await self.analyze_frame(...)
```

## Model Comparison

**gpt-4o-mini:**
- ✅ Fast (~2-3s response)
- ✅ Very cheap ($3/day continuous)
- ⚠️ Good but not exceptional understanding

**gpt-4o:**
- ✅ Excellent understanding
- ⚠️ Moderate cost (~$50/day continuous)
- ⚠️ Slower (~4-5s response)

**gpt-5-chat-latest:**
- ✅ Best understanding and reasoning
- ✅ Handles complex spatial reasoning
- ❌ Expensive (~$168/day continuous)
- ⚠️ Can be slow (~5-7s response)

## References

**Related Projects:**
- YOLOv8 + RealSense: `/home/unitree/AIM-Robotics/YOLOv8n/`
- RealSense examples: `/home/unitree/AIM-Robotics/RealSense/`
- SLAM system: `/home/unitree/AIM-Robotics/SLAM/`

**Documentation:**
- [OpenAI Vision API](https://platform.openai.com/docs/guides/vision)
- [RealSense D435i](https://www.intelrealsense.com/depth-camera-d435i/)
- [OpenAI Pricing](https://openai.com/api/pricing/)

---

Made with 💡 by AIM Robotics
