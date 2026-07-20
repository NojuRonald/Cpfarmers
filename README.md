
# ClipFarmer AI

A fully offline, lightweight streaming assistant that analyzes your gameplay in real time and provides actionable suggestions for creating viral clips.

## Overview
ClipFarmer AI uses local Vision-Language Models (like Qwen3-VL or Llama 3.2-Vision) to monitor your screen. Every few seconds, it processes the game state and outputs exactly three high-energy recommendations directly to a transparent overlay. Since it runs 100% locally, it preserves your privacy and requires zero API subscription fees.

## Features
* **Fully Offline Inference:** Powered by Ollama to ensure maximum privacy and zero latency from cloud servers.
* **Lightweight Screen Capture:** Utilizes `mss` for high-speed, low-overhead frame capturing that will not bottleneck your game.
* **Context-Aware Recommendations:** Understands game UI, health bars, and on-screen text to deliver highly relevant streaming prompts.
* **Transparent Overlay:** Displays suggestions seamlessly over your gameplay without blocking crucial UI elements.

## Prerequisites
* Python 3.10 or higher
* [Ollama](https://ollama.com/) installed locally
* A dedicated GPU (8GB+ VRAM recommended for optimal performance)
* A compatible Vision-Language Model pulled via Ollama (e.g., `qwen3:8b` or `llama3.2-vision`)

## Installation



```

2. **Install Python dependencies:**
```bash
pip install -r requirements.txt

```


*(Core dependencies include `mss` for capture, `requests` for the API, and `PyQt6` or `Electron` for the overlay)*
3. **Pull the required AI model:**
Make sure Ollama is running, then download your preferred vision model:
```bash
ollama pull qwen3:8b

```



## Usage

1. Start your local Ollama server.
2. Run the main script to begin the capture loop and launch the overlay window:
```bash
python main.py

```


3. The transparent window will appear on top of your screen. Launch your game, and the AI will begin polling your screen and updating the overlay with 3 new clip ideas based on the current context.

## Configuration

You can tweak the performance and behavior of the tool in the `config.json` file.

* `capture_interval`: Adjust how often the screen is captured (default is 5 seconds).
* `resolution_scale`: Downscale the image before sending it to the VLM to save VRAM (e.g., `720p`).
* `system_prompt`: Modify the director persona to change the style of the recommendations.

## Performance Tips

Running a local AI alongside a modern game can be demanding. To maintain high FPS, ensure you are using a 4-bit quantized model and limit the screen capture interval.

## License

[MIT License](https://www.google.com/search?q=LICENSE)

```

```
