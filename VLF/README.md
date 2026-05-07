# sw
 - https://github.com/recri/keyer


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



 
 
 
# build
Building a Magnetoelectric (ME) antenna is more like a high-precision chemistry or materials science project than traditional "wire-and-solder" radio building. Because these antennas rely on **mechanical resonance** (vibrating at just the right speed) rather than electrical length, the construction focuses on how you bond different materials together.

Here is how a prototype is typically constructed in a lab setting:

### 1. The "Sandwich" Ingredients
To make this work, you need two specialized materials that react to each other:

* **The Piezoelectric Layer (The "Mover"):** This material expands or shrinks when you hit it with electricity. Common choices are **PZT** (Lead Zirconate Titanate) or **Lithium Niobate**.
* **The Magnetostrictive Layer (The "Radiator"):** This material creates a magnetic field when it is physically squeezed or stretched. The "gold standard" for this is a material called **Terfenol-D** or a metallic glass called **Metglas**.
* **The Glue:** A very thin, high-strength **epoxy**. This is the most critical part, as it must transmit the vibrations perfectly between the two layers without absorbing them.



---

### 2. The Assembly Process
1.  **Preparation:** The layers are cut into tiny rectangles (often just 1–2 centimeters long). The surfaces must be polished until they are perfectly flat so the glue layer can be as thin as possible.
2.  **Lamination:** You "sandwich" the piezoelectric material between two layers of the magnetic material (or vice versa). 
3.  **Curing:** The sandwich is pressed together under high pressure while the glue dries. If there are any air bubbles or if the glue is too thick, the antenna won't vibrate correctly, and it won't send a signal.
4.  **Wiring:** You attach two very fine wires to the piezoelectric layer. These wires will carry your VLF "message" as an AC voltage.

---

### 3. How It Works (The Chain Reaction)
Once built, the antenna operates through a three-step mechanical chain reaction:

1.  **Voltage to Vibration:** You feed a VLF electrical signal (e.g., 25 kHz) into the piezoelectric layer. It begins to vibrate (shrink and grow) 25,000 times per second.
2.  **Vibration to Stress:** Because it is glued to the magnetic layer, it "pumps" that layer, stretching and squeezing it at that same 25 kHz speed.
3.  **Stress to Radio Wave:** Due to the "Magnetostrictive effect," the magnetic layer generates a moving magnetic field as it is stressed. This moving field flies off the device as a **VLF radio wave**.



---

### 4. Why This is "Acoustic"
Even though it is a radio antenna, it is called "acoustically driven" because the frequency of the radio wave is determined by the **speed of sound** through the material, not the speed of light. 

* **Traditional Antenna:** Must be roughly $1/4$ the size of the radio wavelength (which for VLF is kilometers long).
* **ME Antenna:** Only needs to be roughly $1/2$ the size of the **acoustic wave** (sound wave) inside the crystal. Since sound travels much slower than light, the antenna can be thousands of times smaller.

### Summary of the "Build"
| Component | Function | Material Example |
| :--- | :--- | :--- |
| **Active Element** | Turns electricity into motion | PZT Ceramic |
| **Radiating Element** | Turns motion into magnetism | Metglas / Terfenol-D |
| **Interface** | Connects the two | Cyanoacrylate or Epoxy |
| **Signal Source** | The "Message" | VLF Signal Generator |

---

### Mathematics

---

#### 1. Mechanical Resonance Frequency

The ME antenna radiates at its **acoustic resonance**, not its electromagnetic resonance. The frequency is set by the speed of sound through the composite and the physical length of the bar:

$$f_r = \frac{v_{sound}}{2L}$$

where L is the bar length and v_sound is the longitudinal acoustic velocity in the material.

**Sound velocities:**

| Material | v_sound (m/s) | Notes |
| :--- | :--- | :--- |
| PZT-5A | 4350 | Most common piezo for ME antennas |
| PZT-5H | 4000 | Higher d33 but lower velocity, more fragile |
| Metglas 2605SA1 | 5800 | Iron-silicon-boron metallic glass |
| Terfenol-D | 1640 | Very slow — lowers f_r, allows shorter bars |
| Galfenol (FeGa) | 3870 | Practical machining alternative |

**Required bar length for target frequency** (PZT-5A dominant composite, v_eff ≈ 4350 m/s):

$$L = \frac{v_{sound}}{2 f_r}$$

| Target f_r | Bar length (PZT-5A) | Bar length (Terfenol-D) |
| :--- | :--- | :--- |
| 1 kHz | 2175 mm (impractical) | 820 mm |
| 5 kHz | 435 mm | 164 mm |
| 10 kHz | 217 mm | 82 mm |
| 25 kHz (NAA) | 87 mm | 33 mm |
| 25 kHz (NLK) | 87 mm | 33 mm |

**Why VLF is practical:** At 25 kHz an 87 mm bar resonates acoustically. The equivalent EM quarter-wave antenna would need to be 3,000 m long. Size reduction factor ≈ **34,500×**.

---

#### 2. Piezoelectric Strain and Displacement

The piezoelectric layer converts voltage to mechanical strain. For the 3-1 mode (thickness electrodes, longitudinal vibration along the bar — the standard ME configuration):

$$S_1 = d_{31} \times E_3 = d_{31} \times \frac{V}{t_p}$$

$$\Delta L = S_1 \times L = d_{31} \times \frac{V}{t_p} \times L$$

| Symbol | Meaning |
| :--- | :--- |
| S₁ | Longitudinal strain (ΔL/L, dimensionless) |
| d₃₁ | Piezoelectric strain coefficient (m/V) |
| E₃ | Electric field in thickness direction (V/m) |
| V | Applied voltage (V) |
| t_p | Piezo thickness (m) |
| L | Bar length (m) |

**Material d₃₁ values:**

| Material | d₃₁ (×10⁻¹² m/V) |
| :--- | :--- |
| PZT-5A | −171 |
| PZT-5H | −274 |
| Lithium Niobate | −21 |

**Worked example** — PZT-5A, L = 87 mm, t_p = 0.5 mm, V = 100 V:

$$\Delta L = 171\times10^{-12} \times \frac{100}{5\times10^{-4}} \times 0.087 = 171\times10^{-12} \times 200{,}000 \times 0.087 \approx \mathbf{2.98 \text{ µm}}$$

**At mechanical resonance**, the Q factor amplifies this:

$$\Delta L_{peak} = Q_{mech} \times \Delta L_{static}$$

For Q_mech = 100 (typical for well-bonded PZT-Metglas):

$$\Delta L_{peak} = 100 \times 2.98 \approx 298 \text{ µm} = 0.3 \text{ mm peak-to-peak vibration}$$

This is why resonance is essential — three orders of magnitude of free amplification.

---

#### 3. Electromechanical Coupling Coefficient

k₃₁ describes what fraction of input electrical energy converts to mechanical energy (and vice versa):

$$k_{31} = \frac{d_{31}}{\sqrt{s_{11}^E \times \varepsilon_{33}^T}}$$

| Material | k₃₁ | Meaning |
| :--- | :--- | :--- |
| PZT-5A | 0.44 | 44% energy conversion per cycle |
| PZT-5H | 0.39 | 39% — lower despite higher d₃₁ |
| Lithium Niobate | 0.17 | Poor for transmitting |

The overall ME coupling coefficient k_ME also depends on how well the bond transmits strain from the piezo to the magnetostrictive layer. A poor bond can reduce effective k_ME to below 0.1 even with ideal materials.

---

#### 4. Static Capacitance of the Piezo Element

The piezo looks like a capacitor to the drive circuit. Accurate knowledge of C₀ is required to design the matching inductor:

$$C_0 = \varepsilon_{33}^T \times (1 - k_{31}^2) \times \frac{A}{t_p}$$

where A = electrode area (m²), t_p = piezo thickness (m), ε₃₃ᵀ = permittivity at constant stress.

For PZT-5A: ε₃₃ᵀ = ε₀ × 1750 = 8.85×10⁻¹² × 1750 = 15.5×10⁻⁹ F/m

**Worked example** — 40 mm × 20 mm × 0.5 mm PZT-5A plate:

$$A = 0.040 \times 0.020 = 8\times10^{-4} \text{ m}^2$$

$$C_0 = 15.5\times10^{-9} \times (1 - 0.44^2) \times \frac{8\times10^{-4}}{5\times10^{-4}} = 15.5\times10^{-9} \times 0.806 \times 1.6 \approx \mathbf{20 \text{ nF}}$$

---

#### 5. Matching Inductor

The drive circuit must cancel C₀ with a parallel or series inductor so the amplifier does not waste power fighting the capacitive reactance. At resonance the amplifier sees only the small mechanical resistance:

$$L_{match} = \frac{1}{(2\pi f_r)^2 \times C_0}$$

**Lookup table (C₀ = 20 nF):**

| f_r | L_match |
| :--- | :--- |
| 5 kHz | 50.7 mH |
| 10 kHz | 12.7 mH |
| 25 kHz | 2.03 mH |
| 40 kHz | 0.79 mH |

The matching inductor must be wound on a low-loss core (iron powder or air core) to avoid adding resistance. Use a Q_inductor > 50 at the drive frequency.

---

#### 6. Butterworth-Van Dyke Equivalent Circuit

Near mechanical resonance the ME antenna behaves as the following electrical circuit:

```
BUTTERWORTH-VAN DYKE MODEL
════════════════════════════════════════

         Lm (motional inductance)
         Cm (motional capacitance)
         Rm (mechanical loss resistance)
          │
    ┌────UUU────┤├──────/\/\/────┐
    │      motional branch       │
o───┤                            ├───o
    │         C0                 │
    └──────────┤├────────────────┘
               static (clamped)
               capacitance

At frequency f:
  Below f_r  → capacitive (C0 dominates)
  At f_r     → resistive  (only Rm seen)
  Above f_r  → inductive  (Lm dominates)
  At f_a > f_r → second resonance (antiresonance)
```

**Motional element values** (derived from impedance sweep measurements):

$$L_m = \frac{1}{(2\pi f_r)^2 \times C_m}$$

$$C_m = \frac{8}{\pi^2} \times k_{31}^2 \times C_0 \quad \text{(for 3-1 mode)}$$

$$R_m = \frac{1}{2\pi f_r \times C_m \times Q_{mech}}$$

For Q_mech = 100, C₀ = 20 nF, k₃₁ = 0.44, f_r = 25 kHz:

$$C_m = \frac{8}{\pi^2} \times 0.194 \times 20\text{ nF} \approx 3.14 \text{ nF}$$

$$L_m = \frac{1}{(2\pi \times 25000)^2 \times 3.14\times10^{-9}} \approx 12.9 \text{ mH}$$

$$R_m = \frac{1}{2\pi \times 25000 \times 3.14\times10^{-9} \times 100} \approx 20.3 \text{ Ω}$$

---

#### 7. DC Bias Field for the Magnetostrictive Layer

Without a DC bias, the magnetostrictive layer operates at the nonlinear zero-field point — driving at f_r produces output at 2f_r (frequency doubling). The bias sets the linear operating point.

**Required bias field at the Metglas surface:**

| Material | Optimal H_bias | Notes |
| :--- | :--- | :--- |
| Metglas 2605SA1 | 5–20 Oe (400–1600 A/m) | Very low bias needed |
| Terfenol-D | 200–500 Oe (16–40 kA/m) | Needs stronger magnet |
| Galfenol | 50–150 Oe (4–12 kA/m) | Moderate |

**Field from a NdFeB disc magnet** at distance d along its axis:

$$H(d) = \frac{B_r}{2\mu_0} \left[\frac{t_m}{\sqrt{r_m^2 + (d + t_m/2)^2}} - \frac{0}{\sqrt{r_m^2 + (d - t_m/2)^2}}\right]$$

Simplified for d ≥ r_m (on-axis, away from face):

$$H(d) \approx \frac{B_r \, r_m^2 \, t_m}{2\mu_0 \, (r_m^2 + d^2)^{3/2}}$$

For NdFeB N52 (B_r = 1.45 T), disc r_m = 5 mm, t_m = 3 mm, at d = 5 mm from face:

