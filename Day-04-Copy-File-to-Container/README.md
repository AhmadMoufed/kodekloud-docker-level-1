# Day 04 – Copy File from Docker Host to Container

### Task
The Nautilus DevOps team has confidential data stored on **App Server 3**.  
A container named `ubuntu_latest` is running on the same server.

### Requirement
Copy the encrypted file below from the Docker host to the container:
```text
/tmp/nautilus.txt.gpg
````

* Destination inside container: `/tmp/`
* File must not be modified

---

### Solution

1. SSH into Application Server 3:

```bash
ssh banner@stapp03
```

2. Copy the file from host to container:

```bash
docker cp /tmp/nautilus.txt.gpg ubuntu_latest:/tmp/
```

3. (Optional) Verify file inside container:

```bash
docker exec ubuntu_latest ls /tmp/
```
