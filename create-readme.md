# How to Write GitHub .md file 
## .md extention specifying Github Page 

#### How to Seletion Language in .md files 
**English** | [Türkçe](docs/readme_tr.md) | [Russian](docs/readme_ru.md)

This repository contains a simple Java application packaged with Docker, featuring persistent storage.

## How to Create Table of Contents

- [Introduction](#introduction)
- [Prerequisites](#prerequisites)
- [Setup Instructions](#setup-instructions)
  - [1. Clone the Repository](#1-clone-the-repository)
  - [2. Build the Docker Image](#2-build-the-docker-image)
  - [3. Run the Container](#3-run-the-container)
- [Persistent Storage](#persistent-storage)
- [Accessing the Application](#accessing-the-application)
- [Stopping the Application](#stopping-the-application)
- [Cleanup](#cleanup)
- [License](#license)

## Add a Link URL in a Title or Name

Here, Docker is Link name.

- [Docker](https://www.docker.com/)

### 1. Clone the Repository

First, clone the repository to your local machine:

```bash
git clone https://github.com/yourusername/java-docker-persistent-storage.git
cd java-docker-persistent-storage
```
### 2. Build the Docker Image
```bash
docker build -t java-img .
```

### 3. Run the Container
```bash
docker run -itd --name java-app -p 8080:8080 java-img
```

# Accessing the Server
Once the container is running, you can access the server by navigating to:

```
http://Your_docker_host_ip:4000
```
## 🫂 Contributors

<a href="https://github.com/dogukanurker"><img src="https://avatars.githubusercontent.com/u/62756402" title="dogukanurker" width="80" height="80"></a>
<a href="https://github.com/adindrabkin"><img src="https://avatars.githubusercontent.com/u/47116975" title="adindrabkin" width="80" height="80"></a>
<a href="https://github.com/codehwang"><img src="https://avatars.githubusercontent.com/u/26578588" title="codehwang" width="80" height="80"></a>
<a href="https://github.com/dkashkarev"><img src="https://avatars.githubusercontent.com/u/67013355" title="dkashkarev" width="80" height="80"></a>
<a href="https://github.com/dkashkarev"><img src="https://avatars.githubusercontent.com/u/2644169" title="barmar" width="80" height="80"></a>
