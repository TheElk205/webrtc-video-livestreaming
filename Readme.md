**Push URL for OBS:** `rtmp://your-server:1935/live/stream`
**WHEP URL for browser:** `http://your-server:8889/live/stream/whep`

---

## 3. Recording details

MediaMTX records the **raw incoming stream** — no re-encoding, zero CPU cost.

| Format | Notes |
|---|---|
| `fmp4` | Fragmented MP4 — survives crashes, seekable, recommended |
| `mpegts` | MPEG-TS — simpler, universal compatibility |

Files land in `/recordings/live/stream/2025-01-15_14-30-00.mp4` automatically. Segments roll every hour (configurable).

---

## 4. Firewall ports
```
1935/tcp   — RTMP ingest
8889/tcp   — WebRTC signaling (HTTPS in prod)
8888/tcp   — HLS fallback
9997/tcp   — API
8189/udp   — WebRTC media (UDP, must be open!)
```