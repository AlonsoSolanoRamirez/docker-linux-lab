# Docker Linux Lab

## Overview

This project simulates a small Linux environment using Docker containers.

It demonstrates how to run multiple containers, connect them through a custom network, and perform basic troubleshooting tasks.

---

## Technologies
- Docker 
- Linux (Ubuntu, Alpine)

---

## Setup & Usage

### 1. Create a network

docker network create my-network

### 2. Run container

docker run -dit --name ubuntu1 --network my-network ubuntu
docker run -dit --name alpine1 --network my-network alpine

### 3. Access containers

docker exec -it ubuntu1 bash
docker exec -it alpine1 sh

---

## Networking Test

Inside ubuntu1:
 apt update
 apt install -y iputils-ping iproute2
 ping alpine1

Inside alpine1:
 apk add iputils
 ping ubuntu1

---

## Troubleshooting Performed

- Verified container connectivity using ping
- Installed missing networking tools (iproute2, iputils)
- Checked network interfaces using 'ip a'
- Tested DNS resolution between containers.
- Simulated failure scenarios

---

## Example Commands 

docker ps
docker network ls 
ip a 
ps aux

---

## Project Structure
.
|_____README.md

---

## What I Learned 

- How to create and manage Docker containers
- How container networking works
- Differences between Linux distributions (Ubuntu vs Alpine)
- Basic troubleshooting inside containers

---

