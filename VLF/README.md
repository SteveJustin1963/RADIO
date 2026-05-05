# VLF Reception Using PC Audio Port

Based on https://youtu.be/L2W1x6Rb9hI - you can use the audio port on a soundcard to pick up RF signals. This is particularly useful for VLF reception by connecting an antenna directly to the audio port. The sound card acts as an ADC (Analog-to-Digital Converter).

## Software for Linux

### Audio/SDR Software
- **Gqrx** - Popular SDR software with good audio input support (recommended starting point)
- **CubicSDR** - Cross-platform SDR application  
- **SDR++** - Modern SDR software with audio device support
- **FLDIGI** - Good for weak signal digital modes
- **Audacity** - Simple recording and basic spectrum analysis

### Audio Tools
- **PulseAudio** or **ALSA** utilities to configure audio input
- **pavucontrol** - PulseAudio volume control for input selection

### Installation
```bash
sudo apt install gqrx-sdr cubicsdr audacity pavucontrol
```

### Advanced Analysis Tools
- **GNU Radio** - For custom signal processing
- **Inspectrum** - Detailed signal analysis  
- **Baudline** - Real-time spectrum analyzer

# transcription



**The video is "Using a PC sound card to receive VLF radio signals" by VWestlife (about 3-4 minutes long, from 2015).**

It is a **demonstration video** with minimal spoken narration (mostly voiceover explaining the setup while showing screen recordings and on-screen text). It doesn't appear to have full official/closed captions easily available in searches, but here's a close reconstruction based on the content, description, and typical structure of the video:

### Approximate Transcription / Narration Summary

"All you need to receive these signals is your computer's sound card, a free program called SDR Sharp, and an antenna."

"Just connect an antenna to your computer's microphone input, and you can receive VLF (Very Low Frequency) radio signals. A sound card (or built-in sound chip) with a recording sampling rate of at least 96 kHz is recommended."

