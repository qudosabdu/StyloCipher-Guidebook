# Useful Commands

## Linux Commands

### File and Directory Operations

- **List files and directories:** `ls`
- **Change directory:** `cd`
- **Create a directory:** `mkdir`
- **Remove a file or directory:** `rm`
- **Copy files or directories:** `cp`
- **Move or rename files or directories:** `mv`

### Text Manipulation

- **View the content of a file:** `cat`
- **Display a file one screen at a time:** `more`
- **Display a file or command output page by page:** `less`
- **Search for a pattern in a file:** `grep`

## Shell Commands

### Environment

- **Display environment variables:** `printenv`
- **Set an environment variable:** `export`
- **Print working directory:** `pwd`

### Process Management

- **List running processes:** `ps`
- **Kill a process by PID:** `kill`

## Docker Commands

### Container Management

- **List running containers:** `docker ps`
- **List all containers:** `docker ps -a`
- **Build an image from a Dockerfile:** `docker build`
- **Run a container from an image:** `docker run`
- **Stop a running container:** `docker stop`
- **Remove a container:** `docker rm`
- **Remove an image:** `docker rmi`


# docker installation command for azure ubuntu

# Update package information
$ sudo apt-get update

# Install necessary dependencies
$ sudo apt-get install \
    apt-transport-https \
    ca-certificates \
    curl \
    gnupg-agent \
    software-properties-common

# Create a directory for keyrings
$ sudo mkdir -p /etc/apt/keyrings
$ cd /etc/apt/keyrings

# Download Docker's GPG key and save it as docker.gpg
$ curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg

# Add Docker repository to sources.list
$ echo "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null

# Install Docker
$ sudo apt-get install docker-ce docker-ce-cli containerd.io docker-compose-plugin



Feel free to explore and use these commands in your development and system administration tasks.
