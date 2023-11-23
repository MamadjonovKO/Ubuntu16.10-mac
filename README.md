# Ubuntu 16.10 Docker Installation Guide(for MacBooks on Apple Silicon)

## Prerequisites

- Docker installed on your host machine.
- A Docker Hub account.

## Installation Steps

### 1. Install Docker

If Docker is not installed, you can install it using Homebrew:

```sh
brew install --cask docker
```

### 2. Log in to Docker Hub

Create an account on Docker Hub and log in to Docker on your machine.

### 3. Pull the Ubuntu 16.10 Image

Pull the ARM version of the Ubuntu 16.10 image from Docker Hub:

```sh
docker pull armv7/armhf-ubuntu:16.10
```

### 4. Run the Container
Start an interactive container session:

```sh
docker run -it armv7/armhf-ubuntu:16.10 /bin/bash
```
To restart your container later, use:

```sh
docker start -i <container ID>
```

### 5. Update Package Manager Configuration
In the container, open the /etc/apt/sources.list file and uncomment lines starting with deb-src, except those ending with partner. Replace all occurrences of ports.ubuntu.com with old-releases.ubuntu.com. The image in the docker doesn't have any text editor, so you will have to edit the file using docker:

![Screenshot]([https://raw.githubusercontent.com/yourusername/yourrepository/main/screenshot.png](https://github.com/MamadjonovKO/Ubuntu16.10-mac/blob/main/temp/Screenshot%202023-11-23%20at%2022.53.10.png))

![Screenshot]([https://raw.githubusercontent.com/yourusername/yourrepository/main/screenshot.png](https://github.com/MamadjonovKO/Ubuntu16.10-mac/blob/main/temp/Screenshot%202023-11-23%20at%2022.53.30.png))

![Screenshot]([https://raw.githubusercontent.com/yourusername/yourrepository/main/screenshot.png](https://github.com/MamadjonovKO/Ubuntu16.10-mac/blob/main/temp/Screenshot%202023-11-23%20at%2022.54.00.png))

![Screenshot]([https://raw.githubusercontent.com/yourusername/yourrepository/main/screenshot.png](https://github.com/MamadjonovKO/Ubuntu16.10-mac/blob/main/temp/Screenshot%202023-11-23%20at%2022.54.08.png))

![Screenshot]([https://raw.githubusercontent.com/yourusername/yourrepository/main/screenshot.png](https://github.com/MamadjonovKO/Ubuntu16.10-mac/blob/main/temp/Screenshot%202023-11-23%20at%2022.54.40.png))


### 6. Update and Install Packages
Update your package index and upgrade your packages:

```sh
apt-get update && apt-get upgrade
```

Install necessary  tools:

```sh
apt-get install git make gcc ncurses-dev
```


