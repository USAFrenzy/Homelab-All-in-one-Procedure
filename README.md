<h1 align="center"> Homelab-All-in-one-Procedure </h1>
<br>
<p align="center"> Aggregating and updating procedures for my homelab environment. This is intended to be a SOP-like document that will allow for recreation of my current environment. This will also hold any troubleshooting and update/maintenance procedures involved with my environment.</p>
<br><br>

   Table of Contents
---------------------------

1. Architecture & Overview
   * Proxmox Server Specifications
   * TrueNAS SCALE for Storage
   * pfSense for Firewall/Networking
   * SIEM & Cybersecurity Stack
     * Wazuh
     * Greenbone Vulnerability Management (GVM)
     * MISP, TheHive, Cortex
     * Kubernetes Cluster Layout
     * Dedicated PKI with Offline Root CA and Online Intermediate CA
2. VM and Resource Tally
   * 2.1 PKI Infrastructure
     * Offline Root CA VM
     * Intermediate CA VM
   * 2.2 Existing / Supporting VMs
     * NTP Servers
     * Load Balancers
     * TrueNAS Integration
   * 2.3 SIEM / Cybersecurity VMs
     * Wazuh Manager + Dashboard
     * Wazuh Indexer (OpenSearch)
     * Greenbone VM
     * MISP + TheHive + Cortex
   * 2.4 Future Kubernetes Cluster
     * Master Nodes
     * Worker Nodes
   * 2.5 Grand Total Resource Utilization
3. PKI Infrastructure
   * 3.1 Offline Root CA VM
     * VM Setup
     * Generating Root Key and Self-Signed Root Certificate
     * Creating CRLs (Optional)
   * 3.2 Intermediate CA VM
     * VM Setup and Key Generation
     * Signing the Intermediate CSR with the Root CA
     * Issuing Certificates from the Intermediate CA
   * 3.3 Certificate Issuance Workflow
     * CSR Generation on Target Hosts
     * Certificate Signing by Intermediate CA
     * Deployment to Hosts
   * 3.4 Certificate Distribution
     * Linux, Windows, pfSense, and HAProxy Integration
   * 3.5 Maintenance and Security Considerations
4. Proxmox & TrueNAS Preparation
     * Configuring Storage Pools
     * Networking and Bandwidth Optimization
5. Debian VM Creation
     * Steps for VM Deployment
     * Base OS Installation and Configuration
6. SIEM / Cybersecurity Deployment
   * 6.1 Wazuh
     * Manager + Dashboard VM Setup
     * Indexer Setup
   * 6.2 Greenbone Vulnerability Management (GVM)
   * 6.3 MISP + TheHive + Cortex
     * Integration Steps
     * Use Cases and Workflows
7. Network Flow & TLS Handshake
     * pfSense → Load Balancers → Kubernetes / Services
     * Certificates in a Multi-Hop Environment
8. Expanding to Cloudflare
     * Public vs. Internal Domain Management
     * SSL Certificate Scenarios
9. Kubernetes Integration
   * 9.1 Cluster Creation and Initialization
     * Prerequisites and Environment Preparation
     * Generating and Signing Kubernetes Cluster Certificates
     * Initializing the Kubernetes Cluster with kubeadm
     * Joining Additional Nodes
     * Networking with MetalLB and Calico
     * Integration with pfSense and Load Balancers
   * 9.2 Installing and Configuring Traefik
   * 9.3 Installing Falco, kube-bench, kube-hunter, and Fluent Bit
   * 9.4 Integrating Cluster with Wazuh and Security Tools
   * 9.5 Linking Cluster to NTP Servers
   * 9.6 Provisioning Storage from TrueNAS
   * 9.7 Certificates for Services in PKI Context
   * 9.8 Finalizing Cluster Functionality
10.  Maintenance and Upgrades
   * 10.1 Certificate Management
     * Renewals, Rotations, Revocations
   * 10.2 Updating SIEM/Cybersecurity Components
   * 10.3 Updating Virtual Machine Hosts
   * 10.4 General Troubleshooting and Backups
     * Troubleshooting Common Issues
     * Backup Procedures
   * 10.5 Automation Scripts and Tools