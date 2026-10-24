
# Suricata Home Lab

SURICATA is a well respected application many people use to start with when home labbing due to the fact that suricata offers a NIDS/NIPS that is easy to setup and work with.

## Overview

This project demonstrates the deployment and configuration of Suricata in a home lab environment  **!!FOR LINUX!!**. The objective is to monitor network traffic, detect potential threats, and gain hands-on experience with intrusion detection systems.

## Environment

- Suricata
- Linux
- Virtual Machines (optional for dashboard)
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
once installed check the status. 
```bash
systemctl status suricata
```
now that that's out of the way we can get started with the requirements we need to know before we touch the .yaml file.
 1) **INTERFACE**
get the wifi interface using (examples: eth0, enp2s0, wlan0).
   ```bash
   ip a
   ```
2) **OPTIONAL** 
you can get a dashboard to make it easier to view.
i personally "tail -f"  the eve.json or fast.log files but that is something i will explain later on.

   incase you do wish to install a dashboard you've got a variety to choose from. 

| Name | Minimum RAM | Minimum Disk Space | Difficulty | 
|-----------|------------|-------------------|------------|
| EveBox | 512 MB | 1 GB | Easy |
| Grafana + Loki | 2 GB | 5-10 GB | Easy-Medium |
| Wazuh | 4-8 GB | 25-50 GB | Medium |
| OpenSearch Dashboards | 4 GB | 20-30 GB | Medium |
| Security Onion | 16+ GB | 200+ GB | Hard |


3) It is also important that i tell you most of your time is going to be spent in the /etc/suricata/ directory for configuring your SURICATA.
   To view your logs you're going to need the /var/log/suricata/ directory. **keep this in mind**

   Enter the following command to download the latest emerging threat rules. **(   !! this command reboots your device !! )** 
   ```bash
   sudo suricata-update
   ```

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

once inside the .yaml file we head on over to - address-groups -
change this to your ip address. this can be for either the entire network (preferred) or one device.

<img width="600" height="400" align="center" alt="Screenshot 2026-10-23 215534" src="https://github.com/user-attachments/assets/06d532d1-ed9c-49bf-a202-ce55c9e69ac7" />

**the hashtags are comments uncomment this by removing the hashtag**

Now that you've adjusted the HOME_ADDRESS we can move onto af-packet where you will enter your network interface. In my case it's eth0.
<img width="600" height="400" alt="Screenshot 2026-10-23 220153" src="https://github.com/user-attachments/assets/ebfa0d9d-77d3-4e54-ae32-74785b8904c7" />


## TEST
once you've exited the .yaml file the next step is to test the configuration you have just done.
```bash
sudo suricata -T -c /etc/suricata/suricata.yaml
```
if output is: Configuration provided was successfully loaded
you are good to go.

now that that's out the way we can start suricata.
```bash
sudo systemctl enable suricata
sudo systemctl start suricata
```
and then check status again 
```bash
sudo systemctl status suricata
```
<img width="600" height="150" alt="image" src="https://github.com/user-attachments/assets/79a1bfea-4b27-4c72-bda0-30ac2edde346" />

## POST-INSTALLATION 
you can now enjoy the NIDS you've configured to work for your own network.
if you wish to add some of your own rules I will leave some basic rules for different kinds of attacks <a href="https://github.com/unique-bhujel/suricata-setup-guide/blob/main/RULES.md">here</a>















