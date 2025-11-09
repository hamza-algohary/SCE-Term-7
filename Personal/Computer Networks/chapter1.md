**Open System Interconnection** **(OSI)** is a model for computer networks using layered architecture.

**Network Topology** <br> A network consists of end systems (sources & sinks) and an interconnection subsystem (subnetwork).

**Elements of Meaningful Communication** <br> 
1. **Common Theme**
2. **Common Language**
3. **Orderly Session**

Subnetwork needs to provide functions for end systems know as **Transport- Oriented Function**, these are
1. **Interaction with the subnetwork.** Specifying destination address, handling incoming connections and releasing connections.
2. **Quality of transport service.** Specifying error rate, delay, throughput and cost. 
3. **Conversion of signals.** Bits to electrical signals suitable for transportation.
4. **Error control** 

**Components of a Computer Network** <br>
End systems must implement the following functions
1. Authentication.
2. Common syntax.
3. Synchronization
4. Quality & Flow Control
5. Interacting with the subnetwork.
6. Error control.
7. Conversion of bits into electrical signals and vice versa.

Lack of standardization led to the existence of **closed systems**.

Some standards are
1. IBM's System Network Architecture **SNA**
2. Digital's Digital Network Architecture **DNA**
3. Open System Interconnection (**OSI**) reference model developed by ISO (International Organization for Standardization) and ITu-T.
4. Internet Architecture.

**OSI Layers** <br>
1. **Application** like HTTP,FTP & SMTP
2. **Presenstation** present information to applications handling formats conversions and encryption/decryption.
3. **Session** enables apps to start and end connections, synchronization and interaction manangement.
4. **Transport**, provides
   - Quality of service parameters
   - Multiplex multiple connections or parallelize a single connection transparently
   - Offers connection-oriented or connectionless transport. The first ensuring lossles delivery, while the second not.
   - Also provides flow control.
5. **Network** hides routing details from higher layers.
6. **Data Link**
   - Handles frames
   - Detect & correct errors
   - Control flow
7. **Physical**
    - Signal converion & encoding
    - Relays

Upper four layers talk to their corresponding part on destination. While the lower three parts talk to the neighbouring nodes in the network.

All nodes in the subnetwork need to implement the lowest three layers.