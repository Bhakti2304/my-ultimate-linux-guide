# Core components of a Linux Machine

The main component of a Linux Machine is the Linux Kernel.

- The interaction of Harware such as Process management, memory management, device management, network management, everything handles through Kernel.
- On top of Linux Kernel, there are System Libraries(OpenSSL, libc, glibc etc), System Utilities( ls, grep, systmectl etc) and On top of that there is CLI or GUI. In case of Linux, there are CLI such as Bash, Zsh, Fish etc.

----------------------------------
# Linux Distributions

Ubuntu, Redhat, Debian, Alpine, Fedora use the OpenSource Linux and add some features or commands or package managers(it helps you to deploy/install dependencies like Python, it helps you to upgrade/ maintain/ delete version of of package like Python or Java) to make their own OS and distribute them as new products.

- Therefore, if you have shell script running on the Ubuntu also have Redhat, due to having same underlying libraries, packages.
- Ubuntu is the most Popular distribution among others. 

-----------------------------------
# Setup Linux Environment 

There are multiple ways to set up a Linux environment on Windows or Mac machines

1. To install Linux on your Windows machine, just type 'wsl' in Powershell and restart your machine.
2. The alternative is Docker container to run a Linux environment.  
   - Just install Docker Desktop and run the below command, which creates a linux container without worrying about the cost and connectivity issues.

```bash
docker run -dit \
  --name ubuntu-container \
  --hostname ubuntu-dev \
  --restart unless-stopped \
  --cpus="2" \
  --memory="4g" \
  --mount type=bind,source=C:/ubuntu-data,target=/data \
  -v /var/run/docker.sock:/var/run/docker.sock \
  -p 2222:22 \
  -p 8080:80 \
  --env TZ=Asia/Kolkata \
  --env LANG=en_US.UTF-8 \
  ubuntu:latest /bin/bash
```

## Explanation of Each Parameter

| Parameter | Description |
|-----------|-------------|
| `-dit` | Runs the container in **detached (-d)**, **interactive (-i)**, and **terminal (-t)** mode. |
| `--name ubuntu-container` | Assigns a name to the container for easy management. |
| `--hostname ubuntu-dev` | Sets the container’s hostname. |
| `--restart unless-stopped` | Ensures the container restarts automatically unless manually stopped. |
| `--cpus="2"` | Limits the container to **2 CPU cores**. |
| `--memory="4g"` | Allocates **4GB RAM** to the container. |
| `--mount type=bind,source=C:/ubuntu-data,target=/data` | **Mounts a folder** from Windows into the container to persist data. |
| `-v /var/run/docker.sock:/var/run/docker.sock` | Allows running Docker commands inside the container (optional). |
| `-p 2222:22` | Maps port **2222** on the host to **22** (SSH) inside the container. |
| `-p 8080:80` | Maps port **8080** on the host to **80** (for web services). |
| `--env TZ=Asia/Kolkata` | Sets the **timezone** (modify based on your location). |
| `--env LANG=en_US.UTF-8` | Sets the **language** settings inside the container. |
| `ubuntu:latest /bin/bash` | Uses the latest **Ubuntu** image and runs Bash shell. |



- To get the container ID, run 'docker ps'
- then run 
      docker exec -it <container_ID>

-------------------------------------------------

- When we use Ubuntu, the package manager is 'apt'.
- when we run
   apt install python3
   it goes to the centralised location. This package manager downloads or caches commonly used dependencies and stores them at the centralised location.

- A repository is a server that stores software packages. When a package manager installs software:

It checks the repository list (e.g., /etc/apt/sources.list in Ubuntu).
It downloads the package and its dependencies.
It installs and configures the software automatically.

- Best Practices for Using Package Managers

✅ Always update your package list before installing software:
sudo apt update && sudo apt upgrade -y

✅ Use autoremove to clean up unused dependencies:
sudo apt autoremove

✅ Enable automatic security updates (Ubuntu):
sudo apt install unattended-upgrades
sudo dpkg-reconfigure unattended-upgrades
