# Section 5: Software-Defined Access (SDA) Configuration

## Overview

This section outlines the configuration tasks for setting up a **Software-Defined Access (SDA)** environment using **Cisco DNA Center (DNAC)**. The tasks focus on verifying the integration with **ISE**, creating security groups, assigning ports, and implementing a security policy to control communication between hosts. The provided topology diagram illustrates the SDA fabric and device roles to guide the configuration process.

### SDA Network Topology

![SDA Network Topology](image-6.png "Network topology diagram for SDA, showing connections between border nodes (sw41, sw45), edge nodes (sw43, sw44), and hosts")

**Diagram Description**: The SDA topology depicts the fabric infrastructure, with **sw41** and **sw45** as **border nodes** and **sw43** and **sw44** as **edge nodes**. The diagram highlights the connections to **Host41** (connected to sw43) and **Host42** (connected to sw44). Focus on the security group assignments and policy configurations within DNAC to manage traffic between these hosts.

!!! note "Note"
        In case if the swithces shows unreachable in DNAC, go to CML and do right click on the links connected to DNAC using L2 switch and click on Connect.

!!! note "Note"
        If you are not able to ping between Host41 and Host42, then first ping the default-gateway IP (172.16.1.254) from both the hosts and then ping between the hosts. It will be successful.


## Task List

### DNAC and ISE Configuration

1. **ISE Integration Verification**  
        - Log in to **Cisco DNA Center (DNAC)** and verify that **ISE** is in an **ACTIVE state**.  
        - Confirm that the **migration process** to integrate ISE with DNAC is complete.

### Security Group Configuration

2. **Security Group Creation**  
        - Create two security groups in DNAC:  
            - **SEC_H41** for **sw43**.  
            - **SEC_H42** for **sw44**.

### Port Assignment

3. **Port Assignment in Fabric Sites**  
        - Assign ports under the fabric site in DNAC:  
            - Assign **G1/0/1** on **sw43** to the **SEC_H41** security group.  
            - Assign **G1/0/1** on **sw44** to the **SEC_H42** security group.

### Security Policy Configuration

4. **Security Policy Creation**  
        - Create a **security policy** in DNAC to **block communication** between the **SEC_H41** and **SEC_H42** security groups.

### Connectivity Verification

5. **Ping Verification**  
        - Verify that **ping** between **Host41** (connected to sw43) and **Host42** (connected to sw44) is **blocked** due to the security policy.

## Quick Check

- After completing the configurations in **Section 5**, confirm that **ping** between **Host41** and **Host42** is **blocked**.  
- Use DNAC tools and CLI commands (e.g., `ping`, `show cts role-based permissions`) on **sw43** and **sw44** to validate the security policy enforcement.

## Next Steps

- Refer to the SDA topology diagram for clarity on device roles and connections.  
- Complete each task sequentially to ensure proper setup and policy enforcement.  
- Validate configurations using DNAC dashboards and CLI commands to confirm ISE integration, security group assignments, and traffic blocking.