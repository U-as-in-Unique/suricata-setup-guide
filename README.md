
# Suricata Home Lab

SURICATA is a well respected application many people use to startout with home labbing due to the fact that suricata offers a NIDS/NIPS that is easy to setup and work with.

## Overview

This project demonstrates the deployment and configuration of Suricata in a home lab environment. The objective is to monitor network traffic, detect potential threats, and gain hands-on experience with intrusion detection systems.

## Environment

- Suricata
- Linux
- Virtual Machines
- Tailscale
- Test network environment

## Features

- Network traffic inspection
- Custom rule creation
- Alert generation
- Log analysis
- Threat detection testing

## Installation

first of all install SURICATA using the command shown below.
```bash
sudo apt install suricata
```
once suricata is installed we will do a quick little checkup 
for this we will head into sudo using 
```bash
sudo
```

and then the following 
```bash
systemctl status suricata
```

