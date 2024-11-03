# LteSchedulingEval

# LTE Uplink Overview

This repository aims to evaluate the performance of different scheduling algorithms based on metrics of throughput, delay, and fairness. The uplink refers to the communication link from the user equipment (UE) – such as a smartphone or mobile device – to the base station (eNodeB) in LTE networks. This document outlines the key concepts, steps, and advantages of LTE's uplink design.

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

# LTE Scheduling Algorithms: Round Robin and Proportional Fair

This document provides an overview of two popular scheduling algorithms used in LTE (Long-Term Evolution) networks for resource allocation: **Round Robin (RR)** and **Proportional Fair (PF)**. These algorithms help manage network resources, balancing user fairness and overall network performance.

---

## 1. Round Robin (RR) Scheduling

**Round Robin (RR)** is a time-based scheduling algorithm that treats all users equally by allocating resources in a cyclic manner.

- **How It Works:** 
  - The eNodeB assigns radio resources to each user sequentially, without considering channel quality or data rate needs. For example, each user is allocated a time slot in order (User 1, then User 2, then User 3, etc.) before cycling back to the first user.
  - Each user receives an equal amount of time on the channel, resulting in fair access by time.

- **Advantages of Round Robin Scheduling:**
  - **Fairness**: Ensures all users have equal access to network resources.
  - **Simplicity**: Easy to implement and requires minimal computational resources.

- **Disadvantages of Round Robin Scheduling:**
  - **Inefficiency in Varying Conditions**: It does not consider users’ channel conditions, potentially leading to inefficiency.
  - **Lower Overall Throughput**: Allocates resources regardless of channel quality, resulting in lower network throughput, especially for users in low-signal areas.

---

## 2. Proportional Fair (PF) Scheduling

**Proportional Fair (PF)** scheduling balances fairness and efficiency by considering both the user’s current channel quality and their historical average throughput.

- **How It Works:**
  - The PF scheduler prioritizes users with a high instantaneous data rate relative to their average throughput, allowing them to transmit when channel conditions are favorable.
  - This approach combines **short-term scheduling** (to maximize network performance) with **long-term fairness** (to ensure all users have reasonable access).

- **Advantages of Proportional Fair Scheduling:**
  - **Higher Throughput**: Utilizes favorable channel conditions to maximize overall network throughput.
  - **Fair Access Based on Demand**: Balances user needs with network efficiency by allocating more resources to users with high relative channel quality.

- **Disadvantages of Proportional Fair Scheduling:**
  - **Complexity**: More computationally intensive, requiring the eNodeB to track users’ average throughput and channel quality.
  - **Potential Fairness Issues in High Demand**: Users with consistently poor channel conditions may experience reduced throughput, especially in congested networks.

---

## Comparison Summary

| Feature                | Round Robin (RR)             | Proportional Fair (PF)            |
|------------------------|------------------------------|------------------------------------|
| **Fairness**           | High (equal time allocation) | Moderate (fair access with throughput focus) |
| **Efficiency**         | Low (ignores channel quality)| High (adapts to channel conditions) |
| **Complexity**         | Low                          | Moderate to High                  |
| **Best Use Cases**     | Equal demand, similar signal conditions | Varied user conditions, higher throughput requirements |

---

### In Summary

Both Round Robin and Proportional Fair algorithms serve unique purposes in LTE. Round Robin provides simple, equal access to resources and is useful for equal-demand scenarios. Proportional Fair scheduling, however, is designed for higher throughput, adapting to varying channel conditions while balancing user demand and fairness. Choosing the right scheduling algorithm depends on the network’s goals for throughput, fairness, and computational resources.

---

# Network Configuration

The 5g toolbox and Communications Toolbox Wireless Network Simulation Library and Communications Toolbox were used to implement the network.

- **Base node configuration**
  - Position          [0 0 30]
  - DuplexMode        FDD
  - CarrierFrequency  2.6e9
  - ChannelBandwidth  30e6
  - SubcarrierSpacing 15e3
  - ReceiveGain       11


- **User Equipment configuration**
  - Name         Dynamic value based on index in array 
  - Position     Dynamic value based on index in array
  - ReceiveGain  11