$$H(5\text{ mm}) \approx \frac{1.45 \times (5\times10^{-3})^2 \times 3\times10^{-3}}{2 \times 4\pi\times10^{-7} \times ((5\times10^{-3})^2 + (5\times10^{-3})^2)^{3/2}} \approx 58{,}000 \text{ A/m} = 730 \text{ Oe}$$

This is too high for Metglas. Use a weaker N35 grade magnet, or increase the standoff distance d until H(d) falls in the 400–1600 A/m target range. A Hall sensor (e.g., SS49E) held against the Metglas surface confirms the correct bias level before bonding the magnets in place.

---

#### 8. Radiated Magnetic Dipole Moment

The ME antenna behaves as a magnetic dipole. The magnetic moment m (A·m²) determines radiated field strength:

$$m = \frac{dM}{d\varepsilon} \times \varepsilon_{peak} \times V_{mag}$$

where dM/dε is the piezomagnetic coefficient (A/m per unit strain), ε_peak is the peak strain at resonance, and V_mag is the magnetostrictive layer volume.

For Metglas 2605SA1: dM/dε ≈ 1×10⁶ A/m

$$\varepsilon_{peak} = \frac{\Delta L_{peak}}{L} = \frac{298\times10^{-6}}{0.087} \approx 3.4\times10^{-3}$$

For a Metglas layer 87 mm × 20 mm × 0.025 mm (V = 43.5×10⁻⁹ m³):

$$m = 10^6 \times 3.4\times10^{-3} \times 43.5\times10^{-9} \approx 1.48\times10^{-4} \text{ A·m}^2$$

**Near-field radiated H at distance d:**

$$H(d) = \frac{m}{2\pi d^3}$$

| Distance | H field | Equivalent B |
| :--- | :--- | :--- |
| 0.1 m | 23.5 mA/m | 29.5 pT |
| 1 m | 23.5 µA/m | 29.5 fT |
| 10 m | 23.5 nA/m | 29.5 aT |

These are small but detectable with a search coil or SQUID magnetometer at close range.

---

### ASCII Circuits

---

```
ME ANTENNA — PHYSICAL CONSTRUCTION (cross-section, not to scale)
════════════════════════════════════════════════════════════════════

      ←──────────── 87 mm (λ_acoustic/2 at 25 kHz) ────────────→

      ┌──────────────────────────────────────────────────────────┐  ↑
      │   Metglas 2605SA1  (magnetostrictive)                    │  │ 25µm
      ├──────────────────────────────────────────────────────────┤  │
      │   Epoxy bond  (M-Bond 610, target < 5µm)                 │  │ ~2µm
      ├──────────────────────────────────────────────────────────┤  │
      │                                                          │  │
      │   PZT-5A ceramic  (piezoelectric)                        │  │ 500µm
      │   Electrodes on top and bottom faces                     │  │
      │                                                          │  │
      ├──────────────────────────────────────────────────────────┤  │
      │   Epoxy bond  (M-Bond 610, target < 5µm)                 │  │ ~2µm
      ├──────────────────────────────────────────────────────────┤  │
      │   Metglas 2605SA1  (magnetostrictive)                    │  │ 25µm
      └──────────────────────────────────────────────────────────┘  ↓
                                                               Total ≈ 554µm

  NdFeB N35 disc (5mm×3mm)                 NdFeB N35 disc (5mm×3mm)
  ●  N pole                                                 S pole  ●
  │←──── H_bias ≈ 800 A/m along bar axis ────────────────────────→│

  Silver epoxy contacts to PZT electrodes:
  Top electrode  → Drive+ (fine wire bond, strain-relieved loop)
  Bottom electrode → Drive−  (same)

  Mount on foam or suspended by its own wire leads — do NOT clamp
  the bar ends or the acoustic resonance is killed.


ME ANTENNA — side view showing vibration mode
════════════════════════════════════════════════════════════════════

  At rest:
  ├─────────────────────────────────────────────────────────────────┤
                           L = 87mm

  At resonance (exaggerated):
  ├──────────────────────────────────────────────────────────────────┤ → extend
  ├────────────────────────────────────────────────────────────────┤   ← compress
  ├──────────────────────────────────────────────────────────────────┤ → extend

  Node (zero motion) at centre:   ↑ max motion at both ends ↑
                    ─────────────●─────────────
                              centre
  Mount point must be at the NODE (centre) if any support is used.
  Clamping anywhere else damps the resonance.
```

---

```
BUTTERWORTH-VAN DYKE IMPEDANCE MODEL — drive circuit view
════════════════════════════════════════════════════════════════════

                    Lm = 12.9mH    Cm = 3.14nF    Rm = 20Ω
                    ┌────UUUU────────┤├────────────/\/\/─┐
                    │         motional branch             │
  DRIVE ────────────┤                                     ├──── GND
                    │              C0 = 20nF              │
                    └──────────────┤├────────────────────┘

  Below f_r (25kHz): C0 dominates → capacitive load → drive wastes power
  At f_r:            only Rm seen → purely resistive → maximum power transfer
  Above f_r:         Lm dominates → inductive load → power factor drops

  MATCHING INDUCTOR (cancels C0, forces amplifier to see only Rm):

  L_match = 2.03mH placed in PARALLEL with the ME antenna terminals.

                    L_match = 2.03mH
  DRIVE+ ────UUUU──────────────────────┬──── ME antenna (+)
                                       │
                                     [BVD model above]
                                       │
  DRIVE− ──────────────────────────────┴──── ME antenna (−)

  At f_r: L_match and C0 resonate → appear as open circuit
  → amplifier sees only Rm = 20Ω → all power goes into vibration
```

---

```
FULL DRIVE CIRCUIT — MOSFET half-bridge, 25kHz, ~10W
════════════════════════════════════════════════════════════════════

                         +50V (HV supply)
                              │
                         ┌────┴────┐
                         │  Q1     │  ← IRF540N  (100V/33A)
                         │ Hi-side │    or IRF840 for higher voltage
                         └────┬────┘
                              │  ← bootstrap node
                         ┌────┴────────────────────────────┐
                         │         IR2104 gate driver       │
                         │  HIN ──← MCU PWM (25kHz, 50%)   │
                         │  LIN ──← same signal, inverted   │
                         │                                  │
                         │  Vb/Vs: bootstrap cap 100nF/100V │
                         └────┬────────────────────────────┘
                              │
                         ┌────┴────┐
                         │  Q2     │  ← IRF540N (lo-side)
                         │ Lo-side │
                         └────┬────┘
                              │
                             GND

  BRIDGE OUTPUT ──────────────┬──────── L_match (2.03mH air core)
                              │                │
                         [deadtime           [ME antenna]
                          120ns min]        C0=20nF + BVD
                              │                │
                             GND             GND

  DEAD TIME: Both Q1 and Q2 must NEVER be ON simultaneously.
  Use IR2104 built-in 520ns deadtime or add RC delay on gate.
  Without deadtime: +50V shorts to GND instantly — MOSFETs destroyed.


GATE DRIVE DETAIL (each MOSFET)
────────────────────────────────────────────────────────────────────

  IR2104 OUT ──[R_g 10Ω]──┬──── Gate
                           │
                         [D_fast]  ← BAT85 Schottky in parallel with R_g
                           │         Fast turn-OFF, slow turn-ON
                           │         Reduces switching noise
                        [R_pull]  ← 10kΩ gate-to-source
                           │         Keeps MOSFET OFF on startup
                          GND


VOLTAGE WAVEFORM AT BRIDGE OUTPUT
────────────────────────────────────────────────────────────────────

  +50V ─ ─ ─ ─┐      ┌──────┐      ┌──────┐      ┌──────
               │      │      │      │      │      │
    0V         └──────┘      └──────┘      └──────┘

  ← 40µs (25kHz period) →

  ME antenna + L_match form a series resonant circuit.
  Current through ME antenna is sinusoidal despite square wave drive:

  I_ME ─ ─ ─ ─╭──╮    ╭──╮    ╭──╮    ╭──╮
               ╯  ╰────╯  ╰────╯  ╰────╯  ╰
  (sine wave filtered by LC network)
```

---

```
DC BIAS APPLICATION
════════════════════════════════════════════════════════════════════

  TOP VIEW of ME antenna bar:

  [N magnet]──────────────[bar]──────────────[S magnet]
      ●  N                                        S  ●
      │←────────── H_bias along bar axis ─────────→│

  SIDE VIEW showing magnet standoff distance d:

                    ME bar (87mm × 20mm)
  ┌──────┐          ┌──────────────────────────────┐          ┌──────┐
  │ NdFeB│←── d ───│░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░│─── d ───→│ NdFeB│
  │ N35  │  5mm    │  Metglas / PZT-5A / Metglas   │  5mm    │ N35  │
  │ disc │          └──────────────────────────────┘          │ disc │
  └──────┘                                                     └──────┘
  5mm × 3mm                                                   5mm × 3mm
  B_r = 1.08T                                                 B_r = 1.08T

  CHECK BIAS LEVEL:
  Place SS49E Hall sensor flat on Metglas surface.
  Adjust magnet standoff d until Hall sensor reads 5–20 Oe (0.5–2.0 mT).
  Fix magnets with non-conductive epoxy at confirmed standoff distance.
  Do NOT use steel screws or brackets near the antenna — they distort H_bias.
```

---

```
IMPEDANCE SWEEP — finding mechanical resonance
════════════════════════════════════════════════════════════════════

  TEST SETUP:

  Function gen ──[R_sense 100Ω]──────────────── ME antenna
  (sine, 0.5Vpp)        │                           │
                        CH1                        CH2
                    (reference)               (across antenna)

  |Z| = |V_CH2| / I = |V_CH2| × R_sense / |V_CH1|

  SWEEP 10kHz to 40kHz, plot |Z| vs frequency:

  |Z|
   │
   │         C0 region
   │        (capacitive slope)
   │       ╲
   │        ╲         ← series resonance f_r
   │         ╲      ╱‾╲         |Z| = Rm ≈ 20Ω (minimum)
   │          ╲    ╱   ╲
  Rm ─ ─ ─ ─ ─╲──╱─ ─ ─╲─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─
   │            ╲╱       ╲      ← antiresonance f_a
   │                      ╲       |Z| = maximum
   │                       ╲
   └──────────────────────────────────────────── f
               f_r          f_a
              25kHz         25.5kHz (approx)

  f_r: minimum impedance → drive here for maximum current
  f_a: maximum impedance → avoid (current collapses)
  Separation f_a − f_r gives k_31 estimate:
    k_31² ≈ π²/4 × (f_a − f_r)/f_r


WAVEFORMS DURING NORMAL OPERATION
────────────────────────────────────────────────────────────────────

  DRIVE VOLTAGE (bridge output, square wave):
  +50V ─╮    ╭──╮    ╭──╮    ╭──╮
        ╰────╯  ╰────╯  ╰────╯  ╰────

  ANTENNA CURRENT (filtered to sine by LC resonance):
   5A ─ ─╭──╮    ╭──╮    ╭──╮    ╭──╮
          ╯  ╰────╯  ╰────╯  ╰────╯  ╰

  MECHANICAL VIBRATION AMPLITUDE (at resonance, peaks in ~Q cycles):
  0 ──╱‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾ (builds up over ~Q/f_r = 4ms)
     ← ring-up time Q/f_r ≈ 100/25000 = 4ms →

  RADIATED MAGNETIC FIELD (proportional to vibration amplitude):
  0 ──╱‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾‾
     ← 4ms ring-up before full output is reached →

  OOK DATA RATE LIMIT: t_settle = Q/f_r = 100/25000 = 4ms → max ~125 bits/s
  Reduce Q (intentionally degrade bond or add mechanical damping)
  to trade field strength for data rate — same trade-off as tuned loop.
```

---

### Component Selection Guide

