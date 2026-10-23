
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
- Dashboard (optional) 

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
now that that's out of the way we can get started with the requirements we need to know before we touch the .yaml file.

1)get the wifi interface using (examples: eth0, enp2s0, wlan0).
   ```bash
   ip a
   ```
2)**optional** you can get a dashboard to make it easier to view.
   i personally tail -f  the eve.json or fast.log files but that is something i will explain later on.

   incase you do wish to install a dashboard you've got a variety to choose from. 
   The following dashboards will be ranked from lightest to heaviest.

    **EveBox**
   -min RAM: 512MB
      -min DISK: 1GB
         difficulty: easy

   **Grafana + Loki**
   -min RAM: 2GB
      -min DISK: 5-10GB
         difficult: Medium

   **Opensearch**
   -min RAM: 4GB
      -min DISK: 20-30 GB
         difficulty: medium
   
   **Wazuh**
   -min RAM: 4-8GB
      -min DISK: 25-50GB
         difficulty: medium

   **Security Onion**
   -min RAM: 16GB+
      -min DISK: 200GB+
         difficulty: HARD



   

4) 




