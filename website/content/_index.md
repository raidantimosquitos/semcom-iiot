---
title: Introduction
type: docs
author: Lucas Herranz Gancedo
weight: 1
---

<img src="/images/ntust-logo.png" alt="National Taiwan University of Science and Technology">

![NTUST](/images/ntust-logo.png)

# Research Project Proposal - Network slicing for Smart Manufacturing Industrial Internet of Things (IIoT) networks.

## Research summary

Network slicing is an innovative telecommunications technology that enables the creation of multiple isolated virtual networks, or "slices," within a single physical mobile network infrastructure. This capability is particularly significant in the context of smart manufacturing, where diverse applications require customized connectivity solutions to optimize operational efficiency, data processing, and system reliability. The emergence of network slicing is publicized as a key enabler of Industry 4.0, facilitating the seamless integration of advanced technologies such as the Internet of Things (IoT), artificial intelligence (AI), and 5G networks to transform traditional manufacturing processes into intelligent, connected ecosystems[^1] [^2] [^3].

In smart manufacturing environments, the demand for high bandwidth, ultra-reliable low latency, and extensive device connectivity can vary dramatically among different applications. Network slicing addresses these varying requirements by allocating network resources dynamically, ensuring that critical operations like real-time monitoring, automation, and data analytics are supported effectively. This technology not only enhances operational flexibility but also promotes the development of innovative applications, such as extended reality for operator training and AI-driven predictive maintenance, which are becoming increasingly vital in modern manufacturing settings[^4] [^5] [^6].

Despite its potential benefits, the implementation of network slicing in smart factories is fraught with challenges, including the complexity of resource allocation, managing fluctuating network conditions, and ensuring robust security measures across multiple slices. Addressing these issues is critical to maintaining high performance and reliability in dense industrial environments, where communication failures can lead to significant operational disruptions and financial losses [^7] [^8] [^9].
As the landscape of smart manufacturing continues to evolve, ongoing advancements in network technologies, particularly with the anticipated shift toward 6G, are expected to further enhance the capabilities and applicability of network slicing in this sector[^10] [^11] [^12].

## Background

Network slicing is a transformative technology that enables the creation of multiple isolated virtual networks, or "slices," within a single physical mobile network. Each slice is specifically tailored to meet the requirements of various applications and services, offering distinct functionalities and resource allocations that traditional networks cannot provide. This adaptability is particularly crucial in dynamic environments such as smart manufacturing, where the demands for high bandwidth, low latency, and reliability can vary significantly across different use cases [^1] [^2].

### Smart manufacturing and its requirements

Smart manufacturing refers to the integration of advanced information and communication technologies (ICT) to enhance production processes through automation and data analytics. The aim is to create a connected and responsive manufacturing ecosystem that improves productivity, quality, and sustainability[^3] [^4].

Given the complexities of smart factories—characterized by diverse machinery, irregular object shapes, and the influence of industrial activities on wireless channels—effective communication and resource management are paramount[^5] [^3].

### Radio propagation challenges

In indoor factory environments, unique challenges arise due to the presence of metallic objects and electrical interference, which significantly affect radio propagation. This necessitates precise modeling of wireless channels to ensure reliable communication among machines and devices[^5] [^6].

As traditional wired systems struggle to meet the evolving needs of smart factories, the integration of wireless technologies supported by network slicing emerges as a viable solution, enhancing the flexibility and reconfiguration of industrial networks[^7] [^6].

### The role of network slicing

Network slicing allows for the dynamic allocation of resources tailored to specific applications, such as low-latency communication for automated machinery or high-bandwidth connections for real-time data analytics[^1] [^2] [^8].

The adoption of network slicing in smart manufacturing is bolstered by the advancements in technologies such as software-defined networking (SDN) and network function virtualization (NFV), enabling seamless orchestration and management of network resources[^9] [^8].

As the landscape of smart manufacturing continues to evolve, the implementation of network slicing is expected to play a critical role in shaping the future of industrial connectivity.

## Network slicing in Smart Manufacturing

