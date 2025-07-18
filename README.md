# Argo CD Applications - GitOps Repository

This repository contains the GitOps-managed applications for a personal Kubernetes cluster. It is directly linked to [Argo CD](https://argo-cd.readthedocs.io/en/stable/), which continuously ensures that the cluster state matches the declarative configuration stored here.

## Kubernetes Cluster

This repository is designed to work with the cluster defined here:  
👉 [Hamza-Ikiou/kubernetes-cluster](https://github.com/Hamza-Ikiou/kubernetes-cluster)

The cluster is provisioned locally using Vagrant, VirtualBox, and `kubeadm`, with Argo CD installed on top to manage deployed applications.

## GitOps Workflow

- Each application is defined via an Argo CD `Application` manifest under `applications/`.
- These manifests point to local Helm charts stored in `helm-charts/`.
- Argo CD is configured to monitor this Git repository and automatically apply any changes to the cluster.
- Changes to this repository (adding/updating/removing applications) are automatically reflected in the cluster state.