# Day 05 – Troubleshoot Docker Container Issue

### Task
A static website running inside a container named `nautilus` is not accessible on **App Server 1**.

### Investigation Requirements
1. Verify that container volume `/usr/local/apache2/htdocs` is correctly mapped to host volume `/var/www/html`
2. Confirm that the website is accessible on host port `8080`
3. Ensure the following command works:
```bash
curl http://localhost:8080/
````

---

### Solution

1. SSH into Application Server 1:

```bash
ssh tony@stapp01
```

2. List all containers:

```bash
docker ps -a
```

3. Inspect the container:

```bash
docker inspect a0fba16201c9
```

4. Verify volume mapping:

```json
"Mounts": [
  {
    "Type": "bind",
    "Source": "/var/www/html",
    "Destination": "/usr/local/apache2/htdocs",
    "Mode": "",
    "RW": true,
    "Propagation": "rprivate"
  }
]
```

5. Test website access:

```bash
curl http://localhost:8080/
```

**Issue observed:**

```text
curl: (7) Failed to connect to localhost port 8080: Connection refused
```

6. Start the container:

```bash
docker start a0fba16201c9
```

7. Test again:

```bash
curl http://localhost:8080/
```

**Result:**

```text
welcome to xFusionCorp Industries!
```
