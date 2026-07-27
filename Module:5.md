# 📦 Module 5: Containers & Kubernetes

![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)
![Kubernetes](https://img.shields.io/badge/Kubernetes-326CE5?style=for-the-badge&logo=kubernetes&logoColor=white)
![IBM Cloud](https://img.shields.io/badge/IBM%20Cloud-052FAD?style=for-the-badge&logo=ibm&logoColor=white)
![YAML](https://img.shields.io/badge/YAML-CB171E?style=for-the-badge&logo=yaml&logoColor=white)

> **Duration:** 3 Days • **Format:** Lecture + Hands-On • **Level:** Beginner → Intermediate

Welcome to Module 5! This is where infrastructure gets modern. You'll go from *"what even is a container?"* to actually deploying an application on **IBM Kubernetes Service (IKS)**. Keep this README open on the side — it's built for daily revision, interview prep, and quick lookup, not for reading cover-to-cover in one sitting.

> 🧠 **Prerequisites:** Basic Linux commands, comfort with the terminal, and a rough idea of client-server architecture. Nothing more.

---

## 🗺️ Module Roadmap

```
Container Fundamentals   (What & Why containers exist)
        ↓
Docker Deep Dive          (The most popular container engine)
        ↓
Dockerfile & YAML         (How to define containers as code)
        ↓
Container Orchestration   (Why one container is never enough)
        ↓
Kubernetes Administration (Managing containers at scale)
        ↓
IBM Cloud IKS              (Running it all in production)
```

---

## 🗂️ Table of Contents

**Section A — Container Fundamentals**
- [5.1 What is a Container?](#51-what-is-a-container)
- [5.2 VMs vs Containers](#52-vms-vs-containers)
- [5.3 Containerization Technologies](#53-containerization-technologies)

**Section B — Docker Deep Dive**
- [5.4 What is Docker?](#54-what-is-docker)
- [5.5 How Docker Works](#55-how-docker-works)
- [5.6 Docker Editions](#56-docker-editions)
- [5.7 Docker Core Concepts](#57-docker-core-concepts)
- [5.8 Docker Installation](#58-docker-installation)
- [5.9 Docker Commands](#59-docker-commands)

**Section C — Dockerfile & YAML**
- [5.10 Writing Dockerfiles](#510-writing-dockerfiles)
- [5.11 Docker Compose](#511-docker-compose)
- [5.12 YAML Basics](#512-yaml-basics)

**Section D — Container Orchestration**
- [5.13 What is Container Orchestration?](#513-what-is-container-orchestration)

**Section E — Kubernetes Administration**
- [5.14 Kubernetes Overview](#514-kubernetes-overview)
- [5.15 Kubernetes Architecture](#515-kubernetes-architecture)
- [5.16 Kubernetes Resource Model](#516-kubernetes-resource-model)
- [5.17 Kubernetes Orchestration](#517-kubernetes-orchestration)
- [5.18 Creating a Cluster](#518-creating-a-cluster)
- [5.19 IBM Cloud IKS](#519-ibm-cloud-iks)
- [5.20 Deploy MW Application on Kubernetes/IKS](#520-deploy-mw-application-on-kubernetesiks)

**Wrap-Up**
- [✅ Hands-On Practice Goals](#-hands-on-practice-goals)
- [📋 Master Quick Revision Cheat Sheet](#-master-quick-revision-cheat-sheet)
- [🎯 Top Interview Q&A](#-top-interview-qa-quick-fire)

---

# SECTION A: Container Fundamentals

## 5.1 What is a Container?

### Introduction

Every developer knows the pain: *"It worked on my machine!"* — and then it breaks the moment it hits testing or production. Different OS versions, missing dependencies, mismatched library versions — the app that ran perfectly on a laptop suddenly refuses to start on a server.

Containers exist to kill that problem permanently. A container packages an application **along with everything it needs to run** — code, runtime, system libraries, configuration — into a single, portable unit. That unit behaves identically whether it's running on your laptop, a teammate's machine, or a cloud server in another country.

### Why Do We Need It?

- Apps fail due to **environment differences** (different OS, missing libraries, version mismatches)
- Setting up a new dev environment manually takes hours (sometimes days)
- Traditional VMs solve isolation but are **heavy and slow to start**
- Modern applications (microservices) need something **lightweight** that can spin up and down in seconds

### Definition

> **A container is a lightweight, standalone, executable software package that bundles an application with everything it needs to run — code, runtime, libraries, and settings — so it runs consistently across any environment.**

### How It Works

Containers don't virtualize hardware like a VM does. Instead, they share the **host machine's OS kernel** and use two core Linux kernel features to stay isolated:

| Kernel Feature | Role |
|---|---|
| **Namespaces** | Isolate what a process can *see* (its own PID, network, filesystem, hostname) |
| **cgroups (Control Groups)** | Isolate what a process can *use* (CPU, memory, disk I/O limits) |

```
Application
    ↓
Container
    ↓
Container Engine (Docker / containerd)
    ↓
Host OS (Linux Kernel)
    ↓
Hardware
```

Because there's no separate guest OS to boot, containers start in **milliseconds to seconds**, not minutes.

### Real World Example / Analogy

> 🚢 **Shipping Container Analogy:** Before standardized shipping containers existed, loading a ship was chaos — every type of cargo needed different handling. Once the standard steel container was invented, any crane, ship, or truck anywhere in the world could handle it, regardless of what was *inside* it. Software containers do the same thing for applications — standardize the "box" so any server, cloud, or laptop can run it identically.

### Key Components

| Component | Description |
|---|---|
| **Image** | Read-only template used to create a container |
| **Container Runtime** | Software that runs containers (e.g., containerd, CRI-O) |
| **Namespaces** | Provide process isolation |
| **cgroups** | Enforce resource limits |
| **Union File System** | Layers multiple filesystems into one (used for images) |

### Advantages

- ✅ Lightweight — shares host OS kernel
- ✅ Fast startup (seconds, not minutes)
- ✅ Portable across environments
- ✅ Consistent — "works on my machine" becomes "works everywhere"
- ✅ Efficient resource utilization — run many containers per host

### Limitations

- ❌ Weaker isolation than a VM (shares host kernel)
- ❌ Not ideal for running a full different OS (e.g., Windows container on Linux host)
- ❌ Data doesn't persist by default — needs volumes
- ❌ Can increase security surface if misconfigured (e.g., running as root)

### Real World Use Cases

- Microservices architectures
- CI/CD pipelines (consistent build/test environments)
- Cloud-native application deployment
- Local development environments that mirror production

### Best Practices

- Keep containers **stateless** — store data in volumes, not inside the container
- Run **one primary process per container**
- Use **small, minimal base images** (e.g., Alpine)
- Never run containers as root unless absolutely required

### Quick Revision

| Ask Yourself | Answer |
|---|---|
| What does a container share with the host? | The OS kernel |
| What two Linux features make containers possible? | Namespaces + cgroups |
| Typical container startup time? | Seconds (sometimes milliseconds) |

---

## 5.2 VMs vs Containers

### Introduction

Both **Virtual Machines (VMs)** and **containers** solve the same core problem — isolating applications so they don't interfere with each other. But they solve it at completely different layers of the stack, and that difference drives almost every architecture decision (and interview question) you'll face around this topic.

### Why Do We Need It?

Before containers, VMs were the standard way to isolate workloads. Understanding *why* containers emerged as a lighter alternative — and where VMs are still the better choice — is core interview and architecture knowledge.

### Definition

> **A Virtual Machine virtualizes hardware and runs a full guest OS on top of a hypervisor. A container virtualizes the operating system and shares the host kernel, running only the application and its dependencies.**

### How It Works

```
VIRTUAL MACHINE STACK              CONTAINER STACK
----------------------              ----------------------
App A   |  App B   |  App C        App A   |  App B   |  App C
Bins/Libs  Bins/Libs   Bins/Libs    Bins/Libs  Bins/Libs   Bins/Libs
Guest OS   Guest OS    Guest OS     ----------------------
----------------------              Container Engine
     Hypervisor                     ----------------------
----------------------                     Host OS
      Host OS                       ----------------------
----------------------                     Hardware
      Hardware
```

Notice the difference: every VM carries its **own full Guest OS**. Containers skip that entirely and share the Host OS through the container engine — that's the entire reason containers are so much lighter.

### Real World Example / Analogy

> 🏠 **Houses vs Apartments:** A VM is like a standalone house — it has its own plumbing, electricity, and foundation (its own OS). A container is like an apartment in a shared building — residents share the building's infrastructure (the host OS) but still have their own private, locked space.

### Key Components

| Factor | Virtual Machines | Containers |
|---|---|---|
| **Architecture** | Hypervisor + full Guest OS per VM | Container engine, shares Host OS kernel |
| **Resource Utilization** | Heavy — GBs of RAM/disk per VM | Light — MBs, many containers per host |
| **Startup Time** | Minutes (full OS boot) | Seconds |
| **Portability** | Large images, less portable | Highly portable, small images |
| **Isolation** | Strong (full OS-level isolation) | Process-level isolation (shares kernel) |
| **Best For** | Running different OSes, legacy apps, strict isolation | Microservices, cloud-native, CI/CD |

### Advantages & Limitations — When to Use Which

| Use a VM when... | Use a Container when... |
|---|---|
| You need to run a **different OS** than the host | You just need to run an **app**, not a whole OS |
| You need **strong security isolation** (multi-tenant, untrusted code) | You need **fast startup and scaling** |
| Running legacy monolithic applications | Running microservices |

### Real World Use Cases

- **VMs:** Hosting multiple OS types on one server, legacy enterprise apps, strict compliance workloads
- **Containers:** Microservices, DevOps pipelines, Kubernetes workloads, cloud-native apps

> 💡 **Note:** In real cloud environments, these aren't mutually exclusive — most containers actually run **inside** VMs (e.g., a Kubernetes worker node is often itself a VM). It's containers *and* VMs, not containers *vs.* VMs, in production.

### Best Practices

- Default to containers for new, stateless, cloud-native applications
- Reach for VMs when strict kernel-level isolation or a different OS is a hard requirement
- Don't force legacy monoliths into containers without re-architecting them first

### Quick Revision

| VM | Container |
|---|---|
| Has its own Guest OS | Shares Host OS kernel |
| Boots in minutes | Starts in seconds |
| Heavier (GBs) | Lighter (MBs) |
| Managed by a Hypervisor | Managed by a Container Engine |

---

## 5.3 Containerization Technologies

### Introduction

Docker made containers mainstream, but it isn't the only containerization technology — and it isn't even always the one running under the hood anymore. Knowing the landscape (and *why* it changed) is a common interview trap.

### Why Do We Need It?

Different tools solve slightly different problems: some are full developer platforms (Docker), some are daemonless and security-focused (Podman), some are low-level runtimes built specifically to power orchestrators like Kubernetes (containerd, CRI-O).

### Definition

> **Containerization technologies are the tools and runtimes used to build, run, and manage containers.** Docker popularized the workflow; several other tools now implement parts of that same workflow differently.

### How It Works

Most modern container tools are built on **OCI (Open Container Initiative)** standards — meaning an image built by Docker can typically be run by Podman, containerd, or CRI-O too. They're interoperable by design.

### Key Components

| Tool | What It Is | Notable Trait |
|---|---|---|
| **Docker** | Full container platform (build, run, share) | Most popular, huge ecosystem, daemon-based |
| **Podman** | Docker-compatible container engine | **Daemonless** and rootless by default — stronger security posture |
| **LXC (Linux Containers)** | OS-level virtualization, closer to a lightweight VM | Runs a full init system, not just one app |
| **containerd** | Low-level container runtime | Powers Docker internally; also used directly by Kubernetes |
| **CRI-O** | Lightweight runtime built specifically for Kubernetes | Implements the Kubernetes CRI (Container Runtime Interface) |

### Real World Use Cases

- **Docker** — local development, CI/CD pipelines, general-purpose container workflows
- **Podman** — security-sensitive environments needing rootless containers (common in regulated industries)
- **containerd / CRI-O** — running as the actual runtime *inside* Kubernetes nodes

> 💡 **Interview Note:** Kubernetes removed direct Docker support (dockershim) starting v1.24. Kubernetes today talks to runtimes like **containerd** or **CRI-O** via the **CRI (Container Runtime Interface)** — not directly to Docker. Docker-built images still work fine because they follow the OCI image format.

### Best Practices

- For local dev and learning: Docker is still the easiest starting point
- For Kubernetes clusters: understand that containerd/CRI-O — not Docker — is running your containers
- For rootless/security-first environments: evaluate Podman

### Quick Revision

| Tool | One-Line Identity |
|---|---|
| Docker | The popular full-featured platform |
| Podman | Daemonless, rootless Docker alternative |
| LXC | OS-level container virtualization |
| containerd | Low-level runtime, powers Docker & K8s |
| CRI-O | Lightweight runtime built for Kubernetes |

---

# SECTION B: Docker Deep Dive

## 5.4 What is Docker?

### Introduction

Docker is the tool that took the *idea* of containers (which existed in Linux for years via LXC) and turned it into something any developer could use in minutes. It gave containers a simple CLI, a build system (Dockerfile), and a public registry (Docker Hub) — and that combination is what made containers go mainstream around 2013 onward.

### Why We Need Docker

- Raw Linux containerization (namespaces + cgroups) is powerful but **hard to use directly**
- Docker wraps all that complexity behind simple commands like `docker run`
- It standardizes how images are **built, shared, and run** across any machine with Docker installed

### Definition

> **Docker is an open-source platform that automates the deployment of applications inside lightweight, portable containers by packaging an application with its dependencies into a standardized unit.**

### Docker Use Cases

- ✅ Packaging applications for consistent dev/test/prod environments
- ✅ Powering CI/CD pipelines (build once, run anywhere)
- ✅ Running microservices independently
- ✅ Local development that mirrors production exactly

### Quick Revision

| Question | Answer |
|---|---|
| What problem did Docker solve? | Made containers easy to build, run, and share |
| What's Docker's default public registry? | Docker Hub |
| What file defines how a Docker image is built? | Dockerfile |

---

## 5.5 How Docker Works

### Introduction

Docker isn't one single program — it's a small ecosystem of parts that talk to each other. Understanding this architecture is one of the most commonly asked interview topics in DevOps rounds.

### Docker Architecture

```
      ┌─────────────────────┐
      │    Docker Client       │   (docker CLI — what you type)
      └───────────┬───────────┘
                  │  REST API
                  ▼
      ┌─────────────────────┐
      │    Docker Daemon        │   (dockerd — does the real work)
      │  ───────────────────    │
      │  Manages:                │
      │   • Images                │
      │   • Containers              │
      │   • Networks                 │
      │   • Volumes                    │
      └───────────┬───────────┘
                  │  pull / push
                  ▼
      ┌─────────────────────┐
      │   Docker Registry       │   (Docker Hub, ECR, ACR, Private)
      └─────────────────────┘
```

| Part | Role |
|---|---|
| **Docker Client** | The `docker` CLI you type commands into |
| **Docker Daemon (`dockerd`)** | Background service that builds, runs, and manages containers |
| **Docker Registry** | Stores and distributes images (Docker Hub by default) |
| **Docker Objects** | Images, Containers, Networks, Volumes, Plugins — the "things" Docker manages |
| **Docker Engine** | The combination of `dockerd` + REST API + CLI — the whole platform |

### How It Works (Step by Step)

1. You type a command like `docker run nginx` into the **Client**
2. The Client sends this as a REST API request to the **Daemon**
3. The Daemon checks if the `nginx` image exists locally
4. If not, it **pulls** the image from the **Registry** (Docker Hub)
5. The Daemon uses the image to **create and start** a container

### Real World Example / Analogy

> 🍳 **Restaurant Analogy:** The Docker Client is the waiter taking your order. The Docker Daemon is the kitchen actually cooking the food. The Registry is the supplier warehouse where ingredients (images) are stored and fetched from when the kitchen doesn't have them in stock.

### Best Practices

- Keep the Docker Daemon updated and monitor its logs
- Prefer private registries for proprietary images
- Never expose the Docker daemon socket publicly without authentication (it's root-equivalent access)

### Quick Revision

| Component | One-Line Role |
|---|---|
| Docker Client | Sends your commands |
| Docker Daemon | Does the actual work |
| Docker Registry | Stores images |
| Docker Engine | Client + Daemon + REST API, combined |

---

## 5.6 Docker Editions

### Introduction

When Docker was commercialized, it split into a free community offering and a paid enterprise offering. This distinction shows up in older documentation and training material, so it's worth knowing — even though the naming has evolved since.

### Key Components

| Edition | Description |
|---|---|
| **Docker Community Edition (CE)** | Free, open-source, community-supported. What most developers use daily. |
| **Docker Enterprise Edition (EE)** | Paid tier with enterprise support, advanced security, and management tooling. |

> 💡 **Current-Day Note:** Docker sold its Enterprise business to **Mirantis** in 2019 — it now lives on as **Mirantis Kubernetes Engine**. Today, Docker Inc. instead offers **Docker Desktop** with Personal, Pro, Team, and Business subscription tiers. The CE vs EE naming is largely historical, but "Community edition = free, unrestricted core Docker" is still the right mental model.

### Real World Use Cases

- **CE / Docker Engine (free)** — individual developers, small teams, learning, most CI pipelines
- **Enterprise tooling** — large organizations needing centralized image management, RBAC, and vendor support contracts

### Quick Revision

| Term | Meaning Today |
|---|---|
| Docker CE | Free, open-source Docker Engine |
| Docker EE | Rebranded as Mirantis Kubernetes Engine |
| Docker Desktop | Modern paid/free tiered product for local development |

---

## 5.7 Docker Core Concepts

### Introduction

Three ideas form the backbone of everything you do in Docker: **Containers** (the running thing), **Images** (the blueprint), and **Registries** (where images live). Get comfortable with these and the rest of Docker falls into place quickly.

### 🔹 Containers — Lifecycle & States

A container moves through a predictable lifecycle:

```
docker create  →  Created
       ↓
 docker start  →  Running  ⇄  Paused (docker pause)
       ↓
  docker stop  →  Stopped / Exited
       ↓
   docker rm   →  Removed
```

| State | Meaning |
|---|---|
| **Created** | Container exists but hasn't started |
| **Running** | Actively executing |
| **Paused** | Processes frozen, container still exists |
| **Stopped (Exited)** | Process finished or was stopped |
| **Removed** | Container deleted permanently |

### 🔹 Images — Layers, Base Images, Tags

> **An image is a read-only template made of stacked, cacheable layers — each Dockerfile instruction typically creates one layer.**

```
Layer 4:  Your App Code        (COPY . .)
Layer 3:  Dependencies          (RUN npm install)
Layer 2:  Runtime                 (FROM node:20)
Layer 1:  Base OS                   (Debian slim)
```

- **Base Image** — the starting point (e.g., `ubuntu`, `alpine`, `node`, or `scratch` for an empty base)
- **Image Tags** — version labels in the format `name:tag` (e.g., `nginx:1.25`). If you omit a tag, Docker defaults to `:latest`

> ⚠️ **Best Practice:** Never rely on `:latest` in production — pin to a specific version tag so builds stay reproducible.

### 🔹 Container Registry

| Registry | Type |
|---|---|
| **Docker Hub** | Default public registry, huge library of official images |
| **AWS ECR** | Amazon's managed private registry |
| **Azure Container Registry (ACR)** | Microsoft's managed private registry |
| **Private Registries** | Self-hosted (e.g., Harbor, Nexus, or `registry:2`) for proprietary images |

### Advantages

- ✅ Image layers are cached — rebuilds are fast when only the top layers change
- ✅ Same image runs identically everywhere
- ✅ Registries make sharing images across teams trivial

### Best Practices

- Order Dockerfile instructions from **least to most frequently changing** to maximize layer cache hits
- Use specific, pinned image tags — never blind `:latest` in production
- Use private registries for anything proprietary or sensitive

### Quick Revision

| Concept | One-Liner |
|---|---|
| Image | Read-only, layered blueprint |
| Container | Running instance of an image |
| Tag | Version label (`name:tag`) |
| Registry | Storage/distribution hub for images |

---

## 5.8 Docker Installation

### Introduction

Docker installs differently depending on your OS, mainly because Linux runs containers natively while Windows and macOS need a lightweight VM layer underneath to provide a Linux kernel.

### Installing on Linux (Ubuntu)

```bash
# Remove any old versions first
sudo apt-get remove docker docker-engine docker.io containerd runc

# Set up Docker's official repository
sudo apt-get update
sudo apt-get install ca-certificates curl gnupg
sudo install -m 0755 -d /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg

# Install Docker Engine
sudo apt-get update
sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```

### Installing on CentOS

```bash
sudo yum install -y yum-utils
sudo yum-config-manager --add-repo https://download.docker.com/linux/centos/docker-ce.repo
sudo yum install docker-ce docker-ce-cli containerd.io
sudo systemctl start docker
```

### Installing on Windows

- Install **Docker Desktop for Windows**
- Requires **WSL2** (Windows Subsystem for Linux) as the backend — Docker Desktop will prompt you to enable it
- Hyper-V is used as an alternative backend on older setups

### Installing on macOS

- Install **Docker Desktop for Mac** (Intel or Apple Silicon build)
- Runs a lightweight Linux VM in the background since macOS has no native container support

### Post-Installation Steps

```bash
# Run Docker without sudo every time
sudo usermod -aG docker $USER
newgrp docker

# Enable Docker to start on boot
sudo systemctl enable docker
sudo systemctl start docker

# Verify installation
docker --version
docker run hello-world
```

> 💡 **Tip:** If `docker run hello-world` pulls the image and prints a welcome message, your installation is working correctly.

### Best Practices

- Always install from Docker's **official repository**, not generic distro packages, for the latest features
- Add your user to the `docker` group so you don't need `sudo` for every command — but know this is effectively root-equivalent access, so only trusted users should be in that group
- Verify with `hello-world` immediately after installing

### Quick Revision

| OS | Requires |
|---|---|
| Linux | Native support, install Docker Engine directly |
| Windows | Docker Desktop + WSL2 |
| macOS | Docker Desktop + built-in lightweight Linux VM |

---

## 5.9 Docker Commands

### Introduction

You'll use a small, repeatable set of commands 90% of the time. This section is your command reference — bookmark it.

### 🔹 Image Commands

| Command | Description | Example |
|---|---|---|
| `docker pull` | Download an image from a registry | `docker pull nginx:1.25` |
| `docker push` | Upload an image to a registry | `docker push myrepo/app:v1` |
| `docker images` | List local images | `docker images` |
| `docker rmi` | Remove an image | `docker rmi nginx:1.25` |
| `docker build` | Build an image from a Dockerfile | `docker build -t myapp:v1 .` |

### 🔹 Container Commands

| Command | Description | Example |
|---|---|---|
| `docker run` | Create and start a container | `docker run -d -p 8080:80 nginx` |
| `docker start` / `docker stop` | Start or stop an existing container | `docker stop mycontainer` |
| `docker ps` | List running containers (`-a` for all) | `docker ps -a` |
| `docker exec` | Run a command inside a running container | `docker exec -it mycontainer bash` |
| `docker logs` | View container logs | `docker logs -f mycontainer` |
| `docker rm` | Remove a container | `docker rm mycontainer` |
| `docker inspect` | View detailed JSON config of a container/image | `docker inspect mycontainer` |

> 💡 **Common `docker run` flags:** `-d` (detached/background), `-it` (interactive terminal), `-p host:container` (port mapping), `-v host:container` (volume mount), `--name` (custom container name).

### 🔹 Network Commands

| Command | Description | Example |
|---|---|---|
| `docker network ls` | List all networks | `docker network ls` |
| `docker network create` | Create a custom network | `docker network create mynet` |
| `docker network connect` | Attach a container to a network | `docker network connect mynet mycontainer` |

### 🔹 Volume Commands

| Command | Description | Example |
|---|---|---|
| `docker volume create` | Create a named volume | `docker volume create mydata` |
| `docker volume ls` | List volumes | `docker volume ls` |
| `docker volume rm` | Remove a volume | `docker volume rm mydata` |

### Best Practices

- Always use `-d` for long-running services so your terminal isn't blocked
- Use `--name` on containers you'll reference often — saves you from copying container IDs
- Clean up regularly: `docker system prune` removes unused images, containers, and networks

### Quick Revision

| I want to... | Command |
|---|---|
| Download an image | `docker pull <image>` |
| Run a container in background | `docker run -d <image>` |
| See running containers | `docker ps` |
| Get a shell inside a container | `docker exec -it <container> bash` |
| See what happened (logs) | `docker logs <container>` |

---

# SECTION C: Dockerfile & YAML

## 5.10 Writing Dockerfiles

### Introduction

A Dockerfile is a plain text recipe — a list of instructions Docker follows, top to bottom, to build an image. Once you understand each instruction, writing Dockerfiles becomes second nature.

### Why Do We Need It?

Without a Dockerfile, building images means manually running commands inside a container and committing the result — messy, unrepeatable, and impossible to version control. A Dockerfile makes image builds **scripted, repeatable, and version-controlled** like any other code.

### Key Instructions

| Instruction | Purpose | Example |
|---|---|---|
| `FROM` | Sets the base image (always the first instruction) | `FROM node:20-alpine` |
| `RUN` | Executes a command during build, creates a new layer | `RUN npm install` |
| `COPY` | Copies files from host into the image | `COPY . /app` |
| `ADD` | Like COPY, but can also extract archives and fetch URLs | `ADD app.tar.gz /app` |
| `WORKDIR` | Sets the working directory for subsequent instructions | `WORKDIR /app` |
| `ENV` | Sets environment variables | `ENV NODE_ENV=production` |
| `EXPOSE` | Documents which port the container listens on | `EXPOSE 3000` |
| `CMD` | Default command when the container starts (overridable) | `CMD ["node", "server.js"]` |
| `ENTRYPOINT` | Fixed executable for the container (harder to override) | `ENTRYPOINT ["node"]` |

> 🎯 **Classic Interview Question — CMD vs ENTRYPOINT:** `CMD` provides a *default* command that's easily overridden at runtime (`docker run image other-command`). `ENTRYPOINT` sets a *fixed* executable that always runs — arguments passed at runtime get appended to it, not replace it. They're often combined: `ENTRYPOINT ["node"]` + `CMD ["server.js"]` means the container always runs `node`, but the script name can be swapped.

> 🎯 **COPY vs ADD:** Prefer `COPY` for everyday use — it's simple and predictable. Only reach for `ADD` when you specifically need auto-extraction of local tar archives or a remote URL fetch.

### Example Dockerfile

```dockerfile
# Base image
FROM node:20-alpine

# Set working directory inside the container
WORKDIR /app

# Copy dependency files first (better layer caching)
COPY package*.json ./
RUN npm install --production

# Copy the rest of the application code
COPY . .

# Set environment variable
ENV NODE_ENV=production

# Document the port the app listens on
EXPOSE 3000

# Run as a non-root user for security
USER node

# Default startup command
CMD ["node", "server.js"]
```

### Best Practices

- Order instructions from **least → most frequently changing** (dependencies before app code) to maximize cache reuse
- Use **small base images** (`alpine`, `slim`) to reduce image size and attack surface
- Combine related `RUN` commands with `&&` to reduce the number of layers
- Add a `.dockerignore` file (like `.gitignore`) to skip `node_modules`, `.git`, logs, etc.
- Avoid running containers as `root` — use the `USER` instruction
- Use **multi-stage builds** to keep final images lean (build tools stay out of the production image)

### Quick Revision

| Instruction | Remembers As |
|---|---|
| `FROM` | Starting point |
| `RUN` | Build-time command |
| `COPY` | Bring files in |
| `WORKDIR` | "cd" for the rest of the file |
| `ENV` | Environment variables |
| `EXPOSE` | Documents the port |
| `CMD` | Default, overridable command |
| `ENTRYPOINT` | Fixed, hard-to-override command |

---

## 5.11 Docker Compose

### Introduction

Real applications rarely run as a single container — a typical app needs a web server, a database, and maybe a cache, all running together and talking to each other. Starting each one manually with `docker run` gets tedious fast. **Docker Compose** solves this by letting you define your entire multi-container application in a single YAML file.

### Why Do We Need It?

- Manually running multiple `docker run` commands with the right flags every time is error-prone
- Multi-container apps need a shared network and coordinated startup
- Compose gives you a **single command** (`docker compose up`) to spin up your whole stack

### Definition

> **Docker Compose is a tool for defining and running multi-container Docker applications using a single YAML configuration file.**

### `docker-compose.yml` Structure

```yaml
version: "3.9"

services:
  web:
    build: .
    ports:
      - "3000:3000"
    depends_on:
      - db
    environment:
      - NODE_ENV=production

  db:
    image: postgres:16
    environment:
      - POSTGRES_PASSWORD=secret
    volumes:
      - db-data:/var/lib/postgresql/data

networks:
  default:
    driver: bridge

volumes:
  db-data:
```

| Top-Level Key | Purpose |
|---|---|
| **services** | Each container your app needs (web, db, cache, etc.) |
| **networks** | How services communicate with each other |
| **volumes** | Persistent storage shared across container restarts |

> 💡 **Note:** Modern Compose (the `docker compose` CLI plugin, V2) no longer requires the `version:` key — it's optional now. You'll still see it often in existing training material and older projects.

### Docker Compose Commands

| Command | Description |
|---|---|
| `docker compose up` | Start all services (add `-d` to run in background) |
| `docker compose down` | Stop and remove all services, networks |
| `docker compose ps` | List running services |
| `docker compose logs` | View logs from all services |
| `docker compose build` | Rebuild service images |
| `docker compose exec` | Run a command inside a running service |
| `docker compose stop` | Stop services without removing them |

### Best Practices

- Use `depends_on` to control startup order for dependent services
- Never hardcode secrets directly in `docker-compose.yml` — use an `.env` file instead
- Use named volumes for anything that needs to persist (databases especially)

### Quick Revision

| Command | Use |
|---|---|
| `docker compose up -d` | Start everything, in background |
| `docker compose down` | Stop and clean everything up |
| `docker compose logs -f` | Tail logs live |

---

## 5.12 YAML Basics

### Introduction

YAML ("YAML Ain't Markup Language") is the format you'll write constantly in DevOps — Docker Compose files, Kubernetes manifests, CI/CD pipelines, Ansible playbooks — all YAML. It's designed to be human-readable, but it's strict about one thing: **indentation**.

### Why Do We Need It?

Kubernetes and Docker Compose both need a way to describe complex, nested configuration in a format that's easy for humans to read *and* write. YAML fills that role better than JSON for hand-written config files.

### YAML Syntax — Key-Value Pairs

```yaml
name: John
age: 25
role: DevOps Engineer
```

### Lists

```yaml
skills:
  - Docker
  - Kubernetes
  - Linux
```

### Dictionaries (Nested Mappings)

```yaml
person:
  name: John
  address:
    city: Bengaluru
    pincode: 560001
```

### Indentation Rules

- Use **spaces only** — never tabs (YAML will error out or misparse)
- Indentation defines nesting — be consistent (2 spaces is the common convention)
- A colon `:` after a key must be followed by a space before the value

### YAML vs JSON

| Feature | YAML | JSON |
|---|---|---|
| Readability | High — minimal punctuation | Lower — lots of braces/quotes |
| Comments | Supported (`#`) | Not supported |
| Common Use | Config files (K8s, Compose, CI/CD) | APIs, data interchange |
| Strictness | Indentation-sensitive | Bracket-sensitive |
| Compatibility | Valid JSON is (mostly) valid YAML | N/A |

### Best Practices

- Use a YAML linter/validator before applying manifests (a single bad indent breaks the whole file)
- Stick to 2-space indentation consistently across a project
- Always quote strings that could be misread as another type (e.g., `"yes"`, `"123"`, `"null"`)

### Quick Revision

| Rule | Remember |
|---|---|
| Tabs | Never allowed |
| Indentation | Defines structure/nesting |
| Lists | Use `-` |
| Comments | Start with `#` |

---

# SECTION D: Container Orchestration

## 5.13 What is Container Orchestration?

### Introduction

One container is easy to manage by hand. A hundred containers, spread across a dozen servers, that need to restart when they crash, scale up during traffic spikes, and get updated without downtime — that's impossible to manage manually. That's the exact problem **container orchestration** solves.

### Why Orchestration is Needed

- Running containers manually doesn't scale past a handful of them
- If a container crashes at 3 AM, someone (or something) needs to restart it automatically
- Traffic spikes need automatic scaling — up and back down
- Rolling out updates to hundreds of containers without downtime requires coordination

### Definition

> **Container orchestration is the automated management of container lifecycles — deployment, scaling, networking, and availability — across a cluster of machines.**

### Orchestration Tools Overview

| Tool | Description |
|---|---|
| **Kubernetes (K8s)** | Industry-standard orchestrator, backed by CNCF, massive ecosystem |
| **Docker Swarm** | Docker's native, simpler orchestration tool — easy setup, far smaller ecosystem today |
| **Apache Mesos** | General-purpose cluster manager, was popular pre-Kubernetes, now niche |

> 💡 **Reality Check:** Kubernetes has become the de facto standard for orchestration. Swarm and Mesos are still worth knowing conceptually (and for interviews), but almost all new production deployments today are built on Kubernetes.

### Key Orchestration Concepts

| Concept | What It Means |
|---|---|
| **Scheduling** | Deciding *which* machine in the cluster a container should run on |
| **Scaling** | Automatically adding/removing container instances based on load |
| **Self-Healing** | Automatically restarting or replacing failed containers |
| **Load Balancing** | Distributing incoming traffic evenly across running containers |

### Real World Use Cases

- Running production microservices at scale
- Zero-downtime deployments and rollbacks
- Auto-scaling e-commerce platforms during sales/traffic spikes

### Best Practices

- Design containers to be **stateless and disposable** — orchestrators assume they can kill and restart them anytime
- Define resource requests/limits so the scheduler can place workloads intelligently
- Use health checks so the orchestrator actually knows when to self-heal

### Quick Revision

| Term | One-Liner |
|---|---|
| Scheduling | Where should this run? |
| Scaling | How many copies do we need right now? |
| Self-Healing | Restart it automatically if it dies |
| Load Balancing | Spread traffic evenly |

---

# SECTION E: Kubernetes Administration

## 5.14 Kubernetes Overview

### Introduction

Kubernetes (often shortened to **K8s** — "K", 8 letters, "s") is the tool that won the orchestration race. It was built by Google, based on over a decade of running containers internally at massive scale, and then given away as open source — which is a big part of why it became the industry default.

### Why Do We Need It?

Once you have containers, you need something to actually run them reliably in production — restarting failures, scaling under load, rolling out updates safely, and managing networking between services. Kubernetes is that "something."

### Definition

> **Kubernetes is an open-source container orchestration platform that automates the deployment, scaling, and management of containerized applications across a cluster of machines.**

### History of Kubernetes

```
Google's internal "Borg" system (used for 10+ years internally)
        ↓
Kubernetes open-sourced by Google (2014)
        ↓
Donated to the Cloud Native Computing Foundation - CNCF (2015)
        ↓
Became the industry-standard orchestrator (today)
```

### Kubernetes vs Docker Swarm

| Factor | Kubernetes | Docker Swarm |
|---|---|---|
| **Complexity** | Higher learning curve | Simple, quick to set up |
| **Scalability** | Extremely high, battle-tested at massive scale | Good for smaller clusters |
| **Ecosystem** | Huge — Helm, Istio, Prometheus, etc. | Small, limited tooling |
| **Auto-scaling & Self-healing** | Advanced, highly configurable | Basic |
| **Industry Adoption** | Dominant standard | Rare in new projects |

### Kubernetes Use Cases

- Running microservices at enterprise scale
- Multi-cloud and hybrid-cloud deployments
- Automated CI/CD driven deployments
- Self-healing, auto-scaling production workloads

### Best Practices

- Don't reach for Kubernetes for a simple single-container app — it's overhead you don't need yet
- Learn core objects (Pods, Deployments, Services) thoroughly before touching advanced tooling (Helm, Operators)

### Quick Revision

| Question | Answer |
|---|---|
| Who originally built the ideas behind K8s? | Google (internally, as "Borg") |
| Who maintains Kubernetes today? | CNCF (Cloud Native Computing Foundation) |
| Main competitor tool? | Docker Swarm (much smaller adoption today) |

---

## 5.15 Kubernetes Architecture

### Introduction

A Kubernetes cluster has two types of machines: the **Control Plane** (the brain, making decisions) and **Worker Nodes** (the muscle, actually running your containers). Every component has one clear job — and this architecture is one of the most-asked topics in any K8s interview.

### Control Plane Components

```
                 ┌─────────────────────────────┐
                 │        CONTROL PLANE           │
                 ├─────────────────────────────┤
                 │  kube-apiserver                 │  ← front door / REST API
                 │  etcd                             │  ← cluster's database
                 │  kube-scheduler                   │  ← decides pod placement
                 │  kube-controller-manager          │  ← keeps desired state
                 └───────────────┬───────────────┘
                                 │
                                 │  manages
                                 ▼
                 ┌─────────────────────────────┐
                 │         WORKER NODE            │   (repeats per node)
                 ├─────────────────────────────┤
                 │  kubelet                         │  ← node's agent
                 │  kube-proxy                       │  ← networking rules
                 │  Container Runtime                 │  ← containerd / CRI-O
                 │  Pods                                │  ← your app containers
                 └─────────────────────────────┘
```

| Control Plane Component | Role |
|---|---|
| **kube-apiserver** | The front door — all communication (kubectl, internal components) goes through it |
| **etcd** | Distributed key-value store holding the entire cluster's state |
| **kube-scheduler** | Decides which worker node a new Pod should run on |
| **kube-controller-manager** | Runs controllers that constantly reconcile actual state → desired state |

| Worker Node Component | Role |
|---|---|
| **kubelet** | Agent that ensures containers described in Pod specs are actually running |
| **kube-proxy** | Manages network rules, enables Service routing to Pods |
| **Container Runtime** | Actually runs the containers (containerd, CRI-O) |

### Real World Example / Analogy

> 🏢 **Company Analogy:** The Control Plane is the management office — the API server is reception (everything routes through it), etcd is the filing cabinet (source of truth), the scheduler is HR assigning new hires to desks, and the controller manager is the supervisor making sure everything matches the plan. Worker Nodes are the factory floor actually doing the work.

### Best Practices

- Run the Control Plane with **high availability** (multiple replicas) in production — it's a single point of failure otherwise
- Never edit `etcd` directly — always go through the API server
- Monitor `kubelet` health on every node; if it goes down, that node stops receiving new work

### Quick Revision

| Component | Lives On | One-Liner |
|---|---|---|
| kube-apiserver | Control Plane | The front door |
| etcd | Control Plane | The database |
| kube-scheduler | Control Plane | Decides placement |
| controller-manager | Control Plane | Keeps desired state |
| kubelet | Worker Node | Runs the Pods |
| kube-proxy | Worker Node | Handles networking |

---

## 5.16 Kubernetes Resource Model

### Introduction

Kubernetes needs ways to organize, group, and control access to resources inside a cluster — especially once multiple teams or environments share the same cluster. Four concepts handle this: Namespaces, Labels/Selectors, Annotations, and Resource Quotas.

### Why Do We Need It?

Without organization, a cluster running hundreds of Pods across multiple teams becomes unmanageable chaos — no way to isolate environments, find related resources, or stop one team from eating all the cluster's resources.

### Key Components

| Concept | Purpose | Example |
|---|---|---|
| **Namespaces** | Virtual sub-clusters for isolating groups of resources | `dev`, `staging`, `prod` namespaces |
| **Labels & Selectors** | Key-value tags used to group and *select* resources | `app: frontend`, `env: prod` |
| **Annotations** | Non-identifying metadata (not used for selection) | Build version, contact email, changelog notes |
| **Resource Quotas** | Limits on CPU/memory/object count per namespace | Max 10 Pods in the `dev` namespace |

### How It Works

```yaml
# Example: a Pod with labels
apiVersion: v1
kind: Pod
metadata:
  name: my-app
  namespace: dev
  labels:
    app: frontend
    env: dev
  annotations:
    owner: "aj@example.com"
```

A **Service** or **Deployment** then uses a **selector** to find all Pods matching `app: frontend` — labels are how Kubernetes objects "find" each other.

### Real World Example / Analogy

> 🗂️ **Office Analogy:** Namespaces are separate floors in a building (Dev floor, Staging floor, Prod floor). Labels are name tags employees wear ("Team: Frontend") that let you filter and find people quickly. Annotations are like a sticky note with extra info that isn't used to search — just to inform.

### Best Practices

- Always separate environments using **namespaces** (`dev`, `staging`, `prod`) — never mix them
- Use consistent, meaningful **label** conventions across the whole team (`app`, `env`, `team`)
- Set **resource quotas** per namespace to prevent one team/app from starving the whole cluster

### Quick Revision

| Concept | Used For |
|---|---|
| Namespace | Isolating groups of resources |
| Label | Grouping/selecting resources |
| Annotation | Extra metadata, not used for selection |
| Resource Quota | Capping resource usage per namespace |

---

## 5.17 Kubernetes Orchestration

> This is the heart of day-to-day Kubernetes work — the objects you'll create and manage constantly: Pods, Deployments, Services, ConfigMaps/Secrets, and Persistent Storage.

### 🔹 Pods

**Introduction:** The Pod is the smallest deployable unit in Kubernetes — you never deploy a "container" directly, you always deploy a Pod (which wraps one or more containers).

**Why Do We Need It?** Sometimes a container needs a tightly-coupled helper (like a logging agent) that must share the same network and storage. Pods let a group of containers act as a single logical unit.

> **Definition:** A Pod is a group of one or more containers that share the same network namespace, IP address, and storage volumes, and are always scheduled together on the same node.

| Pod Type | Description |
|---|---|
| **Single-Container Pod** | Most common — one app container per Pod |
| **Multi-Container Pod** | Main container + helper "sidecar" container(s) (e.g., a log shipper) sharing the same network/storage |

**Pod Lifecycle Phases:**

```
Pending  →  Running  →  Succeeded / Failed
                              ↓
                          Unknown (if the node can't be reached)
```

| Phase | Meaning |
|---|---|
| **Pending** | Accepted by cluster, not all containers created yet |
| **Running** | Bound to a node, at least one container running |
| **Succeeded** | All containers terminated successfully (exit 0) |
| **Failed** | At least one container terminated with an error |
| **Unknown** | Pod state can't be determined (node unreachable) |

> 💡 **Best Practice:** Never treat Pods as permanent — they're disposable by design. Use a **Deployment** to manage them so Kubernetes recreates them automatically if they die.

---

### 🔹 Deployments

**Introduction:** You'll almost never create a bare Pod directly in real usage — you create a **Deployment**, which manages Pods for you: keeping the right number running, and handling updates safely.

> **Definition:** A Deployment is a Kubernetes object that manages a set of identical Pods (via a ReplicaSet), providing declarative updates, scaling, and rollback capability.

**Creating a Deployment:**

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: my-app
spec:
  replicas: 3
  selector:
    matchLabels:
      app: my-app
  template:
    metadata:
      labels:
        app: my-app
    spec:
      containers:
        - name: my-app
          image: myrepo/my-app:v1
          ports:
            - containerPort: 3000
```

```bash
kubectl apply -f deployment.yaml
```

**Rolling Updates:** When you update the image version in the YAML and re-apply, Kubernetes replaces old Pods with new ones **gradually** — a few at a time — so the app stays available throughout.

**Rollbacks:** If a new version breaks something, undo it instantly:

```bash
kubectl rollout status deployment/my-app
kubectl rollout undo deployment/my-app
```

> 💡 **Interview Note:** A Deployment doesn't manage Pods directly — it manages a **ReplicaSet**, which in turn manages the Pods. This layering is what enables safe rolling updates and rollbacks.

---

### 🔹 Services

**Introduction:** Pods are disposable — they get new IP addresses every time they're recreated. A **Service** gives your application a stable network identity so other things can reliably find it, regardless of which Pods are currently running behind it.

> **Definition:** A Service is a stable network endpoint that routes traffic to a dynamic set of Pods, selected by label.

| Service Type | Description | Use Case |
|---|---|---|
| **ClusterIP** (default) | Internal-only IP, reachable only inside the cluster | Internal microservice-to-microservice communication |
| **NodePort** | Exposes the Service on a static port (30000–32767) on every node's IP | Quick external access, dev/testing |
| **LoadBalancer** | Provisions an external load balancer (via the cloud provider) | Production-facing internet traffic |

```yaml
apiVersion: v1
kind: Service
metadata:
  name: my-app-service
spec:
  type: LoadBalancer
  selector:
    app: my-app
  ports:
    - port: 80
      targetPort: 3000
```

> 💡 **Analogy:** If Pods are food trucks that move around the city daily, a Service is the fixed phone number customers call — it always routes them to *whichever* truck is currently working, without customers needing to know its location.

---

### 🔹 ConfigMaps and Secrets

**Introduction:** Applications need configuration (URLs, feature flags) and sensitive data (passwords, API keys) — but neither should be hardcoded into container images. ConfigMaps and Secrets externalize both.

| | ConfigMap | Secret |
|---|---|---|
| **Purpose** | Non-sensitive configuration data | Sensitive data (passwords, tokens, keys) |
| **Storage** | Plain text | Base64-**encoded** (not encrypted, by default!) |
| **Example** | App URLs, feature flags, log level | DB passwords, API keys, TLS certs |

> ⚠️ **Critical Interview Gotcha:** Kubernetes Secrets are **base64-encoded, not encrypted**, by default. Anyone with API access can trivially decode them. For real security, you need **encryption at rest** enabled on `etcd`, or an external secrets manager (e.g., HashiCorp Vault, IBM Cloud Secrets Manager).

```yaml
apiVersion: v1
kind: ConfigMap
metadata:
  name: app-config
data:
  LOG_LEVEL: "info"
  API_URL: "https://api.example.com"
```

---

### 🔹 Persistent Volumes (PV) & Persistent Volume Claims (PVC)

**Introduction:** Containers are ephemeral — anything written inside them disappears when the container restarts. Databases and other stateful apps need storage that **survives** Pod restarts. That's what PV and PVC provide.

> **Definitions:**
> - **PersistentVolume (PV):** An actual piece of storage in the cluster (a cloud disk, NFS share, etc.), provisioned by an admin or dynamically
> - **PersistentVolumeClaim (PVC):** A user's *request* for storage — Kubernetes matches (binds) it to a suitable PV

```
Developer defines a PVC → "I need 5Gi of storage"
              ↓
   Kubernetes finds/binds a matching PV
              ↓
   PV = the actual storage (cloud disk, NFS, etc.)
              ↓
        Pod mounts the volume and uses it
```

### Advantages (Kubernetes Orchestration Overall)

- ✅ Self-healing — crashed Pods are automatically recreated
- ✅ Zero-downtime rolling updates and instant rollbacks
- ✅ Stable networking via Services, even as Pods come and go
- ✅ Configuration and secrets stay separate from application code

### Limitations

- ❌ Steep learning curve — many interconnected concepts
- ❌ Secrets aren't encrypted by default — needs extra setup
- ❌ Debugging distributed, multi-Pod issues can be complex

### Best Practices

- Always deploy via **Deployments**, never bare Pods
- Use **ClusterIP** by default; only use **LoadBalancer**/**NodePort** when external access is genuinely needed
- Never commit real secrets into Git, even as YAML — use a secrets manager or sealed secrets
- Always request PVCs for anything stateful (databases, file uploads)

### Quick Revision

| Object | One-Liner |
|---|---|
| Pod | Smallest deployable unit (one or more containers) |
| Deployment | Manages Pods — scaling, updates, rollbacks |
| Service | Stable network address for a set of Pods |
| ConfigMap | Non-sensitive config data |
| Secret | Sensitive data (base64-encoded, not encrypted!) |
| PV | Actual storage in the cluster |
| PVC | A request/claim for that storage |

---

## 5.18 Creating a Cluster

### Introduction

Before you can deploy anything, you need an actual Kubernetes cluster. There are three common paths, depending on whether you're learning, testing, or running production.

### Key Components

| Method | Best For | Description |
|---|---|---|
| **kubeadm** | Production, on-prem/VMs | Manual, hands-on cluster bootstrapping — you manage the Control Plane yourself |
| **Minikube** | Local learning/dev | Single-node cluster running inside a VM/container on your laptop |
| **Cloud Managed Services** | Production | Provider manages the Control Plane for you (IBM IKS, AWS EKS, Azure AKS, Google GKE) |

### How It Works

```bash
# Minikube — local single-node cluster
minikube start
kubectl get nodes

# kubeadm — production, multi-node (run on the control-plane host)
sudo kubeadm init --pod-network-cidr=192.168.0.0/16
```

> 💡 **Note:** `kind` (Kubernetes-in-Docker) is another popular local option alongside Minikube, especially for running multi-node clusters locally inside Docker containers.

### Real World Use Cases

- **Minikube** — learning, local development, quick experiments
- **kubeadm** — on-premises or self-managed cloud VM clusters where you want full control
- **Managed Services (IKS/EKS/AKS/GKE)** — production workloads where you don't want to operate the Control Plane yourself

### Best Practices

- Start with **Minikube** to learn — don't jump straight into managing your own Control Plane
- For production, prefer a **managed service** unless you have a strong operational reason (compliance, on-prem requirement) to self-manage

### Quick Revision

| Method | One-Word Summary |
|---|---|
| kubeadm | Manual |
| Minikube | Local |
| Managed Service (IKS/EKS/AKS/GKE) | Production-ready |

---

## 5.19 IBM Cloud IKS

### Introduction

**IBM Kubernetes Service (IKS)** is IBM Cloud's managed Kubernetes offering — IBM runs and maintains the Control Plane for you, so you only focus on your workloads (the Worker Nodes and what runs on them).

### Why Do We Need It?

Running your own Control Plane means patching, securing, and monitoring `etcd`, the API server, and the scheduler yourself. IKS removes that operational burden entirely — IBM handles Control Plane availability, updates, and security patching.

### Definition

> **IKS is IBM Cloud's fully managed Kubernetes service that provisions, operates, and scales Kubernetes clusters, integrating natively with other IBM Cloud services (Container Registry, VPC, IAM, monitoring).**

### Setting Up IKS

```bash
# Install & log in to the IBM Cloud CLI
ibmcloud login
ibmcloud plugin install container-service

# Create a cluster
ibmcloud ks cluster create classic --name my-cluster --zone <zone> --flavor <flavor> --workers 3

# Point kubectl at your new cluster
ibmcloud ks cluster config --cluster my-cluster
kubectl get nodes
```

### Managing IKS Clusters

| Task | Command |
|---|---|
| List clusters | `ibmcloud ks clusters` |
| Get cluster details | `ibmcloud ks cluster get --cluster my-cluster` |
| Resize worker pool | `ibmcloud ks worker-pool resize` |
| Update Kubernetes version | `ibmcloud ks cluster master update` |

> 💡 **Note:** Exact IBM Cloud CLI flags evolve over time — always cross-check current syntax against the [IBM Cloud CLI docs](https://cloud.ibm.com/docs/containers) before running commands in a real environment.

### Real World Use Cases

- Enterprise workloads that need tight integration with other IBM Cloud services (IAM, VPC, Container Registry)
- Regulated industries needing IBM Cloud's compliance certifications
- Hybrid-cloud setups alongside IBM Cloud Satellite

### Best Practices

- Use **IBM Cloud Container Registry (icr.io)** to store your images close to your cluster
- Enable cluster **auto-scaling** on the worker pool for variable workloads
- Use **namespaces** and **IAM access policies** together to control who can touch what

### Quick Revision

| Question | Answer |
|---|---|
| What does IKS manage for you? | The Control Plane |
| What do you still manage? | Worker Nodes' workloads (your apps) |
| Default IBM image registry? | IBM Cloud Container Registry (`icr.io`) |

---

## 5.20 Deploy MW Application on Kubernetes/IKS

### Introduction

This is where everything in this module comes together — taking an application from source code to a running, accessible service on a real Kubernetes cluster.

### Step 1: Preparing the Application

Containerize the app first — write a Dockerfile, build the image, and push it to a registry the cluster can pull from:

```bash
docker build -t icr.io/my-namespace/mw-app:v1 .
docker push icr.io/my-namespace/mw-app:v1
```

### Step 2: Creating the Deployment YAML

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: mw-app
spec:
  replicas: 3
  selector:
    matchLabels:
      app: mw-app
  template:
    metadata:
      labels:
        app: mw-app
    spec:
      containers:
        - name: mw-app
          image: icr.io/my-namespace/mw-app:v1
          ports:
            - containerPort: 8080
          resources:
            requests:
              cpu: "250m"
              memory: "256Mi"
            limits:
              cpu: "500m"
              memory: "512Mi"
```

### Step 3: Creating the Service YAML

```yaml
apiVersion: v1
kind: Service
metadata:
  name: mw-app-service
spec:
  type: LoadBalancer
  selector:
    app: mw-app
  ports:
    - port: 80
      targetPort: 8080
```

### Step 4: Deploying and Verifying

```bash
# Apply both manifests
kubectl apply -f deployment.yaml
kubectl apply -f service.yaml

# Verify the rollout
kubectl get pods
kubectl get deployments
kubectl get services
kubectl describe deployment mw-app

# Watch it live
kubectl get pods --watch
```

> 💡 **Tip:** "MW" in enterprise/IBM training contexts typically refers to a **Middleware** sample application. The deployment pattern above — Dockerize → Deployment → Service → verify — works identically for any application; only the image and ports change.

### Best Practices

- Always set **resource requests/limits** — an unbounded Pod can starve the whole node
- Use `kubectl rollout status` after every deploy to confirm it actually succeeded before moving on
- Keep Deployment and Service YAML files in version control (Git), not just applied ad-hoc

### Quick Revision

| Step | Command |
|---|---|
| 1. Build & push image | `docker build` + `docker push` |
| 2. Define Deployment | `deployment.yaml` |
| 3. Define Service | `service.yaml` |
| 4. Apply | `kubectl apply -f <file>` |
| 5. Verify | `kubectl get pods/deployments/services` |

---

# ✅ Hands-On Practice Goals

Work through these in order — each builds on the last:

- [ ] Install Docker on Linux
- [ ] Pull and run a Docker container
- [ ] Build a custom Docker image using a Dockerfile
- [ ] Push the image to Docker Hub / a registry
- [ ] Write a Docker Compose YAML for a multi-container app
- [ ] Create a Kubernetes cluster using Minikube
- [ ] Deploy a Pod and a Deployment
- [ ] Create a Kubernetes Service
- [ ] Deploy an application on IBM Cloud IKS

---

# 📋 Master Quick Revision Cheat Sheet

| Term | One-Line Definition |
|---|---|
| **Container** | Lightweight, portable unit packaging an app + its dependencies |
| **Image** | Read-only, layered template used to create containers |
| **Dockerfile** | Script of instructions to build an image |
| **Docker Compose** | Tool to define & run multi-container apps via YAML |
| **Docker Daemon** | Background service (`dockerd`) that does the real work |
| **Registry** | Storage/distribution hub for images (Docker Hub, ECR, ACR, icr.io) |
| **Namespace (Docker)** | Not applicable — this is a K8s term; Docker isolation uses kernel namespaces internally |
| **Container Orchestration** | Automated management of containers at scale |
| **Kubernetes (K8s)** | Industry-standard container orchestration platform |
| **Control Plane** | The "brain" of a K8s cluster (API server, etcd, scheduler, controller manager) |
| **Worker Node** | Machine that actually runs your Pods (kubelet, kube-proxy, runtime) |
| **Pod** | Smallest deployable unit — one or more containers sharing network/storage |
| **Deployment** | Manages Pods — scaling, rolling updates, rollbacks |
| **Service** | Stable network endpoint for a dynamic set of Pods |
| **ConfigMap** | Externalized, non-sensitive configuration |
| **Secret** | Externalized sensitive data (base64-encoded, not encrypted by default) |
| **PV / PVC** | Actual storage / a request for that storage |
| **Namespace (K8s)** | Virtual sub-cluster for isolating resources |
| **IKS** | IBM's managed Kubernetes service |

### Command Cheat Sheet

| Task | Docker | Kubernetes |
|---|---|---|
| See what's running | `docker ps` | `kubectl get pods` |
| View logs | `docker logs <id>` | `kubectl logs <pod>` |
| Get a shell inside | `docker exec -it <id> bash` | `kubectl exec -it <pod> -- bash` |
| Describe/inspect | `docker inspect <id>` | `kubectl describe pod <pod>` |
| Apply/run config | `docker compose up -d` | `kubectl apply -f file.yaml` |
| Stop/remove | `docker stop` / `docker rm` | `kubectl delete pod <pod>` |

---

# 🎯 Top Interview Q&A (Quick-Fire)

| # | Question | Short Answer |
|---|---|---|
| 1 | Container vs VM — core difference? | Containers share the host OS kernel; VMs run a full guest OS each |
| 2 | What makes containers lightweight? | No guest OS — just namespaces (isolation) + cgroups (limits) |
| 3 | CMD vs ENTRYPOINT? | CMD = overridable default command; ENTRYPOINT = fixed executable |
| 4 | COPY vs ADD? | COPY is simple file copy; ADD also extracts archives & fetches URLs |
| 5 | What's a Docker image layer? | A cached, read-only filesystem diff created by each Dockerfile instruction |
| 6 | Why avoid `:latest` in production? | It's not pinned — builds become unpredictable and unreproducible |
| 7 | What does a Deployment manage under the hood? | A ReplicaSet, which in turn manages the Pods |
| 8 | ClusterIP vs NodePort vs LoadBalancer? | Internal-only vs static port on every node vs external cloud load balancer |
| 9 | Are Kubernetes Secrets encrypted? | No — base64-encoded only, by default. Needs encryption-at-rest for real security |
| 10 | PV vs PVC? | PV = actual storage resource; PVC = a user's request/claim for storage |
| 11 | What replaced dockershim in Kubernetes? | containerd / CRI-O, via the Container Runtime Interface (CRI) |
| 12 | Role of etcd? | Distributed key-value store holding the entire cluster's state |
| 13 | Role of kube-scheduler? | Decides which node a new Pod should run on |
| 14 | What is a multi-container Pod used for? | Sidecar patterns — e.g., a log shipper running alongside the main app |
| 15 | Why use namespaces (K8s)? | Isolate resources across teams/environments (dev, staging, prod) |
| 16 | What triggers a rolling update? | Changing the Pod template in a Deployment (e.g., new image tag) and re-applying |
| 17 | How do you roll back a bad deployment? | `kubectl rollout undo deployment/<name>` |
| 18 | What manages Kubernetes networking on each node? | kube-proxy |
| 19 | Who open-sourced Kubernetes, and when? | Google, in 2014 (donated to CNCF in 2015) |
| 20 | What does IKS manage for you that self-hosted K8s doesn't? | The Control Plane (API server, etcd, scheduler, controller manager) |

---

### 🎓 End of Module 5 — Containers & Kubernetes

*Built for daily revision • IBM Training • Interview Prep • Cloud & DevOps Learning*