```
COMPONENT REFERENCE — 25kHz ME antenna prototype
════════════════════════════════════════════════════════════════════

 Component         Value / Type            Notes
 ──────────────────────────────────────────────────────────────────
 PZT layer         PZT-5A                  40mm × 20mm × 0.5mm
                   APC International       Less fragile than PZT-5H
                   Part: 850               d31 = −171 pm/V

 Metglas layer     2605SA1 ribbon          87mm × 20mm × 0.025mm
                   Hitachi Metals          Two layers (top + bottom)
                                           Available in 25µm ribbon

 Epoxy             M-Bond 610              Cure 120°C for 1hr under
                   (Vishay Micro)          0.5MPa clamp pressure
                   or Hysol EA9361         Target bond line < 5µm

 Bias magnets      NdFeB N35               5mm dia × 3mm thick
                   disc magnets            Two pieces, one each end
                   (NOT N52 — too strong)  Adjust d to get 800 A/m

 Matching inductor 2.03mH air core         Wind on non-ferrous former
                   Q > 50 at 25kHz         26 AWG, measure with LCR
                                           after winding — trim turns

 Q1, Q2 (bridge)   IRF540N                 100V / 33A / 77mΩ
                   TO-220                  Logic-level compatible

 Gate driver       IR2104                  Bootstrap half-bridge driver
                   SOIC-8                  Built-in 520ns deadtime

 R_gate            10Ω / 0.25W            Each gate separately
 D_gate            BAT85 Schottky          Parallel with R_gate
                                           (fast turn-off)

 Bootstrap cap     100nF / 100V            Ceramic X7R
                   (C_boot)                Between Vb and Vs pins

 HV supply         40–60V DC               Switch-mode PSU or
                   500mA min               2× 24V laptop bricks
                                           in series

 R_sense (test)    100Ω / 2W              Wirewound, 4-wire
                                           Remove after tuning

 Hall sensor       SS49E                   TO-92 package
 (bias check)      Linear output           Vout = 2.5V at 0 field
                                           Sensitivity 1.4 mV/Gauss
```

---

### Testing Procedure

**Step 1 — Impedance sweep before bonding**

Test each layer separately first. Connect PZT plate to function generator through 100 Ω sense resistor. Sweep 10–40 kHz. Note the series resonance (current peak) — this is the free resonance of the bare piezo. It will shift downward slightly after bonding to Metglas because the composite is stiffer.

**Step 2 — Set and verify DC bias**

Before bonding magnets, slide them along the bar while monitoring the SS49E Hall sensor output on a multimeter. Mark the position where H = 800 A/m (SS49E output = 2.5 V + 0.8 V = 3.3 V). Bond magnets at that standoff with non-conductive epoxy. Allow full cure before applying any drive power.

**Step 3 — Impedance sweep of assembled antenna**

Repeat the sweep with the full bonded assembly. Confirm f_r has shifted from the bare-piezo value. Measure Rm from the minimum |Z| point. Calculate Q_mech from the 3 dB bandwidth:

$$Q_{mech} = \frac{f_r}{f_{upper} - f_{lower}} \quad \text{where } |Z| = \sqrt{2} \times R_m \text{ at } f_{upper,lower}$$

Target Q_mech > 50. If Q < 20, the bond is lossy — check for voids or excess epoxy.

**Step 4 — Low-power drive test (bench supply)**

Drive at 5 V (low power) at the measured f_r. Monitor antenna current with R_sense. Current should peak sharply at f_r. Mistuning by 50 Hz should reduce current by >50% at Q = 100. If the resonance is broad, Q is low.

**Step 5 — Radiation check**

Hold search coil (50T, 3 cm diameter) at 10 cm from the antenna midpoint, axis aligned with the bar axis. Connect to oscilloscope. At f_r you should see the radiated signal clearly. Rotate the search coil 90° — signal should drop to near zero (magnetic dipole null at 90° to the dipole axis).

**Step 6 — Full power and modulation**

Bring bridge supply to 50 V. Monitor antenna temperature — the bond epoxy must not exceed 80°C (above which it softens and the bond slips). For OOK modulation, gate the MCU PWM signal with data bits. Allow 4 ms (Q/f_r) settling time per symbol for full amplitude.

```
RADIATION PATTERN — top view (horizontal plane)
════════════════════════════════════════════════════════════════════

  Magnetic dipole pattern (figure-8):

             H_max
               ↑
               │
    ───────────●───────────  bar axis →
               │             (H = 0 along bar axis at 90°)
               ↓
             H_max

  Maximum radiation: perpendicular to bar length
  Null:              along bar length (both ends)

  Orient the antenna bar so the broadside faces your target.
```

---

# Making It Better

To make a Magnetoelectric (ME) antenna better, you have to overcome its biggest weakness: because it is so small, it doesn't "push" much energy into the air.

Using an **array** is the most professional way to scale this up. However, there are also material and electronic ways to boost performance.

---

### 1. The Array Approach (Power in Numbers)
Instead of one tiny "stamp" vibrating, you link dozens or hundreds of them together.

* **Constructive Interference:** If you line up 10 ME antennas and make them all vibrate at the exact same microsecond (in phase), their magnetic fields add together.
* **Beamforming:** By slightly timing the vibrations differently across the array, you can "steer" the radio beam in a specific direction without moving the antennas.
* **The "Speaker Wall" Analogy:** One tiny earbud speaker can't fill a stadium with sound, but a "wall of sound" (an array of hundreds of speakers) can. An ME array works exactly the same way for radio waves.

**Technical note:** For a power-boosting series array, all elements must share the same mechanical resonance frequency. A mismatch of even 20 Hz causes one element to act as a mechanical brake on the others. Elements are mounted on a shared elastic plate so the vibration of each helps drive its neighbours, creating a positive feedback loop. A microcontroller is required to synchronise the drive phase across all elements.

| Configuration | Primary Benefit | Notes |
| :--- | :--- | :--- |
| **Series (same frequency)** | Power & intensity | ~1.9× per unit added |
| **Parallel (offset frequencies)** | Bandwidth & data rate | Smears resonance peak |
| **Multilayer stack** | Compact efficiency | More coupling per cm³ |

---

### 2. Tuning for Resonance
To get the most power out of a single unit, you must find its **Mechanical Resonance**.

* **The Concept:** Every object has a frequency where it wants to vibrate (like a wine glass ringing when hit). If your VLF signal matches the physical "ring" frequency of your crystal sandwich, the vibration becomes much more violent, and the radio signal gets much stronger.
* **How to find it:** Sweep your drive frequency while monitoring current draw with a multimeter or oscilloscope. Current peaks (impedance dips) at the mechanical resonance. A NanoVNA or LCR meter gives you the same result faster.
* **How to trim it:** Slightly shaving or lapping the edges of the material changes its physical length and therefore its resonance frequency. Remove material in small steps and re-measure.

**Temperature drift:** Mechanical resonance shifts ±50–200 Hz as temperature changes by 10 °C. A Phase-Locked Loop (PLL) circuit continuously tracks the impedance minimum and adjusts the drive frequency to follow it. Without this, a 10 °C temperature swing can drop output by 90%.

---

### 3. DC Bias — The Magnetic Turbo
Magnetostrictive materials (the layers that create the radio wave) work correctly **only** if they are already under a static magnetic "pre-load."

* **The Improvement:** Place a small neodymium (NdFeB) permanent magnet at each end of the Metglas layer, poles aligned along the long axis of the device.
* **Why it is critical:** Without bias, the magnetostrictive response is non-linear. A 25 kHz drive signal produces a 50 kHz output (frequency doubling) instead of 25 kHz. The bias sets the linear operating point on the magnetostrictive curve, much like pulling a slingshot halfway back before you start — making the material much more sensitive to the tiny vibrations coming from the piezoelectric layer. Coupling efficiency roughly doubles compared to an unbiased device.
* **Practical level:** The optimum bias field for Metglas 2605SA1 is approximately 5–20 Oe. For Terfenol-D it is higher, around 200–500 Oe. Too much bias saturates the material and kills the effect.

---

### 4. Better Materials

The default material choices work but have practical problems. These alternatives are worth considering:

| Default | Better Alternative | Reason |
| :--- | :--- | :--- |
| Terfenol-D | **Galfenol (FeGa)** | Less brittle, machinable with normal tools, easier to source, good magnetostriction |
| PZT-5H | **PZT-5A** | Lower d₃₃ but far less fragile; PZT-5H cracks under sustained mechanical stress |
| Generic epoxy | **Hysol EA9361 or M-Bond 610** | Stiffer cure, thinner achievable bond line, better strain transfer |
| Metglas (generic) | **Metglas 2605SA1** | Best-characterised alloy for ME work, widely cited in research, available in ribbon form |

---

### 5. Bonding — The Real Bottleneck
The README says "glue these layers together" but bond quality is where most DIY builds fail. The coupling coefficient drops sharply if the glue layer exceeds a few microns:

1. **Polish** both mating surfaces to optical flatness — work through 400, 800, 1200 grit wet-and-dry
2. **Apply epoxy under vacuum** (a cheap food vacuum bag works) to eliminate air pockets
3. **Cure under clamp pressure** (~0.5–1 MPa) using a simple vice with felt pads
4. **Target bond line < 5 µm** — visible glue squeeze-out at the edges means you used too much

Silver-filled epoxy improves bonding for some alloy combinations. Cyanoacrylate (superglue) is an acceptable fast-prototype option but creeps under sustained vibration.

---

### 6. Driving Circuit Improvements

The TC4424A + IRL640A half-bridge from the earlier section is a good starting point. Two upgrades make a significant difference:

* **Class E amplifier:** Designed specifically for capacitive resonant loads (which is exactly what a piezo element is). Can reach >90% efficiency versus ~60% for the basic MOSFET half-bridge. Requires a tuned inductor but the component count is similar.
* **PLL frequency tracker:** As noted above, mechanical resonance drifts with temperature. A simple PLL (e.g., built around a 74HC4046 or implemented in an STM32 timer) locks the drive frequency to the impedance minimum automatically. This is essential for any deployment outside a temperature-controlled lab.

---

### 7. Single vs. Array Comparison

| Feature | Single ME Antenna | ME Array |
| :--- | :--- | :--- |
| **Size** | Tiny (~1 cm) | Larger (smartphone to tablet footprint) |
| **Range** | Very short (room-sized) | Long (through several walls or deeper soil) |
| **Complexity** | Simple — one drive wire | Requires sync circuit to keep elements in phase |
| **Power** | Micro-watts | Milli-watts to Watts |

---

### 8. Advanced: The Multi-Layer Stack
Instead of a 3-layer sandwich (Magnetic–Piezo–Magnetic), you can build a **multi-layer stack** — alternating thin layers of piezoelectric and magnetic material repeated 10–20 times (like a stack of pancakes).

Each additional layer adds more surface area that is "squeezing." This produces a much stronger magnetic field without making the antenna much wider or longer — just a bit thicker. Research prototypes with 20-layer stacks have demonstrated coupling coefficients roughly 3–4× higher than the equivalent single-layer device of the same footprint.

---

### 8. Verification and Measurement

There is no point tuning an ME antenna without a way to measure it:

* **Impedance sweep (NanoVNA or LCR meter):** Find the exact mechanical resonance frequency before applying any power. The resonance appears as a sharp dip in impedance. This frequency is your drive target.
* **Search coil:** Wind 20–50 turns of fine wire on a 5 cm former. Connect to an oscilloscope. Hold it 10–30 cm from the antenna while transmitting. You should see the VLF signal appear. This confirms the ME effect is producing radiation and not just the drive circuit wiring acting as an accidental antenna.
* **Lock-in technique:** For very low power levels, use a lock-in amplifier (or a software equivalent in an audio interface) referenced to your drive frequency. This pulls the ME signal out of the noise floor and lets you measure field strength quantitatively.

---

# Alternative Transmitter Approaches

Since you are looking for a balance between effectiveness, size, and cost, here are two more practical "alternative" paths for VLF transmission. While the Magnetoelectric (ME) antennas discussed above are high-tech and tiny, they are difficult to build at home.

Here is how a **Large Tuned Coil** and **Rotating Magnetic Fields** compare for a DIY-friendly, effective setup.

---

