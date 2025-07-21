# Section 3: DMVPN and Branch Connectivity Configuration

## Overview

This section outlines the configuration tasks for establishing a **Dynamic Multipoint Virtual Private Network (DMVPN)** across **Branch 123**, **Branch 21**, and **Branch 31**, integrated with **EIGRP** and **BGP** to ensure robust connectivity. The tasks focus on setting up EIGRP with authentication, configuring BGP peering, establishing DMVPN with encryption, and verifying spoke-to-spoke connectivity. The provided topology diagram illustrates the DMVPN structure and connections to guide the configuration process.

### DMVPN Network Topology

![DMVPN Network Topology](image-4.png "Network topology diagram for DMVPN, showing connections between R11 (hub), R21, and R31 (spokes)")

**Diagram Description**: The DMVPN topology illustrates the hub-and-spoke architecture with **R11** as the hub router in **Branch 123** and **R21** and **R31** as spoke routers in **Branch 21** and **Branch 31**, respectively. The diagram also highlights the BGP peering with the **R8 PE router** and the underlay connectivity requirements. Focus on the tunnel interfaces, encryption settings, and routing configurations to ensure proper setup.

## Task List

### Branch 21 and Branch 31 Configuration

1. **EIGRP Configuration**  
        - Configure **EIGRP named mode "CCIE"** with **Autonomous System 123** within **Branch 21** and **Branch 31**.  

2. **EIGRP Authentication**  
        - Enable **MD5 authentication** for EIGRP.  
        - Use the key-chain name **"CCIE_Practice_Lab"** for authentication.

3. **BGP Peering**  
        - Establish **BGP peering** between **R21** (in **Branch 21**) and **R31** (in **Branch 31**) with the **R8 PE router**.  
        - Use **BGP AS21** on **R21** and **BGP AS31** on **R31**.

4. **Underlay Connectivity**  
        - Verify that the underlay network between **Branch 123**, **Branch 21**, and **Branch 31** is operational.  
        - Ensure **R11**, **R21**, and **R31** can ping each other using their **Loopback0** interfaces.

### DMVPN Configuration

5. **DMVPN Setup**  
        - Configure **DMVPN** across **Branch 123**, **Branch 21**, and **Branch 31**, with **R11** as the hub router and **R21** and **R31** as spoke routers.  
        - Set the **tunnel key** to **101**.  
        - Ensure the **tunnel MTU** is consistent across all sites.

6. **DMVPN Encryption**  
        - Encrypt all traffic crossing the MPLS network using **IPsec** with:  
                - A **preshared key** of **"cisco"**.  
                - **3DES encryption** and **MD5 hashing** for secure communication.

7. **EIGRP over DMVPN**  
        - Configure **EIGRP named mode "CCIE"** with **Autonomous System 123** over the DMVPN.  
        - Ensure reachability between **Host21** (in **Branch 21**) and **Host31** (in **Branch 31**).

## Quick Check

- After completing the configurations in **Section 3**, verify that **ping** works between the hosts in **Branch 21** and **Branch 31** (spoke-to-spoke connectivity).  
- Confirm that a **dynamic tunnel** is established between **R21** and **R31** spokes using appropriate show commands (e.g., `show dmvpn`, `show ip eigrp neighbors`).  
- Validate routing tables and tunnel status to ensure proper DMVPN operation.

## Next Steps

- Refer to the DMVPN topology diagram for clarity on hub-and-spoke connections and configurations.  
- Complete each task sequentially to ensure proper setup and connectivity.  
- Use diagnostic commands (e.g., `show crypto isakmp sa`, `show ip route`, `ping`) to verify encryption, routing, and connectivity across the branches.