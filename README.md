  PSK modulation/demodulation on simulink
This project demonstrates how to simulate a PSK (Phase Shift Keying) communication system in Simulink, including modulation, transmission through a noisy channel, and demodulation.

Project Overview
We model a digital communication system where:

A binary signal (representing sensor data or control commands) is modulated using PSK.

The modulated signal is transmitted through a noisy channel (simulated using AWGN).

The receiver demodulates the signal and recovers the original data using a Chebyshev filter.

The goal is to ensure reliable data transmission even in the presence of noise.

Key Components
1. Modulation (PSK - Phase Shift Keying)
The binary signal (0s and 1s) is encoded by shifting the phase of a carrier wave (4 Hz, 4V amplitude).

Phase shifts:

0° → Binary "0"

180° → Binary "1"

2. Transmission Channel (AWGN - Additive White Gaussian Noise)
Simulates real-world noise in communication (e.g., wireless or wired interference).

SNR (Signal-to-Noise Ratio): Set to 10 dB (adjustable).

3. Demodulation & Filtering
The received signal is mixed with the original carrier to recover the baseband signal.

A Chebyshev low-pass filter removes high-frequency noise:

Filter order: 20 (aggressive filtering for better noise removal).

Cutoff frequency: 10 rad/s.

Simulation Steps
1. Model Setup (Simulink Blocks)
Signal Source → PSK Modulator → AWGN Channel → PSK Demodulator → Chebyshev Filter → Output.

Visualization: Scope blocks display:

Original binary signal

Modulated PSK signal

Noisy transmitted signal

Recovered signal after filtering

2. Testing & Validation
MIL (Model-in-the-Loop):

Simulate the model in Simulink to verify correct behavior.

Check signal integrity before and after transmission.

SIL (Software-in-the-Loop):

Generate embedded C code (compatible with ARM Cortex-M).

Validate real-time performance on hardware.

Results
Successful demodulation even with added noise.

The Chebyshev filter effectively removes noise while preserving signal shape.

The final output matches the original input, proving the system’s reliability.

How to Use This Project
Open the Simulink model (PSK_ModDemod.slx).

Run the simulation to see the signal at each stage.

Adjust parameters (e.g., SNR, filter settings) for different noise conditions.

Generate C code (for embedded deployment) if needed.


Requirements
MATLAB & Simulink (R2021a or later).

DSP System Toolbox (for filter design).

Embedded Coder (for SIL testing and code generation).

Conclusion
This simulation demonstrates a practical PSK communication system that can be adapted for real-world applications like sensor networks, wireless control, or digital telemetry.

For questions or improvements, feel free to contribute! 🚀