## 1. The Large Tuned Coil (The "High-Q" Loop)
This is the most "tried and true" method for VLF. Instead of miles of wire in the air, you use a lot of wire wrapped in a circle.

### How to make it better:
* **Tuning (Resonance):** This is the secret sauce. A coil by itself is just a heater. Add capacitors in series with the coil to match your target frequency and the impedance drops, allowing a massive amount of current to flow through the wire and creating a much stronger magnetic field.
* **Litz Wire:** At VLF frequencies, electricity tends to travel on the surface of the wire (the "skin effect"). Using Litz wire (thousands of tiny insulated strands) reduces resistance, making the antenna much more efficient.
* **Size vs. Turns:** A 1-meter diameter loop with 100 turns of wire is often more effective than a 10-meter loop with only 1 turn.
* **Ferrite core:** Insert a ferrite rod (like the ones found in old AM radios) through the centre. This concentrates the magnetic field and lets you shrink the antenna while keeping the same signal strength.

> **Simple analogy:** It is like a swing on a playground. If you push at just the right time (resonance), the swing goes high with very little effort. Without the capacitor tuning, it is like pushing the swing at the wrong time — you waste all your energy.

---

### Mathematics

---

#### 1. Loop Inductance

For a single-layer circular loop of N turns, mean radius r, wire radius a, wound with a pitch that gives a coil length l:

**Short coil / thick coil (Wheeler approximation — most practical loops):**

$$L = \frac{\mu_0 \pi N^2 r^2}{l + 0.9r} \quad \text{(air core, } l < 0.8r \text{)}$$

**Single-turn loop (l → 0):**

$$L_{1T} = \mu_0 r \left(\ln\frac{8r}{a} - 2\right)$$

**Multilayer winding correction** — if the coil is wound in b layers each of height h:

$$L_{multi} \approx L_{single} \times b^2 \quad \text{(layers in series)}$$

**Worked example** — 1 m diameter (r = 0.5 m), N = 100 turns, l = 0.05 m, wire radius a = 0.5 mm (24 AWG):

$$L = \frac{4\pi\times10^{-7} \times \pi \times 10000 \times 0.25}{0.05 + 0.45} = \frac{9.87\times10^{-3}}{0.5} \approx \mathbf{19.7 \text{ mH}}$$

---

#### 2. Skin Effect and Wire Resistance

At VLF, current crowds into a thin skin at the wire surface. The skin depth δ determines the effective conductor area:

$$\delta = \sqrt{\frac{\rho}{\pi f \mu_0}} = \frac{0.066}{\sqrt{f}} \text{ mm} \quad \text{(copper at 20°C)}$$

| Frequency | Skin depth δ | Wire diameters fully used |
| :--- | :--- | :--- |
| 1 kHz | 2.09 mm | Any wire < 4 mm dia fully used |
| 5 kHz | 0.93 mm | Only 1.86 mm dia fully used |
| 10 kHz | 0.66 mm | Only 1.32 mm dia fully used |
| 25 kHz | 0.42 mm | Only 0.84 mm dia fully used |

**AC resistance of a solid wire at frequency f:**

$$R_{AC} = R_{DC} \times \frac{r_{wire}}{2\delta} \quad \text{(when } r_{wire} \gg \delta \text{)}$$

**Why Litz wire fixes this:** Litz wire consists of many individually insulated strands, each thinner than δ. All strands carry equal current. Total AC resistance equals the DC resistance of one strand divided by the number of strands — no skin penalty.

For 25 kHz (δ = 0.42 mm), each Litz strand must be < 0.84 mm diameter. Standard Litz for 25 kHz uses strands of 0.1 mm (38 AWG).

**Resistance ratio** — solid 20 AWG (r = 0.406 mm) vs Litz at 10 kHz (δ = 0.66 mm):

$$\frac{R_{AC}}{R_{DC}} = \frac{0.406}{2 \times 0.66} \approx 0.31 \quad \rightarrow \text{solid wire is fine here}$$

At 25 kHz with 18 AWG (r = 0.51 mm):

$$\frac{R_{AC}}{R_{DC}} = \frac{0.51}{2 \times 0.42} \approx 0.61 \rightarrow 1.6\times \text{ penalty — Litz starts to pay off}$$

**Rule of thumb:** Use Litz wire when the wire radius exceeds the skin depth. Below 10 kHz with wire thinner than 16 AWG, solid wire is adequate.

---

#### 3. Resonant Capacitor

Series resonance makes the loop impedance purely resistive (= R_wire), allowing maximum current for a given source voltage:

$$f_0 = \frac{1}{2\pi\sqrt{LC}} \implies C_{res} = \frac{1}{(2\pi f_0)^2 L}$$

**Lookup table (L = 19.7 mH, 1 m loop, 100T):**

| Target f₀ | C_res | Nearest E12 |
| :--- | :--- | :--- |
| 500 Hz | 5.14 µF | 4.7 µF |
| 1 kHz | 1.29 µF | 1.2 µF |
| 5 kHz | 51.4 nF | 47 nF |
| 10 kHz | 12.8 nF | 12 nF |
| 25 kHz | 2.06 nF | 2.2 nF |

**Voltage across capacitor at resonance** — can be very high:

$$V_C = Q \times V_{source}$$

For Q = 50 and V_source = 10 V: V_C = 500 V peak. Use capacitors rated ≥ 2× this value. Polypropylene film capacitors (MKP type) handle high AC voltage and high ripple current — electrolytics will fail immediately.

---

#### 4. Q Factor

Q is the single most important figure of merit. It multiplies the circulating current (and therefore the radiated field) for free:

$$Q = \frac{\omega_0 L}{R_{total}} = \frac{2\pi f_0 L}{R_{wire} + R_{source}}$$

where R_source is the output impedance of the driving amplifier (aim for < 0.1 Ω — use a current-mode or low-impedance voltage amp).

**Q for the worked example at 1 kHz** with R_wire = 2 Ω (100T of 24 AWG, 1 m loop ≈ 314 m wire):

$$Q = \frac{2\pi \times 1000 \times 19.7\times10^{-3}}{2} = \frac{123.8}{2} \approx \mathbf{62}$$

**Circulating current and radiated field:**

$$I_{circ} = Q \times I_{source}$$

$$H_{axis}(d) = \frac{N \, I_{circ} \, r^2}{2(r^2 + d^2)^{3/2}} \quad \text{(on axis, near field)}$$

For d ≫ r (far from the loop):

$$H(d) \approx \frac{N \, I_{circ} \, \pi r^2}{2\pi \, d^3} = \frac{m}{2\pi \, d^3}$$

where m = N × I_circ × A is the **magnetic dipole moment** (A·m²). Maximising m is the design goal.

**Dipole moment for worked example** at Q = 62, I_source = 1 A:

$$m = N \times I_{circ} \times \pi r^2 = 100 \times 62 \times \pi \times 0.25 \approx \mathbf{4869 \text{ A·m}^2}$$

**Field at 100 m:**

$$H(100) = \frac{4869}{2\pi \times 10^6} \approx 0.78 \text{ mA/m}$$

**Bandwidth** (how precisely C_res must be tuned):

$$\Delta f = \frac{f_0}{Q} = \frac{1000}{62} \approx 16 \text{ Hz}$$

A high-Q loop is frequency-selective. If your transmit frequency drifts more than ~8 Hz from f₀, power drops by 3 dB. Use a variable capacitor or a bank of switched fixed caps for tuning.

---

#### 5. Amplifier Power and Impedance Matching

The amplifier sees a resistive load R_wire at resonance. Required amplifier output power for a target circulating current:

$$P_{amp} = I_{circ}^2 \times R_{wire} = (Q \times I_{source})^2 \times R_{wire}$$

Rearranging for target I_circ:

$$P_{amp} = \frac{I_{circ}^2 \times R_{wire}}{1} \quad \implies \quad I_{circ} = \sqrt{\frac{P_{amp}}{R_{wire}}}$$

For R_wire = 2 Ω and P_amp = 50 W:

$$I_{circ} = \sqrt{\frac{50}{2}} = 5 \text{ A} \quad \implies \quad m = 100 \times 5 \times \pi \times 0.25 \approx 393 \text{ A·m}^2$$

**Impedance transformation** — if the amplifier output impedance is 4–8 Ω but R_wire is 0.5 Ω, a coupling transformer with turns ratio n:

$$n = \sqrt{\frac{R_{amp}}{R_{wire}}} = \sqrt{\frac{8}{0.5}} = 4 \implies \text{4:1 transformer}$$

Or use a **link coil**: wind 2–5 turns of heavy wire separately on the same loop former, connect to amp. The link coil magnetically couples power in without direct electrical connection — provides inherent impedance transformation and galvanic isolation.

---

#### 6. Ferrite-Loaded Loop (Size Reduction)

Adding a ferrite rod through the loop centre multiplies effective permeability by μ_eff:

$$L_{ferrite} = \mu_{eff} \times L_{air}$$

$$\mu_{eff} \approx \frac{\mu_r}{1 + D_m(\mu_r - 1)}$$

where D_m is the **demagnetisation factor** of the rod (depends on length-to-diameter ratio):

| Rod l/d ratio | D_m | μ_eff (μᵣ = 2000) |
| :--- | :--- | :--- |
| 10 | 0.020 | ≈ 48 |
| 20 | 0.006 | ≈ 147 |
| 50 | 0.001 | ≈ 667 |
| 100 | 0.0003 | ≈ 1250 |

A long, thin rod (high l/d) gives better μ_eff. A 200 mm × 10 mm rod (l/d = 20) gives μ_eff ≈ 147, reducing the required number of turns by √147 ≈ 12× for the same inductance.

---

### ASCII Circuits

