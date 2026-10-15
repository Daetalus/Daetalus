### Hi, I'm Boxiang Sun 👋

Software engineer based in France. About ten years of Python and C/C++, working mostly below the application layer: Python runtimes and the C API, native builds and packaging, and deploying services on real hardware, lately including LLM inference.

**Currently:** open to roles in AI infrastructure, LLM inference and deployment, and Python/C++ systems engineering, anywhere in Europe (open to relocation) or remote; also open to opportunities in China.

---

#### 🧠 LLM inference deployment

- **[llama.cpp as a SlapOS service](https://github.com/SlapOS/slapos/commit/4bd50d5ed130d375f8e1f67227bb2ec3b3ccb876)** (2025). Packages llama.cpp as a configurable inference service with CPU, CUDA and Vulkan (AMD Ryzen AI Max+) backends. Exposes KV-cache quantization, GPU layer offload, batch/micro-batch and prefill/generation thread settings. Includes a Hugging Face model fetcher with retries and sharded GGUF support (e.g. gpt-oss-120b), an nginx front end and automated tests.

#### 💬 LLM applications (built at Nexedi, 2025–2026; © Nexedi SA, published with permission)

- **[renderjs_gen](https://github.com/Daetalus/renderjs_gen)**. Turns a natural-language request into a working RenderJS gadget (HTML + JS) using a small local model. RenderJS has almost no public training data, so instead of one-shot generation it runs a five-step LangGraph pipeline: LLM spec synthesis → deterministic spec repair → retrieval of framework examples from ChromaDB (EmbeddingGemma) → fragment-by-fragment code generation with deterministic assembly → static validation against framework rules. Served through a llama.cpp endpoint; each step is unit-tested.
- **[rjs-chat-ui](https://github.com/Daetalus/rjs-chat-ui)**. ChatGPT-style assistant over Nexedi's documentation. Hybrid retrieval (Chroma dense search with `bge-m3` + BM25 + a title index that boosts matching pages), answers streamed over SSE from self-hosted llama.cpp models (Qwen3-30B-A3B), JWT accounts and chat history, and per-stage latency profiling. FastAPI + LangChain backend, RenderJS front end. ([Vue version](https://github.com/Daetalus/rag-vue-ui) of the same app.)

#### 🐍 Python runtimes and the C API

- **[Pyston v1](https://github.com/pyston/pyston_v1/pulls?q=is%3Apr+author%3ADaetalus+is%3Amerged)**, Dropbox's JIT-compiling Python implementation (2015–2017). **~190 commits across 70 merged PRs.** Brought CPython behaviour into Pyston: integer, long, float and complex semantics, list and sort, `sys.getsizeof` and the CPython parser. Contributed reference-counting fixes during the runtime's move to refcounting, and worked on getting NumPy and SciPy test suites running on Pyston.
- **[Cython](https://github.com/cython/cython/commit/9a02e1ca0f64f8282762d9f5abd0ce5ede98d615)**: added Pyston support.
- **NumPy**: [Pyston compatibility fix](https://github.com/numpy/numpy/commit/a0e778177e17347f0bdf309ea2fb29e2dc3e0bf4) and a [test helper bug fix](https://github.com/numpy/numpy/commit/7747c3a88cb0cad5687093d1345efcb2743fc1d5).
- **PySide2 / Shiboken** (Qt for Python, 2018): implemented Python slicing and slice assignment for `QByteArray` ([1](https://github.com/pyside/pyside-setup/commit/aadfb8afc9d7f9ae00bdb53b72e39ff0b2bebe6d), [2](https://github.com/pyside/pyside-setup/commit/d16894f9bf9a2dfea1204469bf818a2ca7aeaa38), [3](https://github.com/pyside/pyside-setup/commit/ee8e7117c79f6820cb228e0f0da522ce7d3c1dce)), fixed QString → Python `str` conversion and Unicode handling ([4](https://github.com/pyside/pyside-setup/commit/73fd61d556735c9781847620c511bb43ccae9a95), [5](https://github.com/pyside/pyside-setup/commit/ddbd93680730811a5020b4d429c2e3e11d6823e3)), fixed a `Py_buffer` release bug ([6](https://github.com/pyside/pyside-setup/commit/b8201a3ad2e778ed58cb285369055dc4d0d450bd)) and a Python 3 type-flag issue ([7](https://github.com/pyside/pyside-setup/commit/f16328b8705f39a10216356d3c14f28607f62a72)).
- **wxWidgets: Google Summer of Code 2014, "wxUniv improvements"** (C++). Worked on the wxUniversal/X11 port: [rewrote the X11 clipboard](https://github.com/wxWidgets/wxWidgets/commit/b045f9506b26d3d1c81f73398fb4ad250cbd87e8), [added Unicode key events](https://github.com/wxWidgets/wxWidgets/commit/ad84d9f97d5d47fb7f91bc1780887b16d10c4b84), [enabled Cairo graphics on X11](https://github.com/wxWidgets/wxWidgets/commit/51309ad50aab30e6a98df79d455bdf1dce7596f4), [refactored buttons into a shared wxAnyButton](https://github.com/wxWidgets/wxWidgets/commit/43c99ef613e6aabd9bca5024488854a63a7032b6) and [aligned slider](https://github.com/wxWidgets/wxWidgets/commit/af4f17a553d1c6f764476c74e2d62688507e0a04), list box and text control behaviour with the other ports so the unit tests pass. *(Merged from SVN, so commits show the maintainer as author.)*

#### 📦 Native builds, packaging and service reliability (Nexedi / SlapOS, ~60 commits)

- Ported large native codebases into a reproducible build system: **[headless Chromium](https://github.com/SlapOS/slapos/commit/1fb0ff92388b17a91302effa0fcaf59b07e8b99c)** (GCC toolchain, ninja, X11/ALSA dependencies), **[Pyodide](https://github.com/SlapOS/slapos/commit/17746078bcc28608eccc4cc6b15345786c7f6fa4)** (CPython compiled to WebAssembly) and **[PeerTube](https://github.com/SlapOS/slapos/commit/80ae430aaf45ff2d2ce36d2c9854bdcdf3361446)** (with backup/restore).
- Upgraded Python across a large package stack (3.7, then 3.10/3.12), including C-extension packages, and [migrated components to Meson](https://github.com/SlapOS/slapos/commit/61c13f548a7e203ffd99c749bc4fac0dd3750169).
- **ERP5** (~85 commits): [built a support-request web app](https://github.com/Nexedi/erp5/commit/9bc457e0cf) end to end (2017): [post/discussion module](https://github.com/Nexedi/erp5/commit/bd496547c8), [ECharts wrapper](https://github.com/Nexedi/erp5/commit/1e6b8dc2f5), RSS, offline app cache, faster statistics and worklist queries, and Selenium UI tests.
- Recovery after unclean reboots: fixed stale [PostgreSQL](https://github.com/SlapOS/slapos/commit/939281b45a0eaf6c634d0aeb1b3c0f5e9cb38c11) and [httpd](https://github.com/SlapOS/slapos/commit/ee35dc1c21b7d094dbbfcebf916f0d87233c65ca) PID-file failures. Wrote [resiliency tests for GitLab](https://github.com/SlapOS/slapos/commit/d2e4dc61ada2d80f1833c0935c2b6d5b7ee7a071) and PeerTube.

---

**Languages:** Python · C · C++ · JavaScript  
**Tools:** CMake · Meson · ninja · Buildout · CUDA builds · nginx · PostgreSQL · Git  
**Spoken:** Chinese (native) · English (working proficiency) · French (intermediate, improving)

📫 daetalusun@gmail.com
