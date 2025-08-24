# active-lowpass-filter-ltspice
First-order RC low-pass with op-amp buffer (LTspice). Looking for contributors.
# Active Low-Pass Filter (LTspice)

A first-order RC low-pass buffered by a unity-gain op-amp.  
**Public & open to contributions** — see Issues.

## Circuit
- R = 10 kΩ, C = 1 nF ⇒ \( f_c = \frac{1}{2\pi RC} \approx 15.9 \text{ kHz} \)
- Op-amp as a **voltage follower** (+ = RC node, − shorted to OUT)
- Supplies: ±15 V (common ground)

## Results
- **Bode (magnitude)**: ~0 dB at low freq, −3 dB near 15.9 kHz, −20 dB/decade afterward.
- **Step response**: exponential rise with \( \tau = RC \approx 10 \mu s \).
- **LTspice measurements**: see `docs/meas_results.txt`.

## How to run (LTspice)
- AC: plot `dB(V(vout)/V(vin))`.
- Transient: `PULSE(0 1 0 1u 1u 1 1)` and `.tran 0 100u 0 0.1u`.
- Open **SPICE Error Log** (Ctrl+L) for `.meas` outputs.

## Looking for contributors
Check open Issues labeled **good first issue** or **help wanted**. PRs welcome!
