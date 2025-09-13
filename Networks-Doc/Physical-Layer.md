# Physical Layer (Part 1)

The **Physical Layer** is the lowest layer of the OSI model. It is responsible for the **actual transmission of raw bits (0s and 1s) as signals** over a physical medium such as copper wires, fiber optics, or air (in case of wireless communication). Unlike the higher layers, it does not deal with meaning of data; it only ensures that the data in the form of bits can travel from one device to another.  

---

## Services of the Physical Layer  
The physical layer provides several fundamental services:  

1. **Representation of Bits**: Bits (0 and 1) are converted into signals for transmission. The encoding scheme defines how a bit value is represented in terms of voltage, frequency, or phase.  
2. **Data Rate**: It specifies how many bits can be transmitted per second, usually measured in bits per second (bps).  
3. **Synchronization**: The sender and receiver must be synchronized at the bit level, so that the receiver can correctly interpret the incoming signal.  
4. **Interface**: Defines how a device connects to the transmission medium. For example, the design of connectors, plugs, or antenna systems.  
5. **Line Configuration**: Describes how devices are connected. This can be point-to-point (one sender to one receiver) or multipoint (several devices share the same link).  
6. **Network Topologies**: Defines different ways of connecting multiple devices in a network, such as mesh, star, ring, bus, tree, or hybrid.  
7. **Transmission Modes**:  
   - Simplex: One-way communication.  
   - Half-duplex: Both ways but one at a time.  
   - Full-duplex: Both ways simultaneously.  
8. **Baseband and Broadband Transmission**: The physical layer deals with both. Baseband sends signals directly, while broadband uses modulation to send signals over long distances.  

---

## Signals – The Carrier of Bits  
In order to transmit data, bits must be transformed into signals.  

- **Analog signals** are continuous in nature and can take any value within a range. An example is human voice.  
- **Digital signals** are discrete, meaning they can take only specific values such as 0 or 1.  

**Signals are described by certain parameters:**  
- **Amplitude**: The strength or height of the signal.  
- **Frequency**: The rate at which the signal changes over time. A signal that does not change has frequency zero. Frequency and period are inverses of each other.  
- **Phase**: The position of the waveform relative to a reference time (time zero).  
- **Wavelength**: The distance a wave travels in one cycle, which is calculated as propagation speed divided by frequency.  

---

## Frequency Domain and Fourier Analysis  
While a simple sine wave is easy to understand, data communication requires complex signals. A composite signal is made up of many sine waves with different amplitudes, frequencies, and phases.  

- **Fourier Analysis** states that any composite signal can be decomposed into simple sine waves.  
- If the signal is periodic, the result is a series of discrete frequencies.  
- If the signal is non-periodic, the result is a continuous range of frequencies.  
- **Bandwidth** is defined as the difference between the highest and the lowest frequency in a composite signal. It is a key property because it determines how much data can be transmitted.  

---

## Digital Transmission  
Most communication systems use digital transmission.  

- **Bit Rate** defines how many bits are transmitted per second.  
- **Baseband Transmission** is when digital signals are sent directly without modulation. Example: Ethernet in LANs.  
- **Broadband Transmission** involves modulating signals so multiple types of data can be sent simultaneously over long distances. Example: Cable TV or fiber optics.  

An important principle is that as the bit rate increases, the required bandwidth also increases.  

---

## Causes of Signal Impairment  
Signals rarely travel without problems. Imperfections in the transmission medium cause impairments such as:  

1. **Attenuation**: Loss of signal strength as it travels. This is measured in decibels (dB).  
2. **Distortion**: Change in the shape of the signal.  
3. **Noise**: Random unwanted signals that interfere with the original message.  

The quality of a signal is often expressed as **Signal-to-Noise Ratio (SNR)**. A high SNR means a clearer signal, while a low SNR indicates more interference.  

---

## Network Performance Measures  
To judge how well a network performs, several metrics are used:  

1. **Bandwidth**:  
   - In hertz, it refers to the frequency range that a channel can pass.  
   - In bits per second, it refers to the transmission speed of the channel.  

2. **Latency (Delay)**: The total time it takes for a message to travel from sender to receiver. It includes:  
   - Propagation Time = Distance / Propagation speed.  
   - Transmission Time = Message size / Bandwidth.  
   - Queuing Time = Time a message waits at intermediate devices.  
   - Processing Delay = Time taken by devices to process the data.  

3. **Throughput**: The actual rate of successful data transfer, which may be lower than bandwidth due to congestion.  

4. **Channel Utilization**: A measure of how effectively the available channel capacity is being used.  

5. **Bandwidth-Delay Product**: Defines how many bits can be present inside the network link at a time.  

6. **Jitter**: The variation in packet delay. High jitter causes poor quality in applications such as video calls or real-time audio.  

---
