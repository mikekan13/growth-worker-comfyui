# growth-worker-comfyui

This is a build of [runpod-workers/worker-comfyui](https://github.com/runpod-workers/worker-comfyui) **5.11.0**, vendored unchanged except for building with **`COMFYUI_VERSION=0.39.0`** (instead of upstream's 0.34.0), for the GROWTH project.

ComfyUI >= 0.37 is needed for Qwen-Image-2.1 (`TextEncodeQwenImage21`, `QwenImage21Cache`).

- Image: `ghcr.io/mikekan13/growth-worker-comfyui:5.11.0-comfy0.39.0` (the `-base` flavor: no baked models; models come from the network volume at `/runpod-volume/models/...`)
- Built by `.github/workflows/build.yml` on GitHub Actions (Dockerfile target `base`, `CUDA_VERSION_FOR_COMFY=12.8`).
- The installed ComfyUI version is written to `/comfyui-version.txt` inside the image.

Changes from upstream 5.11.0:
- `Dockerfile`: default `COMFYUI_VERSION` 0.39.0; extra `RUN` that writes `/comfyui-version.txt` and echoes ComfyUI/torch versions.
- Upstream `.github/workflows/*` replaced by a single GHCR build workflow.
- Upstream README kept as `README.upstream.md`. License: upstream `LICENSE` (unchanged).
