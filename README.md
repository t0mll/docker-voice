# docker-voice

The below has been tested on Ubuntu 20.04

## Install Docker using the repository
### Set up the repository

1. Update packages
```
sudo apt-get update
sudo apt-get install \
    apt-transport-https \
    ca-certificates \
    curl \
    gnupg-agent \
    software-properties-common
```

2. Add Docker's official GPG key
```
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
```
3. Setup **stable** repository
```
sudo add-apt-repository \
   "deb [arch=amd64] https://download.docker.com/linux/ubuntu \
   $(lsb_release -cs) \
   stable"
```

### Install Docker Engine
1. Update the `apt` package index and install latest version fo Docker Engine

```
 sudo apt-get update
 sudo apt-get install docker-ce docker-ce-cli containerd.io
```