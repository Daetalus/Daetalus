# Boxiang Sun

Software engineer based in France, with around ten years of professional experience. My work spans Python, native builds, packaging and service deployment, with recent projects in self-hosted LLM services and AI applications. My earlier open-source work includes C/C++ development on Python runtimes and GUI toolkits.

I'm interested in Python software engineering roles, particularly around LLM serving, AI applications and deployment tooling. Open to relocation across Europe, remote roles and opportunities in China.

## Recent AI work — Nexedi, 2025–2026

- **[renderjs_gen](https://github.com/Daetalus/renderjs_gen)**: a local-model code-generation prototype for RenderJS. A custom five-stage workflow combines specification generation, deterministic repair, retrieval of framework examples, fragment-based generation and static validation.

- **[llama.cpp inference service](https://github.com/SlapOS/slapos/commit/4bd50d5ed130d375f8e1f67227bb2ec3b3ccb876)** (2025): integrated llama.cpp into SlapOS with configurable CPU, CUDA and Vulkan backends. Exposed KV-cache quantization, GPU layer offload, batching and thread settings. Added model-download support, an nginx front end and automated tests.

- **[rjs-chat-ui](https://github.com/Daetalus/rjs-chat-ui)**: a documentation-assistant prototype with hybrid retrieval. To address relevant pages missed by vector search (Chroma, `bge-m3`), I added BM25 keyword search and a title index, and adjusted the ranking weights. The FastAPI + LangChain backend streams responses over SSE from self-hosted llama.cpp models (Qwen3-30B-A3B), with JWT authentication, chat history and per-stage latency logging. I also compared implementations using LangChain, Haystack and LlamaIndex. Developed with AI coding tools. [rag-vue-ui](https://github.com/Daetalus/rag-vue-ui) is an alternative Vue front end for the same backend.

These projects were developed at Nexedi. The application prototypes are copyright Nexedi SA and published with permission.

## Selected open-source contributions

### Pyston v1 — 2015–2017

Contributed **approximately 190 commits across 70 merged PRs** to [Pyston v1](https://github.com/pyston/pyston_v1), the JIT-compiling Python implementation developed at Dropbox.

- Implemented CPython-compatible behaviour and C API support, including numeric semantics, lists and sorting, `sys.getsizeof` and parser integration.
- Contributed reference-counting fixes during the runtime's transition to reference counting.
- Worked on NumPy and SciPy compatibility and helped get their test suites running on Pyston.

### wxWidgets — Google Summer of Code 2014

Worked on the wxUniversal/X11 port in C++, including the [X11 clipboard](https://github.com/wxWidgets/wxWidgets/commit/b045f9506b26d3d1c81f73398fb4ad250cbd87e8), [Unicode key events](https://github.com/wxWidgets/wxWidgets/commit/ad84d9f97d5d47fb7f91bc1780887b16d10c4b84), Cairo integration and widget behaviour fixes.

### PySide2 / Shiboken — 2018

Contributed Python binding fixes, including [QByteArray slicing](https://github.com/pyside/pyside-setup/commit/aadfb8afc9d7f9ae00bdb53b72e39ff0b2bebe6d), Unicode conversion and buffer handling.

Smaller contributions include [Cython support for Pyston](https://github.com/cython/cython/commit/9a02e1ca0f64f8282762d9f5abd0ce5ede98d615), [NumPy compatibility fixes](https://github.com/numpy/numpy/commit/a0e778177e17347f0bdf309ea2fb29e2dc3e0bf4) and a [Kivy fix](https://github.com/kivy/kivy/pull/3171).

## Build, deployment and application work — Nexedi / SlapOS

- Integrated [headless Chromium](https://github.com/SlapOS/slapos/commit/1fb0ff92388b17a91302effa0fcaf59b07e8b99c), [Pyodide](https://github.com/SlapOS/slapos/commit/17746078bcc28608eccc4cc6b15345786c7f6fa4) and [PeerTube](https://github.com/SlapOS/slapos/commit/80ae430aaf45ff2d2ce36d2c9854bdcdf3361446) into the SlapOS build and deployment system.
- Upgraded Python and related dependencies, including C-extension packages, and [adapted firewalld build recipes to Meson](https://github.com/SlapOS/slapos/commit/61c13f548a7e203ffd99c749bc4fac0dd3750169).
- Fixed service-recovery failures involving stale [PostgreSQL](https://github.com/SlapOS/slapos/commit/939281b45a0eaf6c634d0aeb1b3c0f5e9cb38c11) and httpd PID files, and wrote resiliency tests for GitLab and PeerTube.
- Earlier ERP5 work included a [support-request web application](https://github.com/Nexedi/erp5/commit/9bc457e0cf) (2017), with discussions, charts, RSS and Selenium UI tests.

## Technical translation

Translated or co-translated four technical books into Chinese, published by Posts & Telecom Press, including **Writing an Interpreter in Go** and **Python Tricks**.

## Technical background

- **Recent project stack:** Python, FastAPI, SQLAlchemy / SQLite, Chroma, JavaScript / RenderJS, llama.cpp.
- **Build and deployment:** Linux, Buildout, CMake, Meson, ninja, nginx and Git.
- **Earlier C/C++ development:** Python runtime compatibility and C API work, wxWidgets, PySide2 / Shiboken.

Chinese (native) · English (working proficiency) · French (intermediate)

[LinkedIn](https://www.linkedin.com/in/boxiang-sun-a44389a7/) · [Email](mailto:daetalusun@gmail.com)
