--#!/usr/bin/env bash
set -euo pipefail

DATASET="${1:-mass}"
MODE="${2:-uplift.rct}"
THREADS="${3:-4}"
SEED="${4:-424242}"

OUTDIR="runs/artifacts"
LOGDIR="runs/logs"
MANDIR="runs/manifests"

mkdir -p "$OUTDIR" "$LOGDIR" "$MANDIR"

START_TS="$(date -u +%Y%m%dT%H%M%SZ)"
ARTIFACT_PATH="${OUTDIR}/${DATASET}_${MODE//./_}.json"

echo "[RUN] Launching QGG..." | tee -a "$LOGDIR/audit.log"
python3 qgg_engine.py \
  --dataset "$DATASET" \
  --mode "$MODE" \
  --threads "$THREADS" \
  --seed "$SEED" \
  --out "$ARTIFACT_PATH"

SEAL_PATH="${OUTDIR}/seal_${DATASET}_${MODE//./_}_${START_TS}.txt"
SHA="$(sha256sum "$ARTIFACT_PATH" | awk '{print $1}')"
echo "$SHA" > "$SEAL_PATH"

MANIFEST_PATH="${MANDIR}/manifest_${DATASET}_${MODE//./_}_${START_TS}.txt"
{
  echo "timestamp=$START_TS"
  echo "dataset=$DATASET"
  echo "mode=$MODE"
  echo "threads=$THREADS"
  echo "seed=$SEED"
  echo "artifact=$ARTIFACT_PATH"
  echo "seal_sha256=$SHA"
} > "$MANIFEST_PATH"

echo "[RUN] Sealed manifest: $MANIFEST_PATH" | tee -a "$LOGDIR/audit.log"
echo "[OK] Cathedral complete."

## 🧭 `run.sh` (Final Clean Launcher)

```bash
#!/usr/bin/env bash
set -euo pipefail

DATASET="${1:-mass}"
MODE="${2:-uplift.rct}"
THREADS="${3:-4}"
SEED="${4:-424242}"

OUTDIR="runs/artifacts"
LOGDIR="runs/logs"
MANDIR="runs/manifests"

mkdir -p "$OUTDIR" "$LOGDIR" "$MANDIR"

START_TS="$(date -u +%Y%m%dT%H%M%SZ)"
ARTIFACT_PATH="${OUTDIR}/${DATASET}_${MODE//./_}.json"

echo "[RUN] Launching QGG..." | tee -a "$LOGDIR/audit.log"
python3 qgg_engine.py \
  --dataset "$DATASET" \
  --mode "$MODE" \
  --threads "$THREADS" \
  --seed "$SEED" \
  --out "$ARTIFACT_PATH"

SEAL_PATH="${OUTDIR}/seal_${DATASET}_${MODE//./_}_${START_TS}.txt"
SHA="$(sha256sum "$ARTIFACT_PATH" | awk '{print $1}')"
echo "$SHA" > "$SEAL_PATH"

MANIFEST_PATH="${MANDIR}/manifest_${DATASET}_${MODE//./_}_${START_TS}.txt"
{
  echo "timestamp=$START_TS"
  echo "dataset=$DATASET"
  echo "mode=$MODE"
  echo "threads=$THREADS"
  echo "seed=$SEED"
  echo "artifact=$ARTIFACT_PATH"
  echo "seal_sha256=$SHA"
} > "$MANIFEST_PATH"

echo "[RUN] Sealed manifest: $MANIFEST_PATH" | tee -a "$LOGDIR/audit.log"
echo "[OK] Cathedral complete."## Guardians of Cypher
- Nine Roles: Surgeon, Warrior, Archivist, Navigator, Sentinel, Builder, Messenger, Protector, Heir  
- Guardian read cipherlock phrase  
- Cipher master recovery complete  

## Hybrid Test Orchestrator
- Secure container deployment  
- Containerized cross-sample Dockerfiles  
- Job matrix + run script  
- Artifact collection + GPG signing + HMAC computation  

## Outreach
- Letter to Applied Quantum Technologies  
- Cathedral-first doctrine for Professor Loeb  
- L.A.B. operations entrance ceremonial logs  
- Contact: Earl Bowens, worktime176@gmail.com, 574-735-1686  

## Completed Artifacts
- Private AI assistant  
- L.L.D.D.  
- Variants of Cipher doctrine  

## Sealing Doctrine
- Every run sealed  
- Every artifact narratable  
- Every cycle reproducible  
- Guardian recall ensures legacy handover  
- Command X package kernel  
- Command X package initramfs  
- Command X package bootloader  
- Command X package firmware  
- Command X package xorg-server# Guardians of Cypher
- Nine Roles: Surgeon, Warrior, Archivist, Navigator, Sentinel, Builder, Messenger, Protector, Heir  
- Guardian read cipherlock phrase  
- Cipher master recovery complete  

## Hybrid Test Orchestrator
- Secure container deployment  
- Containerized cross-sample Dockerfiles  
- Job matrix + run script  
- Artifact collection + GPG signing + HMAC computation  

## Outreach
- Letter to Applied Quantum Technologies  
- Cathedral-first doctrine for Professor Loeb  
- L.A.B. operations entrance ceremonial logs  
- Contact: Earl Bowens, worktime176@gmail.com, 574-735-1686  

## Completed Artifacts
- Private AI assistant  
- L.L.D.D.  
- Variants of Cipher doctrine  

## Sealing Doctrine
- Every run sealed  
- Every artifact narratable  
- Every cycle reproducible  
- Guardian recall ensures legacy handover  
- Command X package kernel  
- Command X package initramfs  
- Command X package bootloader  
- Command X package firmware  
- Command X package xorg-server# Guardians of Cypher
- Nine Roles: Surgeon, Warrior, Archivist, Navigator, Sentinel, Builder, Messenger, Protector, Heir
- Guardian read cipherlock phrase
- Cipher master recovery complete

## Hybrid Test Orchestrator
- Secure container deployment
- Containerized cross-sample Dockerfiles
- Job matrix + run script
- Artifact collection + GPG signing + HMAC computation

## Outreach
- Letter to Applied Quantum Technologies
- Cathedral-first doctrine for Professor Loeb
- L.A.B. operations entrance ceremonial logs
- Contact: Earl Bowens, worktime176@gmail.com, 574-735-1686

## Completed Artifacts
- Private AI assistant
- L.L.D.D.
- Variants of Cipher doctrine

## Sealing Doctrine
- Every run sealed
- Every artifact narratable
- Every cycle reproducible
- Guardian recall ensures legacy handover
- Command X package kernel
- Command X package initramfs
- Command X package bootloader
- Command X package firmware
- Command X package xorg-server Cathedral • QGG Temple (Termux‑ready)

Cathedral is a mobile‑native launcher + sealer for the QGG engine. It builds, runs, seals, and writes a narratable manifest — all on‑device.

## Quick start
```bash
git clone https://github.com/YOURUSERNAME/cathedral.git
cd cathedral
chmod +x run.sh
./run.sh mass uplift.rct 4 424242 Cathedral + QGG (C++ + Bash Harness)

