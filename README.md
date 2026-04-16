# Host Discovery Service using Ryu Controller and Mininet

## Project Overview

This project implements a Host Discovery Service in an SDN environment using Mininet and the Ryu Controller.

The controller automatically detects connected hosts and stores:

* MAC Address
* IP Address
* Switch ID
* Port Number

## Problem Statement

Design and implement a Host Discovery Service that automatically detects hosts in an SDN network and maintains an updated host database.

## Tools Used

* Ubuntu Linux
* Mininet
* Ryu Controller
* Open vSwitch
* Wireshark
* Python

## Network Topology

Scenario 1: Single switch with 3 hosts

h1, h2, h3 connected to s1

Scenario 2: Single switch with 4 hosts

h1, h2, h3, h4 connected to s1

## Commands Used

Start Controller:

~/.local/bin/ryu-manager host_discovery.py

Run 3-host topology:

sudo mn --topo single,3 --controller remote

Run 4-host topology:

sudo mn -c
sudo mn --topo single,4 --controller remote

Testing:

pingall
nodes
net
dump
iperf

Flow Table:

sudo ovs-ofctl -O OpenFlow13 dump-flows s1

## Functionality

* Detects new hosts dynamically
* Maintains host database
* Learns MAC and port mapping
* Forwards packets intelligently
* Works with dynamic topology updates

## Validation

Scenario 1:
3 hosts detected successfully.

Scenario 2:
4 hosts detected successfully after topology update.

Ping connectivity successful.

## Wireshark Observation

Captured:

* ARP packets
* ICMP packets
* OpenFlow packets

## Conclusion

The Host Discovery Service was successfully implemented using Mininet and Ryu Controller. Hosts were dynamically detected and network behavior was validated successfully.
