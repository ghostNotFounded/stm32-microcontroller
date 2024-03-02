# STM32 Build Process

## STM32F103C8Tx (x = 6)

1. **Connect Ground and Power:**
   - Connect VSS (ground preference for digital) and VSSA (ground preference for analog) to a single GND pin.
   - Connect VBAT and VDD to a +3.3V power source. VDD is the main power supply.
     - *Note:* VBAT is tied with VDD unless using a real-time clock or extra battery.

2. **Decoupling Capacitors:**
   - Add decoupling capacitors close to the circuit:
     - 100nF capacitor for each VBAT and VDD.
     - Add a 10uF bulk decoupling capacitor between 3.3V and GND.

3. **VDDA Pin Connection:**
   - VDDA pin is for the analog section. Connect:
     - 10nF and 1uF capacitors in series for filtering.

4. **Common Ground Connection:**
   - Connect all grounds to a common GND.

5. **Ferrite Bead Connection:**
   - Use a Ferrite bead with a 1uF capacitor between 3.3V and GND.

6. **NRST Pin Connection:**
   - NRST is the reset pin. Connect a 100nF decoupling capacitor.
     - *Tip:* Expose NRST pin for manual reset if needed. Label the wire for clarity.

7. **BOOT0 Pin Configuration:**
   - The BOOT0 pin enables or disables the bootloader.
     - Pull it high to enable UART USB programming.

## Additional Resources:
- [Decoupling Capacitors](https://eepower.com/capacitor-guide/applications/coupling-and-decoupling/#:~:text=A%20decoupling%20capacitor%20acts%20as,to%20keep%20the%20voltage%20stable.)
