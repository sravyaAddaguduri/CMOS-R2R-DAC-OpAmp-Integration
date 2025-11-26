# CMOS-R2R-DAC-OpAmp-Integration
Transistor-level design and simulation of a 4-bit R-2R ladder DAC integrated with a two-stage CMOS operational amplifier using Cadence Virtuoso (90 nm gpdk).Includes op-amp performance analysis-AC gain vs phase, transient, PSRR, slew rate, power analysis and DAC transient staircase output verification.

## Project Highlights
1)4-bit R–2R Ladder DAC<br>
Converts digital inputs d₀–d₃ (LSB → MSB) to a corresponding analog level.<br>
Designed using 2 kΩ / 1 kΩ resistor network for stable reference division.<br>
Demonstrates a clean 16-step staircase output with an ideal LSB of 112.5 mV (for Vref = 1.8 V).<br>
2)Custom Two-Stage CMOS Op-Amp (gpdk90)<br>
Designed and simulated from transistor level:<br>
High-gain differential stage,
Common-source output stage,
Compensation capacitor implemented using load<br>
Optimized and validated through:
AC Gain & Phase Margin,
Transient Response,
Slew Rate,
PSRR,
Power Consumption.

Performance Summary Table:
| Parameter                     | Value                     
|-------------------------------|---------------------------|
| Technology                    | 90 nm GPDK                | 
| Supply Voltage (VDD)          | 1.8 V                     |                                                
| Open-Loop Gain                | 61 dB                     |                                   
| Phase Margin                  | 58°                       |                            
| Slew Rate                     | 3.9 V/µs                  |                          
| Peak-to-Peak Output Swing     | ~999 mV p-p               |                       
| Power Consumption             |54.9172uW                   |           
| PSRR                          | ~67 dB                    |             
| Load Capacitance              | 2 pF                      |                     
| Output Configuration          | Buffer (Voltage Follower) | 

All measurement screenshots are included in calculator_results.
### 4-Bit R–2R Ladder DAC
The DAC uses an R–2R resistor ladder with a 1.8 V reference. Digital inputs (D₃–D₀) are generated using VPULSE sources to cycle through all 16 codes. The verified two-stage op-amp is integrated as a unity-gain buffer at the output, ensuring low output impedance and clean, monotonic staircase behavior.
### Transient Analysis of the DAC
Transient analysis was performed on the 4-bit R-2R ladder DAC in Cadence Virtuoso using the Spectre simulator. The stop time was set to 80 µs, sufficient to observe the complete 4-bit digital count sequence from 0000 to 1111.<br>
Four VPULSE digital sources (D0–D3) were used as inputs, each switching between 0 V (logic 0) and 1.8 V (logic 1).
### DAC Output Characteristics:<br>
Total steps: 16<br>
Reference voltage: 1.8 V<br>
Theoretical LSB:<br>

LSB = Vref / 16 = 1.8 V / 16 = **112.5 mV**<br>
	​Simulated LSB matches theoretical value (see calculator screenshot)
#### Applications
This architecture is foundational for:<br>
Sensor interfaces<br>
Low-resolution signal processing<br>
Mixed-signal ICs<br>
Embedded DAC modules<br>
Programmable analog systems<br>
