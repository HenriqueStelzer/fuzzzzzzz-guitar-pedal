# Fuzzzzzzz - A guitar pedal
### My take on the classic fuzz face circuit
The Fuzzzzzzz guitar pedal is designed to give a boutique, warm, saturated fuzz tone full of character to make every tone better.

![image](https://blueprint.hackclub.com/user-attachments/blobs/proxy/eyJfcmFpbHMiOnsiZGF0YSI6MzIyMjQsInB1ciI6ImJsb2JfaWQifX0=--28d04e754bfd8452231a5bed593a2aa54a2583ec/image.png)

### Features
* Three control knobs for gain, equalizing and output level
* Asymmetric clipping
* True bypass
* Quality 9V power decoupling
* Plenty of room for modding

![image](https://blueprint.hackclub.com/user-attachments/blobs/proxy/eyJfcmFpbHMiOnsiZGF0YSI6MzIyMjcsInB1ciI6ImJsb2JfaWQifX0=--c24c00ddd431f0ef602fa29b1e30a47778a372e2/image.png)

### Circuit Overview
  The circuit is composed of a gain controlling input stage with a controllable inverting amplifier that buffers and boosts the signal with a gain ranging from 6dB to 21.6dB. The gain stage has a topology inspired by the classic fuzz face guitar pedal but modded to have a lower noise floor, use common components and a slightly different flavor of clipping. The output stage consists of a recovery/buffering stage with tone control for boosting high-mid frequencies and a final output level control.

![WhatsApp Image 2025-12-27 at 00.16.44](https://blueprint.hackclub.com/user-attachments/blobs/proxy/eyJfcmFpbHMiOnsiZGF0YSI6MzAzNjksInB1ciI6ImJsb2JfaWQifX0=--3a988a2277f9d4ed29ce4e22f9c3ae2de60cf241/WhatsApp%20Image%202025-12-27%20at%2000.16.44.jpeg)

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
| 27    | R16*              | 1       | 47R       | Resistor_THT:R_Axial_DIN0309_L9.0mm_D3.2mm_P12.70mm_Horizontal      | Resistor 1/2W                                                    |
| 28    | R17, R18          | 2       | 220K      | Resistor_THT:R_Axial_DIN0207_L6.3mm_D2.5mm_P7.62mm_Horizontal       | Resistor 1/4W                                                    |
| 29    | R19              | 1       | 4K7       | Resistor_THT:R_Axial_DIN0309_L9.0mm_D3.2mm_P12.70mm_Horizontal      | Resistor 1/2W                                                    |
| 30    | RV1-RV3          | 3       | 100KA     | Potentiometer_THT:Potentiometer_Alpha_RD901F-40-00D_Single_Vertical | Potentiometer                                                    |
| 31    | U1               | 1       | JRC4558   | Package_DIP:DIP-8_W7.62mm_Socket                                    | Dual General Purpose, Operational Amplifier, DIP-8/SOIC-8/SSOP-8 |