```
COMPLETE TUNED LOOP TRANSMITTER
════════════════════════════════════════════════════════════

OVERVIEW — block diagram
────────────────────────────────────────────────────────────

  ┌──────────┐    ┌───────────┐    ┌──────────┐    ┌──────────────┐
  │   MCU    │    │  Class D  │    │ Coupling │    │  TUNED LOOP  │
  │ (Teensy) ├───▶│  Amp      ├───▶│ network  ├───▶│  ANTENNA    │
  │ sine out │    │ TPA3118   │    │ (see     │    │  N=100T     │
  │ or PWM   │    │ or LM3886 │    │ below)   │    │  r=0.5m     │
  └──────────┘    └───────────┘    └──────────┘    └──────────────┘
                      │                                    │
                     +12–24V                    C_res in series
                                                (1.2µF at 1kHz)


DIRECT DRIVE — simplest connection (low impedance amp)
────────────────────────────────────────────────────────────

  Amp (+) ────────────────┬────────────────────────┐
                          │                        │
                       [C_res]               [LOOP COIL]
                       1.2µF                 N=100T, r=0.5m
                       MKP film              L≈19.7mH
                       500V rating           R_wire≈2Ω
                          │                        │
  Amp (−) ────────────────┴────────────────────────┘
                          │
                         GND (amp reference)

  ← Series LC resonant circuit — amp drives only R_wire at f₀ →
  ← Capacitor and inductor voltages are equal and opposite    →
  ← Net impedance = R_wire ≈ 2Ω at resonance                 →


LINK COIL DRIVE — impedance matching for high-power amps
────────────────────────────────────────────────────────────

  Amp (+) ─────────────────┐
                           │
                      [LINK COIL]    ← 3–5T of 14AWG wound
                      3T, 14AWG        on same former as
                      (no cap needed)  main loop. Not electrically
                           │           connected to main coil.
  Amp (−) ─────────────────┘

                      [MAIN LOOP]    ← 100T, separate winding
                      100T, Litz       on same former
                    ┌──────┬──────┐
                    │      │      │
                 [C_res]  GND    GND
                 1.2µF              ← one end of main loop
                 MKP                  grounded for safety


VARIABLE TUNING — switched capacitor bank
────────────────────────────────────────────────────────────

  LOOP ──┬────[C1: 0.68µF]────[SW1]────┐
         ├────[C2: 0.33µF]────[SW2]────┤
         ├────[C3: 0.15µF]────[SW3]────┤
         ├────[C4: 0.068µF]───[SW4]────┤
         └────[C_trim: 0–100nF]─────────┘── GND
               (air variable cap)

  Binary-weighted cap bank + trim cap covers full VLF range.
  SW1–SW4 = relay or analogue switch (DG411).
  Trim cap allows fine resonance centering.


FULL SCHEMATIC — 1kHz, 50W transmitter
────────────────────────────────────────────────────────────

                        +24V
                          │
                    ┌─────┴──────┐
                    │  LM3886    │   ← 68W audio power amp
                    │  power amp │     in non-inverting config
                    │            │     gain = 20 (26dB)
     MCU sine ─────▶│ IN+        │
     (1kHz, 1Vpp)   │            │
                    │  OUT ──────┼──────────────┐
                    │            │              │
                    └─────┬──────┘           [C_res]
                          │                  1.2µF / 500V
                         GND                 MKP film
                                                │
                                                │
                                   ┌────────────┴──────────────────┐
                                   │                               │
                                   │    LOOP ANTENNA               │
                                   │    ┌─────────────────────┐    │
                                   │    │                     │    │
                                   │    │   100 turns         │    │
                                   │    │   Litz 0.1mm×50str  │    │
                                   │    │   wound on 1m dia   │    │
                                   │    │   PVC pipe frame    │    │
                                   │    │                     │    │
                                   │    └─────────────────────┘    │
                                   │                               │
                                   └───────────────────────────────┘
                                                   │
                                                  GND


LOOP FORMER — physical construction (cross section)
────────────────────────────────────────────────────────────

      ←───────── 1 metre diameter ─────────→

                    Litz wire
                    (100 turns)
                       ↓↓↓
    ┌──────────────────────────────────────┐  ← PVC pipe 20mm OD
    │██████████████████████████████████████│     (loop former)
    │██  winding channel  (25mm wide)  ████│
    │██████████████████████████████████████│
    └──────────────────────────────────────┘

  Octagonal frame (8 straight sections of PVC pipe
  joined by 135° elbows) is easier to build than a
  true circle and has <2% inductance error.

  ←── 8 sides ──→   each side = 2r×sin(π/8) ≈ 0.383m for r=0.5m

      ┌─────────┐
     /           \
    /             \
   │               │   ← octagonal loop, top view
   │               │     r = 0.5m (centre to side midpoint)
    \             /
     \           /
      └─────────┘


FERRITE ROD OPTION — fold the loop onto a rod
────────────────────────────────────────────────────────────

  WITHOUT FERRITE (1m loop, 100T, air):
  ┌──────────────────────────────────────┐
  │                                      │  L ≈ 19.7 mH
  └──────────────────────────────────────┘  100T needed for target L

  WITH FERRITE ROD (200mm × 10mm, μᵣ=800 rod, μ_eff≈120):
  ████████████████████████████████████████  L ≈ 19.7 mH
  (turns wound tightly on rod)              only 9T needed!
  N_ferrite = N_air / √μ_eff = 100/√120 ≈ 9T

  Same inductance, same resonant frequency, 9T vs 100T.
  Trade-off: rod saturates at lower current than air-core loop.
  Saturation current: I_sat = H_sat × l_rod / N_ferrite


MEASUREMENT POINTS
────────────────────────────────────────────────────────────

  Amp ──[R_sense 0.1Ω]──[C_res]──[LOOP]── Amp
         │                        │
        CH1                      CH2    ← oscilloscope channels
     (source                  (across
      current)                 loop)

  At resonance:
    CH1 peaks (max current)
    Phase(CH1) = Phase(CH2) (voltage and current in phase)
    V_loop = I_circ × R_wire (should be small — most voltage
                               is across C_res)
```

---

### Signal Waveforms

```
TUNED LOOP — waveforms at resonance (1kHz, Q=62)
════════════════════════════════════════════════════════════

AMP OUTPUT VOLTAGE:
  V_amp  ╭──╮    ╭──╮    ╭──╮    ╭──╮    ╭──╮
   10Vpp ╯  ╰────╯  ╰────╯  ╰────╯  ╰────╯  ╰────
         ←──── 1ms ────→

LOOP CURRENT (×Q = 62 amplification):
  I_circ ╭──╮    ╭──╮    ╭──╮    ╭──╮    ╭──╮
   ~5A    ╯  ╰────╯  ╰────╯  ╰────╯  ╰────╯  ╰────
         ← IN PHASE with V_amp at resonance →

VOLTAGE ACROSS C_res (= Q × V_amp, opposite polarity to V_loop):
  V_C   ─╮    ╭────╮    ╭────╮    ╭────╮    ╭───
  620Vpp  ╰────╯    ╰────╯    ╰────╯    ╰────╯
         ← 180° phase shifted from V_amp →
         WARNING: 620V peak on capacitor!

VOLTAGE ACROSS LOOP (= I_circ × R_wire, tiny compared to V_C):
  V_loop ╭─╮   ╭─╮   ╭─╮   ╭─╮   ╭─╮
    10V   ╯ ╰───╯ ╰───╯ ╰───╯ ╰───╯ ╰───
         ← same phase as V_amp →

RADIATED H FIELD (proportional to I_circ):
  H(t)  ╭──╮    ╭──╮    ╭──╮    ╭──╮    ╭──╮
         ╯  ╰────╯  ╰────╯  ╰────╯  ╰────╯  ╰────
```

---

### Component Selection Guide

```
COMPONENT REFERENCE — 1kHz, 50W, 1m loop
════════════════════════════════════════════════════════════

 Component       Value / Type              Notes
 ──────────────────────────────────────────────────────────
 Loop former     1m dia octagon            8× 383mm PVC pipe
                 PVC 20mm OD               + 135° elbows

 Loop wire       100T Litz                 0.1mm strand dia
                 0.1mm × 100 strands       for f > 5kHz
                 or 20AWG solid            adequate below 5kHz

 C_res           1.2µF / 630V              WIMA MKP10 or
                 polypropylene film        Vishay MKP1848
                 (NOT electrolytic)        High ripple current

 Power amp       LM3886 (68W)              Non-inverting, gain=20
                 or TPA3118 (30W)          Add heatsink to LM3886
                 or subwoofer plate amp    Plate amp = easiest build

 MCU             Arduino / Teensy          Sine wave via DAC
                 + DAC output              or PWM + RC filter

 R_sense         0.1Ω / 5W                Wirewound or
 (test only)     4-wire Kelvin             current sense resistor

 Ferrite rod     200mm × 10mm             Fair-Rite type 77
 (optional)      μᵣ = 2000                reduces turns needed
                                           by factor √μ_eff ≈ 12×

 Variable cap    0–500pF air variable      Fine tuning only
 (trim)          or 10-gang AM radio       Stack multiple for
                 variable                  larger range
```

---

### Testing Procedure

**Step 1 — Measure loop inductance bare**

Connect LCR meter across the loop with no capacitor. Measure L at the target frequency. Verify it matches the Wheeler formula within 10%. If not, recount turns.

**Step 2 — Calculate and fit C_res**

Use C = 1/(4π²f²L). Fit the nearest value. Connect in series. Measure the series resonant frequency with a function generator and R_sense resistor — sweep until current peaks. Note actual f₀.

```
  Sweep test setup:

  Func gen ──[R_sense 10Ω]──[C_res]──[LOOP]──┐
                 │                            │
                CH1                          CH2
            (reference)                  (loop voltage)

  Resonance: V_CH2 minimum (loop looks like short = R_wire)
             I = V_CH1/R_sense = maximum
```

**Step 3 — Measure Q and R_wire**

At resonance, measure V across R_sense (= I_circ × R_sense) and V across the whole LC:

$$Q = \frac{V_{loop}}{V_{source}} \quad R_{wire} = \frac{V_{source}}{I_{circ}}$$

If Q < 20, R_wire is too high — check solder joints, connection resistance, and wire gauge.

**Step 4 — Check capacitor voltage**

With a ×10 probe, measure voltage across C_res at operating power. Verify it is within capacitor rating. For Q=62 and 10V source: expect ~620V across C_res. Use capacitors rated ≥ 2× measured peak.

**Step 5 — Search coil verification**

Hold a 20-turn, 5 cm search coil at 1 m from loop. Connect to oscilloscope. Signal should be clearly visible. Walk the search coil away — note the distance at which it drops into the noise floor. This is your effective range under current conditions.

**Step 6 — OOK modulation**

To modulate: gate the amplifier input with the MCU (multiply the sine wave by a data bit). Alternatively, switch a series MOSFET in the amp supply rail. Verify with the search coil that the signal switches cleanly. Rise/fall time is limited only by the loop Q:

$$t_{settle} = \frac{Q}{\pi f_0} = \frac{62}{\pi \times 1000} \approx 20 \text{ ms}$$

A loop with Q = 62 at 1 kHz takes ~20 ms to ring up and down — this sets the maximum OOK data rate to ~25 bits/s. Reduce Q (add series resistance) to trade field strength for higher data rate.

---

## 2. Rotating Magnetic Fields (Mechanical Antennas)
A clever, low-tech approach: instead of using electricity to create a magnetic field, you use **physical motion**.

### How it works:
* Take a very strong **permanent magnet** (Neodymium N52 grade).
* Spin it at high RPM using a motor.
* The spinning magnet creates a moving magnetic field. To a radio receiver, this looks exactly like a VLF radio wave.

### Why it works well:
* **Efficiency:** It is much easier to spin a magnet with a small motor than to build a high-power amplifier driving a large wire antenna.
* **Simplicity:** No complex RF electronics needed. A motor controller (e.g., an ESC used for drones) varies the motor speed to set the transmit frequency.
* **Modulation:** Data is sent by slightly speeding up or slowing down the motor — this is Frequency Shift Keying (FSK) implemented mechanically.
* **Penetration:** Magnetic fields at very low frequencies (300 Hz to 3 kHz) are almost impossible to block with soil or concrete, making rotating-magnet transmitters well suited to through-the-earth communication.

---

## 2b. Modulating a Rotating Magnet Without Changing Motor Speed

The biggest weakness of the mechanical approach is **inertia**. A physical motor and magnet have mass, so you cannot speed them up or slow them down fast enough to send data at a reasonable rate — the lag is too great.

The solution: leave the mechanical side spinning at a constant, locked RPM to generate the carrier wave, and use **electrical interference** to shape the magnetic field as it leaves the device.

---

### Method 1: The "Magnetic Shutter" (Flux Switching)
Instead of changing the magnet, you change the path the magnetic field takes.

* **The Concept:** Place a stationary coil of wire (a stator) or a piece of high-permeability material (e.g., a ferrite core) between the spinning magnet and your target.
* **The Modulation:** An electronic circuit pumps current into the stationary coil. When the coil is ON, it creates its own magnetic field that cancels or redirects the spinning magnet's field.
* **The Result:** To a receiver, the spinning magnet appears to "disappear" or "flip." This can be done thousands of times per second (On/Off Keying) because electrons in the circuit move at nearly the speed of light while the magnet keeps spinning at constant RPM.

---

### Method 2: Stator Coil Injection (Active Cancellation)
Surround the spinning magnet with a fixed set of coils — similar to the casing of an electric motor.

* **The Setup:** The magnet spins inside at a constant frequency (e.g., a 1 kHz carrier wave).
* **The Modulation:** Timed pulses of power are sent into the surrounding coils to achieve:
    * **Phase Shift Keying (PSK):** Briefly drag or push the magnetic field to change its phase position without changing motor speed.
    * **Amplitude Modulation (AM):** Partially oppose the field to make the signal appear weaker or stronger.

> **Analogy:** The spinning magnet is like a steady lighthouse beam. Instead of speeding up the lighthouse (impossible), you put a fast electronic shutter in front of the lens to blink out a message.

---

### Method 3: The Variable Reluctance Method (Hybrid)
The most efficient DIY approach for electrical modulation of a rotating field.

