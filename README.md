# azure-secure-vnet-architecture-
Azure project demonstrating secure VNet architecture, subnet segmentation, NSGs, private VM communication, and Nginx.

##Project Overview 

This project demonstrates the deployment and configuration of a secure network architecture in Microsoft Azure using Virtual Networks, subnets, Network Security Groups (NSGs), Linux virtual machines, and Nginx.
The environment consists of two Linux virtual machines deployed into separate subnets within the same virtual network:

LGvm – Frontend/management VM
BackendVM – Backend web server

The main objective was to configure network segmentation and security controls while allowing the frontend VM to communicate with the backend VM using its private IP address.
The backend VM hosts an Nginx web server, which was successfully accessed from LGvm over the private network.

##Project Objectives
1)Create an Azure Virtual Network with multiple subnets

2)Deploy Linux virtual machines into separate subnets

3)Configure Network Security Groups (NSGs)

4)Control inbound network traffic using NSG rules

5)Install and configure Nginx on the backend VM

6)Test private VM-to-VM communication

7)Verify HTTP connectivity using curl

8)Use Azure CLI and Linux Bash commands to manage and troubleshoot the environment

## Network Configuration

The Azure environment was deployed inside a single Virtual Network with separate subnets for the frontend and backend workloads.

### Virtual Machines

| VM        | Role                   | Private IP | Public IP         |
| --------- | ---------------------- | ---------- | ----------------- |
| LGvm      | Frontend/management VM | `10.0.1.4` | `102.133.226.195` |
| BackendVM | Backend web server     | `10.0.2.4` | None              |

### Subnets

| Subnet         | Address Range | Purpose                |
| -------------- | ------------- | ---------------------- |
| LGsubnet       | `10.0.1.0/24` | Frontend/management VM |
| PrivateSubnet1 | `10.0.2.0/24` | Backend VM             |

The backend VM was placed in a separate subnet and accessed using its private IP address rather than a public IP.

### Network Security Groups

Network Security Groups were used to control inbound traffic.

| Rule      | Priority | Protocol | Direction | Port | Access |
| --------- | -------: | -------- | --------- | ---: | ------ |
| AllowSSH  |      100 | TCP      | Inbound   |   22 | Allow  |
| AllowHTTP |      110 | TCP      | Inbound   |   80 | Allow  |

SSH access was permitted on port 22 for administration, while HTTP traffic was permitted on port 80 for the Nginx web server.