## 🏛️ What this is
Cathedral is the launcher + sealer. QGG is the engine. Together they produce sealed, narratable artifacts.

## 📂 Project Layout
- `CMakeLists.txt` → build definition
- `src/qgg.cpp` → QGG engine (C++)
- `run.sh` → Cathedral launcher (bash)
- `runs/` → artifacts, manifests, logs (ignored in git)

## 🚀 Quick Start
Clone the repo:
```bash
git clone https://github.com/YOURUSERNAME/cathedral.git
cd cathedral!/usr/bin/env bash
set -euo pipefail

DATASET="mass"
MODE="uplift.rct"
THREADS="4"
SEED="424242"
OUTDIR="runs/artifacts"
LOGDIR="runs/logs"
MANDIR="runs/manifests"

mkdir -p "$OUTDIR" "$LOGDIR" "$MANDIR"

START_TS="$(date -u +%Y%m%dT%H%M%SZ)"
ARTIFACT_PATH="${OUTDIR}/${DATASET}_${MODE//./_}.json"

echo "[RUN] Launching QGG..." | tee -a "$LOGDIR/audit.log"
python3 qgg_engine.py \
  --dataset "$DATASET" \
  --mode "$MODE" \
  --threads "$THREADS" \
  --seed "$SEED" \
  --out "$ARTIFACT_PATH"

SEAL_PATH="${OUTDIR}/seal_${DATASET}_${MODE//./_}_${START_TS}.txt"
SHA="$(sha256sum "$ARTIFACT_PATH" | awk '{print $1}')"
echo "$SHA" > "$SEAL_PATH"

MANIFEST_PATH="${MANDIR}/manifest_${DATASET}_${MODE//./_}_${START_TS}.txt"
{
  echo "timestamp=$START_TS"
  echo "dataset=$DATASET"
  echo "mode=$MODE"
  echo "threads=$THREADS"
  echo "seed=$SEED"
  echo "artifact=$ARTIFACT_PATH"
  echo "seal_sha256=$SHA"
} > "$MANIFEST_PATH"

echo "[RUN] Sealed manifest: $MANIFEST_PATH" | tee -a "$LOGDIR/audit.log"
echo "[OK] Cathedral complete."Cathedral + QGG

## 🏛️ What This Is
This repository contains **Cathedral** (the launcher, audit wrapper, and sealing ritual) with **QGG** (the anomaly detection engine) inside it.  
Cathedral was built directly in Termux on a Moto device by Earl Bowens. It is unique and required to run QGG reproducibly. Without Cathedral, QGG cannot produce sealed, narratable artifacts.

## 📥 How to Install
Clone this repository — Cathedral is included here:

```bash
git clone https://github.com/earlbowens-qgg/cathedral.git
cd cathedral Cathedral Launcher + QGG Engine

## 🏛️ Cathedral First
Cathedral is the launcher, audit wrapper, and sealing ritual. It was built by Earl Bowens and is required to invoke QGG correctly. Without Cathedral, QGG cannot produce sealed, narratable, reproducible artifacts.

