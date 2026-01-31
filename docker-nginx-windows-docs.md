# Install Docker Desktop on Windows & Run Nginx (Step-by-Step)

This guide walks you through installing **Docker Desktop on Windows** and deploying a **sample Nginx container**.

## Prerequisites
- Windows 10 or Windows 11 (64-bit)
- Administrator access
- Virtualization enabled in BIOS
- Active internet connection

> Docker Desktop uses **WSL 2** (Windows Subsystem for Linux). The installer usually configures this automatically.

## Step 1: Download Docker Desktop

1. Download the installer [Docker Desktop for Windows - x86_64](https://desktop.docker.com/win/main/amd64/Docker%20Desktop%20Installer.exe?utm_source=docker&utm_medium=webreferral&utm_campaign=docs-driven-download-win-amd64)

## Step 2: Install Docker Desktop

1. Double-click `Docker Desktop Installer.exe`
2. When prompted:
   - Keep **"Use WSL 2 instead of Hyper-V"** checked (recommended)
3. Click **OK** and wait for the installation to finish
4. Restart your PC if prompted

## Step 3: Start Docker Desktop

1. Open **Start Menu**
2. Search for **Docker Desktop** and open it
3. Wait until you see:  
   **“Docker Desktop is running”**

### Verify Installation

Open **Command Prompt** or **PowerShell** and run:

```bash
docker --version
```

Expected output (version may differ):

```bash
Docker version 26.x.x, build xxxxx
```

## Step 4: Run Nginx in a Docker Container

Run the following command:

```bash
docker run -d -p 8080:80 --name mynginx nginx
```

### What this command does:

* `docker run` → Creates and runs a container
* `-d` → Runs in detached (background) mode
* `-p 8080:80` → Maps port 8080 on your PC to port 80 in the container
* `--name mynginx` → Names the container `mynginx`
* `nginx` → Uses the official Nginx image from Docker Hub

If the image is not present locally, Docker will download it automatically.

## Step 5: Open Nginx in Your Browser

Open your browser and go to:

```bash
http://localhost:8080
```

You should see the **“Welcome to nginx!”** page

## Step 6: Check Running Containers

Run:

```bash
docker ps
```

You should see the `mynginx` container running.

---

## Step 7: Stop and Remove the Container (Optional)

To stop the container:

```bash
docker stop mynginx
```

To remove the container:

```bash
docker rm mynginx
```

## Useful Docker Commands

Pull an image manually:

```bash
docker pull nginx
```

List Docker images:

```bash
docker images
```

List all containers (including stopped ones):

```bash
docker ps -a
```

## Conclusion

You have successfully.

- Installed Docker Desktop on Windows
- Pulled the Nginx image
- Deployed and accessed Nginx using Docker

[For latest information refer official site](https://docs.docker.com/desktop/setup/install/windows-install/)