
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
<h3> 1) INTERFACE </h3>
get the wifi interface using (examples: eth0, enp2s0, wlan0).
   ```bash
   ip a
   ```
<h3> 2) **optional** </h3> 
you can get a dashboard to make it easier to view.
i personally tail -f  the eve.json or fast.log files but that is something i will explain later on.

   incase you do wish to install a dashboard you've got a variety to choose from. 
   The following dashboards will be ranked from lightest to heaviest.

| Name | Minimum RAM | Minimum Disk Space | Difficulty | 
|-----------|------------|-------------------|------------|
| EveBox | 512 MB | 1 GB | Easy |
| Grafana + Loki | 2 GB | 5-10 GB | Easy-Medium |
| Wazuh | 4-8 GB | 25-50 GB | Medium |
| OpenSearch Dashboards | 4 GB | 20-30 GB | Medium |
| Security Onion | 16+ GB | 200+ GB | Hard |


3) It is also important that i tell you most of your time is going to be spent in the /etc/suricata/ directory for configuring your SURICATA.
   To view your logs you're going to need the /var/log/suricata/ directory. **keep this in mind**

   We have now gone over the basics that you should know before configging the .yaml file.


## CONFIGURATION 

<h3> 
.YAML
</h3>

typing the following command will bring us to the .yaml file we need to configure SURICATA. 
```bash
cd /etc/suricata/
```
now we edit the .yaml file 
```bash
sudo nano /etc/suricata/suricata.yaml
```



