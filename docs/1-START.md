# Radio Mesh AREA Network


## 1. What is Mesh Networking
*From Wikipedia, the free encyclopedia*

A **Mesh Network** is a local area networking topology in which the infrastructure nodes (i.e. bridges, switchs, and other infrastructure devices) connect directly, dynamically and non-hierarchically to as many other nodes as possible and cooperate with one another to efficiently route to and from clients. 

This lack of dependency on one node allows for every node to participate in the relay of information. Mesh networks dynamically self-organize and self-configure, which can reduce installation overhead. The ability to self-configure enables dynamic distribution of workloads, particularly in the event a few nodes should fail. This in turn contributes to fault-tolerance and reduced maintenance costs.

Mesh topology may be contrasted with conventional star/tree local network topologies in which the bridges/switches are directly linked to only a small subset of other bridges/switches, and the links between these infrastructure neighbours are hierarchical. While star-and-tree topologies are very well established, highly standardized and vendor-neutral, vendors of mesh network devices have not yet all agreed on common standards, and interoperability between devices from different vendors is not yet assured.

## 2. Wireless Mesh Network
*From Wikipedia, the free encyclopedia*

A **wireless mesh network (WMN)** is a communications network made up of radio nodes organized in a mesh topology. It can also be a form of wireless ad hoc network.

A **mesh** refers to rich interconnection among devices or nodes. Wireless mesh networks often consist of mesh clients, mesh routers and gateways. Mobility of nodes is less frequent. If nodes constantly or frequently move, the mesh spends more time updating routes than delivering data. In a wireless mesh network, topology tends to be more static, so that routes computation can converge and delivery of data to their destinations can occur. Hence, this is a low-mobility centralized form of wireless ad hoc network. Also, because it sometimes relies on static nodes to act as gateways, it is not a truly all-wireless ad hoc network.

Mesh clients are often laptops, cell phones, and other wireless devices. Mesh routers forward traffic to and from the gateways, which may or may not be connected to the Internet. The coverage area of all radio nodes working as a single network is sometimes called a mesh cloud. Access to this mesh cloud depends on the radio nodes working together to create a radio network. A mesh network is reliable and offers redundancy. When one node can no longer operate, the rest of the nodes can still communicate with each other, directly or through one or more intermediate nodes. Wireless mesh networks can self form and self heal. Wireless mesh networks work with different wireless technologies including `802.11`, `802.15`, `802.16`, cellular technologies and need not be restricted to any one technology or protocol.

## 3. Already exists Projects:
- 1. **Meshtastic**
   - Meshtastic relies on a managed flooding approach (with hop‐limits and SNR‐based contention) for broadcast traffic, and uses next-hop caching for direct unicast messages rather than exchanging per-destination gradient metrics.
   - **Meshtastic’s Managed Flooding:** In Layer 3 (Multi-Hop Messaging), every node rebroadcasts a received packet (decrementing a HopLimit in the header) until the HopLimit reaches zero. Before forwarding, nodes listen briefly—and if they hear another rebroadcast, they suppress their own—to reduce redundant transmissions. A contention window sized by the Signal-to-Noise Ratio (SNR) gives farther nodes a higher chance to flood first, extending overall range
   - **Next-Hop Caching for Unicast:** For direct (unicast) messages, Meshtastic initially floods as above but then tracks which neighbor actually relayed the packet. On subsequent hops, only that “next-hop” forwards, falling back to flooding on failure
