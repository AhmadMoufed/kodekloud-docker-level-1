# Day 01 – Install Docker Packages and Start Docker Service

## Docker Level 1

### Task
The Nautilus DevOps team plans to containerize applications.  
As part of testing, Docker must be installed and started on **Application Server 3**.

### Requirements
- Install `docker-ce` and `docker compose` packages
- Start and enable Docker service

---

### Solution

1. SSH into Application Server 3:
```bash
ssh banner@stapp03
````

2. Verify OS version:

```bash
cat /etc/os-release
```

OS: **CentOS 9**

3. Install required packages and Docker repository:

```bash
sudo dnf -y install dnf-plugins-core
sudo dnf config-manager --add-repo https://download.docker.com/linux/centos/docker-ce.repo
```

4. Install Docker packages:

```bash
sudo dnf install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```

5. Enable and start Docker service:

```bash
sudo systemctl enable --now docker
sudo systemctl start docker
```

6. Verify Docker status:

```bash
sudo systemctl status docker
```
