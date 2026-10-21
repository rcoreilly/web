## Software frameworks

* [Cogent Core](https://cogentcore.org): A cross-platform framework for building powerful, fast, elegant 2D and 3D apps

* [Emergent](https://emersim.org): Neural network simulation infrastructure, built on top of Cogent Core.

* [Axon](https://github.com/emer/axon): Spiking neural network simulation algorithms, used for current models in [compcogneuro.org](https://compcogneuro.org)

See [[zotero]] for usage and configuration of zotero for paper and reference management.

## AI on MacBook Pro

I happen to have an M3 Max chip with 128 GB of ram (always max out your system! sure paid off now given RAM prices!), and can therefore run a decent LLM locally. After sorting through the usual reddit threads etc, here's what I ended up with (Oct, 2026):

* https://github.com/ddalcu/mlx-serve -- because they seem to have the sweet-spot for the best quantized version of the Qwen3.8-Flash-Next model. My trajectory went through: https://lmstudio.ai/ Bionic app (which seemed very slow), then https://omlx.ai/ https://github.com/jundot/omlx which only had a 95Gb version of the model that was too big and caused conflicts with running other apps (install tips: key is to follow the homebrew instructions -- even though I use xcode command line tools, had to reinstall that -- picky. Even so, could not use the `--with-custom-kernel` -- build failed -- no idea what that actually does anyway).

* http://localhost:11234/ (once server is up) has good settings and model download GUI.

* good models: `ddalcu/Qwen3.8-Flash-Next-MLX-Serve-iQ-MLX-4.7bpw` fits in 70Gb, whereas `Qwen3.8-Flash-Next-oQ4e-mtp` takes up 96Gb which was too much, and `Qwen3.8-27B-oQ4e-mtp` which fits in 16Gb, but is less smart and runs more slowly. https://huggingface.co/ddalcu/DeepSeek-V4-Flash-0731-iQ-MLX-3.3bpw does better on the https://arena.ai/leaderboard/agent/code benchmarks, but it takes 105Gb and is therefore not usable. It is also slower.

* Using OpenCode which seems good, and integrates with everything: https://opencode.ai/ https://github.com/anomalyco/opencode -- they should have a new v2 version soon.

* The `mlx-serve launch opencode` or `omlx launch opencode` all seemed to fail (e.g., `OpenCode is not installed. Install: curl -fsSL https://opencode.ai/install | bash` even after I had done that already), so I followed the google AI instructions and just hand-edited the `.json` file below, which worked.

* Some other people recommend https://github.com/beamivalice/sushi (which is a fork of mlx-serve) instead of oMLX -- allows the flash model to be quantized down further for smaller RAM systems. e.g., https://huggingface.co/beamster/Qwen3.8-Flash-Next-Sushi-4bpw is 64Gb. 

* The Flash-Next seems both fast and smart enough to actually be quite usable! I will continue to test it -- not as fast and smart as Claude Opus 5.5 but still it seems reasonably capable.

### OpenCode config file for mlx-server

`~/.config/opencode/ > cat opencode.json`

```json
{
  "provider": {
    "mlx-server": {
      "npm": "@ai-sdk/openai-compatible",
      "name": "mlx-server",
      "options": {
        "baseURL": "http://localhost:11234/v1"
      },
      "models": {
        "Qwen3.8-Flash-Next-MLX-Serve-iQ-MLX-4.7bpw": {
          "name": "Qwen3.8-Flash-Next-MLX-Serve-iQ-MLX-4.7bpw",
          "limit": {
            "context": 262144,
            "output": 65536
          }
        }
      }
    }
  },
  "model": "mlx-server/Qwen3.8-Flash-Next-MLX-Serve-iQ-MLX-4.7bpw"
}
```
