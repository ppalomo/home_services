## Installing Docker

To begin, install the dependencies required by running the following commands:
```shell
$ sudo apt-get update
$ sudo apt-get install ca-certificates curl gnupg lsb-release
```

Add the GPG key used to sign the Docker repository:
```shell
$ sudo mkdir -p /etc/apt/keyrings
$ curl -fsSL https://download.docker.com/linux/debian/gpg | \
sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg

# Verify with
$ echo "deb [arch=$(dpkg --print-architecture) \
signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/debian \
  $(lsb_release -cs) stable" | sudo tee \
  /etc/apt/sources.list.d/docker.list > /dev/null
```

Install Docker:
```shell
$ sudo apt-get update
$ sudo apt-get install docker-ce docker-ce-cli containerd.io
```

The docker CLI requires root privileges by default. You can avoid prefixing commands with sudo by adding yourself to the docker group:
```shell
$ sudo groupadd docker
$ sudo usermod -aG docker $USER
```

## Installing Docker Compose

```shell
$ sudo apt-get install docker-compose-plugin
$ docker compose version
```

## Ejecutar Servicios

```shell
$ docker compose up -d
```