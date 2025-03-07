---
title: Requirements and architecture
type: docs
weight: 1
math: true
---

# Network slicing requirements and architecture for smart manufacturing scenarios.

- Smart factories are a key component of Industry 4.0, leveraging machine and sensor data to optimize manufacturing through real-time feedback.
- Network slicing enhances smart factory networks by creating virtual, isolated networks that support diverse industrial use cases with different QoS needs.
- However, there is a lack of research on designing and managing network slices specifically for smart factories, which must account for unique network architectures, resource types, and strict business demands.
- Research efforts from groups like 5G-ACIA[^1] and 3GPP have defined smart factory use cases for 5G network slicing, including manufacturing control, production monitoring, automation, and maintenance, each with varying data, reliability, and latency requirements.

## Smart factory service requirements

- Smart factory automation falls under 5G's URLLC service category, requiring high reliability, low latency, and determinism. However, not all applications demand these extreme capabilities.
- Some, like surveillance cameras and customer support, need high data rates but can tolerate higher latency, while manufacturing and IIoT require support for many concurrent connections.
- Smart factory services must integrate all three 5G slice types: eMBB, mMTC, and URLLC.
- Network slicing enables the division of smart factory infrastructure into multiple virtual networks, each optimized for specific applications. However, current slicing approaches mainly focus on bandwidth and throughput, highlighting the need for better support of time-sensitive smart factory applications.
- The next section categorizes smart factory use cases based on their requirements.

## Use cases of smart factory

- 3GPP technical specification group has identified five general types of smart factory use cases, including factory automation, human-machine interaction (HMI), process automation, logistics and warehousing, and monitoring and maintenance.

### Factory automation

- Manages complex processes like control automation, process monitoring, and optimization.
- Requires low-latency, highly available, and deterministic communication networks.
- Modular production systems are replacing static ones, increasing demand for wireless communication and localization services.

### HMIs and production IT

- Includes human-machine interfaces (HMIs) like control panels and IT systems such as MES and ERP.
- Augmented Reality (AR) and Virtual Reality (VR) are expected to enhance human-plant interactions.
- Requires real-time data streaming for decision-making and process management.

### Process automation

- Manages production control and substance handling in industries like chemicals, food, and pulp.
- Involves thousands of sensors measuring environmental factors and controlling actuators in closed-loop systems.
- Systems can be distributed across large areas, requiring reliable communication and coordination.

### Logistics and warehousing

- Ensures uninterrupted supply of raw materials using mobile robots and AGVs.
- Warehouses are becoming more automated with conveyors, cranes, and ASRS.
- Requires precise localization, tracking, and real-time monitoring of assets.

### Monitoring and maintenance

- Focuses on process and asset monitoring without immediate real-time control.
- Includes predictive maintenance and big data analytics for optimizing operations.
- Not latency-critical but requires efficient handling of large-scale sensor data.

### Conclusions

- **Smart factory use cases have different network slicing demands** based on reliability, bandwidth, latency, scalability, and serviceability.
- **Three types of network slices** are defined based on traffic characteristics: deterministic periodic slices, deterministic aperiodic slices and non-deterministic slices.
- **Deterministic periodic slices are the most critical** as they require bounded latency for real-time industrial applications.

#### Deterministic periodic slices

Generates traffic at regular intervals with strict latency requirements (e.g., motion control, sensor monitoring).

| Supporting use cases        | Applications         | Latency         | Payload              | Bandwidth | Density    |
| --------------------------- | -------------------- | --------------- | -------------------- | --------- | ---------- |
| **Motion control**          | Printing machine     | $$\leq 1 \ ms$$ | $$\leq 1 \ KB$$      | -         | ⭐⭐⭐     |
| **Control to Control**      | Machine coordination | $$3 - 10 \ ms$$ | $$\leq 1 \ KB$$      | -         | ⭐⭐       |
| **Massive sensor networks** | Monitoring           | $$1 - 10 \ ms$$ | $$60 - 270 \ bytes$$ | -         | ⭐⭐⭐⭐⭐ |

_Density Level from lowest_ (⭐) _to highest_ (⭐⭐⭐⭐⭐).

#### Deterministic Aperiodic Slices

Event-driven traffic that must meet specific time limits (e.g., mobile robots, autonomous process control).

| Supporting use cases        | Applications        | Latency         | Payload              | Bandwidth | Density  |
| --------------------------- | ------------------- | --------------- | -------------------- | --------- | -------- |
| **Mobile robots**           | Emergency stops     | $$3 - 10 \ ms$$ | $$30-240 \ bytes$$   | -         | ⭐⭐     |
| **Closed-loop control**     | Automation          | $$5 - 10 \ ms$$ | $$10-100 \ bytes$$   | -         | ⭐⭐⭐⭐ |
| **Massive sensor networks** | Cooperative control | $$5 - 10 \ ms$$ | $$10 - 100 \ bytes$$ | -         | ⭐⭐⭐   |

_Density Level from lowest_ (⭐) _to highest_ (⭐⭐⭐⭐⭐).

#### Non-Deterministic Slices

No strict transmission deadlines (e.g., system maintenance, software updates).

| Supporting use cases      | Applications                         | Latency       | Payload | Bandwidth          | Density    |
| ------------------------- | ------------------------------------ | ------------- | ------- | ------------------ | ---------- |
| **System maintenance**    | Software/firmware updates            | Non-real time | -       | $$100-500 \ Mbps$$ | ⭐⭐⭐⭐   |
| **Safety panels**         | User interaction                     | Non-real time | -       | $$5-20 \ Mbps$$    | ⭐         |
| **Plan asset management** | Software updates and reconfiguration | Non-real time | -       | $$1-100 \ Mbps$$   | ⭐⭐⭐⭐⭐ |

_Density Level from lowest_ (⭐) _to highest_ (⭐⭐⭐⭐⭐).

## Key enabling technologies

- **Smart factory network slicing relies on emerging technologies** such as IoT, cloud manufacturing, SDN, and NFV to optimize manufacturing processes.
- **IoT enables real-time monitoring and control** by interconnecting digital sensors and devices, allowing a digital representation of production environments.
- **Cloud manufacturing virtualizes industrial resources**, turning them into services and enabling flexible production, but latency challenges drive the adoption of edge computing for time-sensitive tasks.
- **SDN enhances network flexibility and control** by centralizing network management, optimizing traffic, and improving energy efficiency in industrial networks.
- **NFV boosts scalability and resource efficiency** by virtualizing network functions (VNFs) on shared infrastructure, and when combined with **SDN**, **IoT**, and **cloud**, it strengthens network slicing for smart factories.

## References

[^1]: 5G ACIA, 5G Alliance for Connected Industries and Automation, [Link](https://5g-acia.org/)
