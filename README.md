## GNURadio Problem Set for ECSE 351 Spring 2025 (Capture Effect)

This project demonstrates the **capture effect** — a phenomenon in in FM-modulated systems where the receiver, presented with two signals at the same frequency, locks onto the **stronger signal** and effectively suppresses the weaker one.


---

## Requirements

- GNU Radio 3.8 or later
- Python 3

## Description of the simulated system 
The GNU Radio flowgraph implements a simulation of the capture effect using two modulated audio streams transmitted simultaneously. There are two sperate files (flow diagrams) for wideband frequency modulation (WBFM) and narrowband frequency modulation (NBFM), with the goal of showing how WBFM has a highly-sensitive capture effect.

Two Wav File Source blocks provide distinct audio signals which are bandpass filtered and then modulated using Narrowband FM (Wide band FM) via NBFM (WBFM( Transmit blocks. The two resulting FM signals are scaled using Multiply Const blocks to simulate unequal signal strengths which are tunable via ```rel_amp``` parameter. These signals are then summed using an Add block to model their coexistence on the same channel. The combined signal is passed through an NBFM (WBFM) Receive block that demodulates the dominant signal, demonstrating the capture effect. Audio output is sent to both an Audio Sink and a QT GUI Frequency Sink for real-time spectrum visualization. Adjustable parameters such as modulation index (```mod_in```), audio gain, and relative amplitude (```rel_amp```) allow users to explore how signal strength affects receiver behavior. Two test WAV files are provided

## Acknowledgements
Credit to Kristina Collins and David Kazdan for proposing the problem (Thresholding). The code was complied by GNU GUI

## License
This project is licensed under the MIT License. 
