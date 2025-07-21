# Device Details

## Overview

This document provides detailed information about the devices used in the **CCIE Enterprise Infrastructure Practice Lab**, including host configurations, SDWAN edge device login credentials, and GUI access details for management platforms. Use this reference to ensure accurate configurations and seamless access to all lab components.

## Host Details

The following table lists the hosts in the lab along with their IP address assignments.

| Device Name | IP Address       |
|-------------|------------------|
| Host1       | 10.1.110.1/24    |
| Host2       | 10.1.120.1/24    |
| Host3       | 192.168.2.1/24   |
| Host4       | 192.168.3.1/24   |
| Host5       | 192.168.4.1/24   |
| Host11      | DHCP             |
| Host21      | 10.1.211.1/24    |
| Host31      | 10.1.133.1/24    |
| Host41      | 172.16.1.1/24    |
| Host42      | 172.16.1.2/24    |
| Host100     | 192.168.1.1/24   |

!!! note "Note"
    All hosts use the username **cisco** and password **cisco** for access.

## SDWAN Edge Device Login Details

The table below provides login credentials for the SDWAN edge devices (cEdge routers) in the lab.

| Device Name | Username | Password |
|-------------|----------|----------|
| cEdge1      | admin    | admin    |
| cEdge2      | cisco    | cisco    |
| cEdge3      | cisco    | cisco    |
| cEdge4      | cisco    | cisco    |

## SDA Switches Details
| Device Name | Username | Password | Enable Password |
|-------------|----------|----------|-----------------|
| sw41        | dnacadmin|C1sco12345|   cisco         |
| sw45        | dnacadmin|C1sco12345|   cisco         |
| sw43        | dnacadmin|C1sco12345|   cisco         |
| sw44        | dnacadmin|C1sco12345|   cisco         |

## GUI Access Details

The following table lists the URLs and login credentials for accessing the management platforms used in the lab.

| Device Name | URL                           | Username | Password     |
|-------------|-------------------------------|----------|--------------|
| vManage     | https://198.18.130.1:8443/    | admin    | cisco        |
| CML         | https://198.18.1.30/          | admin    | C1sco12345   |
| DNAC        | https://198.18.129.100/       | admin    | C1sco12345   |
| ISE         | https://198.18.129.30/        | admin    | C1sco123     |

!!! note "Note"
    **Use Win-Jumphost, to access vManage.**
    
## Usage Guidelines

- **Host Access**: Use the provided IP addresses and credentials to configure and verify connectivity for all hosts.
- **SDWAN Edge Devices**: Access cEdge devices using the listed credentials for CLI-based configurations and template applications.
- **Management Platforms**: Log in to vManage, CML, DNAC, and ISE using the specified URLs and credentials to manage SDWAN, lab simulations, SDA, and security policies.
- **Security**: Ensure credentials are handled securely and used only within the lab environment.

This document serves as a critical reference for navigating the lab infrastructure. Refer to it alongside the lab sections and topology diagrams to streamline your configuration and troubleshooting processes.