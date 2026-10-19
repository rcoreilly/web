## Software frameworks

* [Cogent Core](https://cogentcore.org): A cross-platform framework for building powerful, fast, elegant 2D and 3D apps

* [Emergent](https://emersim.org): Neural network simulation infrastructure, built on top of Cogent Core.

* [Axon](https://github.com/emer/axon): Spiking neural network simulation algorithms, used for current models in [compcogneuro.org](https://compcogneuro.org)

See [[zotero]] for usage and configuration of zotero for paper and reference management.

## AI on MacBook Pro

I happen to have an M3 Max chip with 128 GB of ram (always max out your system! sure paid off now given RAM prices!), and can therefore run a decent LLM locally. After sorting through the usual reddit threads etc, here's what I ended up with (Oct, 2026):

* https://omlx.ai/ as the local server. key to install is to go to https://github.com/jundot/omlx and follow the homebrew instructions. Even though I use xcode command line tools, had to reinstall that -- picky. Even so, could not use the `--with-custom-kernel` -- build failed -- no idea what that actually does anyway.

* http://localhost:8000/admin/dashboard (once server is up) has good settings and model download GUI.

* good models: `Qwen3.8-Flash-Next-oQ4e-mtp` -- takes up 96Gb, and `Qwen3.8-27B-oQ4e-mtp` which fits in 16Gb, but is less smart and runs more slowly.

* oMLX has a totally useless chat app, with no ability to point it at a directory. Multiple people recommended OpenCode:

* https://opencode.ai/ https://github.com/anomalyco/opencode/tree/v2 has good integration, theoretically..

* You should be able to do this: `omlx launch opencode` but it would only say: `OpenCode is not installed. Install: curl -fsSL https://opencode.ai/install | bash` even after I had done that already..

* So I followed the google AI instructions for how to do it -- see `.json` file below, which worked.

* Some other people recommend https://github.com/beamivalice/sushi instead of oMLX -- allows the flash model to be quantized down further for smaller RAM systems -- will probably have to give that a try too. Benchmarks show it being faster that oMLX. First I used https://lmstudio.ai/ Bionic app, which had a decent GUI, but seemed very slow (using 3.8 27B smaller model). Somehow the larger flash model is faster too!?

* The Flash-Next seems both fast and smart enough to actually be quite usable! I will continue to test it -- not as fast and smart as Claude Opus 5.5 but still it seems reasonably capable.

### OpenCode config file for oMLX:

```json
~/.config/opencode/ > cat opencode.json 
{
  "provider": {
    "omlx": {
      "npm": "@ai-sdk/openai-compatible",
      "name": "oMLX",
      "options": {
        "baseURL": "http://localhost:8000/v1"
      },
      "models": {
        "Qwen3.8-Flash-Next-oQ4e-mtp": {
          "name": "Qwen3.8-Flash-Next-oQ4e-mtp",
          "limit": {
            "context": 262144,
            "output": 65536,
          }
        },
        "Qwen3.8-27B-oQ4e-mtp": {
          "name": "Qwen3.8-27B-oQ4e-mtp",
          "limit": {
            "context": 262144,
            "output": 32768,
          }
        }
      }
    }
  },
  "model": "omlx/Qwen3.8-Flash-Next-oQ4e-mtp"
}
```
