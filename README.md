# Awesome-Edge-Small-Language-Models

# Top Edge & Small Language Models Ecosystem

**Curated List of SaaS Products & Open-Source GitHub Projects**  
*Focused on On-Device SLM Runtimes, Mobile Inference Engines & Edge AI Deployment*  
**Last updated: October 2026**

This repository tracks notable **SaaS platforms** and **open-source projects** for **Edge & Small Language Models (SLMs)**. These tools and models enable running capable language models—typically under 4B parameters—directly on smartphones, PCs, IoT devices, and embedded hardware, eliminating cloud dependency for privacy, latency, and offline operation.

**Examples** include Google Gemini Nano, Apple Intelligence, Qualcomm AI Stack, MediaTek NeuroPilot, Edge Impulse, ONNX Runtime Mobile, TensorFlow Lite (LiteRT), Core ML, ExecuTorch, and MLC LLM (the category leaders).

**Open-source emphasis**: This section is heavily expanded with every major active project for self-hosting, custom model deployment, and transparent edge inference—ideal for developers, embedded engineers, and organizations building sovereign AI on constrained hardware. The open-source SLM landscape spans model families optimized for edge (Gemma, Phi, Qwen, SmolLM), inference runtimes (LiteRT-LM, llama.cpp, MLC LLM), and ultra-compact models for microcontrollers.

Contributions welcome! Open an PR to add/update entries. Keep descriptions factual and link to official sites.

