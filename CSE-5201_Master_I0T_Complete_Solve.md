# Future Internet and IoT (CSE-5201) — Complete Solved Exam Guide

> M.Sc. in Computer Science and Engineering (Professional), Jagannath University
> Course: **Future Internet and IoT** | Course Code: **CSE-5201**

This document contains **fully solved, exam-ready answers for all 5 past Final Examination papers** (17th, 16th, 15th, 14th batch, and the undated Winter-2023 final) — every question, every sub-part, 60 marks each. Answers are sourced primarily from the official course lecture slides (Lectures 1–7); topics not present in the slides are clearly flagged and supplemented with standard academic knowledge.

---

## Table of Contents

- [Exam Structure](#exam-structure)
- [Source Material & Coverage Notes](#source-material--coverage-notes)
- [17th Batch — Final Examination Winter-2025](#17th-batch--final-examination-winter-2025)
- [16th Batch — Final Examination Winter-2024](#16th-batch--final-examination-winter-2024)
- [15th Batch — Final Examination Summer-2023](#15th-batch--final-examination-summer-2023)
- [14th Batch — Final Examination Summer-2024](#14th-batch--final-examination-summer-2024)
- [Winter-2023 Final Examination (Undated Batch)](#winter-2023-final-examination-undated-batch)
- [Disclaimer](#disclaimer)

---

## Exam Structure

| Exam Type | Duration | Total Marks | Answering Rule |
|---|---|---|---|
| **Final** | 3.0 hours | 60 | Answer any **5 of 7** questions (12 marks each) |

Each question is broken into 3 sub-parts **(a), (b), (c)**. All 7 questions of every paper are solved below so you can study the full question bank.

---

## Source Material & Coverage Notes

**✅ Fully covered by official lecture slides (Lectures 1–7):**
Future Internet fundamentals, Clean Slate, Network Neutrality, SOA, Layering, GENI, AKARI, NWGN/JGN2, Industrial Revolution/4IR, IoT definition/evolution/layers/applications, M2M communication, IIoT, Sensors & Transducers, Arduino, Raspberry Pi, MQTT, CoAP, Green IoT, Cloud Computing types/security/pricing, Mobile Cloud Computing & applications, Code Offloading/MDC, and smart-application working procedures (inventory, waste, parking, street lighting, irrigation).

**⚠️ Not present in the provided lecture files** *(flagged inline below, supplemented with standard academic/technical knowledge)*:
Computing paradigms (general classification), Virtualization types & Paravirtualization/Xen, Containers vs VMs/Docker, FOG Computing architecture, Edge Computing architecture, SDN/OpenFlow/ToS, Bitcoin & Blockchain (all sub-topics)/Merkle Tree, AAID, Aquaponics-based IoT architecture.

> If additional lecture slides (e.g., Lecture 8, 9, or 10) covering these topics become available, the flagged answers should be re-aligned to your instructor's exact terminology and examples.

---
---

# 17th Batch — Final Examination Winter-2025

## Question 1 (12 marks)

### (a) What is Future Internet? Explain the necessity of Future Internet design. (4)

**Definition**
Future Internet refers to the effort to resolve the challenges facing today's Internet by rethinking the fundamental assumptions and design decisions underlying its current architecture. It can be pursued through an **evolutionary (incremental)** approach or a **revolutionary (Clean Slate)** approach — a complete redesign from scratch while keeping similar functionality but based on new core principles.

**Necessity**
- Growing and changing user demand for greater control over content and services
- Need to interconnect "things" — TVs, PCs, phones, sensors — not just computers
- Convergence of networks, devices, and services (video, audio, data, voice) on one platform
- Increasing demand for mobility support
- Increasing demand for stronger security
- Current Internet technology has reached limits in scalability, flexibility, performance, and functionality that incremental patches can no longer fix

**Conclusion**
Since today's Internet was not designed for today's scale, mobility, and security needs, a Future Internet — potentially built with a clean-slate design — is necessary to meet these growing demands.

### (b) Explain the layered architecture of Today's Internet. (4)

**Definition**
Today's Internet follows a **layered design principle**, where each layer performs a distinct function and communicates only with the layer directly above or below it.

| Layer | Function |
|---|---|
| Physical Layer | Codes data and transports it over wire/ether |
| Link Layer | Enables neighbour-to-neighbour communication |
| Network (IP) Layer | Enables host-to-host communication; addressing (IP), routing, packet delivery |
| Transport Layer | Enables application-to-application communication — TCP (reliable, byte-stream) or UDP (unreliable, message-based) |
| Application Layer | Implements application-specific protocols (e.g., HTTP, FTP) via the Socket API |

**Significance:** Layering enables simple interconnection of existing networks (design goal 0) and accommodates a variety of physical networks (design goal 3).

**Conclusion:** The layered model allows heterogeneous networks and applications to interoperate over a single common Internet infrastructure.

### (c) State the key functionalities of AKARI project. (4)

**Definition**
AKARI is Japan's biggest architectural research project for the New Generation Network (NWGN), aiming to design a clean-slate network architecture.

**Key Points — AKARI assembles five sub-architectures:**
1. An **integrated layered sub-architecture** with cross-layer collaboration; logical identity kept separate from the data plane
2. A **simplified layered sub-architecture** that reduces duplicated functions across lower layers
3. A sub-architecture for **QoS guarantee and multicast**
4. A sub-architecture to **connect heterogeneous networks through virtualization**
5. A **mobile access sub-architecture** for sensor information distribution and regional adaptive services

**Conclusion:** Together, these five sub-architectures form AKARI's blueprint for a next-generation, virtualization-friendly, QoS-aware Future Internet.

---

## Question 2 (12 marks)

### (a) What is 4IR? Difference between Evolution and Revolution. (2)

**4IR (Fourth Industrial Revolution / Industry 4.0)** began around 2000, marked by IoT and Cyber-Physical Systems, driven by Augmented Reality and Real-Time Intelligence.

| Evolution | Revolution |
|---|---|
| A gradual process where something changes progressively from one stage to another | A total turnaround — a sudden, complete, fundamentally radical change |
| Example: Fancy Carriage → Early Automobile (later refinements) | Example: Invention of the Automobile itself |

Typically, a Revolution leads to further Evolution.

### (b) What is IoT? Describe the evolution process for IoT. (5)

**Definition**
The **Internet of Things (IoT)** is a network of physical objects embedded with sensors, software, and connectivity that allows them to collect and exchange data over the Internet with minimal human involvement.

**Evolution of IoT — Five Major Stages**
1. **Pre-Internet Era (Human-to-Human):** Fixed telephones, mobile telephony, SMS; no data intelligence, no automation
2. **Internet of Content (WWW):** Static web pages, one-way (read-only) communication; email, news portals
3. **Internet of Services (Web 2.0):** Two-way communication, user-generated content, SOA; e-commerce, cloud services
4. **Internet of People:** Emphasis on human interaction through digital/social platforms
5. **Internet of Things (IoT):** Devices themselves communicate and act, with minimal human intervention

**Conclusion:** IoT is the natural final stage of Internet evolution — from connecting people, to connecting content and services, to now connecting "things."

### (c) What is IoT? Describe different architectural layers of IoT with appropriate figure. (5)

**Diagram (describe in words):** Draw 5 stacked horizontal boxes bottom-to-top: **Perception → Network → Middleware → Application → Business**, with arrows showing data flowing upward.

| Layer | Function |
|---|---|
| **Perception Layer** | First layer; sensors/actuators gather data (temperature, motion, sound, etc.) from surroundings |
| **Network Layer** | Connects perception & middleware layers; transfers data securely via 3G/4G/WiFi/infrared |
| **Middleware Layer** | Provides storage, computation, processing, decision-making on the data set |
| **Application Layer** | Manages application processes — email alerts, alarms, smart agriculture, smart watch control |
| **Business Layer** | Handles overall management: flowcharts, graphs, analysis of results, and improving the device/business model |

**Conclusion:** This 5-layer model shows how raw sensor data is progressively transformed into meaningful business decisions.

---

## Question 3 (12 marks)

### (a) What is Transducer? Classify types of sensors based on power requirements. (4)

**Definition**
A **Transducer** is a device that converts one form of energy into another — e.g., converting a physical quantity like sound, pressure, or temperature into an electrical signal for measurement or processing.

| Type | Description | Example |
|---|---|---|
| **Active Sensors** | Do not need an external energy source; directly generate an electric signal in response to the stimulus | Thermocouple, Photodiode, Piezoelectric sensor |
| **Passive Sensors** | Require an external power supply (excitation signal); modify the excitation signal to produce output | Strain gauge |

### (b) What is MQTT? Describe the communication mechanism of MQTT. (5)

**Definition**
**MQTT (Message Queuing Telemetry Transport)** is a lightweight, publish-subscribe based messaging protocol used with TCP/IP, designed for IoT environments with limited bandwidth and small code footprint — unlike HTTP, which needs more bandwidth and processing power.

**Components:** Publishers (lightweight sensors), Subscribers (applications interested in sensor data), Broker (connects publishers and subscribers, classifies data into topics).

**Communication Mechanism**
- Uses a **publish/subscribe architecture** (unlike HTTP's request/response model)
- It is **event-driven**, pushing messages to clients
- The **MQTT broker** is the central point that dispatches messages between senders and rightful receivers
- Each publisher attaches a **topic** to its message — this is the routing information
- Each subscriber registers interest in a topic; the broker delivers matching messages
- Publishers and subscribers **never need to know each other directly** — they only interact through the topic
- This makes MQTT highly scalable with no dependency between data producers and consumers

**Conclusion:** MQTT's broker-based publish/subscribe design makes it ideal for resource-constrained IoT devices needing efficient, decoupled communication.

### (c) What is Raspberry Pi? State the features of Raspberry Pi. (3)

**Definition**
The **Raspberry Pi** is a series of small, low-cost single-board computers developed by the Raspberry Pi Foundation (UK) originally to promote teaching of computer science, but now widely used in robotics and IoT prototyping.

**Key Features**
- Small footprint (~9×6 cm), inexpensive (~$35+)
- Can connect to a monitor, keyboard, and mouse like a full computer
- Has **GPIO pins** (General Purpose Input/Output) for connecting sensors, LEDs, and other components
- Uses a Broadcom SoC with ARM-compatible CPU and GPU (CPU speed 700 MHz – 1.2 GHz+, RAM 256 MB – 1 GB+)
- Storage via microSD card (acts as the "hard drive")
- Has USB ports, HDMI, Ethernet, and on some models Wi-Fi/Bluetooth
- Suited for prototyping, datalogging, media centers, and learning programming

---

## Question 4 (12 marks)

### (a) What is CoAP? Briefly explain the architecture of CoAP. (6)

**Definition**
**CoAP (Constrained Application Protocol)** is an application-layer protocol designed by the IETF CoRE working group to provide a lightweight RESTful (HTTP-like) interface for constrained nodes and networks, commonly used in M2M applications like smart energy and building automation.

**Key Characteristics**
- Based on a **Request-Response** model between end-points
- Built over **UDP** (not TCP as HTTP typically uses), with a lightweight reliability mechanism
- Designed to let low-power sensors use RESTful services within their power constraints

**Architecture — Two Sub-layers**
1. **Messaging Sub-layer** — handles reliability and de-duplication of messages
2. **Request/Response Sub-layer** — handles the actual client-server communication

**Four Messaging Modes:** Confirmable (reliable), Non-confirmable (unreliable), Piggyback (server responds directly within the acknowledgment), Separate (response comes later, in a separate message).

CoAP uses **GET, PUT, PUSH, DELETE** methods (like HTTP) to retrieve, create, update, and delete resources.

**Conclusion:** CoAP's lightweight, UDP-based, two-layer design makes it well suited for resource-constrained IoT devices needing RESTful interaction with minimal overhead.

### (b) What is Green IoT? How does Green IoT contribute to sustainability? (3)

**Definition**
**Green IoT** refers to the design and implementation of IoT systems that minimize environmental impact through energy-efficient technologies and sustainable practices.

**Contribution to Sustainability**
- Reduces power consumption via low-power sensors and optimized communication protocols
- Minimizes carbon footprint by lowering greenhouse gas emissions from data centers and networks
- Promotes efficient resource utilization — smart management of energy, bandwidth, and storage
- Promotes renewable energy — e.g., solar-powered or energy-harvesting IoT nodes
- Reduces electronic waste — through recyclable, long-life IoT devices

### (c) What are key components of Green IoT? (2)

1. **Green Device Layer** — low-power sensors, energy-efficient processors, sleep-mode devices
2. **Green Network Layer** — energy-efficient protocols (ZigBee, BLE, LoRaWAN)
3. **Green Computing Layer** — edge computing, cloud optimization, energy-aware scheduling
4. **Green Application Layer** — applications for smart energy, smart transportation, smart agriculture

---

## Question 5 (12 marks)

### (a) What is cloud computing? Explain different types of clouds. (4)

**Definition**
**Cloud computing** is a style of computing in which dynamically scalable, often virtualized resources (computation, storage, applications) are provided as a service over the Internet, offering cost savings, high availability, and easy scalability.

| Type | Description | Example |
|---|---|---|
| **Public Cloud** | Resources dynamically provisioned over the Internet by a third-party provider; shared among multiple customers | Google Workspace, AWS, Microsoft 365/Azure |
| **Private Cloud** | Built on private networks for exclusive use by one client — full control over data, security, QoS | Amazon VPC, VMware, IBM |
| **Hybrid Cloud** | Combines public and private cloud models; adds complexity of distributing applications across both | Netflix, Hulu, Uber, Airbnb |
| **Community Cloud** | Infrastructure shared among organizations with common data/management concerns | Government cloud for a single country |

### (b) Describe the security vulnerabilities in Cloud computing. (4)

- Taking virtual machines with critical applications/sensitive data into **public, shared cloud environments** raises risk
- Users worry whether they retain the **same security policy control** over their applications/services in the cloud
- Difficult to prove to auditors that the system remains **compliant and secure**
- Traditional network-perimeter security (physical segmentation, hardware firewalls) **cannot protect against attacks between co-located VMs**
- Cloud servers run the **same OS and applications** as local systems, so attackers can remotely exploit known vulnerabilities
- **Co-location of multiple VMs** on shared hardware increases the attack surface
- Mitigation requires deploying security mechanisms *inside* the virtual environment itself — firewalls, intrusion detection/prevention, integrity monitoring, log inspection

**Conclusion:** Because cloud infrastructure is multi-tenant and shared, security must be built into the virtual layer itself, not just the physical perimeter.

### (c) Explain different applications of Mobile Cloud Computing. (4)

**Definition**
**Mobile Cloud Computing (MCC)** moves data storage and processing away from resource-limited mobile devices into powerful, centralized cloud platforms, accessed over a wireless connection via a thin client.

| Application | Description |
|---|---|
| **Mobile Commerce (M-commerce)** | Business/shopping/advertising/financial services via mobile devices; cloud addresses bandwidth, complexity, and security challenges |
| **Mobile Learning (M-learning)** | Combines e-learning with mobility; cloud overcomes cost, bandwidth, and limited-resource issues of traditional m-learning |
| **Mobile Healthcare (M-healthcare)** | On-demand access to medical records, health monitoring, emergency management, and health-aware devices (pulse, BP, alcohol level) |
| **Mobile Gaming (M-gaming)** | Offloads heavy computation (e.g., graphics rendering) to the cloud, saving device energy and enabling longer play sessions |

**Conclusion:** MCC extends the limited computing power of mobile devices, enabling resource-heavy applications to run smoothly by leveraging the cloud.

---

## Question 6 (12 marks)

### (a) What is virtualization? How does virtualization support Future Internet? (6)

> *Not fully covered in provided slides beyond GENI's context — supplemented with standard computing knowledge.*

**Definition**
**Virtualization** is the technology that creates a virtual (rather than physical) version of a resource — such as a server, storage device, or network — allowing multiple isolated virtual instances to run on shared physical hardware.

**How Virtualization Supports the Future Internet**
- **Virtualize network resources** and provide customer-specific, isolated services on shared physical infrastructure
- Enables **multiple heterogeneous network architectures** to coexist and be tested simultaneously on the same physical substrate (as used in testbeds like GENI)
- Supports the **AKARI sub-architecture goal** of connecting heterogeneous networks through virtualization
- Provides **flexibility and extensibility**, letting researchers experiment with new protocols/architectures without disrupting the production Internet
- Improves **resource utilization, scalability, and cost-effectiveness** — key design goals of Future Internet architecture

**General Explanation:** A **hypervisor (Virtual Machine Monitor)** sits between physical hardware and virtual machines, allocating CPU, memory, storage, and network resources to each VM, keeping them isolated from one another while sharing the same underlying hardware.

**Conclusion:** Virtualization is a foundational enabling technology for the Future Internet, allowing flexible experimentation, isolation, and efficient sharing of network infrastructure.

### (b) When do we need Paravirtualization? Describe the Xen-paravirtualization architecture. (3)

> *Not covered in provided slides — standard academic knowledge.*

**When Needed:** Paravirtualization is used when we want near-native performance with lower hypervisor overhead than full virtualization, and when the guest OS can be modified to be "virtualization-aware" (e.g., open-source OS like Linux).

**Xen Paravirtualization Architecture**
- Xen hypervisor runs directly on hardware (**Type-1 hypervisor**)
- **Domain 0 (Dom0):** a privileged, first-booted VM with direct hardware access; manages other VMs and device drivers
- **Domain U (DomU):** unprivileged guest VMs whose OS kernels are modified to make **hypercalls** to Xen instead of executing privileged instructions directly
- Guest OS is aware it is virtualized, so it cooperates with the hypervisor for CPU scheduling, memory management, and I/O — avoiding the overhead of binary translation used in full virtualization

**Conclusion:** Paravirtualization trades OS modification for better performance, suitable where near-native speed matters more than running unmodified guest OSes.

### (c) Advantages of using containers rather than virtual machines. (3)

> *Not covered in provided slides — standard academic knowledge.*

- **Lightweight** — containers share the host OS kernel, so no separate guest OS is needed (unlike VMs)
- **Faster startup** — containers start in seconds vs. minutes for VMs
- **Higher density** — many more containers than VMs can run on the same hardware
- **Lower resource overhead** — less CPU/RAM consumed since there's no duplicate OS layer
- **Portability** — containers package the application with its dependencies, ensuring consistent behavior across environments

---

## Question 7 (12 marks)

### (a) Describe different application areas of IIoT in industrial manufacturing process. (3)

**Definition**
**IIoT (Industrial IoT)** is the application of IoT in industrial settings — a complete ecosystem using big data, AI, and ML to connect industrial machines for predictive maintenance and process optimization.

**Application Areas**
- **SMART Inventory Management** — sensors detect container capacity/stock levels, trigger reordering, prevent overflow/shortages
- **SMART Quality Control** — RFID-tagged products identify defects on the production line in real time
- **Predictive Maintenance** — real-time sensor data predicts machine defects before failure
- **Facility Management** — environmental sensors monitor vibration, temperature, humidity for equipment wear
- **Just-in-Time Manufacturing** — real-time data adjusts production processes to reduce waste
- **Remote Asset Monitoring & Control** — centralized monitoring of geographically distributed machines

### (b) What is FOG computing? Describe the FOG Computing architecture. (5)

> *Not covered in provided slides — standard academic knowledge.*

**Definition**
**Fog Computing** is a decentralized computing infrastructure that extends cloud computing capabilities to the edge of the network, placing processing, storage, and networking services closer to where data is generated (IoT devices), reducing latency and bandwidth use compared to sending all data to a distant cloud.

**FOG Computing Architecture (Layered)**
1. **IoT/Device Layer** — sensors, actuators, and end devices generating raw data
2. **Fog Layer** — a network of fog nodes (gateways, routers, edge servers) that perform local data filtering, aggregation, real-time analytics, and short-term storage close to the devices
3. **Cloud Layer** — receives only processed/aggregated data from the fog layer for long-term storage, deep analytics, and global visibility

**Key Functions of Fog Nodes:** Local data pre-processing to reduce data sent to the cloud, low-latency real-time decision-making, temporary storage and local networking between devices.

**Conclusion:** FOG computing acts as an intermediate layer between IoT devices and the cloud, providing faster response times and reduced network load for latency-sensitive IoT applications.

### (c) Describe the IoT data processing mechanism in Edge Computing. (4)

> *Not covered in provided slides — standard academic knowledge.*

**Definition**
**Edge Computing** processes IoT data directly at or very near the source (the "edge" device itself), rather than sending it to a centralized cloud.

**Data Processing Mechanism**
1. **Data Generation** — IoT sensors/devices continuously generate raw data
2. **Local Processing at the Edge** — an edge device or gateway immediately filters, cleans, and analyzes the data on-site
3. **Real-time Decision Making** — time-critical actions (e.g., alarms, machine shutdowns) are triggered instantly at the edge, without waiting for round-trip cloud communication
4. **Selective Data Transmission** — only relevant, summarized, or exceptional data is forwarded to the cloud for storage or deeper analysis, reducing bandwidth usage
5. **Feedback/Control Loop** — processed insights can be sent back to actuators at the edge to control physical devices

**Conclusion:** By processing data as close as possible to its source, Edge Computing minimizes latency, saves bandwidth, and enables real-time responsiveness — critical for time-sensitive IoT applications like autonomous vehicles, healthcare monitoring, and industrial automation.

---
---

# 16th Batch — Final Examination Winter-2024

## Question 1 (12 marks)

### (a) What is Future Internet? State the challenges of the current Internet.
Future Internet = rethinking the fundamental design of today's Internet (via evolutionary or clean-slate approach) to overcome its limitations. **Challenges:** Security (lack of trust/protection), Mobility (poor support for mobile apps), Reliability & Availability (seamless service expectations vs. real outages), Problem analysis (limited debugging tools), Scalability (routing system limits), Quality of Service (no clear integration path), Economics (profitability for ISPs/operators).

### (b) What is the Clean Slate approach? Justify its usage.
Clean Slate = a **revolutionary approach** — redesigning the Internet's architecture completely from scratch (rather than incremental patches) to offer new abstractions/performance while keeping similar functionality, built on new core principles.

*Justification:* After 30+ years of incremental (evolutionary) improvements, the current architecture has reached a point where people are unwilling/unable to experiment further on it — security, mobility, and scalability demands now require a fresh foundation rather than more patches.

### (c) State the Network Neutrality principle. How does it offer higher adoption?
**Principle:** ISPs must treat all Internet communications equally — they may not intentionally block, slow down, or charge extra for specific online content/applications.

**Higher adoption:** Without neutrality, ISPs (telcos) could levy surcharges based on application/company, discriminating in managing packet flow. Net neutrality prevents this, so growth in functionality/value of the net (and therefore broader, more affordable access) is not delayed by discriminatory practices — encouraging more users and content providers to join.

---

## Question 2 (12 marks)

### (a) What is IoT? Explain the working principle of IoT.
**Definition:** IoT is a network of physical objects embedded with sensors, software, and connectivity, enabling data collection/exchange with minimal human intervention.

**Working Principle (4 stages):**
1. **Sensors/Devices** — collect live data from the environment (simple readings to complex video feeds)
2. **Connectivity** — sensors send data to the cloud via Wi-Fi, Bluetooth, mobile/satellite networks, WAN
3. **Data Processing** — cloud software processes the gathered data (simple checks to complex computer-vision analysis)
4. **User Interface** — results are delivered to the end-user via app alerts, notifications, or an active dashboard/web interface

### (b) Working procedure of IoT-based SMART Inventory management system.
- RFID tags/barcodes identify products
- Sensors/RFID readers collect stock information (weight sensors monitor quantity, environmental sensors monitor conditions)
- Data is processed by the microcontroller (Arduino/ESP32/Raspberry Pi)
- Information is uploaded to a cloud database (Firebase/AWS IoT/MySQL)
- Inventory levels update automatically
- Alerts are generated for low stock or abnormal conditions, and orders can be auto-placed with suppliers

### (c) The most visible drawback of IoT is its security — do you agree? Justify.
Agree. Justification:
- As connected devices increase, the risk of a hacker stealing confidential data rises
- Millions of devices are difficult to monitor/manage collectively
- A single bug can corrupt every connected device in the network
- No international compatibility standard makes secure interoperability between manufacturers difficult
- Security thus remains the most cited and visible weakness limiting trust in IoT deployment, alongside challenges like privacy, data volume, and interoperability.

---

## Question 3 (12 marks)

### (a) What is a Microcontroller? Difference between computer, microprocessor, microcontroller.
**Microcontroller:** A compact integrated circuit on a single chip containing a processor, memory, and I/O, usually embedded inside a device; small and low-cost.

| Term | Description |
|---|---|
| **Microprocessor** | A full computation engine on a single chip; acts as the CPU only |
| **Computer** | A microprocessor packaged on a circuit board with many interfaces and memory chips; designed for general-purpose human interaction |
| **Microcontroller** | CPU + memory + I/O all integrated on one chip; designed to interface with electrical devices, sensors/actuators, and gadgets |

### (b) What is a Sensor? State the qualities of a Sensor.
**Sensor:** A device that converts a physical event/characteristic (e.g., temperature) into an electrical signal for a system to process.

**Qualities:**
- **Range** — min/max value it can measure
- **Span** — difference between max and min input
- **Accuracy** — closeness of measured value to actual value
- **Precision** — ability to reproduce readings within a given deviation
- **Linearity** — max deviation from an ideal straight-line curve
- **Hysteresis** — output difference when input is increased vs decreased
- **Resolution** — minimum change in input the sensor can detect
- **Reproducibility & Repeatability** — consistency of output for the same input
- **Response Time** — time to reach a defined % of final output value

### (c) What is Arduino? Compare Arduino and Raspberry Pi.
**Arduino:** An open-source electronics platform (microcontroller board + IDE) that senses the environment via input from sensors, processes it, and produces outputs; used to build interactive objects.

| Feature | Arduino | Raspberry Pi |
|---|---|---|
| Type | Microcontroller board | Single-board computer |
| OS | No OS (runs single program) | Runs a full OS (e.g., Linux) |
| Processing | Simple, real-time control tasks | Multitasking, computation-heavy tasks |
| Clock Speed | ~16 MHz (Uno) | ~1.2 GHz+ (Pi 3) |
| Cost | Cheaper (~1100 BDT) | More expensive (~5000 BDT) |
| Use case | Sensor/actuator control | Complex applications, media, networking |

---

## Question 4 (12 marks)

### (a) Purpose of an Ultrasonic Sensor + fuel amount calculation.
**Purpose:** An Ultrasonic Sensor measures the distance to an object by transmitting a sound pulse and measuring the time taken for its echo to return (using speed of sound ≈ 340 m/s), e.g., HC-SR04 module.

**Fuel-amount calculation process:**
1. Mount the ultrasonic sensor at the top of the fuel tank, facing down toward the fuel surface
2. The sensor emits a pulse; it travels down, reflects off the fuel surface, and returns as an echo
3. Measure the time-of-flight (t) of the echo
4. Calculate distance from sensor to fuel surface: **Distance = (Speed of sound × t) / 2** (divided by 2 because the pulse travels to the surface and back)
5. Subtract this distance from the known tank height to get the **fuel level (height)**
6. Convert fuel level to volume using the tank's known cross-sectional geometry (Volume = level × cross-sectional area, for a regular tank shape)

### (b) Using an Ultrasonic Sensor to identify fuel theft.
- The sensor continuously monitors and logs the fuel level at regular intervals
- A sudden, rapid drop in fuel level while the vehicle is stationary (engine off, not consistent with normal consumption/engine-running patterns) is flagged as anomalous
- The system (via microcontroller + GPS/GSM module) sends a real-time alert/SMS to the vehicle owner or fleet manager when such an abnormal drop is detected
- Historical level-vs-time data helps distinguish genuine refueling/consumption from theft/siphoning events

### (c) What is aquaponics? Design an IoT-based water quality monitoring architecture.
> *Not covered in provided slides — answered using general IoT-architecture principles.*

**Aquaponics:** A sustainable farming system combining aquaculture (raising fish) with hydroponics (growing plants without soil), where fish waste provides nutrients for plants, and plants help filter/purify the water for the fish.

**IoT-based Water Quality Monitoring Architecture (Layers):**
- **Perception Layer:** pH sensors, dissolved-oxygen sensors, turbidity sensors, temperature sensors, water-level sensors placed in fish tanks/grow beds
- **Network Layer:** Wi-Fi/Zigbee/LoRaWAN transmits sensor readings to a gateway/microcontroller (Arduino/ESP32)
- **Middleware/Processing Layer:** Cloud platform (e.g., Firebase/ThingSpeak) stores data, computes averages/trends, and applies threshold-based decision logic
- **Application Layer:** Mobile app/dashboard alerts the farmer if pH, oxygen, or temperature moves outside safe ranges; can auto-trigger aerators, water pumps, or feeders
- **Business Layer:** Analyzes long-term data to optimize fish stocking density, feeding schedules, and crop yield

---

## Question 5 (12 marks)

> *Bitcoin and Blockchain are not covered in the provided lecture slides. Answered from standard technical knowledge.*

### (a) How do Bitcoin transactions work?
- A user initiates a transaction using their **private key** to digitally sign it, specifying sender's address, receiver's address, and the amount
- The transaction is broadcast to the peer-to-peer Bitcoin network
- **Miners** collect pending transactions into a block and compete to solve a cryptographic puzzle (Proof-of-Work)
- Once solved, the block is added to the **blockchain** (a public, distributed ledger), and the transaction is considered confirmed
- Each subsequent block added further "confirms" the transaction, making it progressively harder to reverse
- The receiver's wallet balance updates once the transaction is confirmed on the chain

### (b) Different Bitcoin applications.
- **Peer-to-peer payments** — direct value transfer without banks
- **Remittances** — cheaper cross-border money transfer
- **Investment/store of value** — held as a digital asset
- **Micropayments** — small online payments (tipping, content access)
- **Smart contract platforms (extended use)** — programmable value transfer
- **E-commerce payments** — accepted by some online merchants

### (c) Limitations of Blockchain. How can they be overcome?

| Limitation | Possible Solution |
|---|---|
| **Scalability** (limited transactions/second) | Layer-2 solutions (e.g., Lightning Network), sharding |
| **High energy consumption** (Proof-of-Work mining) | Switch to Proof-of-Stake or other energy-efficient consensus |
| **Slow transaction confirmation** | Off-chain processing, faster consensus algorithms |
| **Storage growth** (ever-growing ledger) | Pruning, sidechains |
| **Irreversibility of errors** | Multi-signature wallets, careful verification processes |
| **Regulatory uncertainty** | Clearer government/legal frameworks |

---

## Question 6 (12 marks)

> *SDN topics are not covered in the provided lecture slides. Answered from standard networking knowledge.*

### (a) How does the control plane of SDN communicate with the data forwarding plane?
- In **Software-Defined Networking (SDN)**, the control plane (SDN controller) is logically centralized and separated from the data plane (switches/routers that forward packets)
- Communication happens via a **southbound API**, most commonly the **OpenFlow protocol**
- The controller pushes **flow rules** (match-action entries) down to switches, instructing them how to handle specific types of packets
- Switches send events (e.g., new/unmatched packet arrival, link status changes) up to the controller, which then computes and installs the appropriate forwarding rule

### (b) What is Type of Service (ToS)? What is the role of ToS?
**ToS** is an 8-bit field in the IPv4 header used to specify the desired **quality of service** for a packet (e.g., priority, delay, throughput, reliability requirements).

**Role:** It allows routers to make differentiated forwarding decisions — e.g., giving voice/video traffic lower delay priority over bulk file transfers — supporting QoS-aware traffic management across the network.

### (c) What is OpenFlow? How does SDN install a route on the OpenFlow switch?
**OpenFlow** is a standardized southbound communication protocol that allows an SDN controller to directly interact with the forwarding plane of network switches/routers, enabling programmable packet forwarding.

**Route installation process:**
1. A switch receives a packet with no matching flow entry in its flow table
2. It sends a "packet-in" message to the SDN controller
3. The controller computes the appropriate path/action based on its network view and policies
4. The controller sends a "flow-mod" message, installing a new flow entry (match + action, e.g., forward to port X) into the switch's flow table
5. Subsequent packets matching that flow are forwarded directly by the switch without contacting the controller again

---

## Question 7 (12 marks)

### (a) What is FOG computing? State its necessity in IoT data processing.
**FOG computing** extends cloud capabilities to the network edge via a layer of fog nodes (gateways/local servers) that process data closer to IoT devices.

> *Not directly covered in provided slides — standard knowledge.*

**Necessity:**
- IoT generates huge volumes of data continuously; sending all of it to a distant cloud causes high latency and bandwidth strain
- Many IoT applications (industrial safety, healthcare alerts, traffic control) need **real-time, low-latency responses** that a round trip to the cloud cannot guarantee
- FOG nodes filter and pre-process data locally, sending only summarized/critical data to the cloud, saving bandwidth and enabling faster local decisions

### (b) Architectural layers of Edge Computing with figure.
> *Not directly covered in provided slides — standard knowledge.*

**Diagram (describe in words):** Three stacked layers bottom-to-top: **Device/Edge Layer → Edge/Fog Layer → Cloud Layer**, with bidirectional arrows for data flow up and control commands down.

| Layer | Function |
|---|---|
| **Device Layer** | IoT sensors/actuators generate raw data at the source |
| **Edge Layer** | Local edge servers/gateways perform real-time filtering, analytics, and immediate decision-making close to devices |
| **Cloud Layer** | Receives aggregated/processed data for long-term storage, deep analytics, and global coordination |

### (c) Role of Edge computing in healthcare.
- Enables **real-time patient monitoring** (heart rate, SpO₂, ECG) with immediate local alerts, without waiting on cloud round-trips
- Reduces latency for **critical/emergency responses** (e.g., detecting abnormal vitals instantly)
- Preserves **patient data privacy** by processing sensitive data locally before sending only necessary summaries to the cloud
- Reduces bandwidth load from continuous wearable/ICU monitoring devices
- Supports **remote/telemedicine** applications with faster local response even with limited connectivity

---
---

# 15th Batch — Final Examination Summer-2023

## Question 1 (12 marks)

### (a) What is future internet? What are the challenges for future internet?
Future Internet resolves current Internet's limits via evolutionary/clean-slate redesign. Challenges: Security, Mobility, Reliability & Availability, Problem analysis, Scalability, Quality of Service, Economics.

### (b) What is GENI? State and explain the architecture of future internet.
**Definition:** GENI (Global Environment for Network Innovations) is a nationwide programmable experimental facility, initiated by the NSF CISE Directorate (launched August 2005), used to validate Future Internet research at scale under realistic conditions.

**Components:**
- **GENI research program** — supports long-term basic research/experimentation in networking
- **GENI research facility** — a global experimental facility fostering exploration of new network architectures at scale

**GENI Architecture:**
- **Control Plane** — used to discover, reserve, access, program, and manage GENI's compute/communication resources; runs over the regular Internet
- **Data Plane** — set up on demand per experiment, according to the experimenter's specified topology, bandwidth, and programmable switches/controllers; runs over the GENI backbone (Internet2, regional R&E networks, GENI racks)

**Key Features:** Slicing via VLANs (traffic isolation between experiments), deep programmability (OpenFlow-capable switches), and network federation/stitching (coordination across multiple resource providers).

### (c) What do you mean by virtualization? Differ various types of virtualization.
> *Standard knowledge supplement.*

**Virtualization:** Creating a virtual version of a physical resource (server, storage, network) so multiple isolated instances can share the same hardware.

| Type | Description |
|---|---|
| **Full Virtualization** | Complete emulation of hardware; unmodified guest OS runs unaware it's virtualized (uses binary translation) |
| **Paravirtualization** | Guest OS is modified to be aware of virtualization; communicates directly with hypervisor via hypercalls for better performance |
| **OS-level Virtualization (Containers)** | Multiple isolated user-space instances (containers) share a single host OS kernel |
| **Hardware-assisted Virtualization** | Uses CPU-level virtualization extensions (Intel VT-x/AMD-V) to run unmodified guest OS efficiently |

---

## Question 2 (12 marks)

### (a) What is M2M communication? Describe the key elements of M2M communication.
**Definition:** Machine-to-Machine (M2M) communication is direct communication between devices over a wired/wireless channel, enabling networked devices to exchange information and perform actions without manual human assistance (e.g., a smart thermostat adjusting temperature based on location/weather data).

**Key Elements:**
- Field-deployed wireless devices with **embedded sensors**
- **RFID** tags for identification
- A **cellular or Wi-Fi communication link**
- **Autonomous computing software** that interprets data and makes decisions, translating data into pre-programmed automated actions

**M2M Architecture (3 domains):** M2M area network (device) domain, M2M service platform domain, and user/administrator domain — connected via a gateway or direct WAN link.

### (b) Working procedure of IoT-based SMART Inventory management system.
Same procedure as detailed under **16th Batch, Q2(b)** above.

### (c) What is IIoT? Explain the benefit of IIoT in manufacturing process.
**IIoT (Industrial IoT):** The application of IoT in industrial settings — a full ecosystem using big data, AI, and ML to connect industrial machines/devices for predictive maintenance and process optimization; focused on cyber-physical systems monitoring physical factory processes.

**Benefits in Manufacturing:**
- **Increased machine utilization** — real-time insight into machine health/KPIs
- **Predictive maintenance** — predicts defects before failure, reducing downtime
- **Asset tracking** — tracks products through the supply chain
- **Facility management** — monitors vibration, temperature, humidity conditions
- **Just-in-Time manufacturing** — real-time adjustment to eliminate waste
- **Remote asset monitoring** — centralized control of distributed machines
- **Easier interfaces (HMIs)** — intuitive monitoring for operators
- **Knowledge sharing** across plants, and **process/behavior monitoring** for performance insight

---

## Question 3 (12 marks)

### (a) State the challenges of IoT.
Constant Power (limited battery life), Data Volume (huge data generation), Privacy, Interoperability (no common standard), Security, Quality of Service, Data Encryption & Key Management, Network Issues (traffic congestion).

### (b) What do you understand by waste management? State the necessity of a smart waste management system.
**Waste management:** The systematic collection, transportation, processing, and disposal of waste materials generated by households, industries, or municipalities.

**Necessity of a Smart Waste Management System:**
- Traditional waste collection follows fixed schedules regardless of actual bin fill levels, wasting fuel and manpower
- Overflowing bins cause hygiene, odor, and environmental problems in cities
- A smart system enables **real-time monitoring of fill levels**, so collection trucks are dispatched only when needed, along **optimized routes** — reducing operational cost, fuel consumption, and improving cleanliness in smart cities

### (c) Describe the waste collection procedure of a Smart Waste Management system with a flowchart.

**Flowchart (describe in words):**
`Start → Sensor detects garbage/fill level → Data sent to microcontroller → Data uploaded to cloud → Is bin level ≥ threshold? → [No: continue monitoring] → [Yes: generate alert] → Optimized route sent to collection vehicle → Waste collected → Municipal authority dashboard updated → End`

**Steps:**
1. Ultrasonic/level sensors inside bins continuously monitor garbage level
2. Data is transmitted to a microcontroller (Arduino/ESP32/Raspberry Pi)
3. Information is uploaded to a cloud platform (ThingSpeak/Firebase/AWS IoT)
4. If the bin exceeds the threshold fill level, an alert is generated
5. Waste collection vehicles receive optimized routes to bins needing collection
6. Municipal authority monitors all bins remotely via a dashboard/mobile app

---

## Question 4 (12 marks)

### (a) What is Cloud Computing? Describe different types of services offered.
**Definition:** Dynamically scalable, often virtualized resources provided as a service over the Internet.

| Service | Description |
|---|---|
| **IaaS (Infrastructure-as-a-Service)** | Outsourced computing resources — storage, hardware, servers, networking components |
| **PaaS (Platform-as-a-Service)** | A platform (OS, runtime, tools) for developing/deploying applications without managing underlying infrastructure |
| **SaaS (Software-as-a-Service)** | Ready-to-use software applications delivered over the Internet (e.g., Google Docs, Office 365) |

### (b) What is MCC? Describe the MCC architecture with figure.
**Definition:** Mobile Cloud Computing moves data storage/processing away from mobile devices into powerful centralized cloud platforms, accessed wirelessly via a thin client.

**Diagram (describe in words):** Mobile devices ↔ Base stations ↔ Central processors/Mobile network operators (authentication/authorization/accounting) ↔ Internet ↔ Cloud controllers ↔ Cloud services (web/app/database servers, using virtualization + SOA).

**Architecture description:**
- Mobile devices connect to mobile networks through base stations
- Requests are sent to central processors linked to servers providing mobile network services (auth, authorization, accounting)
- Requests are delivered to the cloud via the Internet
- Cloud controllers process requests and provide corresponding services, built using utility computing, virtualization, and SOA concepts

### (c) What are the challenges of Mobile Cloud Computing?
Low bandwidth, Security and Privacy, Service Availability, Alteration of Networks and Platforms, Limited Energy source (battery constraints on mobile devices).

---

## Question 5 (12 marks)

### (a) What is FOG computing? Describe the FOG Computing architecture.
Same as detailed under **17th Batch, Q7(b)** above.

### (b) Describe the IoT data processing mechanism in Edge Computing.
Same as detailed under **17th Batch, Q7(c)** above.

### (c) Describe the difference between FOG computing and Edge computing.

| Aspect | Fog Computing | Edge Computing |
|---|---|---|
| Processing location | Intermediate layer — fog nodes/gateways between devices and cloud | Directly at or very near the device itself |
| Architecture | Hierarchical, network-wide layer coordinating multiple edge devices | Localized, device-level processing |
| Latency | Low, but slightly higher than pure edge | Lowest — near-instant local processing |
| Scope | Can manage/aggregate data from many edge devices across a wider area | Typically limited to a single device or very local cluster |
| Example use | Aggregating factory-floor sensor data before sending to the cloud | A smart camera processing video locally in real time |

---

## Question 6 (12 marks)

### (a) What is a sensor? Explain the usage of Light Detection and Proximity Sensor.
**Sensor:** Converts physical events into electrical signals.

- **Light Detection Sensor (LDR — Light Dependent Resistor):** Its resistance is inversely proportional to ambient light intensity — resistance decreases as light increases, and vice versa. Used in automatic street lighting, light-based day/night detection, and photo sensors.
- **Proximity Sensor:** Detects the presence or absence of a nearby object without physical contact. Used for process monitoring, object counting, and checking availability of free spaces — e.g., parking spaces, seating in stadiums, malls, and airports.

### (b) Describe the parameters used to measure Indoor Air Quality (IAQ).
> *General IAQ parameters, aligned with the pollution/environmental sensors covered in your slides.*
- **CO₂ level** — indicates ventilation adequacy
- **Carbon monoxide / toxic gas levels** — detected via gas sensors (e.g., MQ-2, MQ-135)
- **Temperature** — comfort and air quality indicator
- **Humidity** — affects mold growth and air comfort
- **Particulate Matter (PM2.5/PM10)** — dust/smoke particles
- **VOC (Volatile Organic Compounds)** — chemical pollutants from furniture, paints, cleaning agents

### (c) Purpose of various sensors used for measuring IAQ.
- **Gas sensors (MQ-2, MQ-135)** — detect smoke, carbon monoxide, and toxic gases affecting breathability
- **Temperature & humidity sensors** — monitor environmental comfort/conditions that affect air quality perception
- **Dust/particulate sensors** — measure suspended particles harmful to respiratory health
- **CO₂ sensors** — indicate whether a space is adequately ventilated

Together, these sensors allow an IoT system to continuously assess whether indoor air is safe and trigger alerts or automated ventilation/purification if thresholds are exceeded.

---

## Question 7 (12 marks)

> *Docker is not covered in the provided lecture slides. Answered from standard technical knowledge.*

### (a) What do you mean by docker? State docker vs virtual machine with example.
**Docker:** A platform that uses OS-level virtualization (containerization) to package applications with all their dependencies into lightweight, portable **containers** that share the host OS kernel.

| Docker (Containers) | Virtual Machine |
|---|---|
| Shares host OS kernel | Runs a full separate guest OS |
| Lightweight (MBs), starts in seconds | Heavyweight (GBs), takes minutes to boot |
| Example: running a Node.js app in a Docker container | Example: running a full Windows Server VM on VMware/Hyper-V |
| Higher density on same hardware | Lower density due to OS overhead |

### (b) Why docker? How to run docker for light virtualization?
**Why Docker:**
- Faster startup and deployment
- Consistent environment across development, testing, and production ("works on my machine" problem solved)
- Efficient resource usage — many containers on one host
- Easy scaling and microservices support

**Running Docker (light virtualization) — general steps:**
1. Install the Docker Engine on the host OS
2. Write a **Dockerfile** specifying the application, dependencies, and base image
3. Build a Docker **image** from the Dockerfile (`docker build`)
4. Run a **container** from that image (`docker run`), which shares the host kernel but stays isolated in its own filesystem/process namespace
5. Manage multiple containers using Docker Compose or an orchestrator (e.g., Kubernetes) if needed

### (c) What is IoT? Explain security issues in IoT with example.
**IoT:** (as defined earlier).

**Security issues:**
- **Data theft/eavesdropping** — e.g., a hacker intercepting data from an unencrypted smart camera feed
- **Device hijacking** — e.g., IoT devices recruited into botnets (like the Mirai botnet attack using compromised IoT cameras/routers)
- **Lack of standard security protocols** — many cheap IoT devices ship with weak/default passwords
- **Firmware vulnerabilities** — outdated or unpatched software exploited by attackers
- **Physical tampering** — devices deployed in accessible/unattended locations (e.g., street sensors) can be physically compromised
- **Scale of impact** — a single vulnerability can compromise millions of identical connected devices simultaneously

---
---

# 14th Batch — Final Examination Summer-2024

## Question 1 (12 marks)

### (a) What is Future Internet? State the challenges of current Internet.
Same as detailed under **16th Batch, Q1(a)** above.

### (b) What is GENI? State and explain the architecture of future internet.
Same as detailed under **15th Batch, Q1(b)** above.

### (c) What do you mean by virtualization? Differ various types of virtualization.
Same as detailed under **15th Batch, Q1(c)** above.

---

## Question 2 (12 marks)

### (a) What is IoT? Describe different architectural layers of IoT.
Same 5-layer model (Perception, Network, Middleware, Application, Business) as detailed under **17th Batch, Q2(c)** above.

### (b) The most visible drawback of IoT is its security — do you agree? Justify your answer.
Same as detailed under **16th Batch, Q2(c)** above.

### (c) What is IIoT? Describe the importance of IIoT.
**IIoT:** Application of IoT in industrial settings using big data, AI, ML for predictive maintenance and process optimization.

**Importance:**
- Increases machine utilization and uptime through real-time health monitoring
- Enables predictive maintenance, cutting unplanned downtime and repair costs
- Improves asset tracking across the supply chain
- Enables facility management via environmental condition monitoring
- Supports Just-in-Time manufacturing, reducing waste
- Enables remote monitoring/control of distributed industrial assets
- Provides easier-to-use interfaces (HMIs) for less-technical staff
- Facilitates knowledge-sharing and standardization across multiple plants

---

## Question 3 (12 marks)

### (a) Difference between Arduino and Raspberry Pi. Functionality of ESP8266.
*Arduino vs Raspberry Pi:* Same comparison table as **16th Batch, Q3(c)** above.

**ESP8266 functionality:**
- A low-cost Wi-Fi microchip/microcontroller module used to add wireless internet connectivity to IoT projects
- Commonly used (alongside Arduino/ESP32/Raspberry Pi) as the **microcontroller/processing unit** in IoT systems (smart inventory, smart parking, smart irrigation, street lighting, etc.)
- Functions: reads data from sensors, processes it, and transmits it over Wi-Fi to a cloud server or another device; can also receive commands to control actuators

### (b) Flowchart of a smart street lighting system and its functionality.

**Flowchart (describe in words):**
`Start → LDR sensor detects ambient light level → Is it dark (night)? → [No: keep lights OFF, loop back] → [Yes: check PIR motion sensor] → Motion detected? → [Yes: turn lights ON at full brightness] → [No: dim lights / keep low power mode] → Current/voltage sensor monitors power consumption/faults → Data sent to cloud server → End/Loop`

**Functionality:**
- **LDR (Light Dependent Resistor)** detects ambient light intensity to determine day/night condition
- **PIR sensor** detects motion of vehicles/pedestrians to decide whether full brightness is needed
- **Current/Voltage sensor** monitors power consumption and detects faults
- The **microcontroller** (Arduino/ESP8266/ESP32/Raspberry Pi) processes sensor data, controls the streetlights, and sends status information to the cloud server for monitoring and energy-saving analytics

### (c) Parameters used to measure Indoor Air Quality (IAQ).
Same as detailed under **15th Batch, Q6(b)** above.

---

## Question 4 (12 marks)

> *AAID and Blockchain are not covered in the provided lecture slides. Answered from general/standard knowledge.*

### (a) What is AAID? Explain the role of AAID in IoT.
**AAID** generally refers to an **Auto-generated Application ID / Advertising & Analytics ID** type of unique device/application identifier concept used to uniquely identify and authenticate devices or app instances in a networked system.

**Role in IoT:**
- Provides each IoT device/application instance a **unique identity** for tracking and management
- Supports **device authentication and authorization**, preventing unauthorized devices from joining the network
- Enables analytics platforms to track device-specific usage/behavior patterns for diagnostics and optimization
- Helps in **device lifecycle management** — provisioning, updates, and decommissioning of specific IoT units

*(Since AAID is not defined in the provided slides, confirm your instructor's exact definition/context if it differs.)*

### (b) What is blockchain? What are the fundamental parts of blockchain?
**Blockchain:** A decentralized, distributed, and immutable digital ledger that records transactions across many computers so that no single record can be altered retroactively without altering all subsequent blocks and the consensus of the network.

**Fundamental parts:**
- **Block** — a data structure holding a batch of transactions, a timestamp, and a reference (hash) to the previous block
- **Hash** — a unique cryptographic fingerprint of a block's contents, linking blocks in sequence
- **Chain** — the sequence of linked blocks forming the full ledger history
- **Distributed Ledger** — a copy of the blockchain maintained across many nodes in the network
- **Consensus Mechanism** — the protocol (e.g., Proof-of-Work, Proof-of-Stake) by which the network agrees on the valid next block
- **Nodes/Miners** — participants who validate and add new blocks to the chain

### (c) Discuss blockchain important concepts. How does blockchain work?
**Important concepts:** Decentralization, Immutability, Transparency, Consensus, Cryptographic hashing, Peer-to-peer network.

**How it works:**
1. A transaction is initiated and broadcast to the peer-to-peer network
2. Nodes validate the transaction against network rules
3. Valid transactions are grouped into a new block
4. Miners/validators compete (or are selected) to add the block through the consensus mechanism
5. Once added, the new block is linked to the previous block via its cryptographic hash
6. The updated ledger is propagated and synchronized across all nodes, making the transaction record permanent and tamper-resistant

---

## Question 5 (12 marks)

### (a) What is Code Offloading? Describe different code offloading technologies.
**Definition:** Code Offloading is the migration of computationally intensive software modules/tasks from resource-limited mobile devices to higher-end, resourceful machines (typically in the cloud), to reduce energy consumption and response time.

**Technologies/approaches:**
- **Full offloading** — the entire application/task is sent to the cloud/server for execution
- **Partial (fine-grained) offloading** — only computation-heavy modules are offloaded while lightweight parts run locally (e.g., MAUI framework enabling energy-aware fine-grained offloading)
- **Static offloading** — offloading decisions are fixed at design time
- **Dynamic offloading** — offloading decisions adapt at runtime based on network conditions, battery level, and workload

### (b) What is Mobile Device Cloud (MDC)? Situations/places where an MDC can be formed.
**MDC:** A cloud formed by pooling together the computing resources of multiple nearby mobile devices, allowing them to share processing power, storage, and battery resources collaboratively instead of relying solely on a remote cloud server.

**Situations/places:**
- University campuses or offices with many devices in close proximity
- Public transportation (buses, trains) where commuter devices can pool resources temporarily
- Disaster-recovery or remote areas lacking stable Internet/cloud connectivity
- Crowded public events (conferences, stadiums) with dense device clustering

### (c) Key challenges in MDC-based code offloading. How can an incentive-driven MDC architecture help?

**Key Challenges:**
- **Device mobility** — devices in an MDC may leave the group at any time, disrupting ongoing tasks
- **Heterogeneity** — devices vary widely in processing power, battery, and OS
- **Trust and security** — offloading code to unknown peer devices raises data privacy/security concerns
- **Limited battery of participating devices** — contributing devices also have power constraints
- **Unwillingness to share resources** — users may not want to contribute their device's battery/processing power without benefit

**Incentive-driven MDC architecture:**
- Introduces a **reward mechanism** (credits, monetary micro-payments, priority service) for devices that contribute their resources to the shared pool
- This motivates device owners to participate, addressing the "unwillingness to share" problem
- Combined with reputation/trust scoring, it can prioritize offloading to reliable, well-behaved devices — improving both participation and reliability of the MDC

---

## Question 6 (12 marks)

### (a) What is FOG computing? State the necessity of FOG computing in IoT data processing.
Same as detailed under **16th Batch, Q7(a)** above.

### (b) Explain the Edge Computing architecture.
Same 3-layer architecture (Device → Edge → Cloud) as detailed under **16th Batch, Q7(b)** above.

### (c) State the role of Edge computing in Industries.
- Enables **real-time monitoring and control** of industrial machinery without cloud round-trip delay
- Supports **predictive maintenance** by processing sensor data (vibration, temperature) locally for instant fault detection
- Reduces **bandwidth costs** by only sending summarized/critical data to central systems
- Improves **operational safety** through immediate local alerts/shutdowns in hazardous conditions
- Enables **local autonomy** — factory operations can continue even if the connection to central cloud servers is temporarily lost

---

## Question 7 (12 marks)

> *Merkle Tree and blockchain-vs-database are not covered in the provided lecture slides. Answered from standard technical knowledge.*

### (a) What is Blockchain? Describe the working procedure of a Blockchain.
**Blockchain:** (as defined in Q4(b) above — a decentralized, immutable, distributed ledger of linked blocks).

**Working procedure:** Same steps as described in **14th Batch, Q4(c)** above: transaction initiated → broadcast → validated by nodes → grouped into a block → consensus mechanism adds the block → block linked via hash to previous block → ledger synchronized across all nodes.

### (b) What is a Merkle Tree? Explain with example.
**Definition:** A Merkle Tree (hash tree) is a binary tree data structure where every leaf node is the cryptographic hash of a data block (e.g., a transaction), and every non-leaf node is the hash of its two child nodes' combined hashes, up to a single **root hash (Merkle Root)**.

**Example:**
- Suppose 4 transactions: T1, T2, T3, T4
- Compute leaf hashes: H1=hash(T1), H2=hash(T2), H3=hash(T3), H4=hash(T4)
- Combine pairs: H12=hash(H1+H2), H34=hash(H3+H4)
- Combine again: **Root = hash(H12+H34)**
- This single Root hash is stored in the block header, representing all transactions in that block

**Benefit:** Allows efficient and secure verification that a specific transaction is included in a block, without needing to download/check all transactions — only a small number of hashes along the path to the root (a "Merkle proof") are needed.

### (c) Difference between a database and a blockchain ledger.

| Aspect | Traditional Database | Blockchain Ledger |
|---|---|---|
| Control | Centralized (single authority manages/edits) | Decentralized (distributed across many nodes) |
| Mutability | Records can be updated/deleted | Immutable — once added, records cannot be altered |
| Trust model | Requires trusting the central administrator | Trustless — consensus mechanism ensures validity |
| Structure | Tables with rows/columns (CRUD operations) | Chain of cryptographically linked blocks |
| Performance | Generally faster for high transaction volume | Slower due to consensus/validation overhead |
| Transparency | Access typically restricted/private | Often fully or partially transparent to network participants |

---
---

# Winter-2023 Final Examination (Undated Batch)

## Question 1 (12 marks)

### (a) What is the Future Internet? Explain the necessity of Future Internet design.
Same as detailed under **17th Batch, Q1(a)** above.

### (b) What is Service-Oriented Architecture? Explain the SOA with appropriate figure.
**Definition:** SOA defines a layer's functions as *services* and converges these services to support network operations — services are registered, discovered in a repository, and acquired as needed.

**Diagram (describe in words):** Three boxes — **Service Provider**, **Service Registry/Repository**, **Service Requester/Client** — connected by three labeled arrows: (1) Provider **Publishes** service description to Registry, (2) Requester **Finds** the service by querying the Registry, (3) Requester **Interacts/Invokes** the service directly with the Provider (which replies/receives).

**Three SOA Roles:**
- **Service Provider** — creates a web service and publishes its description to the registry (decides what to expose, price, security vs. availability trade-offs)
- **Service Broker/Registry/Repository** — makes service information available to potential requesters
- **Service Requester/Consumer** — finds entries in the registry and binds to the provider to invoke the service

**Conclusion:** SOA enables flexible, loosely-coupled network operations by treating layer functionalities as discoverable, reusable services rather than fixed protocol stacks.

### (c) What is Virtualization? Explain with example.
**Definition:** Virtualization is the technology of creating a virtual version of a physical resource (network, server, or storage) so multiple isolated services can run on shared infrastructure.

**Example:** In GENI, network virtualization lets many researchers run independent experiments (different network topologies/protocols) simultaneously on the same shared physical substrate, each isolated by "slices" (e.g., separated by VLANs), without one experiment interfering with another.

---

## Question 2 (12 marks)

### (a) What is M2M communication? Describe the key elements of M2M communication.
Same as detailed under **15th Batch, Q2(a)** above.

### (b) What are applications of IoT? Briefly describe the IoT-based waste collection process.
**Applications of IoT:** Healthcare (patient/equipment monitoring), Smart Homes, Smart Cities, Smart Agriculture/Irrigation, Smart Parking, Smart Inventory Management, Industrial IoT (IIoT), Smart Waste Management, Smart Street Lighting, Pollution Control.

**IoT-based Waste Collection Process:**
1. Level/ultrasonic sensors inside bins continuously monitor garbage fill level
2. Data is sent to a microcontroller (Arduino/ESP32/Raspberry Pi)
3. Information is uploaded to a cloud platform (ThingSpeak/Firebase/AWS IoT)
4. If a bin exceeds the threshold fill level, an alert is generated
5. Waste collection vehicles receive optimized collection routes
6. Municipal authorities monitor all bins remotely via a dashboard/mobile app

### (c) What is a Transducer?
A **Transducer** is a device that converts one form of energy into another — such as converting a physical quantity like sound, pressure, or temperature into an electrical signal for measurement or processing.

---

## Question 3 (12 marks)

### (a) What is Computing? Explain different paradigms of computing.
> *Not explicitly covered in provided slides — standard academic knowledge, consistent with the course's Cloud/Mobile/Edge/Fog coverage.*

**Definition:** Computing is the process of using computer technology to complete a goal-oriented task — involving computation, communication, and storage of data.

**Different Paradigms:**
- **Personal/Desktop Computing** — processing done locally on an individual's device
- **Distributed Computing** — tasks are split and processed across multiple networked computers
- **Cloud Computing** — computation and storage delivered as a scalable, on-demand service over the Internet
- **Mobile Cloud Computing (MCC)** — mobile devices offload data storage/processing to the cloud
- **Fog Computing** — processing pushed to an intermediate layer (fog nodes) between devices and the cloud
- **Edge Computing** — processing performed directly at or near the data source (the device itself)
- **Grid Computing** — pooling computing resources from multiple locations to solve large problems collaboratively

### (b) What is Cloud Computing? Explain different types of cloud.
Same as detailed under **17th Batch, Q5(a)** above.

### (c) State the factors to determine the price of a cloud service.
Cloud service pricing is based on three key dimensions:
- **Storage** — measured as the average daily amount of data stored (in GB) over a monthly period
- **Bandwidth** — measured by the total amount of data transferred in/out of the platform through transactions and batch processing (data transfer *within* the same platform is often free)
- **Compute** — measured as the time units needed to run an instance, application, or machine to service requests

---

## Question 4 (12 marks)

### (a) Describe the security vulnerabilities in Cloud computing.
Same as detailed under **17th Batch, Q5(b)** above.

### (b) What is Code Offloading? State the benefits of Code Offloading.
**Definition:** Code Offloading migrates computationally intensive software modules from resource-limited mobile devices to higher-end/cloud servers, to reduce energy consumption and response time.

**Benefits:**
- **Extends battery lifetime** — offloading heavy computation saves device energy
- **Improves data storage capacity and processing power** — leverages cloud resources beyond device limits
- **Reduces running cost** for computation-intensive applications
- **Improves reliability and availability** — data/processing kept safe and accessible in the cloud
- **Enables dynamic, on-demand provisioning** and **scalability** to meet unpredictable demand

### (c) Describe the applications of Mobile Cloud Computing.
Same as detailed under **17th Batch, Q5(c)** above (M-commerce, M-learning, M-healthcare, M-gaming).

---

## Question 5 (12 marks)

### (a) What is FOG computing? Describe the FOG Computing architecture.
Same as detailed under **17th Batch, Q7(b)** above.

### (b) State the differences between cloud computing and edge computing.

| Aspect | Cloud Computing | Edge Computing |
|---|---|---|
| Processing location | Centralized, remote data centers | Local, at or near the data source |
| Latency | Higher (data travels long distances) | Very low (near-instant local processing) |
| Bandwidth usage | High (all raw data sent to cloud) | Low (only relevant/summarized data sent onward) |
| Scalability | Very high, virtually unlimited resources | Limited by local device/node capacity |
| Use case | Big data analytics, long-term storage | Real-time, latency-sensitive applications |

### (c) Explain the role of Edge computing in healthcare.
Same as detailed under **16th Batch, Q7(c)** above.

---

## Question 6 (12 marks)

> *Blockchain is not covered in the provided lecture slides. Answered from standard technical knowledge.*

### (a) What is Blockchain? Describe different types of Blockchain.
**Definition:** Blockchain is a decentralized, distributed, and immutable digital ledger that records transactions across many nodes, secured through cryptographic hashing and consensus.

**Types:**

| Type | Description |
|---|---|
| **Public Blockchain** | Open to anyone; fully decentralized (e.g., Bitcoin, Ethereum) |
| **Private Blockchain** | Restricted to a single organization; access controlled |
| **Consortium (Federated) Blockchain** | Controlled by a group of organizations rather than one entity |
| **Hybrid Blockchain** | Combines public and private elements — some data public, some restricted |

### (b) Explain the key components of Blockchain.
- **Block** — holds a batch of transactions, timestamp, and a hash pointer to the previous block
- **Hash** — a unique cryptographic fingerprint linking blocks sequentially
- **Distributed Ledger** — a synchronized copy of the chain maintained across many nodes
- **Consensus Mechanism** — protocol (Proof-of-Work, Proof-of-Stake, etc.) for agreeing on the valid next block
- **Nodes/Miners** — network participants who validate transactions and add new blocks
- **Digital Signatures/Private Keys** — used to authenticate and authorize transactions

### (c) Who is a miner and how to do mining in a blockchain network?
**Miner:** A network participant who validates pending transactions and competes to solve a computational puzzle in order to add the next block to the blockchain, earning a reward (e.g., cryptocurrency) for doing so.

**Mining process:**
1. Pending transactions are collected into a candidate block
2. The miner repeatedly computes hashes of the block header (varying a "nonce" value) to find a hash that meets the network's difficulty target (Proof-of-Work)
3. The first miner to find a valid hash broadcasts the completed block to the network
4. Other nodes verify the block's validity and the hash puzzle solution
5. Once accepted, the block is added to the chain, and the miner receives the block reward

---

## Question 7 (12 marks)

### (a) What is IIoT? Describe different application areas of IIoT in the industrial manufacturing process.
Same as detailed under **17th Batch, Q7(a)** above.

### (b) The most visible drawback of IoT is its security — do you agree? Justify your answer.
Same as detailed under **16th Batch, Q2(c)** above.

---

## Disclaimer

This is a **student-generated study aid**, not an official course document. All answers prioritize the official course lecture slides (Lectures 1–7) as the primary source of truth. Topics not present in the provided slides (Virtualization types, Paravirtualization/Xen, Docker/Containers, FOG Computing, Edge Computing, SDN/OpenFlow/ToS, Bitcoin & Blockchain, AAID, Aquaponics, Computing paradigms) are clearly flagged inline and supplemented with standard, reliable academic/technical knowledge. If you have additional lecture material (e.g., Lecture 8, 9, or 10) covering these topics, share it so these answers can be re-aligned to your instructor's exact terminology and examples.
