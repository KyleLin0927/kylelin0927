## Hi, I'm Kyle (Jen-Kai Lin)

Independent researcher focused on **structurally faithful 3D generation** — building
diffusion-based models that produce 3D content that is not only visually plausible
but also structurally and geometrically consistent with object priors.

I see this as a prerequisite for moving generative 3D from *"looks like"* to *"usable scenes."*

### Research Interest

My current focus is **sampling-time guidance for 3D diffusion models** — how to
enforce structural priors (topology, connectivity, geometric consistency) during the
reverse process, without retraining the denoiser or modifying its architecture.

I view sampling-time guidance as a valuable complement to conditioning-based
control: useful precisely in regimes where paired data is scarce, the constraint is
underdetermined, and naturalness must come from the diffusion prior rather than
from supervision.

### Current Work

🌳 **[CAST — Connectivity-Aware Sampling for Topology](https://github.com/KyleLin0927/cast-gen3d-tree)**

A training-free sampling-time guidance method on a 3D voxel DDPM. A 346K-parameter
topology scorer (trained in 145 seconds) is injected into the reverse process between
t=800 and t=300, raising connectivity success from 6.5% to 30% on Minecraft-style
tree voxel data — without retraining the denoiser or modifying the architecture.

Three findings I find interesting:

- Connectivity failure in 3D generation is a **sampling-dynamics problem**, not a
  model-capacity problem. Successful and failed samples diverge between
  t = 800 and t = 600 (T = 1000) and rarely self-recover afterwards.
- Guidance applied in a **mid-sampling window** passes both connectivity and
  naturalness sanity checks; intervening too early oversimplifies structure,
  intervening too late leaves no room for the prior to restore naturalness.
- A **lightweight, on-demand scorer** is a practical alternative to conditioning-based
  control when data is scarce — control can be split into multiple narrow,
  domain-specific scorers rather than relying on a single general one.

### Directions I Want to Pursue

- Extending CAST to **standard 3D shape benchmarks** (e.g., ShapeNet) with
  cross-category topology metrics.
- Transferring sampling-time geometric guidance from **voxels to 3D Gaussian
  Splatting** and hybrid representations, where failure modes are different.
- The **multi-guidance composition problem** — how to combine multiple narrow
  scorers when their gradients conflict (sum, uncertainty-weighted, projected
  onto compatible subspaces?). This becomes central as soon as guidance scales
  beyond a single objective.

### Long-term Vision

I want to work on **virtual worlds that people can enter and form memories in** —
worlds with enough structural and behavioral consistency to carry exploration,
encounter, and meaning, not just visual appearance.

Current 3D generation tools cannot yet support this vision. The bottleneck is not
rendering or texture quality, but **representations and generative engines that can
produce coherent, physically and structurally consistent worlds**. I would rather
help build that engine than be limited by what existing tools can do.

### Background

- 📚 BSc in Chemistry, National Chung Hsing University (2022). Self-taught ML
  and computer graphics over the past year; implemented every component of CAST
  in PyTorch from the original papers, including DDPM, 3D U-Net, classifier
  guidance, the topology scorer, and the full sampling pipeline.
- 💼 Previously full-stack engineer at Taiwan Mobile (cryptocurrency exchange
  systems) and contributor to **Apache Gravitino**. Comfortable with production
  system design and end-to-end research engineering.
- 🎯 Currently seeking a research assistant position to build a research track
  record before applying for CS master's programs in Fall 2027.

### Contact

📫 kylelin0927@gmail.com  
🔗 [LinkedIn](https://www.linkedin.com/in/jen-kai-lin/)
