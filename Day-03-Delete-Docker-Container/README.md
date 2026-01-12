# Day 03 – Delete Docker Container

## Docker Level 1

### Task
A test container named `kke-container` was created on **Application Server 2**.  
This container is no longer required and must be deleted.

---

### Solution

1. List all containers:
```bash
docker ps -a
````

2. Stop the container:

```bash
docker stop kke-container
```

3. Remove the container:

```bash
docker rm kke-container
```
