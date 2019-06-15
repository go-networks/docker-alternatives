# docker-alternatives

* [LXC/LXD](https://linuxcontainers.org/): The goal is to offer a distro and vendor neutral environment for the development of Linux container technologies.
<br><br>
Our main focus is system containers. That is, containers which offer an environment as close as possible as the one you'd get from a VM but without the overhead that comes with running a separate kernel and simulating all the hardware.

* [rkt](https://coreos.com/rkt/), a docker alternative, but with several different design philosophies.

* [Kata Containers](https://katacontainers.io/) is an open source community working to build a secure container runtime with lightweight virtual machines that feel and perform like containers, but provide stronger workload isolation using hardware virtualization technology as a second layer of defense. It is a merge of [Intel Clear Containers](https://github.com/clearcontainers) with [Hyper.sh RunV](https://github.com/hyperhq/runv).

* Google的[gVisor](https://github.com/google/gvisor)【 is a user-space kernel, written in Go, that implements a substantial portion of the Linux system surface. It includes an Open Container Initiative](https://www.opencontainers.org/) (OCI) runtime called `runsc` that provides an isolation boundary between the application and the host kernel. The runsc runtime integrates with Docker and Kubernetes, making it simple to run sandboxed containers.

* Amazon的[Firecracker](https://github.com/firecracker-microvm/firecracker)：Firecracker is an open source virtualization technology that is purpose-built for creating and managing secure, multi-tenant container and function-based services that provide serverless operational models. Firecracker runs workloads in lightweight virtual machines, called microVMs, which combine the security and isolation properties provided by hardware virtualization technology with the speed and flexibility of containers. 
<br><br>
The main component of Firecracker is a virtual machine monitor (VMM) that uses the Linux Kernel Virtual Machine (KVM) to create and run microVMs. Firecracker has a minimalist design. It excludes unnecessary devices and guest-facing functionality to reduce the memory footprint and attack surface area of each microVM. This improves security, decreases the startup time, and increases hardware utilization. Firecracker currently supports Intel CPUs, with planned AMD and Arm support. Firecracker will also be integrated with popular container runtimes.

* [LinuxKit](https://github.com/linuxkit/linuxkit) is a toolkit for building custom minimal, immutable Linux distributions.

* [slim](https://github.com/ottomatica/slim) will build a micro-vm from a Dockerfile. Slim works by building and extracting a rootfs from a Dockerfile, and then merging that filesystem with a small minimal kernel that runs in RAM.

* [Darch](https://godarch.com/): Think Dockerfiles, but for bootable, immutable, stateless, graphical (or not) environments for your everyday usage.

This results in a real VM that can boot instantly, while using very limited resources. If done properly, slim can allow you to design and build immutable unikernels for running services, or build tiny and embedded development environments.

### Some container related concepts and libraries

* [OCI Runtime Specification](https://github.com/opencontainers/runtime-spec)

* [CRI-O](https://cri-o.io/) is an implementation of the Kubernetes CRI (Container Runtime Interface) to enable using OCI (Open Container Initiative) compatible runtimes. It is a lightweight alternative to using Docker as the runtime for kubernetes. It allows Kubernetes to use any OCI-compliant runtime as the container runtime for running pods. Today it supports runc and Kata Containers as the container runtimes but any OCI-conformant runtime can be plugged in principle.
<br><br>
CRI-O supports OCI container images and can pull from any container registry. It is a lightweight alternative to using Docker, Moby or rkt as the runtime for Kubernetes.

* An article series about container runtimes:
  * [Part 1](https://www.ianlewis.org/en/container-runtimes-part-1-introduction-container-r)
  * [Part 2](https://www.ianlewis.org/en/container-runtimes-part-2-anatomy-low-level-contai)
  * [Part 3](https://www.ianlewis.org/en/container-runtimes-part-3-high-level-runtimes)
  * [Part 4](https://www.ianlewis.org/en/container-runtimes-part-4-kubernetes-container-run)
