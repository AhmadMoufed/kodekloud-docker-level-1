# Day 02 – Deploy Nginx Container on Application Server

## Docker Level 1

### Task
The Nautilus DevOps team requires an **nginx container** to be deployed on **Application Server 2**.

### Requirements
- Container name: `nginx_2`
- Image: `nginx`
- Tag: `alpine`
- Container must be running

---

### Solution

1. SSH into Application Server 2:
```bash
ssh steve@stapp02
````

2. Run the nginx container:

```bash
docker run -d --name nginx_2 nginx:alpine
```

3. Verify container status:

```bash
docker ps
```
