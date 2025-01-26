# Privasea-Node

## **Sistem Gereksinimleri**

| Bileşenler  | Minimum      | **Önerilen**  |
|-------------|--------------|---------------|
| CPU         | 4            | 6             |
| RAM         | 4 GB         | 16 GB         |
| Depolama    | 100 GB       |               |

---


# Install Docker 
Docker Kurulumu

```
sudo apt update && sudo apt install -y apt-transport-https ca-certificates curl software-properties-common
```

```
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
```

```
sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"
```

```
sudo apt update
```

```
sudo apt install -y docker-ce
```

Verify Docker Installation,
Docker Kurulumunu Doğrulama


```
sudo docker --version
```









