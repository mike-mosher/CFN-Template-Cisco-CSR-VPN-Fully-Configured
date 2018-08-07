# CFN-Template-Cisco-CSR-VPN-Fully-Configured

## Description

This aws cloudformation template was designed to quickly spin up a VPN tunnel from a VGW in one VPC to a Cisco CSR instance in another VPC.  A Lambda Custom Resource is used to configure the Cisco CSR so that the VPN tunnels will automatically come up.  After this, there is an EC2 instance in each VPC that can be used to ping back and forth to test the tunnels

The reason that I created this template was to quickly allow me to reproduce an issue wherein I needed to get on the Cisco IOS command line and troubleshoot an active IPSec VPN connection.

## Overview

This template spins up the following resources:

- Two new VPCs (OnPrem VPC and Cloud VPC)
- one EC2 instance in each VPC to use for testing the tunnels
- a Virtual Private Gateway (VGW) in the Cloud VPC
- a Cisco CSR instance in the OnPrem VPC (to be used as the customer gateway - CGW)

## How to use

Spin up the template, and then SSH to the Cisco CSR to verify the tunnels.  The username and password that you provide in the template parameters are used to login to the CSR.  You can also SSH to the EC2 instaces in each VPC to ping across the tunnels
