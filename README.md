# Hi, I'm Kyle (Jen-Kai Lin)

I work on structurally faithful 3D generation. I build diffusion models that make 3D objects and scenes that look right and are also correct in their structure and geometry.

I see this as the first step for moving generative 3D from "looks like" to "usable scenes."

### My research stance

I think 3D generation needs two signals, and they split by what you can see.

- **Visual signal.** The look, style, and meaning of an object live on the surface. A 3D model trained on little data is usually too weak to do this alone, so appearance should lean on a strong 2D image prior.
Structural signal. Whether the geometry actually holds up often lives in places a 2D prior cannot see. This needs a separate scorer that reads the 3D shape directly.
- **A 2D prior only touches the surface.** Structural correctness lives under it. The two signals can even be different in kind. Visual control can go through SDS, while geometry control can go through sampling-time guidance. How each one enters sampling, and how they combine, is what I study.

### Current Work

🌳 **[CAST — Connectivity-Aware Sampling for Topology](https://github.com/KyleLin0927/cast-gen3d-tree)**

CAST is my proof of concept for the structural half. It is a training-free, sampling-time guidance method on a 3D voxel DDPM. I train the model on Minecraft-style tree data, where structure is easy to see and measure. A small topology scorer (346K parameters, trained in 145 seconds) is added into the reverse process between t=800 and t=300. This raises connectivity success from 6.5% to 30%, with no retraining of the denoiser and no change to its architecture.

### Directions I Want to Pursue

- Map where 2D priors fail on structure. I think a 2D prior cannot judge structure it cannot see, but I want to measure how far that goes. I will take 3D objects with clear structure, break them in controlled ways, and check whether a 2D prior reacts.
- Combine appearance and structure signals. CAST uses only a geometry scorer right now. The next step is to pair it with a domain-aligned 2D prior, so geometry keeps the structure correct while the 2D prior handles style and texture.

### Long-term Vision

I want to build virtual worlds that people can walk into and remember. Not a picture you look at from outside, but a place you can step into, explore, and find meaning in.

For that, a world has to be made of real structure, not something that only looks right from one angle. Today's tools cannot do this yet. The limit is not rendering or texture. It is that we still lack representations and engines that can build worlds that hold together. I would rather help build that engine than be stuck with what current tools allow.

So here is the real goal behind all of it: use AI and Gen 3D to build new worlds, and one day become a Pokémon Trainer in one of them.

### Contact

📫 kylelin0927@gmail.com  
🔗 [LinkedIn](https://www.linkedin.com/in/jen-kai-lin/)
