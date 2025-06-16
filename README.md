# OSPF Routing in a Simulated Internet – COMPX304 Assignment 1

This project simulates the configuration of an internal network using **OSPF (Open Shortest Path First)** in a virtual "mini-Internet" lab environment. It was developed for **COMPX304 – Advanced Networking & Cyber Security** at the University of Waikato.

## 🗺️ Project Goals

- Understand and implement OSPFv2 using **FRRouting (FRR)**
- Configure IP addresses and subnets for an assigned Autonomous System (AS)
- Ensure full intra-AS connectivity using router and host configurations
- Optimize routing using **OSPF link cost tuning**
- Use real router-style CLI (Cisco-like) for network configuration

## ⚙️ Technologies Used

- **FRRouting (FRR)** – Open-source routing protocol suite
- **Linux networking** tools: `ip`, `ping`, `traceroute`, `tcpdump`, `iperf3`
- **SSH access to Docker-based routers/hosts**
- **Git + GitLab** for config version control

## 🏗️ Network Topology

- 8 routers: LOND, HAML, PARI, TRGA, NEWY, BOST, ATLA, ZURI
- Each router has one host attached via a directly connected subnet
- Assigned IP ranges: `X.0.0.0/8`, where `X` is the AS number
- Loopback IPs, host subnet IPs, and router interconnections based on assignment plan

## 📋 Key Features Implemented

- 🔧 **Interface Configuration** for routers and hosts
- 🔁 **OSPF Setup** with backbone area `0.0.0.0` and router loopbacks as OSPF router IDs
- 🌐 **Full network connectivity**: Any host can reach any other host and router
- 🛡️ **Security**: OSPF not enabled on interfaces connected to hosts
- 🚀 **Traffic Engineering**: Adjusted link costs based on real latency tests
- 📈 **Performance Measurement**: Used `ping`, `traceroute`, and `iperf3` to analyze routing performance

## 📝 Project Structure

- configs/ # Saved configurations from ./save_configs.sh
- step-9.txt # Latency & bandwidth test results
- step-10.txt # High-latency baseline measurements
- step-11.txt # Link cost planning
- step-12.txt # Improved routing performance measurements
- readme.md # This file

## 🔄 Sample Commands

```bash
# SSH access
ssh username@linux-labs.cms.waikato.ac.nz
ssh root@mini.cms.waikato.ac.nz -p <your-port>

# Enter router
./goto.sh HAML router

# Enter host
./goto.sh NEWY host

# Save configuration snapshot
./save_configs.sh