# SageAttention UltraViCo for AMD (ROCm)
This is a standalone port of the SageAttention kernels used in UltraVico, modified to run on AMD hardware.

## View Changes
You can see the exact modifications made for AMD compatibility [here](https://github.com/0xDELUXA/ComfyUI-WanVideoWrapper-ultravico_AMD/compare/c10df4ee03fdcc0e49d129671dc5629207974e38...main).

### Technical Changes:
- **Block sizes reduced** for better ROCm compatibility:
  - `BLKQ`: 128 → 64, `BLKK`: 64 → 32
  - `BLOCK_M`: 128 → 64, `BLOCK_N`: 64 → 32
- **Numerical Stability:** Kept accumulation in `float32`.
- **Optimization:** Triton autotuning added.

## Installation (PowerShell)
<pre>
cd ComfyUI/custom_nodes/ComfyUI-WanVideoWrapper/ultravico/
Remove-Item -Recurse -Force sageattn
git clone https://github.com/0xDELUXA/ComfyUI-WanVideoWrapper-ultravico_AMD sageattn
</pre>
