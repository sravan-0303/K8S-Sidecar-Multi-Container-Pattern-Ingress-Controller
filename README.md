
Kubernetes Practicals: Sidecar Pattern & Ingress Controller


This repository contains two separate Kubernetes practicals:

1. Sidecar Multi-Container Pattern (sidecar.yml)
2. Ingress Controller (ingress.yml)

---


1. Sidecar Multi-Container Pattern


Overview:
Demonstrates the sidecar pattern in Kubernetes where a pod contains multiple containers:
- Main container: Runs the primary application
- Sidecar container: Handles auxiliary tasks such as logging, monitoring, or data processing

Key Concepts:
- Multi-container pods
- Container communication via shared volumes
- Logs or data aggregation using a sidecar

Advantages:
- Decouples auxiliary tasks from the main application
- Improves maintainability and scalability
- Enables reusability of sidecar containers across multiple pods

File:
- sidecar.yml – Pod manifest containing both main and sidecar containers

Usage:
Deploy the pod using:
$ kubectl apply -f sidecar.yml
$ kubectl get pods
$ kubectl logs <pod-name> -c <container-name>

---


2. Ingress Controller

Overview:
Demonstrates how to expose Kubernetes services externally using an Ingress Controller.

Key Concepts:
- Difference between Service and Ingress
- Routing traffic to multiple services
- Host/path-based routing

Advantages:
- Provides a single entry point for multiple services
- Enables host- or path-based routing for flexible traffic management
- Simplifies external access without creating multiple LoadBalancers

Files:
- ingress.yml – Ingress manifest pointing to back-end services
- ngnix-app.yml – Nginx application service
- httpd-app.yml – HTTPD application service

Usage:
Deploy the services and ingress using:
$ kubectl apply -f ngnix-app.yml
$ kubectl apply -f httpd-app.yml
$ kubectl apply -f ingress.yml
$ kubectl get pods
$ kubectl get ingress

---

References:
- Kubernetes Sidecar Pattern: https://kubernetes.io/docs/concepts/cluster-administration/logging/
- Kubernetes Ingress: https://kubernetes.io/docs/concepts/services-networking/ingress/