* **How to Build It:** Use a spinning "reluctance rotor" — a shaped piece of iron or ferrite — instead of a spinning permanent magnet.
* **The Excitation:** Place a large, stationary excitation coil next to the rotor.
* **The Operation:**
    1. The rotor spins at a high, constant speed.
    2. Your circuit sends the VLF data signal into the stationary excitation coil.
    3. The spinning iron rotor "chops" the electrical signal and radiates it as a VLF wave.
* **Why it is better:** The spinning part is just iron — no magnet. You have complete control over the field through the stationary coil wires. A single MOSFET can switch the signal on and off instantly.

---

### Modulation Method Comparison

| Method | Data Speed | Complexity | Key Principle |
| :--- | :--- | :--- | :--- |
| **Motor Speed Change** | Very slow | Low | Limited by mechanical inertia |
| **Magnetic Shutter** | Fast | Medium | Coil "blinds" or redirects the magnet |
| **Variable Reluctance** | **Fastest** | Higher | Spinning iron chops a stationary electrical signal |

**Build recommendation:** Keep the motor locked at constant RPM for the carrier. Drive a secondary stationary coil with a high-power MOSFET circuit to interrupt or add to the magnetic field. This gives the raw magnetic power of a spinning magnet with the high-speed switching of digital electronics.

---

## 2c. Building the Variable Reluctance "Magnetic Chopper"

This is essentially a specialised electric motor where the output is a VLF radio wave rather than mechanical torque. The heavy mechanical parts run at constant speed; the electronics handle all the high-speed data switching.

---

### 1. The Mechanical Core: The Chopper Rotor
Instead of spinning a heavy magnet, you spin a reluctance rotor — a piece of material that magnetic fields travel through easily, such as soft iron or ferrite.

* **Shape:** Cut a disc of soft iron or high-permeability steel into a "butterfly" or gear shape with 2 or 4 large teeth.
* **Motor:** Use a high-speed brushless DC motor (drone motor). Carrier frequency equals (Rotations Per Second × Number of Teeth).
    * *Example:* A 1 kHz carrier with a 2-tooth rotor requires 30,000 RPM.
* **Balancing:** At these speeds, even a small vibration destroys the bearings. The rotor must be balanced precisely before running at full speed.

---

### 2. The Electrical Core: Excitation and Modulation Coils
Two stationary coils sit very close to the spinning rotor, without touching it.

* **Primary Coil (The Field):** Creates a steady magnetic field. When a tooth of the rotor passes by, it pulls the field through itself; when the gap passes, the field collapses. This chopping action radiates the magnetic field into the surrounding medium.
* **Modulation Coil (The Data):** Wrapped around the same ferrite core as the primary coil. Your signal is injected here.
* **Air Gap:** The distance between the spinning teeth and the stationary coils must be as small as possible — under 1 mm. The smaller the gap, the more efficient the transmitter.

---

### 3. The Electronic Driver Circuit

* **Power Stage:** A high-power MOSFET (e.g., IRFZ44N) switches the current in the stationary coils.
* **Logic:**
    1. **Carrier:** The motor creates the steady VLF frequency by mechanical chopping.
    2. **Data:** A microcontroller (Arduino, Teensy) sends bits to the MOSFET gate.
    3. **Action:** MOSFET ON → strong field → chopper radiates → **Bit 1**. MOSFET OFF → no field → silence → **Bit 0**.
* **Protection:** A flyback diode (1N4007 or Schottky) across the coil is mandatory. Switching an inductive load without one destroys the MOSFET instantly from inductive kickback.

---

### 4. Step-by-Step Build Order

1. **Frame:** Build a rigid base from wood or plastic — not metal, which creates eddy currents that steal power.
2. **Rotor:** Mount the iron butterfly rotor on the motor shaft. Run up slowly and check for vibration before reaching operating speed.
3. **Stator:** Mount a ferrite rod with coils wound around it. Position the rod end so rotor teeth pass directly in front of it with minimum air gap.
4. **Driver:** Build the MOSFET circuit on breadboard or PCB. Use a separate 12–24 V supply for the coils to keep switching noise away from the microcontroller.
5. **Sync sensor:** Fit an optical tachometer sensor (slotted IR sensor) on the rotor. Feed its output to an interrupt pin on the microcontroller so your code knows the exact rotor position and can time data pulses to tooth arrival.

---

### 5. Why This Outperforms a Pure Spinning Magnet

You are "valving" the magnetism electronically rather than mechanically. The difference is the same as turning a garden hose on and off by stopping the city's water pump (slow — inertia) versus kinking the hose with your hand (fast — nearly instant). Data rates that are impossible with motor-speed FSK become straightforward with MOSFET switching.

> **Safety:** At 30,000 RPM a rotor failure is like a small explosion. Always enclose the spinning assembly in a thick wooden or plastic containment shield during testing.

---

### Frequency Calculator

$$f_{\text{carrier}} = \frac{\text{RPM}}{60} \times N_{\text{teeth}}$$

| Target Frequency | 2-Tooth Rotor | 4-Tooth Rotor |
| :--- | :--- | :--- |
| 500 Hz | 15,000 RPM | 7,500 RPM |
| 1 kHz | 30,000 RPM | 15,000 RPM |
| 3 kHz | 90,000 RPM | 45,000 RPM |

For frequencies above 1 kHz with a 2-tooth rotor, RPM demands become extreme. A 4-tooth rotor running at 15,000 RPM (achievable with most drone motors) is the practical sweet spot for a first build targeting a 1 kHz carrier.

---

## 2d. Solid-State Magnetic Modulators — The Safe Alternative

A heavy metal rotor spinning at 30,000 RPM stores massive kinetic energy. A shaft or adhesive failure turns it into shrapnel. The same high efficiency and small size are achievable with **no moving parts at all** by using high-permeability ferrite cores and a property called **magnetic saturation**.

---

### The Saturable Core Modulator ("Solid-State Chopper")

Normal ferrite conducts magnetic flux easily — like a pipe for magnetism. But flood it with too much magnetism and it saturates: the core can hold no more and behaves like empty air. A small DC current in a control coil is all it takes to flip the core between "conducting" and "transparent." This is a magnetic on/off switch with no moving parts.

**How to build it:**

1. **Core:** Toroid (donut) ferrite core. Type 77 (μᵣ ≈ 2000) or Type 43 (μᵣ ≈ 850) are both readily available and well characterised.
2. **Carrier coil:** Wind ~50 turns of 26 AWG wire around the toroid. Connect to your VLF power source through a resonant capacitor (see maths below).
3. **Control coil:** Wind ~20 turns of 22 AWG wire on the same toroid, in the **opposing** sense to the carrier coil. This is the "shutter" driven by your MOSFET.
4. **Modulation:** Control coil OFF → core unsaturated → carrier radiates. Control coil ON (DC current) → core saturated → carrier cannot radiate. Switch at any rate your MOSFET can handle — megahertz if needed.

---

### Mathematics

---

#### 1. The BH Curve — Core Physics

The behaviour of the saturable core is governed by its B-H (flux density vs field intensity) curve. Understanding this curve is the foundation of all the numbers below.

```
B (Tesla)  B-H CURVE — Type 77 Ferrite
  │
  B_sat ──────────────────────────────── ← saturation knee
0.35T │                        ╱‾‾‾‾‾‾‾
      │                      ╱
      │                    ╱   ← linear region
      │                  ╱      slope = μ₀ × μᵣ
      │                ╱
      │              ╱
      │            ╱
      │──────────╱──────────────────────  H (A/m)
      0        H_sat
              120 A/m

  Below H_sat : core is a high-permeability conductor (μᵣ ≈ 2000)
  Above H_sat : core saturates — μᵣ drops to ≈ 1 (air)
  Control coil pushes H past H_sat → carrier coil sees air core → L collapses → circuit detunes → radiation stops
```

---

#### 2. Core Inductance (Unsaturated State)

$$L_{open} = \frac{\mu_0 \, \mu_r \, N_c^2 \, A_e}{l_e}$$

| Symbol | Meaning | Type 77 toroid 25 mm OD |
| :--- | :--- | :--- |
| μ₀ | Permeability of free space | 4π × 10⁻⁷ H/m |
| μᵣ | Relative permeability (unsaturated) | 2000 |
| Aₑ | Effective cross-section area | 52 × 10⁻⁶ m² |
| lₑ | Effective magnetic path length | 0.063 m |
| N_c | Carrier coil turns | 50 |

$$L_{open} = \frac{4\pi\times10^{-7} \times 2000 \times 2500 \times 52\times10^{-6}}{0.063} \approx \mathbf{5.2 \text{ mH}}$$

**Saturated inductance** — when the control coil drives the core into saturation, μᵣ collapses to ≈ 1:

$$L_{sat} = \frac{\mu_0 \times 1 \times N_c^2 \times A_e}{l_e} = \frac{L_{open}}{\mu_r} = \frac{5.2\text{ mH}}{2000} \approx \mathbf{2.6\ \mu\text{H}}$$

This is a factor-of-2000 inductance collapse. The resonant circuit is violently detuned — carrier current drops to near zero.

---

#### 3. Saturation Control Current

The control coil must generate enough magnetomotive force (MMF) to push the core past H_sat:

$$\text{MMF}_{sat} = H_{sat} \times l_e$$

$$I_{sat} = \frac{H_{sat} \times l_e}{N_{ctl}}$$

| Parameter | Type 77 | Type 43 |
| :--- | :--- | :--- |
| H_sat | 120 A/m | 80 A/m |
| lₑ (25 mm OD toroid) | 0.063 m | 0.063 m |
| MMF required | 7.56 A·t | 5.04 A·t |
| I_sat (N_ctl = 20T) | **378 mA** | **252 mA** |
| I_sat (N_ctl = 10T) | **756 mA** | **504 mA** |

More control turns → lower saturation current → smaller MOSFET → less switching loss. Trade-off: more turns = slower switching due to higher control coil inductance.

**Control coil inductance** (limits switching speed):

$$L_{ctl} = \frac{\mu_0 \, \mu_r \, N_{ctl}^2 \, A_e}{l_e} = \frac{4\pi\times10^{-7} \times 2000 \times 400 \times 52\times10^{-6}}{0.063} \approx 0.83 \text{ mH}$$

**Maximum switching frequency** (set by control coil RL time constant with gate resistor and MOSFET on-resistance):

$$f_{max} = \frac{R_{total}}{2\pi \, L_{ctl}} = \frac{12\text{ V} / I_{sat}}{2\pi \times L_{ctl}}$$

With R_total = V_supply / I_sat = 12/0.378 ≈ 32 Ω:

$$f_{max} \approx \frac{32}{2\pi \times 8.3\times10^{-4}} \approx 6.1 \text{ kHz}$$

For higher data rates, reduce N_ctl (accept higher I_sat) or raise supply voltage.

---

#### 4. Resonant Carrier Circuit

Series resonance with the carrier coil maximises circulating current and therefore radiated field:

$$f_0 = \frac{1}{2\pi\sqrt{L_{open} \, C_{res}}} \implies C_{res} = \frac{1}{(2\pi f_0)^2 \, L_{open}}$$

| Target f₀ | C_res (L = 5.2 mH) | Nearest E12 value |
| :--- | :--- | :--- |
| 500 Hz | 19.5 µF | 18 µF (2 × 10 µF series — use film caps) |
| 1 kHz | 4.87 µF | 4.7 µF |
| 5 kHz | 195 nF | 180 nF |
| 10 kHz | 48.7 nF | 47 nF |
| 25 kHz | 7.8 nF | 8.2 nF |

**At resonance**, the impedance is purely resistive (= R_wire). The voltage across L and C individually can be Q times the source voltage — do not use electrolytic capacitors. Use polypropylene film only.

---

#### 5. Q Factor and Circulating Current

$$Q = \frac{2\pi f_0 L_{open}}{R_{wire}} = \frac{\omega_0 L}{R}$$

$$I_{circ} = Q \times I_{source}$$

| R_wire (Ω) | Q at 1 kHz (L = 5.2 mH) | Circulating current (1 A source) |
| :--- | :--- | :--- |
| 0.3 | 109 | 109 A |
| 1.0 | 32.7 | 32.7 A |
| 3.0 | 10.9 | 10.9 A |

