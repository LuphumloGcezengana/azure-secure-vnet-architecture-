# azure-secure-vnet-architecture-
Azure project demonstrating secure VNet architecture, subnet segmentation, NSGs, private VM communication, and Nginx.

#Project Overview 

This project demonstrates the deployment and configuration of a secure network architecture in Microsoft Azure using Virtual Networks, subnets, Network Security Groups (NSGs), Linux virtual machines, and Nginx.
The environment consists of two Linux virtual machines deployed into separate subnets within the same virtual network:

LGvm – Frontend/management VM
BackendVM – Backend web server

The main objective was to configure network segmentation and security controls while allowing the frontend VM to communicate with the backend VM using its private IP address.
The backend VM hosts an Nginx web server, which was successfully accessed from LGvm over the private network.

Project Objectives
1)Create an Azure Virtual Network with multiple subnets

2)Deploy Linux virtual machines into separate subnets

3)Configure Network Security Groups (NSGs)

4)Control inbound network traffic using NSG rules

5)Install and configure Nginx on the backend VM

6)Test private VM-to-VM communication

7)Verify HTTP connectivity using curl

8)Use Azure CLI and Linux Bash commands to manage and troubleshoot the environment