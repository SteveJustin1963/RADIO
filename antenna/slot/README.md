# Slot Antennas

A slot antenna is formed by cutting a narrow rectangular opening (slot) into a flat conducting surface. RF energy applied across the slot radiates from both faces of the conductor. Simple, low-profile, and easily integrated into metal enclosures, PCBs, or waveguide structures.

---

## Physics

### Babinet's Principle

A slot antenna is the electromagnetic complement of a dipole. Booker (1946) extended Babinet's optical theorem to antennas:

```
Z_slot × Z_dipole = η²/4 ≈ 35,511 Ω²    (η = 377 Ω)
```

For a resonant half-wave dipole (Z_dipole ≈ 73 Ω):

```
Z_slot ≈ 35,511 / 73 ≈ 486 Ω   (center-fed, resonant)
```

This high impedance is the central challenge of slot antenna matching.

### Polarisation

**Slot polarisation is orthogonal to the complementary dipole of the same orientation.**

| Slot orientation | E-field direction | Polarisation |
|-----------------|-------------------|--------------|
| Horizontal slot | Vertical          | Vertical     |
| Vertical slot   | Horizontal        | Horizontal   |

This is a common source of errors — the polarisation is rotated 90° from what you might expect.

### Radiation

- A slot in an infinite ground plane radiates bidirectionally (front and back), identical pattern to a half-wave dipole but with swapped E/H fields
- Theoretical gain: ~2.15 dBi per face
- Add a metal cavity behind the slot for unidirectional radiation

---

## Resonant Dimensions

### Slot Length (dominant parameter)

```
L = (c / 2f_r) × k_shorten        k_shorten ≈ 0.95–0.98 (free space)
```

With a dielectric substrate on one side:

```
ε_eff = (ε_r + 1) / 2
L ≈ c / (2 × f_r × √ε_eff)
```

**Common frequencies:**

| Frequency | Free-space λ | Slot length (k=0.97) |
|-----------|-------------|----------------------|
| 433 MHz   | 692 mm      | 336 mm               |
| 915 MHz   | 328 mm      | 159 mm               |
| 2.4 GHz   | 125 mm      | 60.7 mm              |
| 5.8 GHz   | 51.7 mm     | 25.1 mm              |
| 10 GHz    | 30 mm       | 14.6 mm              |
| 24 GHz    | 12.5 mm     | 6.1 mm               |
| 77 GHz    | 3.9 mm      | 1.9 mm               |

### Slot Width

- Typical: W/L = 1/10 to 1/20 (narrow, high-Q, narrow bandwidth)
- Wide-slot: W/L ≈ 1/5 or more (lower Q, broader bandwidth)
- Rough bandwidth estimate: BW ≈ (W/L) × 100%

### Feed Point Offset for 50 Ω Match

The impedance follows a cosine-squared law along the slot:

```
R_in(x) ≈ 486 × cos²(πx / L)
```

where x is distance from the slot centre. To reach 50 Ω:

```
x_offset ≈ 0.105 × L   from the midpoint  (≈ 21% of half-slot-length from centre)
```

---

## Types

| Type | Key Feature | Gain | Bandwidth |
|------|-------------|------|-----------|
| Half-wave slot in ground plane | Simplest; bidirectional | 2 dBi | ~5–15% |
| Cavity-backed slot | Unidirectional | 2–6 dBi | ~5–15% |
| Slotted waveguide | Array of slots in waveguide wall; high gain | 15–30+ dBi | ~5–10% per slot |
| Microstrip-fed slot | PCB-integrated, aperture coupled | 2–4 dBi | ~5–20% |
| CPW-fed slot | All-on-one-layer construction | 2–6 dBi | up to UWB |
| Bow-tie slot | Wide bandwidth | 2–4 dBi | 50–100%+ |
| Annular/ring slot | Multi-mode, compact | 3–5 dBi | design-dependent |
| SIW slot | PCB waveguide, mm-wave | 10–35 dBi | ~5–15% |

---

## Feed Methods

### Coaxial Probe
- Inner conductor bridges the slot gap, outer braid connects to ground plane
- Position along slot sets impedance — offset by ~21% of half-length from centre for 50 Ω
- Practical up to ~6 GHz

### Microstrip (Aperture-Coupled)
- Microstrip on one PCB face, slot in ground plane on opposite face
- Microstrip crosses slot at 90°; open-circuit stub on far side tunes reactance
- No via required; feed and radiator are isolated by the substrate

### CPW Feed
- Centre conductor + ground planes all on same PCB layer
- Fully planar; no vias
- 50 Ω CPW geometry (FR4, h=1.6 mm): strip W ≈ 3 mm, gap g ≈ 0.3 mm
- U-shaped or arc tuning stubs achieve wide/UWB bandwidth

### Waveguide
- Slot in waveguide wall excited by TE10 mode currents
- Coupling controlled by slot offset from centreline or tilt angle
- Low loss, high power handling

---

## Substrates / Materials

| Material | ε_r | tan δ | Max useful freq | Notes |
|----------|-----|-------|-----------------|-------|
| FR4      | 4.2–4.8 | 0.02 | ~6 GHz | Cheap; lossy above 5 GHz |
| Rogers RO4003C | 3.55 | 0.0027 | 30+ GHz | Standard microwave substrate |
| Rogers RO4350B | 3.66 | 0.0037 | 30+ GHz | Slightly cheaper than 4003C |
| RT/duroid 5880 | 2.2 | 0.0009 | 50+ GHz | Very low loss, PTFE-based |
| Copper sheet/foil | — | — | DC–100+ GHz | No substrate; free-space slot |

---

## Applications

| Domain | Frequency | Slot Type |
|--------|-----------|-----------|
| Marine / airborne radar | 9–10 GHz | Slotted waveguide array |
| Automotive radar | 76–81 GHz | SIW slot array |
| WiFi (hidden in metal case) | 2.4 / 5.8 GHz | PCB or foil slot |
| UHF RFID reader | 865–928 MHz | CPW slot on FR4 |
| Aircraft transponder | 1030/1090 MHz | Fuselage-flush slot |
| 5G mmWave | 28, 39, 60 GHz | SIW phased array |
| Ground-penetrating radar | 0.1–2 GHz | CPW bow-tie slot |
| ISM telemetry | 433 / 868 / 915 MHz | Simple slot, foil tape |

---

## Simulation Tools

| Tool | Method | Cost | Best For |
|------|--------|------|----------|
| OpenEMS + Octave | FDTD | Free | Broadband, PCB slots; scripted workflow |
| NEC2 / xnec2c | MoM | Free | Free-space metal-only slots |
| HFSS | FEM | Commercial | Complex geometry, dielectrics |
| CST Studio | FIT/FDTD | Commercial | Fast broadband sweeps, arrays |
| FEKO | MoM+PO | Commercial | Electrically large structures |

OpenEMS is the recommended free tool for this workflow — it integrates with GNU Octave and runs on Linux.

---

## Key Metrics (what to measure)

| Metric | Target | Instrument |
|--------|--------|------------|
| Return loss (S11) | < −10 dB at operating frequency | VNA |
| VSWR | < 2:1 (pass); < 1.5:1 (good) | VNA |
| Resonant frequency | Within ±2% of design | VNA |
| Bandwidth (−10 dB) | Meets system requirement | VNA |
| Gain | Matches simulation | Gain comparison method |
| Polarisation | Correct orientation | Link test with reference |

---

## Files in This Directory

| File | Contents |
|------|----------|
| `README.md` | This file — theory, types, parameters, reference |
| `HOWTO.md` | Step-by-step: design, build, simulate, test |