(The video then demonstrates plugging a simple long wire antenna into the mic/line input, launching SDR#, setting the sample rate, and tuning to VLF frequencies.)

It shows a waterfall/spectrum display with strong VLF signals appearing (e.g., submarine comms stations like NAA on ~24 kHz, etc.).

It also covers:
- Examples of received signals from distant stations.
- A fun aside about how the old UK VLF station **GBR (16 kHz)** was accidentally recorded onto Mike Oldfield's *Tubular Bells* album during recording at The Manor studio (visible as a tone in audio analysis software).
- Links in the description for software, station lists, and more info.

The rest is mostly visual: screen recordings of SDR# software, signal reception, and basic setup tips (e.g., avoiding interference, grounding advice implied in comments).

### Key Resources from Video Description
- SDR# download: sdrsharp.com
- VLF station lists
- More on the Tubular Bells / GBR story

//

**VLF (Very Low Frequency) signals** are radio waves in the frequency range of **3–30 kHz**, corresponding to wavelengths of **10–100 km**.

This band sits between Extremely Low Frequency (ELF, below 3 kHz) and Low Frequency (LF, 30–300 kHz). VLF waves behave differently from higher-frequency radio waves (like those used for FM radio or Wi-Fi) due to their extremely long wavelengths.

### Propagation Characteristics
VLF waves excel at long-distance propagation thanks to several unique features:

- **Earth-Ionosphere Waveguide**: VLF signals reflect off the lower D-region of the ionosphere (around 60–90 km altitude) and the Earth's surface (especially conductive seawater or ground). This creates a natural "duct" or waveguide that guides signals around the planet's curvature with low attenuation (typically 2–3 dB per 1,000 km).

- **Ground Wave / Surface Wave**: They follow the Earth's contour and diffract around obstacles like mountains, unlike higher frequencies limited by line-of-sight.

- **Penetration**: VLF waves penetrate seawater to depths of roughly 10–40 meters (depending on frequency, salinity, and power), making them ideal for submarine communication. They also penetrate some distance into the ground or Earth.

- **Stability and Reliability**: Propagation is relatively stable, with predictable diurnal (day/night) variations due to changes in the ionosphere. They offer high phase/frequency stability, useful for time signals and navigation.

- **Challenges**: High atmospheric noise (from lightning), very large antennas needed for efficient transmission, and extremely low data rates (often just a few bits per second or even slower).

### Man-Made VLF Signals and Applications
VLF is primarily used for applications needing reliable, long-range, or penetrating communication:

- **Submarine Communication**: The main military use. High-power shore-based transmitters send encrypted commands (often MSK modulation) to submerged submarines worldwide. Submarines use towed or buoy antennas to receive them.

- **Time and Frequency Standards**: Stations like WWVB (60 kHz, though technically LF) broadcast precise time signals for radio clocks.

- **Navigation**: Historical systems like Omega (used 10–14 kHz) for global positioning before GPS. Some VLF beacons remain for naval or scientific use.

- **Scientific and Geophysical Research**: Monitoring the ionosphere, lightning, earthquakes, and space weather.

Major VLF transmitters (examples):
- NAA (Cutler, Maine, USA): 24.0 kHz, ~1 MW
- NLK (Jim Creek, Washington, USA): 24.8 kHz
- DHO38 (Germany): 23.4 kHz
- Others in Russia, Australia, France, etc.

These are massive installations with huge antenna arrays (often multiple tall masts).

### Natural VLF Signals
Lightning produces the most common natural VLF emissions, creating a rich "natural radio" soundscape audible with simple receivers:

- **Sferics** (Atmospherics): Short, sharp clicks or pops from nearby lightning strikes. They sound like twigs snapping or static.

- **Tweeks**: Dispersed sferics that have traveled long distances in the waveguide. They often end with a ringing or "tweeting" sound (higher frequencies arrive first).

- **Whistlers**: Signals that escape into the magnetosphere, travel along Earth's magnetic field lines (sometimes to the opposite hemisphere), and return. They sound like descending whistles or tones because of dispersion (lower frequencies travel slower).

Other phenomena include chorus, hiss, and triggered emissions studied in space physics.

### Receiving VLF Signals
As shown in the video you shared, **VLF reception is accessible to hobbyists**:

- A simple long wire antenna (or active antenna like a Mini-Whip) plugged into a PC sound card's microphone/line input (preferably sampling at 96 kHz or higher).
- Software like SDR# (SDR Sharp), Spectrum Lab, or SAQrx.
- Best at night or in low-noise rural areas. Avoid strong local interference (power lines, electronics).

With this setup, you can hear military stations as steady tones or data signals, plus natural sounds from lightning anywhere on Earth.

### Summary of Key Properties
| Aspect              | Details                              |
|---------------------|--------------------------------------|
| Frequency Range    | 3–30 kHz                            |
| Wavelength         | 10–100 km                           |
| Propagation        | Earth-ionosphere waveguide, ground wave |
| Penetration        | Seawater (10–40m), some ground      |
| Data Rate          | Very low (bits per second)          |
| Main Uses          | Submarine comms, time signals, science |
| Natural Sources    | Lightning (sferics, tweeks, whistlers) |

VLF bridges the gap between "radio" and "audio" frequencies—many signals can be directly heard as audio when demodulated. It's one of the most fascinating and accessible parts of the radio spectrum for both practical and scientific exploration.

If you'd like details on specific stations, antenna building, software setup, or how to identify signals you hear, let me know!

//

**Here's a practical, step-by-step guide to setting up your own VLF receiver using a PC sound card**, just like in the VWestlife video (and many others).

### 1. Check Your Hardware Compatibility
- **Sound card**: Needs a **microphone or line-in** jack that supports at least **96 kHz sampling rate** (for 0–48 kHz reception). 192 kHz is better (0–96 kHz). Many modern laptops and motherboards support this.  
  - Test it: Right-click the speaker icon → Recording devices → Properties of your mic input → Advanced tab. Look for 96 kHz or 192 kHz options.  
  - USB external sound cards with high sample rates work well if your built-in one is limited.
- **Antenna options** (start simple):
  - **Beginner**: 10–30 meters (30–100 ft) of insulated wire (e.g., speaker wire or hookup wire) strung outdoors, away from buildings/power lines. Higher is better.
  - **Recommended**: **Mini-Whip active antenna** (very popular for VLF/LF). Small (whip ~10–30 cm), sensitive, and effective from ~10 kHz up. You can buy one or build from PA0RDT design plans. It needs 9–12V DC power (bias tee or separate supply).
  - Other: Magnetic loop (good for rejecting electric noise) or longwire with isolation transformer.

**Safety note**: Never connect a long outdoor antenna during thunderstorms. Use lightning protection (gas discharge tubes or spark gaps) and proper grounding.

### 2. Software
**Main options**:
- **SDR# (SDR Sharp)**: User-friendly with waterfall display. Free from sdrsharp.com. Great for beginners.
- **SAQrx** (Panoramic VLF Receiver): Lightweight and specifically for VLF.
- **Spectrum Lab** (by DL4YHF): Excellent for analysis, recording, and decoding.
- Others: HDSDR, SDR Console (if using external SDR later).

Download SDR# first.

### 3. Basic Setup Steps
1. **Connect the antenna**:
   - Plug the antenna wire directly into the **microphone input** (pink jack) on your PC. For active antennas like Mini-Whip, use coax cable and provide power via bias tee.
   - **Grounding is crucial** for low noise: Connect the coax shield to a good earth ground (copper rod, cold water pipe, or outdoor ground stake). Ground at the antenna base and again before entering the building.

2. **Configure Windows sound settings**:
   - Set mic input to maximum level (but watch for clipping).
   - Disable enhancements (noise suppression, AGC) in the sound card properties.

3. **Launch SDR#**:
   - Select **Audio** as your source (not RTL-SDR or other).
   - Set **Sample Rate** to 96,000 or 192,000 Hz.
   - In the radio settings, tune to VLF frequencies (e.g., center at 20–25 kHz to see multiple stations).
   - Enable the waterfall/spectrum. Adjust gain so signals are visible but not overloading.

4. **Tune and listen**:
   - Strong US stations (from Sydney, expect weaker but possible signals at night):
     - NAA (Cutler, ME): 24.0 kHz
     - NLK (Jim Creek, WA): 24.8 kHz
     - NML (LaMoure, ND): 25.2 kHz
     - Others like NPM (21.4 kHz), NAU (40.8 kHz) if your sample rate allows.
   - Military signals often sound like steady carriers or buzzing data (MSK modulation). Natural signals: sferics (clicks), tweeks, whistlers.

### 4. Tips for Better Reception
- **Location matters**: Rural or suburban with low RF noise is best. Avoid indoors near electronics/power lines.
- **Time**: Best at night (lower ionospheric absorption) and during quiet geomagnetic conditions.
- **Noise reduction**: Use ferrite chokes on cables, isolate grounds, try common-mode chokes or isolation transformers.
- **Active antenna tips**: Mount outdoors, elevated, away from buildings. Proper grounding of the coax shield dramatically reduces noise.
- **Recording**: Use SDR# or Spectrum Lab to record .wav files for later analysis.

### 5. Common Issues & Troubleshooting
- No signals / high noise → Poor grounding, indoor antenna, or local interference.
- Overload/distortion → Reduce input gain or add attenuation.
- Sound card limited to 48 kHz → Only hears up to ~24 kHz.
- Laptop issues → Try a desktop or USB sound card (many support 192 kHz).

### Progression Path
Once comfortable, upgrade to:
- Better active antennas or loops.
- Dedicated VLF receiver or SDR (e.g., Airspy, RSP1A with upconverter not needed for VLF).
- Decoding tools for time signals or SID (sudden ionospheric disturbance) monitoring for space weather.

This setup costs almost nothing if you have wire and a suitable PC. Many people worldwide receive transatlantic VLF signals with simple setups.

**Would you like**:
- Specific Mini-Whip build instructions?
- SDR# exact configuration screenshots/steps?
- Links to antenna plans or current station lists?
- Recommendations for Sydney-area noise mitigation?

Let me know your equipment (laptop/desktop, etc.) for more tailored advice! Stay safe with outdoor antennas.
//


# tansmitt antenna
Acoustically driven magnetoelectric (ME) antennas are a cutting-edge research field. While they aren't "off-the-shelf" consumer products yet, laboratory prototypes show they can transmit VLF signals using devices only a few centimetres long. [1] 
## How to Build It (The Prototype Structure)
To build a basic [magnetoelectric transmitter](https://pmc.ncbi.nlm.nih.gov/articles/PMC10503940/), researchers typically use a sandwich structure of two types of materials:

* Piezoelectric Layer: (e.g., PZT-5H or Lithium Niobate) This material expands and contracts physically when you apply a voltage.
* Magnetostrictive Layer: (e.g., [Terfenol-D](https://pmc.ncbi.nlm.nih.gov/articles/PMC11536042/) or Metglas) This material produces a magnetic field when it is physically stressed or vibrated.
* The Process: You glue these layers together with epoxy. When you feed an AC signal (the VLF carrier) into the piezoelectric layer, it vibrates. This vibration "squeezes" the magnetostrictive layer, which then radiates a time-varying magnetic field—effectively acting as a [mechanical antenna](https://www.cell.com/iscience/fulltext/S2589-0042%2822%2902105-8). [2, 3] 

## Power and Efficiency

* Input Power: These are ultra-low-power devices. Typical prototypes run on just 2 mW to 10 mW.
* Efficiency: They are roughly 6,000 to 10,000 times more efficient than a traditional electrical antenna of the same tiny size. However, their total radiated power is still very small because the device itself is so tiny.
* Advanced Power: High-power versions using nanocrystalline alloy cores and [Litz wire](https://en.wikipedia.org/wiki/Very_low_frequency) can handle up to 1,200 Watts, but these usually resemble specialized magnetic loops rather than the thin-film ME versions. [4, 5, 6, 7, 8, 9] 

## Expected Range

* Single Unit: A single centimetre-scale transmitter can typically be detected at 3 to 10 metres in laboratory air or through soil.
* Arrayed/Optimised: Experimental arrays or high-sensitivity receivers (like the [Quantum Magnetometers](https://www.nist.gov/news-events/news/2018/01/quantum-radio-may-aid-communications-and-mapping-indoors-underground-and) we discussed) can extend this range. Some mechanical magnet designs have reached 100+ metres at very low frequencies (100-500 Hz).
* Specialised Loop Antennas: High-power 51 cm diameter VLF loops (non-acoustic) have achieved communication distances of up to 1.4 km in mining environments. [3, 5, 6, 8, 10] 

## Key Performance Summary

| Feature | ME Thin-Film Prototype | High-Power Magnetic Loop |
|---|---|---|
| Size | ~1.5 cm | ~50 cm |
| Power | 2 mW – 10 mW | 1,000 W+ |
| Range | 3 – 10 metres | 100 m – 1.4 km |
| Data Rate | ~60 to 100 bits/sec | Low-rate coded signals |

Would you like to see a more detailed circuit diagram for the modulation and driving stages of these piezoelectric transmitters?

[1] [https://www.youtube.com](https://www.youtube.com/watch?v=yMK9Wh4dDqE&t=5)
[2] [https://pmc.ncbi.nlm.nih.gov](https://pmc.ncbi.nlm.nih.gov/articles/PMC11536042/)
[3] [https://www.sciencedirect.com](https://www.sciencedirect.com/science/article/pii/S2352847824001266)
[4] [https://www.nature.com](https://www.nature.com/articles/s41598-020-73973-6)
[5] [https://www.mdpi.com](https://www.mdpi.com/1424-8220/24/2/694)
[6] [https://pmc.ncbi.nlm.nih.gov](https://pmc.ncbi.nlm.nih.gov/articles/PMC10818415/)
[7] [https://www.mdpi.com](https://www.mdpi.com/2072-666X/15/1/11)
[8] [https://www.mdpi.com](https://www.mdpi.com/2079-4991/15/14/1062)
[9] [https://en.wikipedia.org](https://en.wikipedia.org/wiki/Very_low_frequency)
[10] [https://advanced.onlinelibrary.wiley.com](https://advanced.onlinelibrary.wiley.com/doi/10.1002/aelm.202300096)



# more
To drive an acoustically actuated magnetoelectric (ME) transmitter, the circuit focuses on exciting a piezoelectric material at its mechanical resonance, which then vibrates a magnetostrictive layer to radiate VLF signals. [1, 2] 
## 1. Basic Driving Circuit Diagram
The simplest way to drive a piezoelectric VLF transmitter is a Resonant MOSFET Drive. Because the piezo element acts like a capacitor, you use an inductor to form an $LC$ tank circuit that resonates at your target VLF frequency. [3, 4, 5] 
Core Components:

* Signal Source: An [Arduino or Function Generator](https://www.youtube.com/watch?v=F5tQIxdQb4c) (VLF square or sine wave).
* MOSFET Driver IC: (e.g., [TC4424A](https://www.youtube.com/watch?v=EM1KHu6PoLA)) used to rapidly switch the high-power MOSFET.
* Power MOSFET: (e.g., IRL640A) switches the main power through the piezo element.
* Resonant Inductor: Placed in parallel or series with the piezo to boost voltage and efficiency. [3, 4, 5] 

## 2. Full Transmitter Block Diagram
For professional or research-grade VLF communication, a more complex "front-end" is used to handle modulation (like ASK or PSK): [6, 7] 

   1. Modulator: An [STM32 Microcontroller](https://www.sciencedirect.com/science/article/pii/S2352847824001266) or PC generates the baseband data (e.g., 10–100 bits/sec).
   2. Frequency Generator: Creates the VLF carrier (e.g., $24.47\text{ kHz}$).
   3. Power Amplifier: A [Power Operational Amplifier](https://www.researchgate.net/figure/Block-diagram-of-the-transmitter-circuit-including-the-power-operational-amplifier-and-a_fig4_238007319) or high-voltage driver boosts the signal to $\approx 20\text{--}100\text{V}$ to drive the stiff piezoelectric layer.
   4. ME Antenna: The [laminated composite](https://pmc.ncbi.nlm.nih.gov/articles/PMC10821004/) (Metglas/PZT/Metglas) converts that voltage into a vibrating magnetic field. [1, 7, 8, 9, 10, 11] 

## 3. Key Operating Principles

* Electromechanical Resonance (EMR): The circuit must be tuned to the exact physical resonance of the material. If the carrier frequency is off by even $10\text{--}20\text{ Hz}$, the transmission power will drop nearly to zero.
* Directivity: These transmitters often have a [magnetic dipole](https://pmc.ncbi.nlm.nih.gov/articles/PMC6461683/) radiation pattern, meaning the signal is strongest perpendicular to the length of the device.
* Bandwidth: Unlike traditional high-Q antennas, piezo-based transmitters can [dynamically shift](https://www.nature.com/articles/s41467-019-09680-2) their resonance to increase bitrate, bypassing the standard Bode-Fano limit. [2, 12, 13, 14, 15] 

Would you like a specific component list or schematic values for a DIY low-power version of this circuit?

[1] [https://www.sciencedirect.com](https://www.sciencedirect.com/science/article/pii/S2352847824001266)
[2] [https://www.mdpi.com](https://www.mdpi.com/1424-8220/19/4/853)
[3] [https://www.youtube.com](https://www.youtube.com/watch?v=EM1KHu6PoLA&t=5)
[4] [https://www.sameskydevices.com](https://www.sameskydevices.com/blog/how-to-increase-the-audio-output-of-a-piezoelectric-transducer-buzzer)
[5] [https://www.youtube.com](https://www.youtube.com/watch?v=F5tQIxdQb4c)
[6] [https://www.sciencedirect.com](https://www.sciencedirect.com/science/article/pii/S2589004224023769)
[7] [https://pmc.ncbi.nlm.nih.gov](https://pmc.ncbi.nlm.nih.gov/articles/PMC10821004/)
[8] [https://pmc.ncbi.nlm.nih.gov](https://pmc.ncbi.nlm.nih.gov/articles/PMC10821004/)
[9] [https://www.researchgate.net](https://www.researchgate.net/figure/Block-diagram-of-the-transmitter-circuit-including-the-power-operational-amplifier-and-a_fig4_238007319)
[10] [https://repository.library.northeastern.edu](https://repository.library.northeastern.edu/files/neu:ms35xq049/fulltext.pdf)
[11] [https://pmc.ncbi.nlm.nih.gov](https://pmc.ncbi.nlm.nih.gov/articles/PMC11536042/#:~:text=Figure%201A%20shows%20the%20schematic%20diagram%20of,of%20physical%20quantities%20of%20%E2%80%9Celectric%2Dmechanical%20%28force%2C%20magnetism%29%2Dmagnetic%E2%80%9D.)
[12] [https://www.nature.com](https://www.nature.com/articles/s41467-019-09680-2#:~:text=A%20piezoelectric%20radiating%20element%20eliminates%20the%20need,new%20applications%20for%20portable%2C%20electrically%20small%20antennas.)
[13] [https://www.nature.com](https://www.nature.com/articles/s41467-019-09680-2)
[14] [https://www.researchgate.net](https://www.researchgate.net/publication/332379651_A_high_Q_piezoelectric_resonator_as_a_portable_VLF_transmitter)
[15] [https://www.youtube.com](https://www.youtube.com/watch?v=F5tQIxdQb4c)


To build a DIY low-power VLF transmitter using a piezoelectric/magnetoelectric mechanical antenna, you will need a circuit that can drive a capacitive load (the piezo) at its exact mechanical resonance.
## 1. Essential Components List
For a basic prototype, you can use the following parts to create a [resonant MOSFET driver](https://www.youtube.com/watch?v=EM1KHu6PoLA):

* Antenna Core: A [PZT-5H piezoelectric ceramic plate](https://pmc.ncbi.nlm.nih.gov/articles/PMC8596531/) (e.g., $40\text{ mm} \times 20\text{ mm} \times 0.5\text{ mm}$) laminated with layers of [Metglas (FeSiB alloy)](https://www.sciencedirect.com/science/article/pii/S2352847824001266) using high-strength epoxy.
* Microcontroller: Arduino Nano or STM32 to generate the VLF square wave carrier ($3\text{--}30\text{ kHz}$).
* Gate Driver IC: TC4424A or similar high-speed FET driver. This ensures the MOSFET switches fast enough to minimize heat.
* Power MOSFET: IRL640A or [2N3904](https://www.build-electronic-circuits.com/simple-fm-transmitter/) (for very low power). The IRL640A is better for handling the high peak currents of a resonant tank.
* Resonant Inductor ($L$): A high-Q inductor (e.g., $1\text{ H}$ to several $mH$ depending on frequency) to form an $LC$ tank with the piezo's internal capacitance.
* Power Supply: $12\text{V}$ battery or $20\text{V}$ DC supply. [1] 

## 2. Schematic Values & Design
The circuit operates by "charging" the piezo and then "discharging" it through the inductor to create resonance. [2, 3] 

| Parameter [3, 4, 5, 6] | Suggested Value |
|---|---|
| Driving Voltage ($V_{in}$) | $20\text{V}$ to $100\text{V}$ (Higher voltage increases magnetic flux) |
| Operating Frequency | Must match the Mechanical Resonance of your PZT/Metglas laminate (typically $\approx 23\text{--}25\text{ kHz}$) |
| Damping Resistor | $2.4\text{ k}\Omega$ (spread across multiple resistors to dissipate heat) |
| Capacitance ($C_0$) | The static capacitance of your PZT plate (measure with an LCR meter) |

## 3. Critical Tuning Steps

   1. Find Resonance: Use a function generator to sweep frequencies while monitoring the current draw. The point where current peaks (or impedance dips) is your mechanical resonance.
   2. Impedance Matching: Because the piezo is highly capacitive, you must add the inductor in parallel to the piezo. Use the formula $f = \frac{1}{2\pi\sqrt{LC}}$ to estimate the required inductance for your target VLF frequency.
   3. Modulation: For simple data, use the microcontroller to turn the carrier on/off (OOK - On-Off Keying) or slightly shift the frequency (FSK). [5] 

Warning: Driving piezoelectric elements at high voltages can generate significant heat and physical stress that may crack the ceramic if not properly mounted.
Would you like help calculating the exact inductance value needed based on the specific dimensions of your piezoelectric plate?

[1] [https://www.build-electronic-circuits.com](https://www.build-electronic-circuits.com/simple-fm-transmitter/)
[2] [https://www.youtube.com](https://www.youtube.com/watch?v=F5tQIxdQb4c)
[3] [https://www.youtube.com](https://www.youtube.com/watch?v=EM1KHu6PoLA&t=5)
[4] [https://blog.piezo.com](https://blog.piezo.com/how-to-drive-piezoelectric-actuators)
[5] [https://pmc.ncbi.nlm.nih.gov](https://pmc.ncbi.nlm.nih.gov/articles/PMC10503940/)
[6] [https://www.sciencedirect.com](https://www.sciencedirect.com/science/article/pii/S2352847824001266)


Yes, you can absolutely array multiple piezoelectric or magnetoelectric (ME) elements to create a more powerful VLF transmitter. In fact, research shows that "daisy-chaining" or arraying these elements can lead to non-linear performance gains, making the antenna much more effective than the sum of its parts. [1, 2] 
## 1. Benefits of Arraying

* Increased Radiation Intensity: In a $3 \times 3$ array, researchers have achieved nearly 20 times the transmitted magnetic field of a single antenna. For a $10 \times 10$ array, theoretical improvements can reach over 1,300 times.
* Broadened Bandwidth: By connecting elements with slightly different resonant frequencies in parallel, you can expand the overall signal bandwidth (e.g., up to 1.47 times), allowing for faster data rates.
* Linear Gain in Reception: When used as a receiver, the signal amplitude increases linearly with the number of elements in the array. [2, 3, 4, 5] 

## 2. How to Connect Them
Depending on your goal, you can use different electrical configurations:

| Connection Type [1, 3, 4, 6] | Primary Benefit | How it Works |
|---|---|---|
| Series Connection | Power & Intensity | Connect units with the same resonance frequency. This increases the total mechanical vibration and output response (e.g., 1.9x intensity for 3 units). |
| Parallel Connection | Bandwidth & Speed | Connect units with slightly different resonance frequencies. This "smears" the resonance peak, widening the usable frequency range for higher bitrates. |
| Multilayer Stacking | Compact Efficiency | Alternate layers of piezoelectric (PZT) and magnetostrictive (Metglas)[](https://pmc.ncbi.nlm.nih.gov/articles/PMC10503940/) materials. Driving these in parallel increases the "coupling coefficient," making the device much more efficient for its volume. |

## 3. Critical DIY Challenges

* Frequency Matching: For a power-boosting array, all elements must vibrate at the exact same frequency. If one is off by just $20\text{ Hz}$, it can act as a "mechanical brake" on the others.
* Physical Coupling: Mounting them on the same rigid substrate or [clamping them together](https://www.researchgate.net/publication/395470512_Enhancing_VLF_communication_via_performance-optimized_magnetoelectric_antenna_arrays) allows their mechanical strains to "feed" into each other, creating positive feedback that boosts the signal.
* Synchronization: You must ensure the AC drive signal reaches all elements in the same phase. A [microcontroller](https://www.youtube.com/watch?v=Zr4YDvJmqDs) is usually required to manage the timing and phase of the drive circuit. [2, 7, 8] 

Pro-Tip: If you're building a 2x2 or 3x3 array, mount them on a shared [elastic plate](https://www.researchgate.net/publication/385845033_Multi-Physical_Field_Driven_Low_Frequency_Magnetoelectric_Antenna_Array_with_Nonlinearly_Enhanced_Magnetic_Field_Transmission) so the vibrations of one help drive the others, significantly increasing the overall efficiency of your "mechanical antenna". [2] 
Would you like a wiring schematic for a 3-element series array to boost your VLF transmission power?

[1] [https://www.mdpi.com](https://www.mdpi.com/2072-666X/15/1/11?)
[2] [https://www.researchgate.net](https://www.researchgate.net/publication/385845033_Multi-Physical_Field_Driven_Low_Frequency_Magnetoelectric_Antenna_Array_with_Nonlinearly_Enhanced_Magnetic_Field_Transmission)
[3] [https://www.mdpi.com](https://www.mdpi.com/2072-666X/15/1/11?)
[4] [https://www.mdpi.com](https://www.mdpi.com/2072-666X/15/1/11?)
[5] [https://www.researchgate.net](https://www.researchgate.net/publication/382840801_Acoustically-driven_Piezoelectric_Antenna_for_VLF_Transmission_and_Reception)
[6] [https://pmc.ncbi.nlm.nih.gov](https://pmc.ncbi.nlm.nih.gov/articles/PMC10503940/)
[7] [https://www.researchgate.net](https://www.researchgate.net/publication/395470512_Enhancing_VLF_communication_via_performance-optimized_magnetoelectric_antenna_arrays)
[8] [https://www.youtube.com](https://www.youtube.com/watch?v=Zr4YDvJmqDs&t=261)


YouTube has several videos covering both the advanced mechanical and traditional DIY approaches to VLF. Since "quantum" and "magnetoelectric" antennas are still largely in the research phase, the most relevant video tutorials focus on the high-power circuits needed to drive these mechanical elements or the specialized loop antennas that serve as their classical counterparts. [1, 2] 
## 1. Driving Circuits for Mechanical/Piezo Antennas
To make your "quantum" or "rubidium-style" vision work with physical hardware, you need a high-power resonant driver.

* [Simple High Power Piezoelectric Driver Circuit](https://www.youtube.com/watch?v=EM1KHu6PoLA): This is the most critical video for your project. It shows how to use a TC4424A FET driver and an IRL640A MOSFET to drive a piezoelectric element at VLF frequencies using resonance.
* [Piezoelectric Transducer drive theory](https://www.youtube.com/playlist?list=PLwJKuPtJCUfHdhKblAfGyyJWPCJOZSi-6): A playlist from Ultrasonic Advisors that explains the physics of how to properly power these elements. [3, 4] 

## 2. Experimental VLF Hardware
These videos show actual VLF transmitter setups, some using ferrite rods or experimental coils that mimic the "small-scale" behavior you're after. [5] 

* [VLF Transmitter & Receiver experiments](https://www.youtube.com/playlist?list=PLfFan4sDonOfSui0EiRrKFc5neTtL3wBV): A deep dive into hardware setups for VLF and ULF operations.
* [Transmitter and reception coil on VLF tuned](https://www.youtube.com/watch?v=LeIXQ1ajQ70): Demonstrates how ferrite rods affect frequency and amplitude in a VLF transmission coil.
* [DIY IEM using VLF transmitter](https://www.youtube.com/watch?v=NhN14rCLAR4): Shows an experimental setup using ferrite rod transmit antennas and a 100W audio amp for near-field communication. [5, 6, 7, 8] 

## 3. VLF Loop & Antenna Theory
If you want to compare your array idea against traditional (but compact) designs:

* [Compact Resonant VLF Loop](https://www.youtube.com/watch?v=7PUWDPSZ8Jc): Explains how a 1-meter resonant loop can outperform loops four times its size by using high-Q resonance.
* [Resonant Loop for VLF - Great Trick to Improve Sensitivity](https://www.youtube.com/watch?v=Sg8Je0r6p_A): A guide on using capacitors to tune a small loop to specific VLF frequencies. [9, 10, 11, 12] 

## 4. Background on Advanced Concepts

* [What Are Phased Arrays?](https://www.youtube.com/watch?v=9WxWun0E-PM): Essential if you plan to daisy-chain your piezo elements into an array.
* [Understanding Piezoelectric effect!](https://www.youtube.com/watch?v=_XABS0dR15o): Explains the physics of the PZT materials you'll be using. [13, 14] 

Do you want to see a specific code example for an Arduino to generate the VLF carrier signal for one of these drivers?

[1] [https://www.youtube.com](https://www.youtube.com/playlist?list=PLIe6avmZgJg5NlhBekQHowvUnuzixT3Eo)
[2] [https://www.youtube.com](https://www.youtube.com/watch?v=O3RRsls544E&t=3)
[3] [https://www.youtube.com](https://www.youtube.com/watch?v=EM1KHu6PoLA&t=5)
[4] [https://www.youtube.com](https://www.youtube.com/playlist?list=PLwJKuPtJCUfHdhKblAfGyyJWPCJOZSi-6)
[5] [https://www.youtube.com](https://www.youtube.com/watch?v=NhN14rCLAR4)
[6] [https://www.youtube.com](https://www.youtube.com/watch?v=LeIXQ1ajQ70&t=267)
[7] [https://www.youtube.com](https://www.youtube.com/playlist?list=PLfFan4sDonOfSui0EiRrKFc5neTtL3wBV)
[8] [https://www.youtube.com](https://www.youtube.com/watch?v=LeIXQ1ajQ70&t=267)
[9] [https://www.youtube.com](https://www.youtube.com/watch?v=7PUWDPSZ8Jc&t=4)
[10] [https://www.youtube.com](https://www.youtube.com/watch?v=7PUWDPSZ8Jc&t=4)
[11] [https://www.youtube.com](https://www.youtube.com/watch?v=Sg8Je0r6p_A&t=2)
[12] [https://www.youtube.com](https://www.youtube.com/watch?v=Sg8Je0r6p_A&t=2)
[13] [https://www.youtube.com](https://www.youtube.com/watch?v=9WxWun0E-PM#:~:text=Sensor%20Array%20Analyzer:%20https://bit.ly/3s2ex1t.%20Example%20%2D%20Using%20Antenna%20Toolbox%20with%20Phased%20Array%20Systems:%20https://bit.ly/3eIAIqr.)
[14] [https://www.youtube.com](https://www.youtube.com/watch?v=_XABS0dR15o)



# ref

 - https://github.com/recri/keyer
 
 
 