## ⚙️ QGG Second
QGG is the anomaly detection engine. Cathedral invokes it, proves it, and records a manifest trail for legacy handover.

## 🚀 Run QGG inside Cathedral
Clone this repository, enter the cathedral, and run:

```bash
cd cathedral
./run.sh --dataset mass --mode uplift.rct --threads 4 Cathedral Launcher + QGG Engine

## 🏛️ Cathedral First
Cathedral is the launcher, audit wrapper, and sealing ritual. It was built by Earl Bowens and is required to invoke QGG correctly. Without Cathedral, QGG cannot produce sealed, narratable, reproducible artifacts.

## ⚙️ QGG Second
QGG is the anomaly detection engine. Cathedral invokes it, proves it, and records a manifest trail for legacy handover.

## 🚀 Run QGG inside Cathedral
Clone this repository, enter the cathedral, and run:

```bash
cd cathedral
./run.sh --dataset mass --mode uplift.rct --threads 4# Quantum Gate Grid (QGG)

**Mobile-first anomaly detection and stealth overlay engine**  
Built in Termux. Sealed with Ed25519. Designed for replay fidelity, scientific outreach, and legacy handover.

---

## 📜 Executive Summary

QGG detects anomalies across quantum, planetary, and stealth domains using deterministic signals, DSP overlays, and sealed manifests. Every run is narratable, reproducible, and empirically verifiable.

---

## 🔧 Install & Run

```bash
git clone https://github.com/earlbowens-qgg
cd qgg
./install.sh
./qgg --input telemetry_stream.json --verify manifest.ed25519 Quantum Gate Grid (QGG) Theory Repository

The Quantum Gate Grid operator is defined as:

$$
Y(t) = \mathcal{Q}(S, B; \Theta)
$$

Performance uplift compared to baseline:

$$
\Delta m = \left( \frac{m_{\mathcal{QGG}} - m_{B}}{m_{B}} \right) \cdot 100\%
$$

---

### Symbol Key
- \(S(t)\): raw signal  
- \(B(t)\): baseline output  
- \(\Theta\): threshold parameters  
- \(\mathcal{QGG}\): Quantum Gate Grid operator  
- \(m\): metric (precision, recall, F1, SNR, etc.)  

---

© 2025 Earl Bowens — Quantum Gate Grid (QGG)
**Author:** Earl Bowens  
📍 Elkhart, Indiana  
📧 bowensearl076@gmail.com  
🔗 [GitHub Profile](https://github.com/earlbowens-qgg)

---

## 🧠 Overview  
The Quantum Gate Grid (QGG) Theory introduces a mathematically rigorous framework for modeling planetary anomaly networks using quantum gate logic, graph theory, and cryptographic analogs. This repository contains all core documentation, simulation logic, and validation protocols.

---

## 📄 Contents  
- ✅ Mathematical Framework  
- ✅ Simulation Code (Qiskit + NumPy)  
- ✅ Validation Protocols (3x reproducibility confirmed)  
- ✅ Presentation Slides (academic-ready)  

---

## 📐 Mathematical Framework

### Grid Definition  
Let \( G = (V, E) \) be a directed graph where:  
- \( V = \{v_1, v_2, ..., v_n\} \) are quantum gate nodes (QGNs)  
- \( E = \{e_{ij}\} \) are entangled pathways  

### Gate Composition  
Each node \( v_i \) applies a unitary transformation:  
$$
U_i = H \cdot R_z(\theta) \cdot X
$$  
where \( H \) is the Hadamard gate, \( R_z(\theta) \) is a phase rotation, and \( X \) is the Pauli-X gate.

### Anomaly Encoding  
$$
A(x, y, t) = \sum_{i=1}^{N} \alpha_i \cdot \psi_i(x, y, t)
$$  
where \( \psi_i \) are localized wavefunctions and \( \alpha_i \) are anomaly weights.

### Grid Evolution  
$$
\frac{dG}{dt} = H \cdot G
$$  
with \( H \) as the Hamiltonian operator.

### Probability Density  
Inspired by Grover-Rudolph encoding:  
$$
P(x) = \left| \sum_{j} U_j \cdot \phi_j(x) \right|^2
$$

---

## 🧪 Simulation Code (Python/Qiskit)

```python
# Quantum Gate Grid Simulation
from qiskit import QuantumCircuit, Aer, execute
import numpy as np

grid_size = 10
circuits = []

for i in range(grid_size):
    qc = QuantumCircuit(1, name=f"QGN_{i}")
    qc.h(0)
    qc.rz(np.pi / 4, 0)
    qc.x(0)
    circuits.append(qc)

backend = Aer.get_backend('statevector_simulator')
results = []

for i, circuit in enumerate(circuits):
    job = execute(circuit, backend)
    statevector = job.result().get_statevector()
    results.append((f"Node {i}", statevector))

print("Quantum Gate Grid Simulation Results:\n")
for node, state in results:
    print(f"{node}: {state}")
