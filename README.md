# Fuzzzzzzz - A guitar pedal
### My take on the classic fuzz face circuit
The Fuzzzzzzz is a fuzz face-inspired guitar pedal, redesigned with an inverting gain stage, asymmetric hard clipping, and a 720Hz high-pass tone control to sit between the reactivity of a classic fuzz and the control of a modern overdrive. Works great on bass too.

![image](https://blueprint.hackclub.com/user-attachments/blobs/proxy/eyJfcmFpbHMiOnsiZGF0YSI6MzIyMjQsInB1ciI6ImJsb2JfaWQifX0=--28d04e754bfd8452231a5bed593a2aa54a2583ec/image.png)

## Table of Contents

1. [Features](#features)
2. [Circuit Overview](#circuit-overview)
3. [Usage](#usage)
   - [Connections](#connections)
   - [Turning the Effect On and Off](#turning-the-effect-on-and-off)
   - [The Knobs](#the-knobs)
   - [Tips & Tricks](#tips--tricks)
   - [Modding](#modding)
4. [Bill of Materials (BOM)](#bill-of-materials-bom)
5. [Off-Board Bill of Materials](#off-board-bill-of-materials-bom)
6. [Assembly](#assembly)
   - [Tools Required](#tools-required)
   - [Step 1 — Populate the PCB](#step-1--populate-the-pcb)
   - [Step 2 — Drill the Enclosure](#step-2--drill-the-enclosure)
   - [Step 3 — Mount the PCB](#step-3--mount-the-pcb)
   - [Step 4 — Install Off-Board Components](#step-4--install-off-board-components)
   - [Step 5 — Wire Off-Board Components to the PCB](#step-5--wire-off-board-components-to-the-pcb)
   - [Step 6 — Wire the 3PDT Footswitch](#step-6--wire-the-3pdt-footswitch-true-bypass)
   - [Step 7 — Test Before Closing](#step-7--test-before-closing)
   - [Step 8 — Close the Enclosure](#step-8--close-the-enclosure)

## Features
* Three control knobs for gain, tone control and output level
* Asymmetric clipping
* True bypass
* Quality 9V power decoupling
* Plenty of room for modding

![image](https://blueprint.hackclub.com/user-attachments/blobs/proxy/eyJfcmFpbHMiOnsiZGF0YSI6MzIyMjcsInB1ciI6ImJsb2JfaWQifX0=--c24c00ddd431f0ef602fa29b1e30a47778a372e2/image.png)

## Circuit Overview
  The circuit is composed of a gain controlling input stage with a controllable inverting amplifier that buffers and boosts the signal with a gain ranging from 6dB to 21.6dB. The gain stage has a topology inspired by the classic fuzz face guitar pedal but modded to have a lower noise floor, use common components and a slightly different flavor of clipping. The output stage consists of a recovery/buffering stage with tone control for boosting high-mid frequencies and a final output level control.
```
In → Input buffer → Gain control → Modified fuzz clipping stage → Tone Control → Output Buffer → Out
```
## Usage
### Connections

| Jack | Connect to |
|------|-----------|
| **Input (J1)** | Your guitar or bass |
| **Output (J2)** | Your amplifier or next pedal in chain |
| **Power (J3)** | 9V DC, center-negative, 2.1mm barrel (standard Boss-style adapter) |

Current draw is very low (~10mA), so any pedalboard power supply will work fine. A 9V battery via the snap adapter (BAT1) is also supported.

### Turning the Effect On and Off

Stomp **SW1** to toggle the effect on and off. The **LED (D4)** lights up when the effect is active. When bypassed, your signal passes directly from input to output with zero coloration — this pedal uses **true bypass**.

### The Knobs

**Gain (RV1)**
Controls the amount of fuzz and drive. At minimum, expect a light, responsive crunch. At maximum, full aggressive fuzz with heavy harmonic saturation. For most playing styles, the sweet spot sits around **2–3 o'clock**.

**Tone (RV2)**
A high-mid boost control centered around **720Hz** — not a traditional treble cut like a Big Muff. Turning it up adds bite and presence; turning it down gives a warmer, rounder character. It won't get muddy at low settings.

**Level (RV3)**
Sets the output volume. Unity gain — matching your dry signal level — is roughly at **noon**. Go past that to push your amp harder.

### Tips & Tricks

- **Bass players:** the 720Hz high-pass filter keeps the low end tight and defined, making this pedal unusually bass-friendly for a fuzz.
- **Extreme settings:** stacking Gain and Tone both at maximum gives a very aggressive, almost synth-like fuzz character.
- **Guitar volume trick:** like a classic fuzz face, this pedal is sensitive to your guitar's volume knob. Rolling it back cleans up the tone significantly without touching the pedal — use this to your advantage.

### Modding

The pedal was designed with experimentation in mind. Some starting points:

- **Clipping diodes (D1, D2):** Swap the 1N4148s for germanium diodes (1N34A, OA85) for a softer, warmer clipping character with lower threshold voltage.
- **Tone center frequency:** C5 (47nF) sets the 720Hz high-pass corner of the tone control. Increasing the value shifts the center lower for a darker sound; decreasing it pushes it higher for more treble bite.
- **Gain range:** R7 (4K7) sets the minimum gain of the inverting stage. Reducing it lowers the floor for a cleaner minimum gain setting.

---

### Bill of Materials (BOM)
| **#** | **Reference**     | **Qty** | **Value** | **Footprint**                                                       | **Description**                                                  |
|-------|-------------------|---------|-----------|---------------------------------------------------------------------|------------------------------------------------------------------|
| 1     | C1, C10, C12, C15 | 4       | 100nF     | Capacitor_THT:C_Rect_L7.0mm_W2.5mm_P5.00mm                          | Unpolarized capacitor                                            |
| 2     | C2                | 1       | 4u7       | Capacitor_THT:CP_Radial_D5.0mm_P2.50mm                              | Polarized capacitor                                              |
| 3     | C3                | 1       | 100pF     | Capacitor_THT:C_Disc_D5.0mm_W2.5mm_P5.00mm                          | Unpolarized capacitor                                            |
| 4     | C4                | 1       | 2n2       | Capacitor_THT:C_Rect_L7.0mm_W2.5mm_P5.00mm                          | Unpolarized capacitor                                            |
| 5     | C5                | 1       | 47nF      | Capacitor_THT:C_Rect_L7.0mm_W2.5mm_P5.00mm                          | Unpolarized capacitor                                            |
| 6     | C6                | 1       | 47uF      | Capacitor_THT:CP_Radial_D5.0mm_P2.50mm                              | Polarized capacitor                                              |
| 7     | C7                | 1       | 4n7       | Capacitor_THT:C_Rect_L7.0mm_W2.5mm_P5.00mm                          | Unpolarized capacitor                                            |
| 8     | C8                | 1       | 22nF      | Capacitor_THT:C_Rect_L7.0mm_W2.5mm_P5.00mm                          | Unpolarized capacitor                                            |
| 9     | C9                | 1       | 10nF      | Capacitor_THT:C_Rect_L7.0mm_W2.5mm_P5.00mm                          | Unpolarized capacitor                                            |
| 10    | C11               | 1       | 1uF       | Capacitor_THT:C_Rect_L7.0mm_W2.5mm_P5.00mm                          | Unpolarized capacitor                                            |
| 11    | C13               | 1       | 100uF     | Capacitor_THT:CP_Radial_D6.3mm_P2.50mm                              | Polarized capacitor                                              |
| 12    | C14               | 1       | 10uF      | Capacitor_THT:CP_Radial_D5.0mm_P2.50mm                              | Polarized capacitor                                              |
| 13    | D1, D2            | 2       | 1N4148    | Diode_THT:D_DO-35_SOD27_P7.62mm_Horizontal                          | 100V 0.15A standard switching diode, DO-35                       |
| 14    | D3               | 1       | 1N5819    | Diode_THT:D_DO-41_SOD81_P10.16mm_Horizontal                         | 40V 1A Schottky Barrier Rectifier Diode, DO-41                   |
| 15    | D4               | 1       | LED       | LED_THT:LED_D3.0mm                                                  | Light emitting diode                                             |
| 16    | Q1               | 1       | 2N5088    | Package_TO_SOT_THT:TO-92_Inline                                     | 0.2A Ic, 40V Vce, Small Signal NPN Transistor, TO-92             |
| 17    | Q2               | 1       | 2N4401    | Package_TO_SOT_THT:TO-92_Inline                                     | 0.2A Ic, 40V Vce, Small Signal NPN Transistor, TO-92             |
| 18    | R1, R15           | 2       | 1M        | Resistor_THT:R_Axial_DIN0207_L6.3mm_D2.5mm_P7.62mm_Horizontal       | Resistor 1/4W                                                    |
| 19    | R2-R4, R12        | 4       | 10K       | Resistor_THT:R_Axial_DIN0207_L6.3mm_D2.5mm_P7.62mm_Horizontal       | Resistor 1/4W                                                    |
| 20    | R5, R10           | 2       | 100K      | Resistor_THT:R_Axial_DIN0207_L6.3mm_D2.5mm_P7.62mm_Horizontal       | Resistor 1/4W                                                    |
| 21    | R6                | 1       | 220R      | Resistor_THT:R_Axial_DIN0207_L6.3mm_D2.5mm_P7.62mm_Horizontal       | Resistor 1/4W                                                    |
| 22    | R7                | 1       | 4K7       | Resistor_THT:R_Axial_DIN0207_L6.3mm_D2.5mm_P7.62mm_Horizontal       | Resistor 1/4W                                                    |
| 23    | R8, R13           | 2       | 2K2       | Resistor_THT:R_Axial_DIN0207_L6.3mm_D2.5mm_P7.62mm_Horizontal       | Resistor 1/4W                                                    |
| 24    | R9                | 1       | 1K        | Resistor_THT:R_Axial_DIN0207_L6.3mm_D2.5mm_P7.62mm_Horizontal       | Resistor 1/4W                                                    |
| 25    | R11               | 1       | 1K5       | Resistor_THT:R_Axial_DIN0207_L6.3mm_D2.5mm_P7.62mm_Horizontal       | Resistor 1/4W                                                    |
| 26    | R14               | 1       | 33K       | Resistor_THT:R_Axial_DIN0207_L6.3mm_D2.5mm_P7.62mm_Horizontal       | Resistor 1/4W                                                    |
| 27    | R16              | 1       | 47R       | Resistor_THT:R_Axial_DIN0309_L9.0mm_D3.2mm_P12.70mm_Horizontal      | Resistor 1/2W                                                    |
| 28    | R17, R18          | 2       | 220K      | Resistor_THT:R_Axial_DIN0207_L6.3mm_D2.5mm_P7.62mm_Horizontal       | Resistor 1/4W                                                    |
| 29    | R19              | 1       | 4K7       | Resistor_THT:R_Axial_DIN0309_L9.0mm_D3.2mm_P12.70mm_Horizontal      | Resistor 1/2W                                                    |
| 30    | RV1-RV3          | 3       | 100KA     | Potentiometer_THT:Potentiometer_Alpha_RD901F-40-00D_Single_Vertical | Potentiometer                                                    |
| 31    | U1               | 1       | JRC4558   | Package_DIP:DIP-8_W7.62mm_Socket                                    | Dual General Purpose, Operational Amplifier, DIP-8/SOIC-8/SSOP-8 |

# Off-Board Bill of Materials (BOM)
| **#** | **Reference** | **Qty** | **Value**                  | **Description**                                          |
|-------|---------------|---------|----------------------------|----------------------------------------------------------|
| 1     | CASE          | 1       | Hammond 1590BB             | Diecast aluminum enclosure 119x94x34mm                   |
| 2     | J1            | 1       | 6.35mm Jack – Input        | Mono 1/4" TS input jack                                  |
| 3     | J2            | 1       | 6.35mm Jack – Output       | Mono 1/4" TS output jack                                 |
| 4     | J3            | 1       | DC Power Jack 2.1mm        | Barrel connector 2.1mm center-neg (3 poles)              |
| 5     | SW1           | 1       | 3PDT Footswitch            | Latching 3PDT stomp switch for true bypass               |
| 6     | BAT1          | 1       | 9V Battery Snap Adapter    | 9V battery clip with leads                               |
| 7     | HW1           | 4       | M3×30mm Screw              | M3 machine screw, 30mm length                            |
| 8     | HW2           | 12      | M3 Nut                     | M3 hex nut                                               |

---

## Assembly

### Tools Required

- Soldering iron and solder
- Wire cutters and strippers
- Small flathead and Phillips screwdrivers
- Drill and step bit (for enclosure drilling)
- Multimeter (recommended for testing)

### Step 1 — Populate the PCB

Solder components onto the PCB in this order, from shortest to tallest, so taller parts don't get in the way:

1. **Resistors** (R1–R19)
2. **Small capacitors** — ceramic and film (C1, C3, C4, C5, C7, C8, C9, C10, C11, C12, C15)
3. **Diodes** (D1, D2, D3) — the stripe on the body marks the cathode; match it to the marking on the PCB silkscreen
4. **Transistors** (Q1, Q2) — 2N5088 at Q1, 2N4401 at Q2; match the flat face of the TO-92 body to the silkscreen
5. **IC socket** for U1 — solder the socket, not the IC itself
6. **Electrolytic capacitors** (C2, C6, C13, C14) — the longer leg is positive; match it to the `+` marking on the PCB
7. **Potentiometers** (RV1, RV2, RV3)

Once all PCB soldering is done, insert the **JRC4558** into its socket. Never solder the IC directly — heat damages it.

### Step 2 — Drill the Enclosure

Mark and drill the **Hammond 1590BB** enclosure for:

- 3× potentiometer holes (top face)
- 1× LED hole (top face)
- 1× footswitch hole (top face, center)
- 2× 6.35mm jack holes (left and right sides)
- 1× DC barrel jack hole (top or back panel)
- 4× M3 mounting holes for the PCB (matching your PCB layout)

Deburr all holes after drilling to avoid sharp edges cutting into wiring later.

### Step 3 — Mount the PCB

Mount the PCB inside the enclosure using the M3 hardware in this arrangement:
```
Screw head → Case wall → Nut ··· Nut → PCB → Nut
```

This sandwiches the enclosure wall between two nuts and the PCB between two more, keeping everything rigid. Use all **4× M3×30mm screws** and **12× M3 nuts**.

> The rubber feet that come with the Hammond enclosure sit taller than the M3 screw heads, so the screws won't scratch any surface the pedal rests on.

### Step 4 — Install Off-Board Components

Mount and hand-tighten into their drilled holes:

- **J1** — Input jack (left side)
- **J2** — Output jack (right side)
- **J3** — DC power jack
- **SW1** — 3PDT footswitch
- **D4** — LED through the top panel hole; secure with a bezel if desired
- **BAT1** — Route the battery snap adapter inside the enclosure

### Step 5 — Wire Off-Board Components to the PCB

Use short, neat runs of hookup wire. Refer to the schematic for exact pad labels.

#### Power

Connect both the DC jack and the battery snap to the PCB's power input pads. Observe polarity — this pedal uses **center-negative** power, which is standard for guitar pedals. D3 (1N5819) on the PCB provides reverse polarity protection, but always double-check before powering on.

#### Audio Jacks

- J1 tip → PCB `IN` pad; J1 sleeve → GND
- J2 tip → PCB `OUT` pad (via SW1, see below); J2 sleeve → GND

### Step 6 — Wire the 3PDT Footswitch (True Bypass)

The 3PDT switch has 9 lugs arranged in a 3×3 grid. Looking at the switch from the **back** (solder side), number them like this:
```
[ 1 ][ 2 ][ 3 ]
[ 4 ][ 5 ][ 6 ]   ← middle row: commons
[ 7 ][ 8 ][ 9 ]
```

The **middle row** (lugs 4, 5, 6) are the commons — they always carry the signal. The top and bottom rows are the throws — which row the common connects to depends on whether the switch is stomped or not.

Wire it as follows:

| Lug | Connection |
|-----|-----------|
| **1** | PCB `IN` pad |
| **2** | PCB `OUT` pad |
| **3** | LED anode (D4 `+`) |
| **4** | Input jack (J1) tip |
| **5** | Output jack (J2) tip |
| **6** | +9V supply |
| **7** | Bridge to lug 8 with a short wire |
| **8** | Bridge to lug 7 with a short wire |
| **9** | Leave unconnected |

> **Note:** The LED current-limiting resistor (R6, 220Ω) is already on the PCB, so connect lug 3 directly to the LED anode without adding any extra resistor inline.

#### How it works

**Effect ON (LED lit):** The commons (4, 5, 6) connect to the top row (1, 2, 3).
- Lug 4 → Lug 1: Guitar signal goes into the PCB
- Lug 5 → Lug 2: PCB output goes to the amp
- Lug 6 → Lug 3: +9V reaches the LED → LED lights up

**Effect OFF (bypassed):** The commons (4, 5, 6) connect to the bottom row (7, 8, 9).
- Lug 4 → Lug 7, bridged to Lug 8 → Lug 5: Guitar signal goes directly to the amp, skipping the PCB entirely
- Lug 6 → Lug 9: +9V goes nowhere → LED off

This is **true bypass** — when off, the PCB is completely out of the signal path.

### Step 7 — Test Before Closing

Before screwing the enclosure shut:

1. Power the pedal via a 9V adapter
2. Plug a guitar into J1 and an amp into J2
3. Stomp SW1 — the LED should light up and you should hear the fuzz effect
4. Stomp again — the LED should go off and the signal should pass clean with no coloration
5. Turn each knob through its full range and listen for scratchiness or dropouts

If you have a multimeter, probe the test points on the PCB to verify the bias voltages on Q1 and Q2 match the schematic.

### Step 8 — Close the Enclosure

Once everything checks out, tuck all wiring neatly inside the enclosure, seat the battery, and screw the lid shut. Your Fuzzzzzzz is ready to play.
