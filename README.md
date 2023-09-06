# OSI-Model
OSI model (Open source intercommunication model) is a theoretical framework.

OSI model developed by the international organization for standardization (ISO) in 1984.

**OSI model based on 7 layer:**

![alt text](image/OSILayer.png)

## 1. Physical Layer 
Physical Layer converts the binary sequence into a signal and transmits to our local network. It can be an electrical signal in case of copper wire or LAN cable, Light signal in case of optical signal and radio signal in case of Air.


Cloud Load Balancers are broadly divided into two categories - L4 and L7:

- L4: Layer 4 balancer operate from Transport level and use TCP UDP
- L7: Layer 7 balancer operate from Application level and use http https etc

### The main discussion topic of this layer are :
- How bits are presented
- What would be the encoding method
- Wiring Standarts
- Encoding
- Physical topology
- Synchornization
- Bandwith
- Multiplexing

In the OSI (Open Systems Interconnection) model, the physical layer is the lowest layer, responsible for the transmission and reception of raw bit streams over a physical medium, such as copper cables, optical fibers, or wireless communication channels. The physical layer is concerned with how data is physically transmitted from one device to another, and it deals with the following aspects of bit representation:

1. **Physical Medium**: The physical layer is responsible for defining the characteristics of the physical medium, including the type of medium (e.g., copper, fiber-optic, radio waves), the voltage levels, the modulation scheme, and the physical connectors used to transmit and receive data.

2. **Encoding**: In order to transmit data over a physical medium, digital data (0s and 1s) must be converted into signals that can be sent over the medium. This is typically done through encoding techniques, which represent binary data as different electrical or optical states. Common encoding methods include NRZ (Non-Return-to-Zero), Manchester encoding, and various modulation techniques for wireless communication.

3. **Physical Signaling**: The physical layer determines how bits are represented as physical signals. This involves translating the encoded bits into the appropriate electrical voltage levels or optical signals for transmission. For example, in Ethernet, electrical voltage levels represent binary 0s and 1s on copper cables.

4. **Data Rate**: The physical layer defines the data rate or transmission rate, which specifies how many bits are sent per unit of time. This is often measured in bits per second (bps) and is sometimes referred to as the "baud rate."

5. **Transmission Medium Characteristics**: The physical layer also deals with issues related to the characteristics of the transmission medium, including signal attenuation, noise, and interference. It defines mechanisms for dealing with these issues to ensure reliable data transmission.

6. **Topology and Physical Connection**: It specifies the physical topology of the network (e.g., bus, star, ring) and how devices are physically connected to the network.

7. **Synchronization**: Ensures that the sender and receiver are synchronized in terms of when data is sent and when it should be sampled for reception.

8. **Bit Order**: Determines the bit order, which can be either "big-endian" or "little-endian," depending on the network's conventions.

In summary, the physical layer in the OSI model is responsible for the physical representation and transmission of data bits over the communication medium. It defines how data is encoded, transmitted, and received in a way that ensures reliable communication between devices over physical links. The specifics of how bits are represented and transmitted can vary widely depending on the physical medium and the networking technology in use.


### what are the available encoding methods and why alternate mark inversion is best(AMI)?

There are several encoding methods used in communication systems to transmit data over a communication channel. Each encoding method has its own advantages and disadvantages, and the choice of the "best" method depends on the specific requirements and characteristics of the communication system. Let's explore a few common encoding methods and then discuss why Alternate Mark Inversion (AMI) might be preferred in certain situations.

**1. Unipolar Encoding:**
In unipolar encoding, the binary data is represented using a single voltage level, usually positive. This is simple but not very noise-resistant, as there is no inherent way to distinguish between signal absence and a continuous positive signal.

**2. Polar Encoding:**
Polar encoding uses both positive and negative voltage levels to represent binary data. This improves noise immunity and reduces the likelihood of DC bias in the transmitted signal. However, polar encoding still faces challenges in synchronization and DC component elimination.

**3. Bipolar Encoding:**
Bipolar encoding uses positive and negative voltage levels as well as a zero voltage level to represent binary data. This helps with DC component elimination and synchronization, but it can be more complex to implement.

**4. Alternate Mark Inversion (AMI):**
AMI is a specific type of bipolar encoding that addresses the issue of long runs of zeros in the data stream. In AMI, zeros are encoded as alternating positive and negative voltage levels, while ones are represented by zero voltage levels. This helps in synchronization and eliminates the DC bias, which is particularly important in long-distance communication.

**Advantages of AMI:**

1. **DC Component Elimination:** AMI eliminates the DC component in the transmitted signal, which helps in efficient use of the available bandwidth and reduces the risk of signal distortion due to coupling capacitors or other components.

2. **Synchronization:** The alternating nature of AMI helps in maintaining synchronization between the transmitter and receiver. The transitions between positive and negative levels provide regular timing references.

3. **Noise Immunity:** AMI reduces the risk of confusion between data signal absence and continuous zero signal, enhancing noise immunity.

4. **Reduced Signal Power:** Transmitting both positive and negative levels balances the signal power, which can be important in various systems to prevent overheating of components.

**When is AMI Preferred:**

AMI encoding is often preferred in scenarios where the transmitted signal must traverse long distances or encounter noisy environments, such as in telecommunications and data transmission over cables. In such cases, AMI's ability to maintain synchronization, eliminate DC bias, and improve noise resistance becomes crucial. Additionally, when data streams have long runs of zeros (which can occur in certain types of data), AMI is particularly effective in mitigating synchronization challenges.

It's important to note that while AMI has its advantages, there are situations where other encoding methods might be more suitable. The choice of encoding method depends on factors like the channel characteristics, noise levels, available bandwidth, and the specific requirements of the communication system.

### How many topologies are their which one is the most used topology?

There are several network topologies, each with its own advantages and disadvantages. The choice of which topology to use depends on the specific requirements and constraints of a given network. Some of the most common network topologies include:

1. **Star Topology**: In a star topology, all devices are connected to a central hub or switch. This is one of the most commonly used topologies in LAN (Local Area Network) setups because it's easy to manage and provides good fault tolerance.

2. **Bus Topology**: In a bus topology, all devices are connected to a central cable or bus. It's simple but less common nowadays due to limitations in scalability and fault tolerance.

3. **Ring Topology**: In a ring topology, devices are connected in a circular or ring-like fashion. Each device is connected to exactly two other devices. Ring topologies are less common in modern networks due to their lack of fault tolerance.

4. **Mesh Topology**: In a mesh topology, every device is connected to every other device. This offers the highest level of fault tolerance but can be costly to implement due to the sheer number of connections required.

5. **Hybrid Topology**: Hybrid topologies combine two or more different topologies. For example, a network could be a combination of star and mesh topologies to balance fault tolerance and cost-effectiveness.

6. **Tree (Hierarchical) Topology**: A tree topology combines characteristics of a star and bus topology. It's commonly used in wide area networks (WANs) where regional hubs are connected to a central hub.

7. **Point-to-Point Topology**: In a point-to-point topology, each device is directly connected to only one other device. This is common in simple communication links.

The most commonly used topology depends on the specific context and the type of network being discussed. In modern LAN environments, the star topology is often the most used due to its simplicity, ease of management, and reasonable fault tolerance. However, in larger and more complex networks, a combination of topologies or a hierarchical approach may be employed to meet various requirements.