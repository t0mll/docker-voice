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

### Make sure your user has the right permissions
Try to list the current containers
```
docker ps -a
```

If you get an error (permission denied), you need to add your user to the docker group

```
sudo usermod -aG docker ${USER}
```

Log out and log back it to refresh group membership
```
su - ${USER}
```
Re-run the first command to check that the error disappeared.