## Table of Contents
- [SaaS/Hosted Platforms](#saas-hosted-platforms)
- [Open-Source GitHub Projects](#open-source-github-projects)
- [How to Contribute](#how-to-contribute)
- [Disclaimer](#disclaimer)

## SaaS/Hosted Platforms

- **[Google Gemini Nano](https://deepmind.google/models/gemini/nano/)**  
  Google's smallest Gemini model tier, integrated into Android devices (Pixel, Samsung) and Chrome for on-device tasks like summarization, smart reply, and proofreading. Not available as a standalone SDK for general developers.

- **[Apple Intelligence (On-Device Foundation Models)](https://developer.apple.com/apple-intelligence/)**  
  Apple's on-device foundation models powering iOS and macOS features. Developers can access limited on-device inference capabilities through Apple's frameworks, with Private Cloud Compute for tasks exceeding local capacity.

- **[Qualcomm AI Stack](https://www.qualcomm.com/developer/software/qualcomm-ai-stack)**  
  Qualcomm's comprehensive SDK for deploying AI models on Snapdragon NPUs, including the Qualcomm AI Engine Direct and Neural Processing SDK. Optimized for Android, Windows, and automotive platforms.

- **[MediaTek NeuroPilot](https://www.mediatek.com/technology/neuropilot)**  
  MediaTek's AI computing platform for Dimensity chipsets, providing NPU acceleration for on-device LLMs and vision models. Integrates with LiteRT and other frameworks for Android deployment .

- **[Edge Impulse](https://www.edgeimpulse.com/)**  
  Commercial edge ML platform with a free Developer Plan. Specializes in TinyML for microcontrollers and edge devices, though less focused on SLMs specifically. Enterprise tiers add dataset management and production licensing.

- **[ONNX Runtime Mobile](https://onnxruntime.ai/)**  
  Microsoft's cross-platform inference engine with a mobile-optimized build for Android, iOS, and embedded devices. Supports SLMs quantized to INT4/INT8 for efficient on-device execution.

## Open-Source GitHub Projects

- **[LiteRT-LM (Google)](https://github.com/google-ai-edge/LiteRT)**  
  Google's dedicated runtime for on-device LLM inference, evolving from TensorFlow Lite. Delivers exceptional performance with Gemma 4 models: 52 tokens/sec decode on Android GPU, 56 tokens/sec on iOS Metal, and up to 76 tokens/sec via WebGPU . Supports NPU acceleration on Qualcomm, MediaTek, and Intel hardware . The standard for deploying Gemma models on mobile and edge devices.

- **[llama.cpp](https://github.com/ggml-org/llama.cpp)**  
  The foundational C/C++ inference engine for LLaMA-family and other SLMs. Supports CPU, GPU (CUDA, Metal, Vulkan), and GGUF quantization across virtually all edge hardware. Powers most local SLM tools and remains the most portable option for custom deployments.

- **[MLC LLM](https://github.com/mlc-ai/mlc-llm)**  
  Universal LLM deployment engine powered by ML compilation. Runs SLMs natively on iOS, Android, Web (WebGPU/WASM), Windows, Linux, and macOS across NVIDIA, AMD, Apple, and Intel GPUs. Provides OpenAI-compatible API via MLCEngine.

- **[ExecuTorch (PyTorch)](https://github.com/pytorch/executorch)**  
  PyTorch's official on-device inference framework for mobile and edge AI. Optimized backends for iOS, Android, and embedded systems. The path for deploying PyTorch-trained SLMs to resource-constrained devices.

- **[MNN (Alibaba)](https://github.com/alibaba/MNN)**  
  Alibaba's lightweight, high-performance inference engine for mobile and embedded devices. Supports LLM inference with quantization and powers many Chinese on-device AI applications.

- **[NCNN (Tencent)](https://github.com/Tencent/ncnn)**  
  Tencent's high-performance neural network inference framework optimized for mobile platforms. Widely used in Android and iOS applications for vision and language model deployment.

- **[atome-lm](https://github.com/TilelliLab/atome-lm)**  
  A ternary, zero-heap tiny language model that runs inside a $2 microcontroller. Apache 2.0 licensed, with bit-exact Python ↔ C99 ↔ Cortex-M3 parity. Checkpoints fit under 100 KB, targeting ESP32-S3, STM32F4, RP2040, and nRF52840 . The extreme edge of SLM deployment.

- **[whisper.cpp](https://github.com/ggml-org/whisper.cpp)**  
  Port of OpenAI's Whisper speech recognition model to C/C++ for CPU-only and embedded inference. Companion to llama.cpp from the same ggml ecosystem, often paired with SLMs for voice-enabled edge applications.

### Notable Edge-Optimized Model Families (Open Weights)

- **[Google Gemma 4 (E2B/E4B)](https://github.com/google-deepmind/gemma)**  
  Google's open-weight models specifically designed for edge deployment. E2B (2B effective params) requires just 1.1 GB on mobile with LiteRT-LM; E4B needs 2.5 GB. Multimodal (text, image, audio), 128K context, and native function calling . The strongest open model family for mobile inference.

- **[Microsoft Phi Family](https://github.com/microsoft/Phi-3CookBook)**  
  Microsoft's SLM series (Phi-3, Phi-3.5, Phi-4) emphasizing high capability at small sizes. MIT licensed. Phi-Silica, the Windows 11 integrated variant, achieves 650 tokens/sec at 1.5W on Copilot+ PC NPUs . Strong for Windows edge deployment and reasoning tasks.

- **[Qwen 2.5 / Qwen3 (Small Variants)](https://github.com/QwenLM/Qwen2.5)**  
  Alibaba's SLM family with 0.5B, 1.5B, 3B, and 4B options. Strong coding, math, and multilingual performance. Apache 2.0 licensed. Qwen3-4B achieves 62% on BFCL agentic benchmarks, though multi-turn accuracy drops to 35% on constrained hardware .

- **[HuggingFace SmolLM2 / SmolLM3](https://github.com/huggingface/smol-models)**  
  Hugging Face's transparent SLM family (135M, 360M, 1.7B, 3B). SmolLM3-3B is fully open with documented training data, config, and evaluation code. Strong reasoning mode and tool calling. Apache 2.0 licensed .

- **[Apple OpenELM](https://github.com/apple/ml-openelm)**  
  Apple's fully open SLM (270M, 450M, 1.1B, 3B) with training data, logs, checkpoints, and configurations released. MLX support for inference on Apple devices . Best for research and Apple silicon exploration.

- **[MiniCPM5-2B (OpenBMB)](https://github.com/OpenBMB/MiniCPM)**  
  2B parameter model ranking #1 among open models under 4B on Artificial Analysis Intelligence Index (score 23). Matches Gemma 4 12B on some benchmarks. Apache 2.0 licensed, 131K context . Exceptional intelligence density for its size.

- **[LittleLamb 0.3B (Multiverse Computing)](https://multiversecomputing.com/resources/introducing-the-littlelamb-0-3b-model-family)**  
  Compressed Qwen3-0.6B variants (0.3B params) with tool-calling and mobile-optimized versions. The Tool-Calling variant achieves 50.67 on BFCL v4 non-thinking, a 74% improvement over the uncompressed base . Purpose-built for sub-300M on-device agents.

### Additional Strong Open-Source Options

- **TinyLlama (1.1B)** — Pre-trained on 3T tokens for edge deployment. Ultra-compact but suffers severe performance collapse on multi-turn agentic tasks (0% on BFCL multi-turn) .
- **xLAM-2-3B** — Salesforce's agentic SLM achieving 65.74% overall and 55.62% multi-turn on BFCL, the best performance in the 1-3B range in recent benchmarks .
- **DeepSeek-R1-Distill-Qwen-1.5B** — 1.5B distilled reasoning model (~1 GB in Q4) with genuine multi-step reasoning capability for math and logic, suitable for Raspberry Pi and embedded devices .
- **Frameworks for building custom systems**: Pair **LiteRT-LM** for Android/iOS SLM deployment with **Gemma 4 E2B/E4B** models. For broader hardware support, use **llama.cpp** with quantized SLMs (Phi, Qwen, SmolLM). For microcontroller-scale deployment, **atome-lm** provides a path to sub-100KB models. Combine with **ExecuTorch** for PyTorch-native mobile pipelines.

## How to Contribute

1. Fork the repo.
2. Add/edit entries in `README.md` (follow existing format).
3. Include: name, link, 1–2 sentence description, and whether it's SaaS or open-source.
4. Submit PR with a short explanation.

Star the repo if you find it useful!

## Disclaimer

- This is a **community-curated** list — not exhaustive and not an endorsement.
- SLM performance on edge hardware varies dramatically by quantization, runtime, and device thermal constraints; benchmark on target hardware before committing.
- Models in the sub-1B range often fail on complex agentic tasks—the 1-3B range is the practical sweet spot for multi-turn tool use .

---

**Made for embedded AI engineers, mobile developers, edge computing architects, and researchers building private, on-device intelligence.**  
Let's make small language models more capable, accessible, and deployable at the edge.