High circulating current = strong radiated H-field. Every ohm of winding resistance costs you. Use 20 AWG or heavier for the carrier coil; measure R_wire with a 4-wire (Kelvin) measurement before winding.

**Radiated magnetic field** at distance d (near field, d ≪ λ):

$$H(d) = \frac{N_c \, I_{circ} \, A_{coil}}{2\pi \, d^3}$$

where A_coil = πr² is the coil area. Doubling Q doubles I_circ and doubles H(d).

---

#### 6. Carrier Suppression Ratio

How well does saturation kill the carrier? The suppression ratio (in dB) is determined by the inductance ratio:

$$\text{Suppression} = 20\log_{10}\!\left(\frac{L_{open}}{L_{sat}}\right) = 20\log_{10}(\mu_r) = 20\log_{10}(2000) \approx \mathbf{66 \text{ dB}}$$

In practice, 40–50 dB is typical due to imperfect saturation uniformity across the core. More control turns and higher control current improve this.

---

#### 7. Power Dissipation

**Control coil switching loss** (resistive dissipation in control coil at I_sat):

$$P_{ctl} = I_{sat}^2 \times R_{ctl} \times \text{duty cycle}$$

For I_sat = 378 mA, R_ctl = 1 Ω, 50% duty: P_ctl = 0.378² × 1 × 0.5 ≈ **71 mW** — negligible.

**MOSFET switching loss** (dominant at high data rates):

$$P_{sw} = \frac{1}{2} \, V_{DS} \, I_{sat} \, (t_r + t_f) \, f_{data}$$

For IRFZ44N: t_r + t_f ≈ 100 ns, V_DS = 12 V, I = 378 mA, f_data = 1 kHz:

$$P_{sw} = 0.5 \times 12 \times 0.378 \times 100\times10^{-9} \times 1000 \approx \mathbf{0.23 \text{ mW}}$$

Switching loss is irrelevant at VLF data rates. The IRFZ44N runs cold.

---

### ASCII Circuits

```
COMPLETE SATURABLE CORE MODULATOR
════════════════════════════════════════════════════════════

CARRIER POWER STAGE
────────────────────────────────────────────────────────────

                        +Vcc (12–24V)
                            │
                        [R_limit]        ← optional current limit
                         100Ω / 5W       ← remove once tuned
                            │
    Function gen        ┌───┴───┐
    or audio amp ───────┤  C_res├──────────────────┐
    (sine wave          │  4.7µF│  polypropylene    │
     at f₀)            └───────┘  film only         │
                            │                       │
                            │                  ┌────┴────┐
                            │                  │ CARRIER │
                            │                  │  COIL   │  ← N_c = 50T
                            │                  │  N_c    │     26 AWG
                            │                  │ (CW)    │     on toroid
                            │                  └────┬────┘
                            │                       │
                            └───────────────────────┘
                                        │
                                       GND


MODULATION / CONTROL STAGE
────────────────────────────────────────────────────────────

       +12V
         │
         ├──────────────────────────────────────────┐
         │                                          │
        [R_pull] 10kΩ  (keeps gate LOW if MCU resets)
         │                                          │
        [R_g]  47Ω     (gate resistor — limits dV/dt)
         │
MCU ─────┤ Gate
    PWM   │
         [Q1: IRFZ44N]   Vgs_th ≈ 3V, R_ds(on) = 28mΩ
         │ Drain ─────────────────────────────────┐
         │                                        │
         │                                  ┌─────┴────┐
         │                                  │ CONTROL  │
         │                                  │  COIL    │  ← N_ctl = 20T
         │                                  │  N_ctl   │     22 AWG
         │                                  │ (CCW)    │     on SAME toroid
         │                                  └─────┬────┘
         │                                        │
         │                                  [D1: 1N5819]  ← Schottky preferred
         │                                   Flyback       over 1N4007
         │ Source                                 │
         └─────────────────────────────────────────
                                                  │
                                                 GND


TOROID — winding detail (side view, cut-away)
────────────────────────────────────────────────────────────

       ←─────── OD = 25mm ──────→
       ┌─────────────────────────┐  ↑
       │░░░░░░░░░░░░░░░░░░░░░░░░░│  │ height
       │░░  ferrite material  ░░░│  │ 10mm
       │░░░░░░░░░░░░░░░░░░░░░░░░░│  ↓
       └─────────────────────────┘
         ID = 15mm (hole through centre)

  WINDING SENSE — critical, must be opposing:

  Carrier coil  (N_c, CLOCKWISE  when viewed from top):
      wire enters hole going UP on left side →
      wraps over top → down right → through hole going UP...

  Control coil (N_ctl, COUNTER-CLOCKWISE when viewed from top):
      wire enters hole going DOWN on left side →
      wraps over top → down right → through hole going DOWN...

  Result: DC control field OPPOSES carrier AC field at saturation threshold.
  If wound in same sense, control field ADDS to carrier and modulation fails.


TOROID — top view, both coils shown
────────────────────────────────────────────────────────────

                     Carrier in (+)
                          │
          ┌───────────────┼───────────────┐
          │        CW ↻   │               │
          │    ┌──────────┴──────────┐    │
          │    │                     │    │
    Ctl   │    │   ferrite toroid    │    │   Carrier
    out(-)┼────┤                     ├────┼── out (-)
          │    │    (donut shape)    │    │
          │    └──────────┬──────────┘    │
          │        CCW ↺  │               │
          └───────────────┼───────────────┘
                          │
                     Control in (+)

  N_c turns (CW) shown as ─── on top half
  N_ctl turns (CCW) shown as ─── on bottom half
  In reality both coils distributed around full toroid circumference


FULL SYSTEM — end-to-end
────────────────────────────────────────────────────────────

  ┌──────────┐     ┌──────────┐    ┌───────────────────┐
  │ Function │     │  Audio   │    │    C_res           │
  │ generator├────▶│  Power   ├───▶┤  (4.7µF film) ──▶─┤ CARRIER COIL
  │ (f₀ sine)│     │  Amp     │    │                   │ N_c = 50T
  └──────────┘     │ (e.g.    │    └───────────────────┘  on toroid
                   │ TPA3118) │              │                │
                   └──────────┘             GND              │
                                                             │ same toroid
  ┌──────────┐     ┌──────────┐    ┌──────────────┐         │
  │  MCU     │     │  47Ω    │    │  IRFZ44N     │ CONTROL │
  │ (Arduino ├────▶│  R_gate  ├───▶│  MOSFET      ├────────▶┤ COIL
  │  Teensy) │     └──────────┘    │              │         │ N_ctl = 20T
  │ PWM out  │                     └──────┬───────┘         │ (opposing)
  └──────────┘                            │                  │
                                    [1N5819 flyback]        GND
                                          │
                                         GND
```

---

### Signal Waveforms and Operating States

```
WAVEFORMS — all on same time axis
════════════════════════════════════════════════════════════

                  ←─── 1ms (1kHz carrier) ───→

CARRIER SOURCE:  ╭─╮ ╭─╮ ╭─╮ ╭─╮ ╭─╮ ╭─╮ ╭─╮ ╭─╮ ╭─╮ ╭─╮
(continuous      ╯ ╰─╯ ╰─╯ ╰─╯ ╰─╯ ╰─╯ ╰─╯ ╰─╯ ╰─╯ ╰─╯ ╰
 from amp)

MCU DATA OUT:    ▔▔▔▔▔▔▔▔▔▔▔▔▔╗         ╔▔▔▔▔▔▔▔▔╗
(gate drive)     LOW           ║  HIGH   ║  LOW   ║  HIGH
                               ╚═════════╝        ╚═══════

CORE STATE:      [UNSATURATED] [SATURATED][UNSAT.][SAT.  ]
                  μᵣ = 2000    μᵣ ≈ 1     2000     ≈ 1
                  L = 5.2mH   L = 2.6µH

CARRIER CURRENT: ╭─╮ ╭─╮ ╭─╮ ╭─╮                 ╭─╮ ╭─╮
(in carrier coil)╯ ╰─╯ ╰─╯ ╰─╯ ╰─(near zero)─────╯ ╰─╯ ╰

RADIATED FIELD:  ∿∿∿∿∿∿∿∿∿∿∿∿∿∿  ─ ─ ─ ─ ─ ─  ∿∿∿∿∿∿∿∿∿

DECODED DATA:         0                1              0

  Note: carrier does NOT switch instantly — there is a
  settling time ≈ 3 × L_ctl/R_total ≈ 3 × 0.83mH/32Ω ≈ 78µs
  This limits clean OOK to < ~4 kHz data rate.


CONTROL COIL CURRENT DURING SWITCH-ON
────────────────────────────────────────────────────────────

  I_ctl    I_sat = 378mA ──────────────────────────────
    │                  ╱‾‾
    │                ╱          ← exponential rise
    │              ╱              τ = L_ctl/R ≈ 26µs
    │            ╱
    │          ╱
    │________╱
    0        τ    3τ   5τ      time →
             26µs 78µs 130µs

  Core saturates when I_ctl crosses ~378mA (at ~1τ here)
  Full settling to steady state takes ~5τ = 130µs
```

---

### Component Selection Guide

```
COMPONENT REFERENCE
════════════════════════════════════════════════════════════

 Ref    Value          Type                  Notes
 ─────────────────────────────────────────────────────────
 T1     Type 77        Fair-Rite 5977003801  25mm OD toroid
        toroid         or equivalent         μᵣ = 2000

 N_c    50T / 26AWG    Enamel copper wire    CW sense
        (carrier)      R ≈ 0.3Ω measured     use Kelvin meter

 N_ctl  20T / 22AWG    Enamel copper wire    CCW sense (opposing!)
        (control)      R ≈ 0.1Ω

 C_res  4.7µF / 50V    Polypropylene film    NOT electrolytic
        (adjust to     Vishay MKP or         High ripple current
        hit f₀)        WIMA FKP2             rating needed

 Q1     IRFZ44N        N-channel MOSFET      Logic-level gate
        TO-220         55V / 49A             Vgs_th = 2–4V
                       R_ds(on) = 28mΩ

 D1     1N5819         Schottky diode        40V / 1A
        or BAT85       TO-92 or SOD-80       Fast recovery
                                             < 10ns t_rr

 R_g    47Ω            Metal film 1/4W       Limits gate current
                                             prevents oscillation

 R_pull 10kΩ           Any 1/4W              Holds gate LOW
                                             on MCU reset/startup

 Amp    TPA3118        Class-D mono amp      12–24V, up to 30W
        breakout       module                Drives C_res + N_c
                                             Adjust gain for
                                             I_circ = target
```

---

### Testing Procedure

**Step 1 — Verify winding sense (before any power)**

Connect an ohmmeter across the carrier coil. Manually wind one turn of wire on the toroid in CCW direction and connect it to a 1.5V battery momentarily. If the carrier coil shows the same polarity deflection as the control coil would when energised, the senses match — **this is wrong**. Reverse one coil's connections.

**Step 2 — Find resonance (low power)**

Set function generator to 100 mV, sweep 500 Hz–5 kHz. Monitor current with a series 1Ω sense resistor and oscilloscope. Current peaks sharply at f₀. Adjust C_res to hit your target frequency.

```
  Oscilloscope probe placement for resonance check:

  Amp out ──┬── C_res ──┬── N_c ──┬── GND
            │           │          │
           CH1         CH2        R_sense (1Ω)
          (source)  (mid-point)    │
                                  CH3  ← peaks at resonance
```

**Step 3 — Verify saturation kills the carrier**

With carrier running at resonance (CH3 showing peak current), connect bench power supply to control coil. Increase DC current slowly from 0 to 500 mA. Watch CH3 — carrier current should collapse by >90% before 400 mA. If it doesn't collapse, check winding sense.

**Step 4 — Measure suppression ratio**

Use oscilloscope math or a spectrum analyser:
- Carrier ON level (V_on) — control coil off
- Carrier OFF level (V_off) — control coil at I_sat

