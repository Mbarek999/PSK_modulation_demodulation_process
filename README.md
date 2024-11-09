PSK Modulation/Demodulation in Simulink:

In this project, we will simulate the PSK (Phase Shift Keying) encoding and decoding process for real-time applications. The objective is to wirelessly transmit a binary signal through a noisy channel, then restore the signal using coherent demodulation, a strong analog Chebyshev filter, and an analog comparator.

PSK is widely used in applications such as wireless LANs, RFID, and Bluetooth communication.

Wireless Digital Transmission:

Feature Overview
Phase Shift Keying (PSK) is a digital modulation technique that conveys data by altering the phase of a constant-frequency carrier wave.

Noise Simulation: The noisy channel will be simulated using 'AWGN' (Additive White Gaussian Noise), modeling real-world interference. The transmitted signal will also be combined with a Gaussian noise source to simulate channel noise.
Carrier Wave: The carrier wave is a high-frequency signal that carries the modulated data through the channel.
Modulation Process: Modulation is achieved by precisely shifting the phase of the sine and cosine components of the carrier wave to represent binary data.
Demodulation Process: Demodulation involves multiplying the received signal with the carrier wave, followed by low-pass filtering using a Chebyshev filter, and finally, comparison using an analog comparator with a threshold set to 1.
Wireless Transmission: The modulated signal is transmitted and received via antennas for electromagnetic transmission.

Simulation description:
...
