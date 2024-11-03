# LteSchedulingEval

# LTE Uplink Overview

This repository provides an overview of how the LTE (Long-Term Evolution) uplink works. The uplink refers to the communication link from the user equipment (UE) – such as a smartphone or mobile device – to the base station (eNodeB) in LTE networks. This document outlines the key concepts, steps, and advantages of LTE's uplink design.

## Key Concepts

- **Single-Carrier Frequency Division Multiple Access (SC-FDMA):** LTE uses SC-FDMA for uplink transmissions to reduce the peak-to-average power ratio (PAPR), making it more power-efficient for the UE. SC-FDMA is well-suited for battery-powered devices and minimizes device complexity.

- **Resource Blocks (RBs):** The LTE uplink spectrum is divided into resource blocks, the smallest unit of bandwidth allocation. Each RB consists of 12 subcarriers and a 0.5 ms time slot, and UEs are assigned specific RBs for uplink transmission.

- **Physical Uplink Shared Channel (PUSCH):** This is the primary channel for user data sent from the UE to the eNodeB. The PUSCH carries both user data and control information, such as scheduling requests.

- **Physical Uplink Control Channel (PUCCH):** Used for transmitting control information (UCI) such as acknowledgments, channel quality indicators (CQI), and scheduling requests.

- **Hybrid Automatic Repeat Request (HARQ):** HARQ is a key error correction mechanism in LTE. If data packets are corrupted during transmission, the eNodeB requests retransmissions, and the UE sends them until the data is received correctly.

## Steps in LTE Uplink Transmission

1. **Resource Scheduling:** The eNodeB manages uplink scheduling by assigning resource blocks to UEs based on data demand, channel quality, and availability. UEs receive scheduling grants from the eNodeB via the Physical Downlink Control Channel (PDCCH).

2. **Modulation and Coding:** UEs modulate and code data for transmission based on the channel conditions set by the eNodeB.

3. **SC-FDMA Transmission:** UEs use SC-FDMA to transmit data to the eNodeB, which is more power-efficient than OFDMA, used in LTE downlink.

4. **Channel Feedback and Adjustment:** The eNodeB receives channel feedback from UEs, including CQI values, to optimize scheduling and power allocation.

5. **HARQ and Retransmissions:** If errors occur, HARQ requests retransmissions to improve data accuracy.

## Key Advantages of LTE Uplink

- **Power Efficiency:** SC-FDMA helps reduce power requirements for UEs, extending battery life.
- **Low Latency:** LTE's scheduling mechanism supports rapid data transmission and minimal delay.
- **High Data Rates:** Adaptive modulation and efficient resource usage enable high data rates.

---
