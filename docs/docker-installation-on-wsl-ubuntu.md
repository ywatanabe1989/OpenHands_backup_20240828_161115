# https://zenn.dev/acntechjp/articles/d1fc09306cf08f

#### Docker Installation
sudo apt install curl
curl -fsSL https://get.docker.com -o get-docker.sh
sh get-docker.sh
sudo systemctl enable docker

###### /etc/wsl.conf
```
[boot]
systemd=true
```

###### Restart WSL.
``` bash
sudo shutdown
```

###### Check docker service
sudo systemctl status docker

###### Update docker
sudo apt update && sudo apt upgrade -y
sudo apt install -y apt-transport-https ca-certificates curl software-properties-common
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
sudo apt update
sudo apt install --reinstall python3-gi
sudo apt install docker-ce

sudo systemctl start docker
sudo systemctl enable docker
sudo docker run hello-world
