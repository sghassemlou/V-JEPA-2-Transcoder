# V-JEPA 2 Transcoder

Interactive feature viewer and pretrained weights for
**"V-JEPA 2 Video Transcoders Find Motion-Based Features"**
(Ghassemlou & Joseph, 1st IJCAI Workshop on Safe Physical AI, 2026).

We train **archetypal sparse transcoders** on the block-10 FFN of a frozen
**V-JEPA 2.1 ViT-B/16 384px** video encoder --> to our knowledge the first sparse
transcoder decomposition of a self-supervised *video* model's internal features. The headline
model reaches held-out explained variance 0.480 at L0 ≈ 59, and surfaces
motion-aligned features that track a common motion primitive across different
object identities.

## Interactive feature viewer

[`decent-sweep-5_viewer.html`](decent-sweep-5_viewer.html) is a self-contained
viewer for the headline model's discovered features --> each feature's top-activating
Something-Something-v2 clips, with the spatiotemporal `(t, h, w)` locations marked.
All images are embedded, so it works offline in any browser.

**How to view it:**

- **Download and open:** on the file's page above, click **"Download raw file"**,
  then open the downloaded `decent-sweep-5_viewer.html` in any web browser. No
  internet connection required.
- **Live (optional):** if GitHub Pages is enabled for this repo
  (Settings → Pages → deploy from `main`), it renders at
  `https://sghassemlou.github.io/V-JEPA-2-Transcoder/decent-sweep-5_viewer.html`.

## Pretrained weights

The headline checkpoint (held-out EV 0.480, L0 59) and the random-init
control baseline are released on Hugging Face, with a model card, `config.json`,
the model class, and a loading example:

### 🤗 https://huggingface.co/sghassemlou/vjepa2-archetypal-transcoder

The K-means archetype pool is bundled inside the weights, so the decoder is
self-contained. Note that the transcoder operates on V-JEPA 2.1 block-10 FFN
activations --> see the model card for the exact substrate, hook site, and
preprocessing needed to use it.

## Citation

```bibtex
@inproceedings{ghassemlou2026vjepa2transcoder,
  title     = {V-JEPA 2 Video Transcoders Find Motion-Based Features},
  author    = {Ghassemlou, Susan Soraya Afshar and Joseph, Sonia},
  booktitle = {1st IJCAI Workshop on Safe Physical AI},
  year      = {2026}
}
```
