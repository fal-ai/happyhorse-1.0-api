# HappyHorse-1.0 API

<!-- Replace with actual horse banner image -->
![HappyHorse-1.0](assets/banner.png)

[![fal.ai](https://img.shields.io/badge/Platform-fal.ai-purple.svg)](https://fal.ai/happyhorse)

The #1 ranked AI video generation model on the [Artificial Analysis Video Arena](https://artificialanalysis.ai/video) - outperforming Seedance 2.0, Kling 3.0, Runway, and Pika in blind human preference voting.

**Coming soon to [fal.ai](https://fal.ai/happyhorse).**

## What is HappyHorse-1.0?

HappyHorse-1.0 is an AI video generation model that appeared on the Artificial Analysis Video Arena on April 7, 2026 and immediately took the #1 spot in both text-to-video and image-to-video rankings. The model was submitted pseudonymously - the team behind it has not been independently verified.

What makes it notable: it outperformed models from ByteDance, Kuaishou, Runway, and Pika in blind human preference tests, with no marketing, no press release, and no corporate announcement.

> **Note:** HappyHorse-1.0 does not yet have publicly available weights, a public API, or confirmed pricing. This repo will be updated as access becomes available. [Sign up for updates on fal.ai](https://fal.ai/happyhorse).

---

## Leaderboard Rankings (Confirmed)

These rankings are from the [Artificial Analysis Video Arena](https://artificialanalysis.ai/video), which uses an Elo rating system based on blind human preference votes. Users see two videos from the same prompt without knowing which model made which, and pick the one they prefer.

| Category | Elo Score | Rank |
|---|---|---|
| Text-to-Video (no audio) | 1333 | **#1** |
| Image-to-Video (no audio) | 1392 | **#1** |
| Text-to-Video (with audio) | 1205 | #2 |
| Image-to-Video (with audio) | 1161 | #2 |

The gap over the previous T2V (no audio) leader (Seedance 2.0) is roughly 60 Elo points, meaning HappyHorse wins about 58-59% of head-to-head comparisons. That is a meaningful gap, not noise.

**Caveat:** Elo scores for newly added models are more volatile than established ones. Seedance 2.0 had accumulated over 7,500 votes at the time of HappyHorse's debut. HappyHorse's sample count has not been publicly broken out. Rankings could shift as more votes accumulate.

---

## What We Know vs. What's Claimed

We think it's important to be transparent. There's a lot of information floating around about HappyHorse-1.0, and not all of it has been independently verified.

### Confirmed

- Appeared on Artificial Analysis Video Arena on April 7, 2026 as a pseudonymous submission
- Holds #1 Elo in T2V and I2V (no audio) based on blind human preference votes
- No public weights, API, or pricing exist as of April 9, 2026
- Artificial Analysis confirmed the submission and described it as "pseudonymous"

### Claimed by the Team (Unverified)

The following claims come from HappyHorse-affiliated websites and a press release via ABNewswire. They are specific and internally consistent, but no independent researcher has verified them through hands-on testing.

- **Team:** Built by Zhang Di's Future Life Lab team at Taotian Group (Alibaba). Zhang Di is described as the former VP of Kuaishou and technical lead of Kling AI.
- **Architecture:** 15 billion parameters. 40-layer unified self-attention Transformer. Joint audio-video generation in a single forward pass, no cross-attention modules.
- **Performance:** ~2 seconds for a 5-second clip at 256p. ~38 seconds for 1080p on a single NVIDIA H100.
- **Audio:** Native lip-sync across 7 languages - Mandarin, Cantonese, English, Japanese, Korean, German, and French.
- **Open source:** Described as "fully open source" with "complete commercial licensing." As of April 9, the GitHub and Hugging Face links return 404/401 errors.

### Community Speculation (Not Confirmed)

- Possible connection to the daVinci-MagiHuman project (Sand.ai / GAIR Lab at Shanghai Institute of Intelligent Computing). This is the strongest community theory, based on matching benchmarks and similar capability descriptions.
- Early speculation linked it to WAN 2.7 (Alibaba), but this has not held up on technical grounds.
- Third-party sites have built browser-based tools claiming to use HappyHorse with their own pricing. These are unaffiliated and cannot be verified to be running the same model.

---

## Current Access

As of April 2026, there is **no public API or downloadable model** for HappyHorse-1.0.

**Where you can see it in action:**
- [Artificial Analysis Video Arena](https://artificialanalysis.ai/video) - browse or participate in blind comparisons with the actual model outputs

**Where it will be available:**
- [fal.ai/happyhorse](https://fal.ai/happyhorse) - API access coming soon. Sign up to be notified when deployment is live.

---

## Expected API Usage

Based on what we know about the model's capabilities, this is what API access through fal.ai is expected to look like. **These examples are preliminary and may change.**

### Python

```bash
pip install fal-client
```

```python
import fal_client

# Text-to-Video (expected)
result = fal_client.subscribe(
    "happyhorse/happyhorse-1.0/text-to-video",
    arguments={
        "prompt": "A golden retriever runs through a sunlit wheat field, ears flopping in the wind. Camera tracks alongside at ground level, shallow depth of field, warm afternoon light.",
    },
)

print(result["video"]["url"])
```

### JavaScript

```bash
npm install @fal-ai/client
```

```javascript
import { fal } from "@fal-ai/client";

// Text-to-Video (expected)
const result = await fal.subscribe("happyhorse/happyhorse-1.0/text-to-video", {
  input: {
    prompt:
      "A golden retriever runs through a sunlit wheat field, ears flopping in the wind. Camera tracks alongside at ground level, shallow depth of field, warm afternoon light.",
  },
});

console.log(result.data.video.url);
```

> Endpoint IDs, parameters, and pricing will be confirmed once the model is deployed. [Follow updates on fal.ai](https://fal.ai/happyhorse).

---

## Why This Matters

Even setting aside the unverified claims, the core story is significant. A model with no marketing budget and no corporate announcement entered the most credible blind preference leaderboard for AI video and immediately outperformed models backed by some of the largest technology companies in the world.

The Elo data is not self-reported. The votes came from real users who did not know what they were voting on. Whatever HappyHorse actually is, its video generation produces results that real people prefer over the current commercial leaders in the categories tested.

This suggests the frontier of AI video quality is not exclusively determined by compute budget or brand recognition.

---

## Resources

- [fal.ai - HappyHorse](https://fal.ai/happyhorse) - API access (coming soon)
- [Artificial Analysis Video Arena](https://artificialanalysis.ai/video) - See HappyHorse outputs in blind comparisons
- [fal.ai Documentation](https://docs.fal.ai) - Platform docs
- [Python Client](https://docs.fal.ai/clients/python) - `fal-client` reference
- [JavaScript Client](https://docs.fal.ai/clients/javascript) - `@fal-ai/client` reference

## Disclaimer

HappyHorse-1.0 is developed by an unverified team (claimed to be the Future Life Lab at Taotian Group/Alibaba). This repository contains documentation based on publicly available information from the Artificial Analysis Video Arena and the model's affiliated websites. Claims marked as unverified have not been independently confirmed. [fal.ai](https://fal.ai) will provide API access once the model is available for deployment.
