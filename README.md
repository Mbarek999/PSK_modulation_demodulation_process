# PSK Modulation/Demodulation Simulation with Simulink

## Overview
This project implements a complete **Phase Shift Keying (PSK)** communication system in Simulink, demonstrating digital signal transmission through noisy channels. The system includes modulation, AWGN channel simulation, and demodulation with noise filtering - providing a practical framework for understanding digital communications.

## Key Features
- **BPSK Modulation**: Binary phase shifts (0° and 180°) of a 4Hz carrier signal
- **Noisy Channel**: Realistic AWGN simulation with configurable SNR (default: 10dB)
- **Demodulation**: Coherent detection with Chebyshev filtering (20th-order low-pass)
- **Validation**: MIL/SIL testing workflows for simulation and embedded deployment
- **Visualization**: Comparative signal analysis at each processing stage

## System Architecture
```mermaid
graph LR
    A[Binary Input] --> B(PSK Modulator)
    B --> C[AWGN Channel]
    C --> D(PSK Demodulator)
    D --> E[Chebyshev Filter]
    E --> F[Recovered Output]
```

## Implementation Details

### Modulation
- **Carrier Wave**: 4Hz, 4V amplitude
- **Encoding**:
  - Binary 0 → 0° phase
  - Binary 1 → 180° phase shift

### Channel Model
- **Noise Type**: Additive White Gaussian Noise (AWGN)
- **Configurable Parameters**:
  - SNR (default: 10dB)
  - Noise power spectral density

### Demodulation
- **Coherent Detection**: Mixing with reference carrier
- **Filter Specifications**:
  - Type: Chebyshev I Low-pass
  - Order: 20
  - Cutoff: 10 rad/s
  - Passband ripple: 2dB

## Getting Started

### Requirements
- MATLAB R2021a or later
- Simulink
- DSP System Toolbox
- Embedded Coder (for SIL testing)

### Installation
1. Clone the repository
2. Open `PSK_ModDemod.slx` in MATLAB

### Basic Usage
1. Run simulation to observe signal processing chain
2. Adjust parameters via:
   ```matlab
   set_param('PSK_ModDemod/AWGN_Channel', 'SNR', '15') % Example SNR change
   ```
3. View signals on connected Scope blocks

## Advanced Features
- **Model-in-Loop (MIL) Testing**:
  - Validate model behavior before code generation
  - Verify signal integrity metrics

- **Software-in-Loop (SIL)**:
  - Generate ARM Cortex-M compatible C code
  - Processor-in-Loop (PIL) options available

## Expected Results
| Signal Stage | Characteristics |
|--------------|-----------------|
| Original | Clean binary waveform |
| Modulated | Phase-shifted carrier |
| Noisy | Signal with visible distortion |
| Recovered | Restored binary signal |

## Troubleshooting
- **Simulation Errors**:
  - Verify all toolboxes are installed
  - Check sample rate consistency
- **Filter Instability**:
  - Reduce filter order if needed
  - Adjust cutoff frequency

## License
This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details.

## References
1. Proakis, J.G., "Digital Communications", 5th Ed.
2. MathWorks Documentation: PSK Modulation

---
*For support or contributions, please open an issue or submit a pull request.*
