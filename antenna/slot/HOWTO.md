  README.md — Reference document covering:
  
  - Physics (Babinet's principle, polarisation, radiation)
  
  - Resonant dimension formulas and frequency table (433 MHz → 77 GHz)
  
  - All slot types, feed methods, substrates, applications
  
  - Simulation tools summary and key test metrics
  
                                                                                                                                                                
  HOWTO.md — Practical step-by-step guide covering:
  
  1. Design — slot length/width calculations with worked examples, impedance matching, feed offset formula, cavity sizing
  2. Build — four construction methods: copper sheet, adhesive foil tape, PCB, slotted waveguide
  3. Simulate — OpenEMS + Octave structural example for a CPW-fed slot, what to look for in results
  4. Test — VNA calibration, S11 measurement, interpreting Smith chart, ferrite choke (essential), pattern measurement
  5. Tune — length/frequency adjustment, stub tuning, lumped capacitor miniaturisation
  6. Quick-start — complete 2.4 GHz foil tape slot build walkthrough
  7. Pre-flight checklist before first RF test
  
                                                                                                                                                                
  Key things to remember: slot polarisation is 90° rotated from what's intuitive, center-fed slot impedance is ~486 Ω (not 50 Ω — offset the feed), and ferrite 
  choke on the feed cable is non-negotiable for accurate measurements.
  
                                                                  


//////////////////////////////////////////////////////////////////////////






# Slot Antenna HOWTO

Step-by-step: design, build, simulate, and test a slot antenna from scratch.

---

## 1. Design

### Step 1 — Pick your frequency and substrate

Decide:
- Target frequency f_r
- Form factor: free-space metal plate, PCB, copper foil on backing board, waveguide

**Substrate choice:**
- Sub-6 GHz, cheap: FR4 (ε_r ≈ 4.4)
- Sub-30 GHz, accurate: Rogers RO4003C (ε_r = 3.55)
- Free space / hand-built: copper sheet, brass, or adhesive copper foil tape

### Step 2 — Calculate slot length

**Free-space slot (copper sheet or foil, no dielectric):**
```
L = (c / 2f_r) × 0.97
c = 3×10⁸ m/s
```

**PCB slot with substrate on one side (microstrip or CPW feed):**
```
ε_eff = (ε_r + 1) / 2
L = c / (2 × f_r × √ε_eff)
```

**Example — 2.4 GHz, free space:**
```
L = (3×10⁸ / (2 × 2.4×10⁹)) × 0.97
L = 0.0625 × 0.97 = 0.0606 m = 60.6 mm
```

**Example — 2.4 GHz, FR4 (ε_r=4.4):**
```
ε_eff = (4.4 + 1) / 2 = 2.7
L = 3×10⁸ / (2 × 2.4×10⁹ × √2.7) = 0.0379 m = 37.9 mm
```

Start your slot 2–5% shorter than calculated — you can always widen or extend the slot to lower the frequency; you can't easily shorten it.

### Step 3 — Calculate slot width

- Narrow slot (high Q, narrow bandwidth): W = L/15 to L/10
- Wide slot (low Q, wide bandwidth): W = L/5 or more

### Step 4 — Feed method and impedance matching

**Coaxial probe feed:**
- Drill/punch a hole through the ground plane
- Inner conductor of SMA bridges the slot gap
- Offset the feed from slot centre by ≈ 0.105 × L for 50 Ω match
- Start at this position; fine-tune after first measurement

**CPW feed (PCB):**
- Centre strip and ground planes on same layer
- 50 Ω CPW on FR4 (h=1.6 mm): strip W ≈ 3 mm, gap g ≈ 0.3 mm
- Extend a tuning stub (U-shaped or T-shaped) beyond the slot on the feed side
- Initial stub length: λ/4 at f_r (in the CPW medium)

**Microstrip aperture-coupled feed (PCB):**
- Microstrip on bottom layer, slot in top ground plane, microstrip crosses slot at 90°
- Open-circuit stub length past the slot: start at λ/4, optimise in simulation

### Step 5 — Ground plane sizing

- Minimum: ground plane extends λ/4 beyond each slot edge
- Practical minimum: λ/2 × λ/2 total for reliable results
- Preferred: 2λ × 2λ or more

### Step 6 — Cavity (if unidirectional pattern is needed)

Initial cavity depth:
```
D_cavity ≈ c / (4 × f_r)    (λ/4 in air)
```
Cavity width and height: ≥ slot length + λ/4 margin on each side. Tune depth in simulation for minimum backscatter and desired bandwidth.

---

## 2. Build

### Option A — Copper Sheet / Brass

Best for: one-off prototypes at 1–10 GHz where accuracy and rigidity matter.

**Materials:**
- 0.5–1.5 mm copper or brass sheet
- SMA edge-mount or through-hole connector
- Soft solder, flux, soldering iron (or silver solder + torch for brass)

**Process:**
1. Cut sheet to size (ground plane dimensions from Step 5)
2. Mark slot centre and dimensions on the sheet with a scribe
3. Cut slot: rotary tool with cutting disc, metalworking saw, or CNC mill
4. Clean edges with a file; deburr
5. Drill SMA connector mounting holes at the feed offset position
6. Solder SMA: outer shell/braid to ground plane, inner pin bridges the slot gap
7. Check with DMM: inner pin to ground should be open (∞ Ω); if not, you have a short across the slot

### Option B — Adhesive Copper Foil Tape

Best for: fast prototyping at UHF (433, 868, 915 MHz) and low microwave (up to ~3 GHz).

**Materials:**
- Conductive-adhesive copper foil tape (3M 1181/1182, or Würth 3462) — must be conductive adhesive on both sides
- Non-conductive backing board: FR4 sheet, acrylic, foam board, plywood
- SMA connector

**Process:**
1. Calculate slot dimensions; draw layout on backing board
2. Cut copper foil to cover the ground plane area, leaving the slot opening
3. Place and press foil firmly; use a roller to eliminate air bubbles
4. If ground plane is made from multiple tape pieces: overlap seams by ≥5 mm and solder the overlap, or use conductive-adhesive tape — resistive joints cause problems
5. Mount SMA connector: solder outer braid to the foil ground plane, inner pin across the slot gap at feed offset position
6. Test slot is open: DMM resistance across slot should read open circuit

**Tips:**
- Standard copper tape has non-conductive acrylic adhesive — test conductivity across seams before use
- Press tape firmly; air gaps shift ε_eff and detune the slot
- Cut the slot opening with a sharp knife against a metal ruler

### Option C — PCB (Recommended for Repeatability)

Best for: 1–30 GHz, CPW or microstrip feed, repeatable dimensions.

**Design flow:**
1. Lay out slot and feed geometry in KiCad, EasyEDA-Pro, or Altium
2. Top copper layer: slot etched in the ground plane (subtract slot from copper pour)
3. For CPW feed: CPW trace, slot, and tuning stub all on top layer
4. For aperture-coupled microstrip: slot on top (ground plane), microstrip on bottom
5. Run DRC; verify slot dimensions exactly match calculation
6. Export Gerbers; fabricate at JLC PCB, PCBWay, OSHPark, etc.

**PCB layout rules:**
- Slot corners: slightly chamfered (0.2–0.5 mm radius) to reduce current crowding
- Keep other traces ≥ λ/4 from slot edges
- Ground plane is continuous copper pour, no copper inside the slot
- For Rogers/high-frequency substrates: use the fab's controlled-dielectric process

**Soldering SMA connector:**
- For edge-mount SMA: align pin to feed strip; solder grounds to ground plane
- For end-launch connectors on CPW: all pins on the same layer
- Avoid excessive solder; any bridge across the slot kills the antenna

### Option D — Slotted Waveguide

Best for: 3–100 GHz, high gain arrays, high power.

**Materials:**
- Standard WR-series aluminium or brass waveguide section
- SMA or waveguide flange to coax transition for feed

**Slot machining (WR90, X-band ~9.4 GHz):**
```
Waveguide: a=22.86 mm, b=10.16 mm
λ_0 = 31.99 mm
λ_g = λ_0 / √(1 - (λ_0/2a)²) ≈ 39.8 mm
Slot spacing: λ_g/2 = 19.9 mm
Slot length: ~14.6 mm (tune in simulation; shorter than λ_0/2)
Slot width: 1.5–2 mm
Slot offset from centreline: adjust for desired coupling (start at a/4 = 5.7 mm)
```
- Machine slots with CNC mill or drill press; ±0.1 mm tolerance
- Short-circuit the waveguide at one end; feed from the other
- Alternating slots offset to opposite sides of centreline (polarity alternation)

---

## 3. Simulate

Simulate before committing to hardware. OpenEMS + Octave is the recommended free tool on Linux.

### Install OpenEMS

```bash
sudo apt install openems
# or build from source: https://www.openems.de
```

### Basic CPW-fed Slot Simulation (Octave)

Save as `slot_sim.m`:

```octave
close all; clear; clc;
addpath('/usr/share/openEMS/matlab');

unit = 1e-3;  % dimensions in mm

% --- Design parameters ---
f0 = 2.4e9;         % centre frequency
c0 = 3e8;
lambda = c0/f0 * 1e3;  % in mm

slot_L = 60;   % slot length mm
slot_W = 4;    % slot width mm
gnd_L  = 200;  % ground plane length
gnd_W  = 200;  % ground plane width
sub_h  = 1.6;  % substrate thickness mm (0 = no substrate, free-space)
epsR   = 4.4;  % FR4

% CPW geometry (50 ohm on FR4 h=1.6mm)
cpw_strip = 3;   % centre strip width
cpw_gap   = 0.3; % gap width

% --- FDTD setup ---
FDTD = InitFDTD('NrTs', 50000, 'EndCriteria', 1e-4);
FDTD = SetGaussExcite(FDTD, f0, f0);
BC   = {'MUR' 'MUR' 'MUR' 'MUR' 'MUR' 'MUR'};
FDTD = SetBoundaryCond(FDTD, BC);

CSX = InitCSX();

% Substrate
CSX = AddMaterial(CSX, 'substrate');
CSX = SetMaterialProperty(CSX, 'substrate', 'Epsilon', epsR);
CSX = AddBox(CSX, 'substrate', 1, ...
    [-gnd_L/2, -gnd_W/2, -sub_h], [gnd_L/2, gnd_W/2, 0]);

% Ground plane (top copper, with slot removed)
CSX = AddMetal(CSX, 'gnd');
% full ground plane box, slot will be subtracted by omission
% Left of slot
CSX = AddBox(CSX, 'gnd', 10, ...
    [-gnd_L/2, -gnd_W/2, 0], [-slot_L/2, gnd_W/2, 0]);
% Right of slot
CSX = AddBox(CSX, 'gnd', 10, ...
    [slot_L/2, -gnd_W/2, 0], [gnd_L/2, gnd_W/2, 0]);
% Above slot
CSX = AddBox(CSX, 'gnd', 10, ...
    [-slot_L/2, slot_W/2, 0], [slot_L/2, gnd_W/2, 0]);
% Below slot
CSX = AddBox(CSX, 'gnd', 10, ...
    [-slot_L/2, -gnd_W/2, 0], [slot_L/2, -slot_W/2, 0]);

% CPW feed line (bottom layer, runs perpendicular to slot along y-axis)
CSX = AddMetal(CSX, 'cpw');
% centre strip
CSX = AddBox(CSX, 'cpw', 10, ...
    [-cpw_strip/2, -gnd_W/2, -sub_h], [cpw_strip/2, 0, -sub_h]);

% Lumped port across the slot (simplification; for production use a proper port)
CSX = AddLumpedPort(CSX, 100, 1, 50, ...
    [-cpw_strip/2, -cpw_gap, -sub_h], [cpw_strip/2, 0, -sub_h], ...
    [0 1 0], true);

% Mesh
lambda_min = c0 / (f0 * sqrt(epsR)) * 1e3;  % min wavelength in substrate (mm)
mesh_fine = min(slot_W, cpw_gap) / 3;        % fine mesh at gaps
mesh_coarse = lambda_min / 10;

CSX = DefineRectGrid(CSX, unit, ...
    {[-gnd_L/2 : mesh_coarse : -slot_L/2-2, ...
      linspace(-slot_L/2-2, slot_L/2+2, 30), ...
      slot_L/2+2 : mesh_coarse : gnd_L/2], ...
     [-gnd_W/2 : mesh_coarse : -slot_W-2, ...
      linspace(-slot_W-2, slot_W+2, 20), ...
      slot_W+2 : mesh_coarse : gnd_W/2], ...
     [-sub_h*2 : sub_h/4 : sub_h*5]});

% Output port and near-field box
start = [-gnd_L/2, -gnd_W/2, -sub_h*2];
stop  = [ gnd_L/2,  gnd_W/2,  sub_h*5];
CSX = AddDump(CSX, 'nf_E', 'DumpType', 0, 'FileType', 1);
CSX = AddBox(CSX, 'nf_E', 0, start, stop);

% Write and run
Sim_Path = 'tmp_slot';
mkdir(Sim_Path);
WriteOpenEMS([Sim_Path '/slot.xml'], FDTD, CSX);
RunOpenEMS(Sim_Path, 'slot.xml');

% Post-process
freq = linspace(1e9, 4e9, 200);
port = calcPort(port, Sim_Path, freq);
s11  = port.uf.ref ./ port.uf.inc;
figure; plot(freq/1e9, 20*log10(abs(s11)));
xlabel('Frequency (GHz)'); ylabel('S11 (dB)');
title('Slot Antenna Return Loss'); grid on;
ylim([-30 0]);
```

This is a structural starting point — adapt geometry for your design. The OpenEMS wiki and the Guénael slot antenna PDF have complete working examples.

### What to look for in simulation

- S11 minimum should be at your target frequency
- S11 depth: at least −10 dB (target −15 dB or better)
- If resonance is at wrong frequency: adjust slot length (longer → lower f, shorter → higher f)
- If S11 minimum is shallow (< −10 dB): adjust feed offset or stub length
- Check far-field: confirm polarisation is correct, pattern shape matches expectations

---

## 4. Test

### Equipment

| Item | Minimum | Good |
|------|---------|------|
| VNA | NanoVNA V2 (to 3 GHz) | LibreVNA (to 6 GHz) or lab VNA |
| Calibration kit | SMA SOLT cal kit | High-precision SOLT |
| SMA cable | Any 50 Ω, appropriate length | Phase-stable test cable |
| Ferrite choke | Common-mode suppression on cable | — |

### VNA Calibration

Always calibrate at the measurement plane (end of cable, not the VNA port):
1. Connect calibration standards in order: Short → Open → Load (50 Ω)
2. On NanoVNA: Menu → Cal → Calibrate → select standards in sequence → Done → Save
3. Check: with cable open the Smith chart should show far-right (open); cable shorted should show far-left (short); 50 Ω load should show centre

### S11 Measurement

1. Set frequency span: centre on expected resonance, span at least 3× the expected bandwidth
2. Connect antenna to calibrated cable
3. Observe S11 on dB (log magnitude) display
4. Look for a dip: this is the resonance. Record:
   - Resonant frequency f_r (dip minimum)
   - S11 at resonance (depth)
   - Bandwidth: frequencies where S11 = −10 dB
5. Check on Smith chart: at resonance the trace should cross the real axis; the crossing point shows the matched impedance

**If S11 is poor:**

| Symptom | Likely cause | Fix |
|---------|-------------|-----|
| No dip at all | Short across slot | Inspect; check DMM reads open across slot |
| Resonance at wrong frequency | Slot length off; substrate ε_r differs from assumed | Adjust length in simulation; re-fabricate |
| Dip < −6 dB (shallow) | Impedance mismatch | Adjust feed offset; adjust tuning stub length |
| Resonance shifts when cable is moved | Common-mode current on cable | Add ferrite choke clamp 10–20 mm from connector |
| S11 bounces / unstable | Nearby metal objects | Move antenna away from surfaces (min λ/2 clearance) |

### Ferrite Choke (Essential for Accurate Measurements)

Common-mode currents on the outer braid of the feed cable cause the cable itself to radiate and act as part of the antenna — this corrupts both the impedance measurement and the pattern.

Fix: snap a ferrite clamp-on bead (mix 31 or 43 for HF/VHF, mix 61 for UHF/microwave) over the cable, positioned 10–30 mm from the antenna connector. If you don't have one, coil 5+ turns of cable through a toroid core. Verify: after adding choke, moving the cable should not change S11.

### Isolation During Measurement

- Mount antenna on a non-conducting support (foam block, PVC pipe, zip-tie to plastic stand)
- Minimum λ/2 clearance to metallic objects on all sides
- Keep hands and body away; human tissue absorbs RF
- Outdoors or in a clear indoor space is better than near metal furniture

### Radiation Pattern (Basic Method)

For single-element slots with far field distance r > 2D²/λ (usually < 1 m for small slots at GHz):

1. Set up a fixed transmit antenna outdoors (or in a clear space) connected to a signal generator or second port of VNA
2. Mount your slot antenna on a non-conducting rotatable mount (lazy Susan on foam, or purpose-built rotator)
3. Measure received signal level (VNA S21, or spectrum analyser + power meter) vs. rotation angle
4. Record at 5° or 10° intervals through 360°
5. Normalise to maximum; plot in polar coordinates

**Simpler link-test version:**
- Use a known reference antenna (half-wave dipole); record received power
- Substitute slot antenna; record received power at same separation and orientation
- Difference (dB) = gain difference relative to dipole

---

## 5. Tuning

### Slot Too Long (Resonance Below Target)

- Trim slot length: file metal, cut copper tape, or re-etch PCB
- Or: solder a thin metal strip across each slot end to electrically shorten it
- Simulation first: 1% length change ≈ 1% frequency change

### Slot Too Short (Resonance Above Target)

- Extend slot: add conductive tape strips at ends (make slot longer)
- On PCB: difficult — design extra length into original layout and trim during tuning

### Impedance Off (VSWR Good but Wrong Impedance)

- **Coax feed**: move probe position along slot; towards ends = lower impedance
- **CPW/microstrip stub**: adjust stub length; longer stub shifts the matching frequency

### Reactive Loading (Miniaturisation)

To lower resonant frequency without making the slot longer, solder a lumped capacitor across the slot at its centre:
```
f_new ≈ f_old / √(1 + C_lumped / C_slot)
```
SMD 0402 or 0201 capacitors; hand-calculate or iterate in simulation. Works well at sub-3 GHz.

---

## 6. Quick-Start: 2.4 GHz Foil Tape Slot

Simplest possible build for a WiFi / ISM band test antenna:

**Materials:** adhesive copper foil tape (conductive adhesive), FR4 offcut or acrylic sheet (~150×150 mm), SMA connector, SMA-to-SMA test cable

**Steps:**
1. Cut backing board to 150×150 mm
2. Calculate: L = 60.6 mm, W = 6 mm (W/L = 0.1)
3. Cover board with copper tape; leave a 60.6 × 6 mm slot gap centred on the board
4. Feed offset from slot centre: 0.105 × 60.6 = 6.4 mm from slot midpoint along the slot axis
5. At the feed point, drill a 3 mm hole through the backing board
6. Insert SMA connector: outer shell flat against copper tape (solder all four pads), inner pin bridges the slot
7. Connect to NanoVNA; look for S11 dip near 2.4 GHz
8. Trim/extend slot edges with tape to tune frequency
9. Move feed offset position if S11 dip is shallow

**Expected result:** S11 < −10 dB, bandwidth ~200–300 MHz (about 8–12%), bidirectional pattern

---

## 7. Checklist Before First RF Test

- [ ] Slot is open (DMM reads ∞ Ω across slot)
- [ ] Feed connector outer shell makes solid electrical contact to ground plane on both sides
- [ ] Feed inner pin bridges the slot gap cleanly with no solder bridge
- [ ] Ground plane extends at least λ/4 beyond slot on all sides
- [ ] Antenna is mounted away from metallic objects (min λ/2)
- [ ] VNA calibrated at cable end
- [ ] Ferrite choke on feed cable near antenna
- [ ] Frequency span set to ±50% of expected resonance

---

## Resources

- **antenna-theory.com — Slot Antennas**: theory, patterns, Babinet derivation
- **W1GHZ Microwave Antenna Book, Ch.7**: practical slotted waveguide design
- **OpenEMS wiki**: FDTD tutorials; adapt patch antenna examples to slot
- **Guénael slot antenna PDF** (`slot-antennas-openems-octave`): complete OpenEMS/Octave worked examples for ham radio bands
- **RF Wireless World slot calculator**: online slot length calculator
- **NanoVNA App** (PC): better UI than onboard for calibration and analysis