Network slicing is a critical technology in the realm of smart manufacturing, particularly enhanced by the capabilities of 5G networks. It allows the creation of multiple virtual networks on a single physical infrastructure, tailored to meet the specific requirements of diverse applications within smart factories[^5]. This innovation is pivotal for realizing the goals of Industry 4.0, as it enhances operational efficiency and facilitates the integration of various digital processes.

### Overview of Network slicing

Network slicing enables the segmentation of a physical network into several virtual networks, or "slices," each optimized for distinct operational needs. In smart manufacturing, this technology supports real-time monitoring, automation, and system optimization by providing ultra-reliable low latency connections, massive device connectivity, and high data rates[^5]. The unique capability of 5G to provide network slicing positions it as a game-changer for the manufacturing sector, where different processes may require varying levels of connectivity and reliability.

### Applications in smart factories

In a fully digitized smart factory, network slicing facilitates a cohesive and collaborative ecosystem that can operate autonomously with decentralized decision-making[^5].

- **Real-Time Monitoring**: Utilizing sensors that connect via 5G, manufacturers can achieve high reliability and immediate feedback, which is crucial for maintaining operational continuity[^10].
- **Extended Reality and Human-Machine Interfaces (HMIs)**: Network slicing supports the deployment of extended reality technologies, which create immersive environments for operator training and machine interaction, thus enhancing productivity and safety on the factory floor[^11].
- **Integration of AI and Machine Learning**: By connecting AI systems via dedicated slices, manufacturers can improve predictive maintenance and optimize machine performance dynamically, thereby reducing downtime and maintenance costs[^10].

### Challenges and future prospects

Despite the advantages, deploying network slicing in dense smart factory environments poses significant challenges. These include managing the complexity of multiple slices in congested radio environments and ensuring that performance remains consistent across varying conditions[^5].

Moreover, effective slice management is essential to maintain reliability and performance standards. Looking ahead, the evolution towards advanced network technologies like 6G may further enhance the capabilities of network slicing in smart manufacturing. The integration of blockchain technology is also emerging as a promising solution to improve data integrity and security across various slices, fostering collaboration among different stakeholders in the manufacturing ecosystem[^10].

As the industry continues to embrace digital transformation, the strategic implementation of network slicing will be vital in addressing the evolving needs of smart factories.

## State of the art

### Overview of Network Slicing in Smart Manufacturing

Network slicing has emerged as a pivotal technology in the evolution of smart manufacturing, enabling the creation of multiple virtual networks on a single physical infrastructure. This innovation allows manufacturers to tailor connectivity and resources to meet the specific demands of various applications, thereby enhancing operational efficiency and flexibility[^2] [^12].

### Key technologies and architecture

The foundation of network slicing is built on a combination of advanced communication technologies, including 5G, the Internet of Things (IoT), and artificial intelligence (AI)[^1] [^13].

These technologies work in synergy to create a robust and adaptable network environment capable of supporting the diverse needs of the manufacturing sector. As manufacturers transition from traditional approaches to Industry 4.0 and prepare for Industry 5.0, the emphasis on data-driven processes and high network availability becomes critical[^14] [^15].

### Social benefits and industry impact

The implementation of network slicing facilitates significant societal benefits, such as improved supply chain optimization and the ability to customize and personalize products according to consumer preferences[^14] [^15].

Enhanced connectivity allows for real-time data tracking and communication among all stakeholders, leading to increased transparency, reduced lead times, and improved order accuracy. Furthermore, this technology empowers small manufacturers to access advanced capabilities previously reserved for larger corporations, fostering a more competitive and innovative landscape[^16].

### Future prospects

Looking ahead, network slicing is set to play an integral role in the future of smart manufacturing, particularly with the anticipated advancements in 6G technology, which promises hyper-connectivity and ultra-low latency[^13] [^2].

The ability to implement tailored security measures for each network slice also enhances overall network integrity, crucial for critical industrial applications[^12]. As organizations continue to navigate the complexities of digital transformation, the adaptability and efficiency afforded by network slicing will be instrumental in driving the next wave of industrial innovation.

