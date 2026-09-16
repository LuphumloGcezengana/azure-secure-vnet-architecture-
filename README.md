# azure-secure-vnet-architecture-
Azure project demonstrating secure VNet architecture, subnet segmentation, NSGs, private VM communication, and Nginx.
##Project Overview 
This project demonstrates the deployment and configuration of a secure network architecture in Microsoft Azure using Virtual Networks, subnets, Network Security Groups (NSGs), Linux virtual machines, and Nginx.
The environment consists of two Linux virtual machines deployed into separate subnets within the same virtual network:
LGvm – Frontend/management VM
BackendVM – Backend web server
The main objective was to configure network segmentation and security controls while allowing the frontend VM to communicate with the backend VM using its private IP address.
The backend VM hosts an Nginx web server, which was successfully accessed from LGvm over the private network.
Project Objectives
Create an Azure Virtual Network with multiple subnets
Deploy Linux virtual machines into separate subnets
Configure Network Security Groups (NSGs)
Control inbound network traffic using NSG rules
Install and configure Nginx on the backend VM
Test private VM-to-VM communication
Verify HTTP connectivity using curl
Use Azure CLI and Linux Bash commands to manage and troubleshoot the environment