---
"@expo/serve-sim": patch
"expo-device-hub": patch
---

Stream a 60 Hz simulator at 60 fps over the H.264 stream instead of about 45. The frame-rate cap dropped the next on-time frame whenever one landed a few milliseconds late, and the encoder waited for each frame's sample before taking the next, so frames were overwritten whenever encode latency spiked. The cap now keeps to a fixed grid, and up to three frames are encoded at once, still delivered in capture order.