## Challenges and limitations

Network slicing in smart manufacturing presents several challenges and limitations that must be addressed for its successful implementation.

### Complexity of resource allocation

One significant challenge is the complexity of allocating resources effectively among different network slices. This issue arises due to the combinatorial and non-convex nature of the allocation problem, particularly when supporting diverse services like enhanced Mobile Broadband (eMBB), Ultra-Reliable Low-Latency Communication (URLLC), and massive Machine Type Communication (mMTC) under conditions of imperfect Channel State Information (CSI)[^5]. Advanced computational techniques are often required to tackle these complexities, making practical implementation difficult.

### Handling uncertainty

Another limitation is related to handling uncertainty in fluctuating network conditions and varying traffic demands. While some machine learning-based solutions have made advancements in this area, they often assume a level of predictability or require adjustments that may not be feasible in real-world scenarios, thereby limiting their effectiveness[^5]. This unpredictability can lead to performance degradation when unexpected conditions arise, further complicating the resource management process.

### Network downtime and security vulnerabilities

The challenge of network downtime is critical, particularly for manufacturers. Unplanned downtime can lead to significant financial losses, with estimates suggesting costs can reach up to $50 billion annually for industrial manufacturers[^14]. Additionally, network security vulnerabilities pose a risk, as missed updates or lapses in protection can leave systems exposed to cyber threats. The evolving nature of network security necessitates that solutions be integrated directly into the network infrastructure to minimize such risks, adding another layer of complexity to the implementation of network slicing[^14].

### Technological integration

Furthermore, integrating network slicing with existing technologies presents challenges in terms of compatibility and compliance. Ensuring that the infrastructure layer, which encompasses various components such as data centers, routers, and base stations, can efficiently support the multiplexing of different network slices is essential but difficult[^17]. Moreover, the management of these slices must be dynamic and responsive to real-time data to maintain performance and service level agreements (SLAs), which can complicate operational procedures[^12].

### Operational compliance and monitoring

Operational compliance also remains a concern. For example, ensuring that tools and applications are accurately monitored and returned to central storage can be challenging, especially in environments where technicians may not consistently adhere to protocols[^4]. This lack of compliance can hinder operational efficiency and create additional barriers to the successful deployment of network slicing solutions.

## Future trends

### Advancements in network slicing

As the demand for more efficient and tailored connectivity solutions grows, network slicing is expected to play a crucial role in the evolution of smart manufacturing. The integration of artificial intelligence (AI) into network slicing is one of the most significant trends anticipated in the near future. AI-driven network slicing solutions are poised to optimize slice performance and resource utilization by continuously monitoring network conditions and predicting usage patterns, enabling automated adjustments to maintain optimal service levels[^9] [^18].

This shift towards intelligent systems will not only enhance operational efficiency but also reduce the need for manual interventions, thus streamlining network management processes.

### Emphasis on disaggregated networks

The trend towards disaggregated networks, which emphasizes a cloud-native approach and the separation of hardware and software, continues to evolve. This development aims to eliminate vendor lock-in and operational complexities by utilizing conventional white-box hardware alongside cloud-native software[^8]. As smart manufacturing increasingly relies on flexible and scalable network solutions, disaggregated networks are expected to simplify operations while promoting innovation across various service domains.

### Focus on enhanced security measures

With the growing complexity of managing multiple network slices, enhanced security measures will be paramount. As each slice must be isolated yet interconnected, the implementation of advanced security protocols and continuous monitoring systems will be essential to protect against potential threats[^1]. As manufacturers adopt more connected technologies, ensuring robust security across all network slices will become a critical focus for both telecom providers and industrial entities.

### Interoperability and standardization

The need for interoperability among different network domains and technologies is another anticipated trend. Achieving seamless integration across diverse network components will require the adoption of standardized frameworks and protocols[^1]. This will enable smart manufacturing environments to leverage various technologies efficiently, ensuring that innovations such as the Industrial Internet of Things (IIoT), big data analytics, and edge computing can be effectively deployed across different platforms.

