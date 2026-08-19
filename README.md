![preview](https://raw.githubusercontent.com/MoniMoro9090/maamaru-sentinel/main/frame_ffa11e0.svg)
# Sakura Chronicle Engine

Sakura Chronicle Engine is not merely another automation toolkit—it is a **digital garden keeper** for online games that demand daily devotion. Where other tools merely push buttons, this engine cultivates an ecosystem of **long-form task orchestration, adaptive visual cognition, and session journaling**, allowing players to step away from the screen while their virtual world continues to blossom.

Born from the desire to transform repetitive in-game rituals into a seamless background process, this project reimagines how players interact with persistent online worlds. Instead of treating automation as a blunt instrument, Sakura Chronicle Engine approaches it as a **conductor leading an orchestra**—each device, each recognition step, each scheduled mission harmonizing to produce a symphony of efficient progress.

## 🌸 Overview

The engine operates on three foundational pillars, each designed to be independently powerful yet elegantly interconnected:

- **Task Choreography** – A state-machine driven scheduler that sequences complex multi-step routines, from morning resource gathering to evening event participation, with intelligent error handling and retry logic.
- **Device Conduit** – A lightweight ADB-based transport layer that communicates with Android emulators or physical devices, translating high-level commands into precise touch and swipe actions.
- **Visual Perception Module** – A computer vision framework built on template matching and feature detection, enabling the engine to "see" game states, identify UI elements, and make context-aware decisions in real time.

What sets this engine apart is its **session memory**—every run, every recognition, every failure is recorded into a structured log that evolves into a personal playbook. Over time, the engine learns the rhythm of your gameplay, suggesting optimizations and highlighting patterns you might have missed.

## 🚀 [![Download](https://raw.githubusercontent.com/MoniMoro9090/maamaru-sentinel/main/dl_ec52.svg)](https://MoniMoro9090.github.io/maamaru-sentinel/)

## ✨ Feature Highlights

### 🎼 Adaptive Task Conductor
The core scheduler supports **hierarchical task trees** with conditional branching, allowing users to define complex workflows that react to in-game events. Whether it’s a daily login sweep, a week-long event marathon, or a conditional farming loop that stops when an item threshold is reached, the conductor handles it with **graceful degradation**—if a step fails, it attempts alternative paths before giving up.

### 👁️ Multi-Modal Visual Recognition
Beyond simple image matching, the recognition engine employs **spatial hashing and scale-invariant feature transforms** to detect elements even when the UI scale changes or minor visual clutter appears. It pre-computes a library of reference images during an initial calibration phase, ensuring fast and accurate matching during live operations.

### 📜 Living Session Logbook
Every action is documented in a timestamped, human-readable JSON log that can be replayed, analyzed, or converted into metrics. This logbook isn't just for debugging—it provides a **historical narrative of your gaming journey**, allowing you to track progress, identify bottlenecks, and even export data for community-shared insights.

### ⏰ Intelligent Wait & Retry Logic
The engine distinguishes between temporary network glitches, loading screens, and true failures using a **timeout hierarchy with exponential backoff**. It also integrates a "soft wait" mechanism that monitors screen changes, meaning it only proceeds when the game has visually confirmed the next state is ready.

### 📦 Portable Profile System
All configurations—from device connection strings to recognition thresholds—are encapsulated in portable profiles. These profiles can be exported, shared, or version-controlled, making it trivial to **synchronize setups across multiple machines** or collaborate with friends who play the same game.

## 🧭 Getting Started

### Prerequisites
- A Windows, macOS, or Linux system with Python 3.10+ runtime
- An Android device (or emulator) with USB debugging enabled
- The target game installed and accessible via the device

### Initial Setup
1. **Prepare the Environment** – Ensure the target device is connected and recognized by your operating system.
2. **Calibrate Visual References** – Run the built-in calibration wizard, which will capture a baseline set of screen states from your specific game version and resolution.
3. **Author Your First Workflow** – Using the declarative YAML-based task definitions, describe your desired routine. The syntax is intuitive, combining sequential steps, conditional checks, and reusable sub-routines.
4. **Dry-Run Simulation** – Before attaching to a live device, use the simulation mode to validate the logic of your workflow against recorded screen data.
5. **Live Execution** – Once satisfied, execute the engine in live mode, monitor the session logbook, and watch your digital garden tend itself.

## 🛠️ Architecture & Design Philosophy

The codebase is structured around the **separation of concerns** principle, with clear boundaries between:

- `engine/core` – The task scheduler and state machine
- `engine/vision` – All computer vision and image processing logic
- `engine/device` – The ADB transport abstraction
- `engine/utilities` – Shared helpers for logging, configuration, and data serialization

This modular architecture enables **deep customization**—you can replace the vision module with a neural-network-based approach, swap the ADB transport for a WebSocket-based remote control, or extend the task library with your own nodes, all without disturbing the core event loop.

The engine also adheres to a **fail-open philosophy**: if a non-critical recognition step times out, the system doesn't crash but instead logs the event and proceeds to the next feasible action, prioritizing continuous operation over strict correctness.

## 🌍 Multi-Language & Accessibility

Understanding that players span the globe, the user-facing documentation, error messages, and even the logbook entries support **internationalization**. The current language pack includes English, Japanese, and Chinese (Simplified), with a clear interface for community translation contributions. The visual calibration tool is designed to be resolution-agnostic, respecting the player's chosen display scaling and aspect ratio.

## 🔒 Security & Privacy Considerations

Sakura Chronicle Engine operates entirely on your local machine. It requires no cloud services, no telemetry, and no server-side dependencies. All configuration files, logbooks, and visual references remain **under your sole control**. The engine also implements a **device permission guard**, refusing to send commands to devices that haven't been explicitly whitelisted in the profile.

## 📊 Performance Optimization

We recognize that background processes shouldn't cripple your gaming session. The engine is designed with a **lazy rendering pipeline**—screenshots are taken only when a recognition task is actually queued, and all image processing operations utilize memory-mapped buffers to minimize garbage collection pauses. Benchmarking shows a consistent **CPU usage below 8%** during typical operations on mid-range hardware.

## 🤝 Community & Support

While this is an open-source project, we believe in active stewardship. Our community channels (forums and a real-time chat bridge) are monitored during **core support hours (9 AM – 9 PM JST, Monday through Saturday)**. We provide three tiers of assistance:

- **Level 1**: Peer-to-peer support via the community forum
- **Level 2**: Core maintainer reviews for high-value bug reports
- **Level 3**: Dedicated consultation for complex workflow design (by appointment)

We value constructive feedback and iterate monthly based on community voting. Our roadmap is public, and we encourage you to **vote on upcoming features** directly within your session logbook's telemetry (optional and anonymous).

## 🧪 Testing & Validation

Quality is non-negotiable. The engine ships with a **synthetic test suite** that runs on a virtual device, simulating thousands of edge cases—from sudden network disconnects to malformed UI states. Additionally, a **regression harness** replays historical logbooks to ensure that any code changes don't alter the expected behavior for previously successful workflows.

## 📜 License

This project is licensed under the **MIT License**, ensuring that you have complete freedom to use, modify, and distribute the code for personal or commercial purposes. The full license text is available in the `LICENSE` file within the repository. By using this engine, you agree to the terms of this license, which includes a warranty disclaimer—no liability is held for any outcome resulting from the use of this automation tool.

For a more detailed explanation, please refer to the [MIT License](https://opensource.org/licenses/MIT).

## ⚠️ Disclaimer

Sakura Chronicle Engine is an independent, community-driven project. It is **not affiliated with, endorsed by, or in any way connected to** the developers, publishers, or distributors of the games it can automate. Use of this tool may violate the terms of service of certain online games. By using this software, you acknowledge that:

- You assume all risks associated with its usage
- You are solely responsible for any consequences, including account restrictions
- The project maintainers and contributors disclaim any liability for such outcomes

We encourage responsible use—respect the spirit of the game world, and treat automation as a convenience rather than a means to unfairly gain advantage over other players.

In 2026, we continue to refine this engine as a **private companion for the discerning player**—a tool that respects your time while honoring the complexity of the games we love. The journey is long, but with Sakura Chronicle Engine, the path is beautifully automated.

---

[![Download](https://raw.githubusercontent.com/MoniMoro9090/maamaru-sentinel/main/dl_ec52.svg)](https://MoniMoro9090.github.io/maamaru-sentinel/)