$$\text{Suppression (dB)} = 20\log_{10}\!\left(\frac{V_{on}}{V_{off}}\right)$$

Target: > 30 dB. If below 20 dB, increase N_ctl or I_sat.

**Step 5 — MOSFET switching**

Replace bench supply with MOSFET circuit. Send 10 Hz square wave from MCU. Verify carrier switches cleanly on search coil + oscilloscope. Increase rate in decades: 100 Hz → 1 kHz → 4 kHz. Note the frequency where switching edges become rounded — this is your f_max for clean OOK.

**Step 6 — Radiation check**

Hold search coil (20T, 5 cm) at 0.5 m from toroid. Trigger oscilloscope from MCU data line. Confirm transmitted signal appears and disappears in sync with MCU output with acceptable settling time.

---

### The 3-Phase Fluxgate (Simulated Rotating Magnet)

If you want the raw magnetic output of a spinning magnet without the mechanical risk, three stationary coils arranged 120° apart can simulate it exactly.

**How it works:**

1. Arrange three coils 120° apart around a central ferrite or air core.
2. Drive each coil with a VLF sine wave shifted 120° in phase from the others.
3. The resulting magnetic field rotates in a circle at the drive frequency — identical to a physical spinning magnet, but with nothing moving.

---

#### Mathematics

**Phase voltages driving each coil:**

$$V_A = V_{pk} \sin(2\pi f t)$$
$$V_B = V_{pk} \sin\!\left(2\pi f t + \tfrac{2\pi}{3}\right)$$
$$V_C = V_{pk} \sin\!\left(2\pi f t + \tfrac{4\pi}{3}\right)$$

**Magnetic field contribution of each coil at the centre** (for a single-layer coil of N turns, radius r, carrying current I):

$$H_{coil} = \frac{N \, I}{2r}$$

**Decomposing each coil's field into x and y components** (coil A along x-axis, B at 120°, C at 240°):

$$H_x(t) = H_{pk}\!\left[\sin(2\pi ft)\cdot1 + \sin\!\left(2\pi ft+\tfrac{2\pi}{3}\right)\!\cdot\!\cos120° + \sin\!\left(2\pi ft+\tfrac{4\pi}{3}\right)\!\cdot\!\cos240°\right]$$

$$H_y(t) = H_{pk}\!\left[\sin\!\left(2\pi ft+\tfrac{2\pi}{3}\right)\!\cdot\!\sin120° + \sin\!\left(2\pi ft+\tfrac{4\pi}{3}\right)\!\cdot\!\sin240°\right]$$

After trigonometric reduction these simplify to:

$$H_x(t) = \tfrac{3}{2}\,H_{pk}\cos(2\pi ft)$$
$$H_y(t) = \tfrac{3}{2}\,H_{pk}\sin(2\pi ft)$$

The magnitude is constant:

$$|H_{total}| = \tfrac{3}{2}\,H_{pk} = \tfrac{3}{2}\cdot\frac{N\,I_{pk}}{2r}$$

A 3-phase balanced drive produces a field **1.5× stronger** than a single coil driven at the same peak current, and the field vector rotates at exactly the drive frequency f with no mechanical parts.

**Inductance of each coil** (multilayer, air core, Wheeler approximation for a short coil):

$$L \approx \frac{\mu_0 \pi N^2 r^2}{l + 0.9r}$$

where l = coil length (m), r = coil radius (m).

**Resonant capacitor** (place in series with each coil to maximise current at the target frequency):

$$C = \frac{1}{(2\pi f)^2 L}$$

**Worked example** — target f = 1 kHz, coil radius r = 0.05 m (5 cm), N = 100 turns, l = 0.02 m:

$$L \approx \frac{4\pi\times10^{-7} \times \pi \times 10000 \times 0.0025}{0.02 + 0.045} \approx \frac{9.87\times10^{-5}}{0.065} \approx 1.52 \text{ mH}$$

$$C = \frac{1}{(2\pi \times 1000)^2 \times 1.52\times10^{-3}} \approx \frac{1}{6.03\times10^7} \approx 16.6\ \mu\text{F}$$

Peak field at centre with I_pk = 1 A:

$$|H_{total}| = \frac{3}{2} \cdot \frac{100 \times 1}{2 \times 0.05} = \frac{3}{2} \cdot 1000 = 1500 \text{ A/m}$$

**Q factor and efficiency:**

$$Q = \frac{2\pi f L}{R_{wire}}$$

For R_wire = 0.5 Ω at 1 kHz: Q ≈ 19. At resonance the coil current is Q times higher than the source-limited current — keep winding resistance low with heavy wire (20–22 AWG).

**Phase shift timing** (for MCU implementation):

$$\Delta t_{AB} = \frac{T}{3} = \frac{1}{3f} \quad \Delta t_{AC} = \frac{2T}{3} = \frac{2}{3f}$$

At 1 kHz: Δt_AB = 333 µs, Δt_AC = 667 µs between timer interrupts.

---

#### ASCII Circuits

```
PHYSICAL COIL ARRANGEMENT — top view
══════════════════════════════════════

                    COIL A  (0°)
                   ┌────────┐
                   │ 100T   │
                   │ 5cm∅   │
                   └───┬────┘
                       │ axis points to centre
              ─────────┼─────────
             /         │         \
            /          │          \
  ┌────────┐           ●           ┌────────┐
  │ 100T   │      centre point     │ 100T   │
  │ 5cm∅   │    (ferrite rod opt.) │ 5cm∅   │
  └────────┘                       └────────┘
   COIL C (240°)               COIL B (120°)

  All three coil axes meet at the centre point.
  Spacing between coil centres = r × √3 ≈ 8.7 cm
  for r = 5 cm coils.
```

```
DRIVE ELECTRONICS — block diagram
══════════════════════════════════════

                ┌─────────────────────┐
                │   STM32 / Arduino   │
                │                     │
                │ TIM CH1 (0°)   ─────┼──→ [Amp A] ──→ C_res ──→ COIL A
                │ TIM CH2 (120°) ─────┼──→ [Amp B] ──→ C_res ──→ COIL B
                │ TIM CH3 (240°) ─────┼──→ [Amp C] ──→ C_res ──→ COIL C
                │                     │
                └─────────────────────┘
                         │
                       +12V (shared rail, star-point ground)
```

```
SINGLE AMPLIFIER CHANNEL — schematic (repeat ×3)
══════════════════════════════════════════════════

MCU PWM ──[R_g 10Ω]──┬──────────────────────────────────┐
                      │                                  │
                   [IR2104                          [IR2104
                   Hi-side gate]                    Lo-side gate]
                      │                                  │
                   [Q_hi: IRLZ44N]                 [Q_lo: IRLZ44N]
                      │ Drain                            │ Drain
        +12V ─────────┤                                  │
                      │ Source → OUTPUT NODE             │
                      │              │                   │
                      │           [C_res]                │ Source
                      │              │                   │
                      │           [COIL]              ───┤
                      │           (L, R_wire)            │
                      │              │                  GND
                      └──────────────┘
                         Flyback path through body diodes
                         of Q_hi and Q_lo (no external
                         diode needed with MOSFETs)
```

```
SIGNAL WAVEFORMS
══════════════════════════════════════════════════

 COIL A ∿∿∿∿∿∿∿∿∿∿∿∿∿∿∿∿∿∿∿∿∿∿∿∿∿∿∿∿∿∿∿∿∿∿∿∿
        0°

 COIL B      ∿∿∿∿∿∿∿∿∿∿∿∿∿∿∿∿∿∿∿∿∿∿∿∿∿∿∿∿∿∿∿∿
        120° →|←  Δt = T/3

 COIL C          ∿∿∿∿∿∿∿∿∿∿∿∿∿∿∿∿∿∿∿∿∿∿∿∿∿∿∿∿
        240° →|←      Δt = 2T/3

 RESULTANT FIELD VECTOR rotates one full circle
 per period T = 1/f  (e.g. 1 ms at 1 kHz)

 ← T = 1/f →
  ┌────────────────────────────────────────┐
  │  t=0        t=T/4      t=T/2    t=3T/4 │
  │   ↑           →          ↓        ←   │  Field
  │   │                      │             │  direction
  └────────────────────────────────────────┘
```

```
FERRITE CORE OPTION — cross section
══════════════════════════════════════════════════

Without core (air core):          With ferrite rod at centre:

    A           B                     A           B
    │           │                     │           │
    │     ·     │    field point       │  ┌─────┐  │
    │    /|\    │    diffuse           │  │  F  │  │    field
    │   / | \   │                     │  │  e  │  │    concentrated
    │  /  |  \  │                     │  │  r  │  │    and amplified
    │ /   |   \ │                     │  │  r  │  │    by μr
    C           ─                     C  └─────┘  ─

  Use a ferrite rod (Type 77, 10 mm dia × 100 mm)
  along the axis perpendicular to the coil plane.
  Multiply H_total by μ_eff (typically 50–200×
  depending on rod geometry and material).
```

---

#### Build and Test Procedure

1. **Coils:** Wind 3 identical coils — same number of turns, same diameter, same wire gauge. Measure inductance of each with an LCR meter and match them within 2%. Mismatch unbalances the rotating field.

2. **Resonant caps:** Calculate C from the formula above. Use polypropylene film capacitors (low loss). Measure the actual resonant frequency of each L-C pair — they should all match within 0.5%.

3. **Phase generation:** On an STM32, configure TIM1 with centre-aligned PWM and three channels. Set compare values to 0°, 120°, 240° of the sine lookup table. Run a slow rate (10 Hz) first.

4. **Balance check:** At low power, place a compass or Hall sensor at the centre point. With a balanced 3-phase drive the needle (or sensor reading) should rotate smoothly at the drive frequency. Any wobble indicates an amplitude or phase imbalance between channels.

5. **Resonance verification:** Increase drive frequency to target. Monitor current on each channel — it should peak at resonance. All three channels should peak at the same frequency.

6. **Radiation check:** Hold a search coil (20 turns, 5 cm) at increasing distances from the centre. Map field strength vs distance. Expect ~6 dB drop per doubling of distance in the near field.

7. **Field steering:** Swap the connections of any two channels. The field rotation direction reverses. Add a relay or analogue switch to do this electronically for BPSK modulation.

**Practical drive:** A 3-channel Class D audio amplifier (e.g., TPA3118 × 3) driven by an STM32 with three timer-synced PWM outputs is a low-cost implementation. Total component cost under $20.

---

### Safe Method Comparison

| Method | Safety | Effectiveness | Complexity | Best for |
| :--- | :--- | :--- | :--- | :--- |
| **Saturable Core** | 10/10 | High — excellent OOK/FSK | Medium | Data transmission, compact build |
| **3-Phase Fluxgate** | 10/10 | Very high — mimics spinning magnet | Higher | Maximum field strength, no rotation risk |
| **Tuned Loop** | 10/10 | Good — best for distance | Low | Simplest first build |
| **Variable Reluctance rotor** | 3/10 | High | High | Only if containment shield is used |

**Recommendation:** Start with the **Saturable Core** — it uses the same chopping logic as the reluctance rotor but replaces the spinning iron with a MOSFET and 380 mA of DC current. Same physics, no shrapnel.

---

## 3. Comparison for a DIY Build

| Feature | Tuned Coil (Loop) | Rotating Magnet | ME Antenna (Lab) |
| :--- | :--- | :--- | :--- |
| **Cost** | Low (wire + caps) | Medium (motor + magnet) | High (specialised ceramics) |
| **Complexity** | Simple electrical | Simple mechanical | Very high — materials science |
| **Size** | 0.5 m to 2 m | Fist-sized | Stamp-sized |
| **Effectiveness** | Great for distance | Great for penetration | Experimental / short range |

---

## Which Is Better for Your Use Case?

* **Signal 100+ metres through air:** Use the **Tuned Coil**. Predictable performance, standard electronics, can be driven directly by an audio power amplifier (subwoofer-grade).
* **Signal through ground or concrete:** Use the **Rotating Magnet**. Magnetic fields at sub-3 kHz are nearly impossible to attenuate with earth or building materials.



