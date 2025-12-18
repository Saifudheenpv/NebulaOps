🚀 NebulaOps – DevOps & GitOps Platform
NebulaOps is a self-hosted DevOps and GitOps platform built from scratch to demonstrate real-world Kubernetes platform engineering, automation, GitOps workflows, ingress-based traffic management, and full observability.
This project goes beyond tutorials and showcases how modern DevOps systems are designed, deployed, operated, and monitored in real environments.

🎯 Project Purpose
The goal of NebulaOps is to build a production-style Kubernetes platform that demonstrates:
Infrastructure automation
GitOps-based application delivery
Secure and scalable traffic routing
Cluster and application observability
Real troubleshooting and operational skills
This project is designed for learning, showcasing skills, and interview readiness.

🏗️ Architecture Overview
NebulaOps runs on a multi-node Kubernetes cluster:
servera – Control Plane & Platform Services
serverb – Worker Node (Application workloads)
The cluster is built using kubeadm and managed using Ansible, following best practices.

🔁 High-Level Architecture Flow
Developer
   |
   | git push
   v
GitHub (GitOps Repository)
   |
   | Continuous Sync
   v
ArgoCD (GitOps Engine)
   |
   | Kubernetes API
   v
Kubernetes Cluster
   |
   |-------------------------------|
   |                               |
Application Pods             Platform Services
(NGINX App)                  (Prometheus, Grafana)
   |
   | HTTP Routing
   v
NGINX Ingress Controller
   |
   | NodePort / SSH Tunnel
   v
User Browser

🧩 Components Explained

1️⃣ Infrastructure & Automation
Operating System: Ubuntu 24.04
Provisioning: Virtual machines
Configuration Management: Ansible
Container Runtime: containerd
Orchestration: Kubernetes (kubeadm)

Ansible is used to prepare the operating system, install Docker/containerd, and configure Kubernetes prerequisites consistently across nodes.

2️⃣ Kubernetes Platform

Multi-node Kubernetes cluster
Proper node roles (control-plane & worker)
CNI networking using Flannel
Secure CRI configuration using systemd cgroups

This setup reflects how real on-prem or cloud Kubernetes clusters are initialized.

3️⃣ GitOps with ArgoCD (Core Feature)

GitHub is the single source of truth
ArgoCD continuously watches the Git repository
Any change in Git automatically syncs to the cluster
No manual kubectl apply for applications

This ensures declarative, auditable, and automated deployments.

4️⃣ Application Delivery

Sample NGINX application deployed via GitOps
Kubernetes Deployment & Service
Traffic routed using NGINX Ingress Controller
Host-based routing implemented

This demonstrates real-world traffic flow:

User → Ingress → Service → Pod

5️⃣ Observability & Monitoring

Metrics Server for resource metrics
Prometheus for scraping cluster and pod metrics
Grafana for visualization

Dashboards include:

Node CPU & memory usage
Pod-level resource usage
Namespace-level metrics
Cluster health overview

This proves the platform is operable and observable, not just deployable.

6️⃣ Secure Access & Networking

Cluster runs on a libvirt NAT network
External access handled using:
    SSH tunneling
    kubectl port-forward

This reflects real lab and enterprise network constraints and shows practical troubleshooting skills.

🧰 Technology Stack

Ansible
Docker
containerd
Kubernetes
Helm
ArgoCD
NGINX Ingress Controller
Prometheus
Grafana
GitHub

📸 Project Evidence

Screenshots included in this repository demonstrate:

    ArgoCD application health & sync
    Grafana cluster and pod metrics
    Kubernetes nodes and pods status

These provide verifiable proof of the platform working end-to-end.

📊 Architecture Diagram

The full architecture diagram is available in:

docs/architecture.png

It visually represents:

    GitOps flow
    Kubernetes cluster layout
    Ingress routing
    Observability pipeline

🧠 What This Project Demonstrates

    Real DevOps and platform engineering skills
    GitOps principles in practice
    Kubernetes networking and ingress design
    Monitoring and observability setup
    Troubleshooting container runtime, ingress, and networking issues
    Clean documentation and project presentation

🏁 Project Status

NebulaOps v1.0 – Completed ✅

This version represents a stable, production-style DevOps platform.

Future enhancements (optional):

    CI pipelines (GitHub Actions)
    Helm & Kustomize
    Private repositories & secrets
    Cloud deployment (AWS / Azure / GCP)
    Autoscaling and load testing

👤 Author
Saifudheen PV
Aspiring DevOps / AWS / Azure / Redhat