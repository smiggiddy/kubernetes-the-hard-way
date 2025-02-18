> This tutorial is a modified version of the original developed by [Kelsey Hightower](https://github.com/kelseyhightower/kubernetes-the-hard-way) and [Mumshad Mannambeth](https://github.com/mmumshad/kubernetes-the-hard-way). As well as a modified version of the KodeKloud version. I'm using this guide to bootstrap a k8s cluster on XCP-ng. I'm using this to prepare to study for CKA exam. Please feel free to follow along, but this guide will include a few assumptions:
> 1. That you can architech your own hypervisor and underlying networking components to get everything working. 
> 2. that you're somewhat familiar with ansible and 
For a more hands on aproach please follow one of the original tutorials. [Mumshad Mannambeth's Tutorial here](https://github.com/mmumshad/kubernetes-the-hard-way)
> I'll be using the latest verions of the packaging. As I'm updating this document as I'm going some links / refs may not be current. I'll include the step I'm currently working through so if you'd like you can follow along.  
> Step 5 k8s configuration




# Kubernetes The Hard Way using XCP-ng

This tutorial walks you through setting up Kubernetes the hard way on a local machine using XCP-NG.
This guide is not for people looking for a fully automated command to bring up a Kubernetes cluster.
If that's you then check out [Google Kubernetes Engine](https://cloud.google.com/kubernetes-engine), or the [Getting Started Guides](http://kubernetes.io/docs/getting-started-guides/).

Kubernetes The Hard Way is optimized for learning, which means taking the long route to ensure you understand each task required to bootstrap a Kubernetes cluster.

This tutorial is a modified version of the original developed by [Kelsey Hightower](https://github.com/kelseyhightower/kubernetes-the-hard-way).
While the original one uses GCP as the platform to deploy kubernetes,  I use XCP-NG and Ansible to deploy a cluster on a networked machine. If you prefer the cloud version, refer to the original one [here](https://github.com/kelseyhightower/kubernetes-the-hard-way)

<!-- Another difference is that we use Docker instead of containerd. There are a few other differences to the original and they are documented [here](docs/differences-to-original.md) -->

> The results of this tutorial should not be viewed as production ready, and may receive limited support from the community, but don't let that stop you from learning!

## Target Audience

The target audience for this tutorial is someone planning to support a production Kubernetes cluster and wants to understand how everything fits together.

## Cluster Details

Kubernetes The Hard Way guides you through bootstrapping a highly available Kubernetes cluster with end-to-end encryption between components and RBAC authentication.

* [Kubernetes](https://github.com/kubernetes/kubernetes) v1.25.0
* [Docker Container Runtime](https://github.com/containerd/containerd) 18.06
* [CNI Container Networking](https://github.com/containernetworking/cni) 0.7.5
* [Weave Networking](https://www.weave.works/docs/net/latest/kubernetes/kube-addon/)
* [etcd](https://github.com/coreos/etcd) v3.3.9
* [CoreDNS](https://github.com/coredns/coredns) v1.2.2

## Labs

* [Prerequisites](docs/01-prerequisites.md)
* [Provisioning Compute Resources](docs/02-compute-resources.md)
* [Installing the Client Tools](docs/03-client-tools.md)
* [Provisioning the CA and Generating TLS Certificates](docs/04-certificate-authority.md)
* [Generating Kubernetes Configuration Files for Authentication](docs/05-kubernetes-configuration-files.md)
* [Generating the Data Encryption Config and Key](docs/06-data-encryption-keys.md)
* [Bootstrapping the etcd Cluster](docs/07-bootstrapping-etcd.md)
* [Bootstrapping the Kubernetes Control Plane](docs/08-bootstrapping-kubernetes-controllers.md)
* [Bootstrapping the Kubernetes Worker Nodes](docs/09-bootstrapping-kubernetes-workers.md)
* [TLS Bootstrapping the Kubernetes Worker Nodes](docs/10-tls-bootstrapping-kubernetes-workers.md)
* [Configuring kubectl for Remote Access](docs/11-configuring-kubectl.md)
* [Deploy Weave - Pod Networking Solution](docs/12-configure-pod-networking.md)
* [Kube API Server to Kubelet Configuration](docs/13-kube-apiserver-to-kubelet.md)
* [Deploying the DNS Cluster Add-on](docs/14-dns-addon.md)
* [Smoke Test](docs/15-smoke-test.md)
* [E2E Test](docs/16-e2e-tests.md)
* [Extra - Dynamic Kubelet Configuration](docs/17-extra-dynamic-kubelet-configuration.md)
* [Extra - Certificate Verification](docs/verify-certificates.md)
