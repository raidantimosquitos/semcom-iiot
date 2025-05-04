+++
# This title is used as the og:title on Hugo's internal
# opengraph structured data template on the home page.
# See https://ogp.me/ and https://gohugo.io/templates/internal#open-graph.
title = "Semantic Communication in IIoT"
+++

# State-of-the-Art

Semantic communication (SemCom) shifts focus from transmitting raw bits to conveying _meaningful_ information, leveraging context, knowledge, and AI to improve efficiency. Unlike classical Shannon-style communication, which only guarantees bit accuracy, semantic systems encode only the relevant features or “meanings” of data (Pokhrel _et al._, [2022](https://doi.org/10.1007/s00521-022-07065-z)).

This can drastically reduce data volume: in Industrial IoT (IIoT), where massive heterogeneous sensor streams often carry low-density information, extracting semantic features cuts redundancy and network load (IEEE Semantic Communications for Industrial Internet of Things, [2024](https://iccc2024.ieee-iccc.org/workshop/semantic-communications-industrial-internet-things-iiot)).

For example, only the semantically relevant features of a manufacturing sensor stream need to be sent for quality control, rather than all raw readings. Semantic approaches promise lower latency and bandwidth use, which are critical for time-sensitive IIoT control tasks.

{{< figure src="images/semantic-edge-computing-and-semantic-communication.png" class="center" caption="Figure 1: In conventional communication (top), a sensor’s raw data is sent through a network and decoded (often requiring high bandwidth and suffering “cliff effect” under noise). In semantic communication (bottom), an encoder sends only the data’s semantic features or intent (e.g. object class), enabling correct interpretation even under errors." alt="Semantic Edge Computing and Semantic Communication in 6G" >}}

SemCom is especially compelling for IIoT and 6G: it aligns with the push for AI-native networks, edge intelligence, and goal-oriented services. Researchers argue that 6G systems will include a _semantic plane_ alongside traditional layers (Calvanese Strinati _et al._, [2024](https://doi.org/10.48550/arXiv.2402.07573)).

Federated learning (FL) and reinforcement learning approaches are already being explored to realize IIoT semantic systems: for instance, Pokhrel _et al._ ([2022](https://doi.org/10.1007/s00521-022-07065-z)) propose a 6G-IIoT framework using FL and actor-critic RL to learn semantic encoders/decoders across edge nodes. They note that semantic communication is a “_novel paradigm considering the message’s meaning_” and that FL-based architectures show promise in meeting 6G intelligence needs.

Similarly, projects like **SemComIIoT** (a 2023–24 Sino-German research cooperation) explicitly target semantic coding for time-critical IIoT traffic (Fortiss, [SemComIIoT](https://www.fortiss.org/en/research/projects/detail/semcomiiot)).

Overall, recent studies show a surge of interest in semantic methods for IIoT, often employing deep learning (DNN autoencoders, GANs, diffusion models or LLMs) to extract task-relevant features (Ren _et al._, [2024](https://doi.org/10.48550/arXiv.2412.08642)).

---

## 1. SemCom Concepts and Mechanisms in IIoT

In IIoT, data is often task-oriented (e.g. predictive maintenance, quality inspection), so only certain information content matters. Semantic systems exploit this: sources use AI to encode “semantically equivalent” content rather than raw packet. For example, to detect a faulty motor, a camera might only send the “fault detected” label instead of full video frames. This relies on **knowledge bases/graphs** shared by transmitter and receiver: Liang _et al._ ([2024](https://doi.org/10.48550/arXiv.2407.02922)) introduce a probabilistic SemCom model where IIoT devices compress sensor data using knowledge graphs, sending only the most likely semantic entities. Such techniques leverage _semantic compression_ – e.g. graph-based representations – to slash transmitted bits (at the cost of extra local processing).

Crucially, semantic comm systems usually involve joint source–channel coding. Deep learning often implements this: autoencoder networks map source features directly into channel signals. For example, Bourtsoulatze _et al._ ([2019](https://doi.org/10.48550/arXiv.1809.01733)) pioneered deep JSCC for images, where a CNN encoder/decoder pair learns to transmit images over a noisy channel without separate compression/coding.

The same idea applies to IIoT signals (sensor arrays, images, control data), yielding _graceful degradation_ under noise. Other works use generative models: Ren _et al._ survey how GANs, diffusion models, and even large language models (LLMs) can serve as semantic encoders/decoders, essentially letting a powerful AI regenerate content at the receiver instead of raw bits. These methods promise huge overhead reductions – Ren _et al._ ([2024](https://doi.org/10.48550/arXiv.2412.08642)) report >99% data reduction in an example – but require advanced edge hardware.

Another key mechanism is context sharing. Systems may include explicit **semantic dictionaries or ontologies** to ensure sender and receiver interpret symbols the same way
(Calvanese Strinati _et al._, [2024](https://doi.org/10.48550/arXiv.2402.07573)).

In industry, existing technologies like OPC-UA or oneM2M already use semantic annotations for device interoperability; next-gen SemCom extends this into the PHY/MAC layers (Fortiss, [IIoT Lab](https://www.fortiss.org/en/research/fortiss-labs/detail/iiot-lab)).

For instance, semantic-aware protocols might label packets with task IDs, or use network coding that blends multiple sensors’ data in a meaningful way. Although no standardized “semantic MAC” exists yet, research projects suggest integrating semantic RAN controllers (S-RIC) into O-RAN frameworks, enabling intelligent scheduling based on data semantics (Calvanese Strinati _et al._, [2024](https://doi.org/10.48550/arXiv.2402.07573)). In summary, SemCom for IIoT builds on joint coding, AI-driven feature extraction, and shared context/ontology to focus transmissions on _what matters_ in industrial tasks.

---

## 2. Recent Advances (2022-2024)

### 2.1. AI-driven architectures

A central theme SemCom is AI at the edge. Pokhrel _et al._ ([2022](https://doi.org/10.1007/s00521-022-07065-z)) describe an IIoT SemCom framework combining federated learning and actor-critic RL to adapt semantic encoders across devices.

Edge-learning is indeed critical: Arfeto _et al._ ([2025](https://doi.org/10.48550/arXiv.2501.09918)) present _GenSC-6G_, a prototype testbed that integrates large AI models (diffusion and transformer LLMs) for semantic tasks. Their dataset uses generative AI to produce labeled data (e.g. vehicle images) and transmits only high-level features via semantic channel models.

Likewise, Kalita ([2024](https://doi.org/10.48550/arXiv.2407.20970)) proposes an edge-computing framework where LLMs reside near IoT sources: the local LLM interprets commands and encodes meaning, then edge servers ensure rapid, context-aware actions. Such works highlight that edge intelligence is often intertwined with semantic coding: by pushing AI inference to the network edge, IIoT nodes can extract and send only semantic summaries, saving energy and bandwidth while meeting strict latency requirements.

### 2.2. Semantic compression and coding

Recent papers target reducing data for specific IIoT use cases. Liang _et al._ ([2024](https://doi.org/10.48550/arXiv.2407.02922)) study _probabilistic SemCom_ in an IIoT uplink: each node extracts semantic features into a knowledge graph, then jointly optimizes power and compression so all users achieve fair throughput. They show knowledge-graph compression drastically cuts transmitted bits, but requires extra on-device computation (tradeoff with battery/power).

Other works design semantic codecs for vision/audio: for instance, Hu _et al._ ([2022](https://doi.org/10.1109/IOTSMS58070.2022.10061867)) use knowledge graphs to robustify image classification over wireless.

In general, studies demonstrate that _semantic_ JSCC (often deep-learning-based) outperforms classic coding under resource constraints, at the expense of added AI processing.

### 2.3. Architectures and frameworks

Several survey and vision papers outline general architectures. Zhang _et al._ ([2025](https://doi.org/10.48550/arXiv.2411.18199)) provide a broad survey of Semantic Edge Computing (SEC) and SemCom in 6G networks. They illustrate splitting neural encoders between device and edge server: the device-side DNN extracts features, transmits the semantic latent vector, and the edge completes the inference (Figure 1 above).

Another line is goal-oriented networking: Calvanese Strinati _et al._ ([2024](https://doi.org/10.48550/arXiv.2402.07573)) propose a 6G “GOAL-Oriented” semantic framework with semantic planes and controllers atop O-RAN, and Getu _et al._ ([2024](https://doi.org/10.1109/ACCESS.2024.3381967)) survey “goal-oriented SemCom” techniques, emphasizing effectiveness metrics (task success) over mere throughput. These works predict that 6G will integrate semantic layers (e.g. semantic RIC) and AI reasoning engines to manage SemCom services.

### 2.4. Implementations and demonstrations

Although commercial deployments are nascent, prototypes have begun to appear. The GenSC-6G project (Arfeto _et al._, [2025](https://doi.org/10.48550/arXiv.2501.09918)) provides a modular software/hardware framework for testing large-AI SemCom (Figure 2). In industry, OdineLabs recently filed a patent ([2025](https://odine.com/news-insights/odinelabs-inc-completes-official-patent-application-for-ai-powered-semantic-communication-technology-for-5g-6g-networks/)) for a semantic 5G/6G system combining multi-task semantic infrastructure with federated learning at the edge– signaling vendor interest in semantics for IoT.

{{< figure src="images/GenSC-6G-FrameworkArchitecture.png" class="center" caption="Figure 2: A GenSC-6G testbed prototype. The large-AI SC testbed framework prototypes a flexible architecture in which the backbone encoder and communication modules are alterable to fit any backend, and the semantic decoders can be adapted for various downstream goal-oriented tasks. ReLU, TX, RX, mmWave, OFDM, PSK, QAM, MHSA, BLIP, GPT, LLaMA, and FPN stand for the rectified linear unit, transmitter, receiver, millimeter wave, orthogonal frequency division multiplexing, phase-shift keying, quadrature amplitude modulation, multi-head self-attention, bootstrapping language-image pretraining, generative pretrained transformer, LLM Meta AI, and feature pyramid network, respectively." alt="GenSC-6G testbed" >}}

Meanwhile, the **SemComIIoT** demonstrator ([Fortiss/SDU](https://www.fortiss.org/en/research/projects/detail/semcomiiot) plans to validate semantic concepts in a mobile-IIoT testbed (e.g. deterministic 1–2ms latency in semantic MACs). (Fortiss’s [IIoT Lab](https://www.fortiss.org/en/research/fortiss-labs/detail/iiot-lab) already uses “semantic technologies” for device integration, hinting at practical pathways.)

---

## 3. Protocols and Architectures

Current research has begun to outline potential SemCom protocols, though no standards exist yet. At the PHY/MAC, ideas include joint source-channel codes tuned for semantics, or “semantic-aware MAC scheduling” that prioritizes semantically rich transmissions. For example, studies on deep JSCC show that trained DNNs naturally handle source/channel coding with semantics (avoiding the “cliff effect” of digital systems - Bourtsoulatze _et al._ ([2018](https://doi.org/10.48550/arXiv.1809.01733))).

At higher layers, proposals like the semantic plane would carry metadata about content semantics and goals. The 6G-GOALS project suggests adding a _Semantic RAN Intelligent Controller (S-RIC)_ and reasoning modules in the RAN (Calvanese Strinati _et al._, [2024](https://doi.org/10.48550/arXiv.2402.07573)). These components could implement new control signaling (e.g. signaling the required semantic quality or task priority). While largely conceptual so far, some concrete protocols have been sketched. For instance, a “semantic hybrid ARQ” was demonstrated where retransmissions depend on whether semantic content was correctly inferred (Pokhrel _et al._, [2022](https://doi.org/10.1007/s00521-022-07065-z)). Others propose combining network coding with semantics: the [SemComIIoT](https://www.fortiss.org/en/research/projects/detail/semcomiiot)) project description mentions using network coding principles to inject “data meaning” instead of raw bits. On the application side, IoT standards like OPC UA already convey semantically typed data (e.g. sensor semantics) – these can be building blocks for semantic networking, though specialized protocols for semantic compression or query-by-content remain research topics.

In summary, semantic architectures for IIoT envision the entire stack integrating semantics: edge/AIs extract meaning (application layer), shared ontologies ensure common understanding (session layer), adaptive coding schemes operate at MAC/PHY, and a semantic control plane manages resources. Key open questions include how to standardize semantic vocabularies, how to signal semantic priorities in 6G NR, and how to gracefully interwork with legacy bit-oriented systems.

---

## 4. Edge computing and 6G integration

Edge computing is a natural partner for SemCom. By moving intelligence closer to IIoT devices, edge servers can perform heavy semantic encoding/decoding, leaving sensors to handle only lightweight tasks. Zhang _et al._ ([2025](https://doi.org/10.48550/arXiv.2411.18199)) note that semantic edge computing (splitting DNNs across device and edge) can increase throughput and robustness, as the device sends only compressed latent features. In practice, an IIoT sensor might run the first layers of a DNN, send the bottleneck representation wirelessly, and let an edge server finish processing (see Figure 1). This reduces wireless load and the device’s energy use. Edge AI is also key for LLM-based schemes: Kalita ([2024](https://doi.org/10.48550/arXiv.2407.20970)) argues that LLM inference cannot run on tiny IoT nodes, but placing them on edge/cloud routers enables sophisticated semantic understanding with acceptable delay.

Sixth-generation (6G) networks are envisioned to natively support semantics and edge AI. Projects like 6G-GOALS ([2024](https://doi.org/10.48550/arXiv.2402.07573)) propose O-RAN-based architectures with semantic RICs and AI reasoning engines. 6G standards discussions already mention a “semantic plane” to overlay on the protocol stack. Moreover, 6G envisions ubiquitous AI and sensing – e.g. integrating satellite and terrestrial IoT – where semantic protocols can help (e.g. the concept of Internet of Space includes semantic control of aerial devices). Edge and 6G converge in use cases like the _industrial metaverse_, where high-resolution sensing and control require both semantic compression (to limit bandwidth) and edge rendering. In sum, edge computing provides the hardware and low-latency infrastructure that makes semantic IIoT feasible, and 6G provides the flexible architecture (open RAN, network slicing, massive MIMO) to implement semantic-aware networks.

---

## 5. Projects, frameworks and testbeds

Several notable initiatives illustrate the emerging ecosystem:

- **SemComIIoT (Fortiss/SDU)** – A Sino-German project (2023–24) to design end-to-end semantic IIoT systems. Objectives include semantic network coding, decentralized edge/cloud learning of encoders, and deterministic quality of service in mixed traffic. Though still ongoing, it represents one of the first concerted efforts on real-world semantic IIoT (SemComIIoT, [Fortiss/SDU](https://www.fortiss.org/en/research/projects/detail/semcomiiot)).
- **GenSC-6G** – A prototype semantic communication testbed (submitted for IEEE Communications Magazine 2025). It combines generative AI, quantum computing support, and wireless links. The researchers release a large dataset of noisy semantic tasks (e.g. object classification, text inference) and provide a modular software framework for experimenting with semantic encoders/decoders (Arfeto _et al._, [2025](https://doi.org/10.48550/arXiv.2501.09918)).
- **6G-GOALS (Horizon Europe)** – A European project (2023–26) that defines an AI-native 6G architecture with semantic planes and goal-oriented layers. It provides reference designs like semantic RIC units and semantic-effectiveness filtering in RAN (Calvanese Strinati _et al._, [2024](https://doi.org/10.48550/arXiv.2402.07573)).
- **OdineLabs Semantic Patent** – In April 2025, OdineLabs announced a [patent](https://odine.com/news-insights/odinelabs-inc-completes-official-patent-application-for-ai-powered-semantic-communication-technology-for-5g-6g-networks/) for a “multi-task semantic communication” system for 5G/6G, explicitly combining federated learning with semantic coding. This industry move highlights commercial interest in semantic IIoT, aiming to cut latency and bandwidth by processing data’s meaning at the edge.
- **Survey and Standards Efforts** – Academic surveys (e.g. Zhang _et al._, [2025](https://doi.org/10.48550/arXiv.2411.18199), Getu _et al._, [2024](https://doi.org/10.1109/ACCESS.2024.3381967)) and whitepapers ([6G Alliance](https://nextgalliance.org/6g-library/)) are forging consensus on semantic definitions. Workshops like [IEEE ICCC 2024’s Semantic IIoT](https://iccc2024.ieee-iccc.org/workshop/semantic-communications-industrial-internet-things-iiot) emphasize practical issues (semantic coding, resource management, security).

These frameworks are mostly prototypes or studies, but some testbeds exist: for example, a hardware-in-loop demonstrator was reported where an image classifier was split across wireless link (TX processes features, RX reconstructs object) with learned semantic codes (Bourtsoulatze _et al._, [2018](https://doi.org/10.48550/arXiv.1809.01733)). In IIoT labs (e.g. [Fortiss IIoT Lab](https://www.fortiss.org/en/research/projects/detail/semcomiiot)), semantic data integration (via ontologies) is already used for device interoperability. However, full-stack semantic network deployments in factories are still an open frontier.

---

## 6. Benefits and limitations

### 6.1. Benefits of SemCom for IIoT

The literature highlights several advantages for IIoT:

- **Bandwidth and Energy Savings**: By transmitting only meaning, semantic systems can dramatically cut data rates. Experiments on images and sensors show orders-of-magnitude fewer bits sent for the same task accuracy (Bourtsoulatze _et al._, [2018](https://doi.org/10.48550/arXiv.1809.01733)).
- **Robustness**: Deep semantic codes tend to degrade gracefully with noise (avoiding cliff effects), improving reliability in industrial wireless environments (Bourtsoulatze _et al._, [2018](https://doi.org/10.48550/arXiv.1809.01733)).
- **Task Efficiency**: Goal-oriented metrics (e.g. task completion) can be optimized directly. For time-critical control or AR/VR in factories, semantic metrics ensure that network decisions focus on relevant state, reducing end-to-end delays.
- **Edge Fusion**: Semantic encoders integrate naturally with edge AI, enabling collaborative sensing and inference (e.g. multiple sensors jointly encoding context).

### 6.2. Limitations and challenges of SemCom for IIoT

There are also significant open issues:

- **Knowledge Alignment**: Semantic comm requires shared context/ontologies. In heterogeneous IIoT networks, ensuring that edge, cloud, and devices use compatible semantic models is non-trivial (Calvanese Strinati _et al._, [2024](https://doi.org/10.48550/arXiv.2402.07573)). A mismatched ontology can cause misinterpretation.
- **Computational Overhead**: Extracting and encoding semantics (e.g. running a DNN or LLM) is costly on low-power IIoT devices. Many schemes push work to the edge or use compression to cope, but battery/latency trade-offs remain (e.g. Liang _et al._, [2024](https://doi.org/10.48550/arXiv.2407.02922), Kalita _et al._, [2024](https://doi.org/10.48550/arXiv.2407.20970)).
- **Lack of Theory and Standards**: No established information theory fully covers semantics yet. Practical algorithms rely on heuristics or data-driven models. Protocol standards for semantic signaling or MAC are in infancy, so interoperability between legacy and semantic nodes is unclear (e.g. Pokhrel _et al._, [2022](https://doi.org/10.1007/s00521-022-07065-z), Calvanese Strinati, [2024](https://doi.org/10.48550/arXiv.2402.07573)).
- **Security and Privacy**: Semantic data may expose sensitive information if intercepted. Securing meaning (beyond bits) is a new problem.

These and other challenges (e.g. dynamic semantic source evolution, multi-agent consensus) are widely discussed in surveys and workshops.

---

## 7. Summary of key works

| **Work (Year)**                                                                                                                                                              | **Focus**                                                                                                                                  |
| :--------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :----------------------------------------------------------------------------------------------------------------------------------------- |
| Pokhrel _et al._ ([2022](https://doi.org/10.1007/s00521-022-07065-z))                                                                                                        | Federated learning + RL for semantic IIoT – proposes a 6G-IIoT SemCom framework using FL and A3C to learn task-oriented encoders/decoders. |
| Liang _et al._ ([2024](https://doi.org/10.48550/arXiv.2407.02922))                                                                                                           | Probabilistic SemCom in IIoT – joint comm/computation design using knowledge graphs to compress semantics with power constraints.          |
| Ren _et al._ ([2024](https://doi.org/10.48550/arXiv.2412.08642))                                                                                                             | Generative SemCom architectures – surveys GANs, diffusion models, and LLMs for encoding semantic content in 6G networks.                   |
| Kalita ([2024](https://doi.org/10.48550/arXiv.2407.20970))                                                                                                                   | LLM-based Semantic Comm – framework for using large language models at the edge for semantic IoT communication.                            |
| Arfeto _et al._ ([2025](https://doi.org/10.48550/arXiv.2501.09918))                                                                                                          | GenSC-6G testbed – prototype and dataset combining generative AI and quantum computing for semantic 6G applications (e.g. edge inference). |
| Calvanese Strinati _et al._ ([2024](https://doi.org/10.48550/arXiv.2402.07573))                                                                                              | 6G-GOALS architecture – AI-native semantic/goals plane on O-RAN with semantic RAN controllers and reasoning engines for goal-oriented 6G.  |
| Fortiss SemComIIoT ([2023–24](https://www.fortiss.org/en/research/projects/detail/semcomiiot))                                                                               | Project – research on semantic coding, deterministic wireless, and edge AI for time-sensitive industrial networks.                         |
| OdineLabs ([2025](https://odine.com/news-insights/odinelabs-inc-completes-official-patent-application-for-ai-powered-semantic-communication-technology-for-5g-6g-networks/)) | Industry patent – multi-task semantic comm + federated learning framework aiming to optimize bandwidth and latency in 5G/6G.               |

---

## 8. Conclusions and outlook

Semantic communication for IIoT is rapidly evolving from theory to practice. In the past 2–3 years, researchers have demonstrated the _potential_ of semantic encoding (via deep learning, knowledge graphs, etc.) to improve efficiency in industrial scenarios (Liang _et al._, [2024](https://doi.org/10.48550/arXiv.2407.02922)), Pokhrel _et al._, [2022](https://doi.org/10.1007/s00521-022-07065-z)). Experimental frameworks like GenSC-6G and SemComIIoT are laying the groundwork for real-world validation. Integration with edge computing and emerging 6G architectures (semantic planes, O-RAN) is a focal point, promising adaptive, AI-driven industrial networks.

However, much remains to be done. Robust semantic protocols, cross-domain ontologies, and standardized interfaces are still lacking. Overhead of AI computation vs. communication savings must be balanced in resource-constrained IIoT devices. As several surveys note, a formal information theory of meaning is still an open research area (Pokhrel _et al._, [2022](https://doi.org/10.1007/s00521-022-07065-z), Getu _et al._, [2024](https://doi.org/10.1109/ACCESS.2024.3381967)). Future work will likely emphasize _goal-oriented_ performance (e.g. task success under constraints) and develop hybrid semantics (combining symbolic knowledge with neural methods). In summary, semantic IIoT is an emerging frontier: recent advances suggest significant benefits, but realizing operational semantic networks in factories will require coordinated effort in algorithms, systems, and standards.
