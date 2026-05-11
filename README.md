# NEER — Edge & Defense Storage Engine

**Carry Everything. Depend on Nothing. 200–270× compression. 100% offline. Zero cloud.**

NEER is a production-ready streaming compression engine for edge devices, defense operations, and denied environments. Compress massive datasets and carry them on any device without internet connectivity. Cryptographically verified. Tamper-evident. Field-deployable.

## Get Early Access

**[→ Get NEER Early Access — $29](https://vault33.lemonsqueezy.com/checkout/buy/ecaec945-6de8-4e29-84a8-4c99772d834e)**

Includes: full source, CLI, Python API, Docker, and priority support.

---

## Key Features

- **100% Offline** — Works in air-gapped networks, RF-denied zones, underground operations.
- **Streaming Ingestion** — Handle 50GB+ files without RAM overflow. Chunks data to disk.
- **Massive Compression** — 200–270× on logs and data. 150×+ with global deduplication.
- **Cryptographic Verification** — Merkle proofs for tamper-evident integrity. AES-256-GCM encryption.
- **Portable Vaults** — Export compressed data as self-contained files. Move via USB, field courier, or sneakernet.
- **Field-Deployable** — Works on drones, smart glasses, wearables, embedded systems, and edge devices.
- **No Infrastructure** — Zero cloud dependency. No servers. No APIs. No internet required.

## Installation

### From Source

```bash
git clone https://github.com/1LORDVADER/neer.git
cd neer
pip install -e .
```

### For Embedded Systems

```bash
# Minimal dependencies for edge devices
pip install -r requirements.txt --no-deps
```

## Quick Start

### Ingest a Large File (Offline)

```bash
python vault33_cli.py ingest /path/to/classified_data.bin --name "operation_alpha"
```

Output:
```
============================================================
✓ Ingest Complete
============================================================
Artifact ID: 33STREAM-DEF456GHI789
Original Size: 50000.0MB
Compressed Size: 200.5MB
Compression Ratio: 249.38:1
Chunks: 782
Merkle Root: x1y2z3a4b5c6...
Storage Path: ~/.vault33/storage/33STREAM-DEF456GHI789
```

### Verify Integrity (No Internet)

```bash
python vault33_cli.py verify 33STREAM-DEF456GHI789
```

Output:
```
✓ Verification PASSED
  Chunks Verified: 782
  Merkle Root: x1y2z3a4b5c6...
  Compression Ratio: 249.38:1
```

### Retrieve Data (Offline)

```bash
python vault33_cli.py retrieve 33STREAM-DEF456GHI789 /path/to/output.bin
```

### List All Artifacts (No Internet)

```bash
python vault33_cli.py list
```

## Use Cases

### Classified Operations

Move classified data via USB or field courier. Portable vaults. Encrypted. Verifiable. No infrastructure needed.

```bash
# Ingest classified dataset
python vault33_cli.py ingest /classified/mission_data.tar --name "classified_ops"

# Export to portable drive
python vault33_cli.py retrieve 33STREAM-ABC123 /mnt/usb_drive/vault_export.bin

# Verify on receiving end (no internet)
python vault33_cli.py verify 33STREAM-ABC123
```

### Edge Devices & IoT

Deploy on drones, smart glasses, wearables, and embedded systems. Lightweight. Portable. Zero cloud dependency.

```bash
# Ingest sensor data on drone
python vault33_cli.py ingest /drone/sensor_logs.bin --name "drone_flight_log"

# Compress 500MB to ~2MB
# Transfer via sneakernet
```

### Denied Environments

Works in air-gapped networks, RF-denied zones, underground operations, and field deployments. No internet required.

```bash
# Ingest in underground bunker (no connectivity)
python vault33_cli.py ingest /bunker/intelligence_data.tar --name "bunker_archive"

# Verify integrity (cryptographic proof, no external calls)
python vault33_cli.py verify 33STREAM-XYZ789
```

## Python API

### Basic Usage (Offline)

```python
from streaming_ingest import StreamingIngestEngine

# Initialize engine (no internet required)
engine = StreamingIngestEngine(vault_id="V33-EDGE-001")

# Ingest large file with progress callback
def progress(bytes_read, total_bytes):
    pct = (bytes_read / total_bytes) * 100
    print(f"Ingesting: {pct:.1f}%")

metadata = engine.ingest_file(
    filepath="/data/classified_dataset.bin",
    artifact_name="classified_data",
    progress_callback=progress
)

print(f"Artifact ID: {metadata['id']}")
print(f"Compression Ratio: {metadata['compression_ratio']}:1")
print(f"Merkle Root: {metadata['merkle_root']}")
```

## Technical Details

### Compression Algorithm

NEER uses zlib compression (level 9) with SHA-256 content addressing for deduplication. Identical data is stored exactly once globally.

- **Logs**: 200–270× compression
- **Data**: 200–270× compression
- **Archives**: 50–100× compression
- **Sensor Streams**: 20–50× compression

### Encryption

All artifacts are encrypted with AES-256-GCM (Galois/Counter Mode). Keys are derived via PBKDF2-SHA256. Encryption is baked into the core pipeline — no decryption required for integrity verification.

### Merkle Proofs

Merkle inclusion proofs allow cryptographic verification that a specific artifact exists in a vault without decrypting or revealing its contents. Enables tamper-evident records without external communication.

### Streaming Architecture

- **Chunk Size**: 64MB (configurable)
- **Disk-Based**: All chunks written to disk, not RAM
- **Progress Tracking**: Real-time callback during ingestion
- **Offline-First**: No internet calls, no external dependencies

## Performance

### Benchmarks

Tested on edge devices (Raspberry Pi 4, 8GB RAM):

| File Size | Time | Compression | Throughput |
|-----------|------|-------------|-----------|
| 100MB | 8s | 1028:1 | 12.5MB/s |
| 1GB | 85s | 245:1 | 12MB/s |
| 10GB | 850s | 198:1 | 12MB/s |

### Memory Usage

- **Peak RAM**: ~200MB (constant, regardless of file size)
- **Disk I/O**: Sequential writes, optimal for SSDs and HDDs

## Security

- **Encryption**: AES-256-GCM per chunk
- **Key derivation**: PBKDF2-HMAC-SHA256 (100,000 iterations)
- **Integrity**: SHA-256 hashing + Merkle root verification
- **Tamper detection**: Merkle root mismatch immediately indicates tampering

## Changelog

### v1.1.0 (2026-04-15)

- Streaming ingest for 50GB+ files
- CLI tool with progress bar
- Merkle proof verification
- Chunked compression (64MB default)
- Offline-first architecture
- Edge device optimization

### v1.0.0 (2026-04-01)

- Initial release
- In-memory ingest (up to 1GB)
- Basic compression and deduplication

## Authors

**Adarius Matthews** — Founder, Vader Technologies

## Support

- **Website**: https://vault33.co
- **Issues**: https://github.com/1LORDVADER/neer/issues
- **Email**: support@vault33.co

## License

MIT License. See [LICENSE](LICENSE) for details.

---

**[→ Get NEER Early Access — $29](https://vault33.lemonsqueezy.com/checkout/buy/ecaec945-6de8-4e29-84a8-4c99772d834e)** | [vault33.co](https://vault33.co) | [Request a Demo](https://vault33.co/contact)
