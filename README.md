# Networks-2-Project-Mininet

This repository contains the implementation of four exercises for the Networking Final Project. The project explores various network functionalities using Mininet and Ryu Controller, focusing on ARP spoofing, static routing, and VLAN setup with OpenFlow.

## Table of Contents

1. [Introduction](#introduction)
2. [Project Structure](#project-structure)
    1. [Exercise 1: ARP Spoofing](#exercise-1-arp-spoofing)
    2. [Exercise 2: Static Routing](#exercise-2-static-routing)
    3. [Exercise 3: Static Routing with Two Routers](#exercise-3-static-routing-with-two-routers)
    4. [Exercise 4: VLAN with OpenFlow](#exercise-4-vlan-with-openflow)
3. [Setup and Installation](#setup-and-installation)
4. [Running the Exercises](#running-the-exercises)
5. [Notes and Considerations](#notes-and-considerations)
6. [References](#references)
7. [License](#license)

## Introduction

This project demonstrates the use of the Ryu framework to develop network functionalities on top of the Mininet network emulator. The exercises showcase different network configurations and functionalities such as ARP spoofing, static routing between LANs, and VLAN implementation using OpenFlow v1.0.

## Project Structure

### Exercise 1: ARP Spoofing

- **Script:** `arp-spoofing.py`
- **Objective:** To create a switch that intercepts ARP requests and replies with appropriate ARP responses without forwarding the request to the intended recipient.
- **Description:** 
  - This exercise involves setting up a Ryu controller that acts as an intermediary for ARP requests. Instead of allowing the ARP request to reach its intended destination, the controller generates and sends a fake ARP reply, effectively "spoofing" the response.
  - **Key Learning Points:**
    - Understanding the ARP protocol and how ARP requests/responses work in a network.
    - Implementing packet inspection and generation using Ryu and OpenFlow v1.0.
  
### Exercise 2: Static Routing

- **Script:** `mininet-router.py`
- **Objective:** To create a static router that interconnects two switches, enabling routing between two LANs.
- **Description:**
  - This exercise extends the basic networking concepts by introducing static routing between two separate LANs. The router replies to ARP requests for its IP addresses and forwards packets between the LANs by adjusting the Ethernet headers.
  - **Key Learning Points:**
    - Setting up static routing in a Mininet environment.
    - Implementing ARP reply generation and packet forwarding using flow rules in Ryu.

### Exercise 3: Static Routing with Two Routers

- **Script:** `mininet-router-two.py`
- **Objective:** To extend the static routing scenario by introducing two routers that connect two LANs.
- **Description:**
  - This exercise builds on the previous one by adding another router, creating a more complex network topology. The routers communicate with each other to forward packets between the LANs.
  - **Key Learning Points:**
    - Understanding inter-router communication and routing between multiple LANs.
    - Configuring Ryu to handle routing across multiple devices with dynamic flow rules.

### Exercise 4: VLAN with OpenFlow

- **Scripts:** `mininet-router-vlan.py`, `mininet-router-vlan-extended.py`
- **Objective:** To implement a network with VLANs using two interconnected switches and routers.
- **Description:**
  - This final exercise involves creating two VLANs, each associated with a separate IP network, using OpenFlow in a Mininet environment. The routers handle inter-VLAN routing, and the switches manage VLAN encapsulation and decapsulation.
  - **Key Learning Points:**
    - Setting up and managing VLANs within a software-defined network.
    - Handling VLAN tagging and routing across VLANs using Ryu.
    - Implementing additional functionality like ICMP response for unreachable destinations and high-priority traffic routing between routers.

## Setup and Installation

### Prerequisites

- **Mininet:** Version 2.3.0 or higher
- **Ryu Controller:** Version 4.34 or higher
- **Python:** Version 3.6 or higher
- **Linux Environment:** Recommended for running Mininet and Ryu

### Installation

1. **Clone the Repository:**
   ```bash
   git clone https://github.com/your-username/networking-final-project.git
   cd networking-final-project
