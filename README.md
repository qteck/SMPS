# SMPS: DC DC Boost Converter Design

## Design Steps

1. Choosing Vin_nom
   - Vin = 5V

2. Choosing Vout and Iout
   - Vout = 20V
   - Voltage ripple = 0.01*20 = ΔVin = 0.2
   - Iout = 1A

3. Estimating efficiency η
   - 0.8

4. Calculating duty cycle at Vin_min
   - D = 1-Vin/Vout = 1-(5V/20V) = 0.75

5. Choosing Iout
   - Iout = 1A

6. Calculating input current
   - Iin = (Vout * Iout)/( η * Vin)
   - Iin = (20V * 1A) / (0.8 * 5) = 5A

7. Choosing inductor ripple current
   - IL_avg ~= Iin
   - 20% * IL_avg = ΔIL = 1A

8. Calculating inductor value
   - L = Vin * D/( ΔI*Fsw)
   - L = 5V * 0.75/(1*25khz)
   - L = 0.00015 H = 150 µH

9. Calculating inductor peak current
   - IL_peak = IL_avg + (ΔIL/2)
   - IL_peak = 5 + (1/2) = 5.5A

10. Choosing MOSFET current and voltage rating
    - IL_peak * 2 = 5.5 * 2
    - Voltage rating * 2 = 20*2
    
11. Choosing diode current and voltage rating
    - IL_peak * 2 = 5.5*2
    - Voltage rating * 2 = 20*2

12. Choosing output capacitor from ripple requirement
    - Cout = (Iout × D) / (ΔVout × fs)
    - Cout = (1A * 0.75) / (0.2*25khz) = 150uF

13. Choosing load for the current consumption:
    - I = 1; V = 20
    - R = V/I = 20/1 = 20 ohms

## Component considerations

- Suitable inductor, something with high sat current made possible by including relevant core such as ferrite.
- Logic level N-MOSFET switch with low gate capacitance and low Ron resistance.
- Cap that covers 150uF range such as electrolytic with low series resistance.
- Fast Schottky diode with low forward voltage.