### Predictive maintenance and resource allocation

As smart factories increasingly adopt IoT devices for monitoring equipment performance, predictive maintenance will become a key application of network slicing. By leveraging network slicing, manufacturers can ensure that critical data is prioritized, allowing for timely maintenance interventions before equipment failures occur[^6]. This proactive approach will significantly reduce downtime and enhance overall productivity, further driving the demand for intelligent network slicing solutions.

## References

[^1]: Network Slicing for 5G Use Cases - Bridge-Connect, [Link](https://www.bridge-connect.com/post/network-slicing-for-5g-use-cases).

[^2]: Network Slicing: A Technological Deep Dive – Peaker Map, [Link](https://www.peakermap.com/blogs/news/network-slicing-a-technological-deep-dive).

[^3]: Three smart manufacturing case studies - RCR Wireless News, [Link](https://www.rcrwireless.com/20180102/fundamentals/three-smart-manufacturing-case-studies-tag23-tag99).

[^4]: 5G for Manufacturing | Use cases, insights, challenges, benefits, [Link](https://tecknexus.com/industry/smart-manufacturing/).

[^5]: Slicing for Dense Smart Factory Network: Current State, Scenarios, Challenges and Expectations, [Link](https://arxiv.org/html/2405.03230v1).

[^6]: A Look Ahead: 2023 Connectivity Trends for Smart Manufacturing, [Link](https://www.industryweek.com/technology-and-iiot/article/21256000/a-look-ahead-2023-connectivity-trends-for-smart-manufacturing).

[^7]: 5G Network Slicing: Key to Digital Transformation of Industries - ZTE, [Link](https://www.zte.com.cn/global/about/magazine/zte-technologies/2019/4-en/special-topic--5g-core/3.html).

[^8]: The network trends to watch in 2023 & beyond - Amdocs, [Link](https://www.amdocs.com/insights/blog/network-trends-watch-2023-beyond).

[^9]: The Evolving Future of 5G Network Slicing with AI in Telecommunications Holds Limitless Potential, [Link](https://mischadohler.com/the-evolving-future-of-5g-network-slicing-with-ai-in-telecommunications-holds-limitless-potential/).

[^10]: Network Slicing and Blockchain to Support the Transformation of Connectivity Services in the Manufacturing Industry, [Link](https://sdn.ieee.org/newsletter/march-2018/network-slicing-and-blockchain-to-support-the-transformation-of-connectivity-services-in-the-manufacturing-industry).

[^11]: Slicing for Dense Smart Factory Network: Current State, Scenarios, Challenges and Expectations, [Link](https://arxiv.org/abs/2405.03230).

[^12]: Network Slicing Explained: The Future of Tailored 5G Networks [Link](https://blog.emb.global/network-slicing-in-5g/).

[^13]: Role of Patents and Standards in Driving Innovation in Next-Generation Networks, [Link](https://ants2024.ieee-ants.org/program/panels/role-patents-and-standards-driving-innovation-next-generation-networks).

[^14]: Ensuring network availability and uptime in manufacturing - AT&T Business, [Link](https://www.business.att.com/learn/articles/ensuring-network-availability-and-uptime-in-manufacturing.html).

[^15]: Smart factories: Optimizing operations, safety, and productivity with 5G and automation, [Link](https://techcommunity.microsoft.com/blog/telecommunications-industry-blog/smart-factories-optimizing-operations-safety-and-productivity-with-5g-and-automa/3781957).

[^16]: How Does Network Slicing Enable Industry 4.0? - technovina.com, [Link](https://technovina.com/how-does-network-slicing-enable-industry-4-0/).

[^17]: 5G network slicing - Wikipedia, [Link](https://en.wikipedia.org/wiki/5G_network_slicing).

[^18]: Shaping Tomorrow’s Connectivity with AI-Driven Network Slicing, [Link](https://mischadohler.com/ai-network-slicing/).
