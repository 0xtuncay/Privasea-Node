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

Verify Docker Installation
Docker Kurulumunu Doğrulama


```
sudo docker --version
```

Expected output:
Çıktı örneği:

![IMG_20250126_130248](https://github.com/user-attachments/assets/e9bdd538-454b-40cf-8fb6-adfd7def12ef)

Start and Enable Docker Service

Docker Servisini Başlatıyoruz ve Etkinleştiriyoruz.

```
sudo systemctl start docker
```

```
sudo systemctl enable docker
```

# Pull docker mirroring
Repoyu Docker ile çekiyoruz.

```
docker pull privasea/acceleration-node-beta:latest
```


Create the program running directory and navigate to it:

Dizin Oluşturuyoruz, ve İçine giriyoruz.


```
sudo su
```

```
mkdir -p  /privasea/config && cd  /privasea
```

We Create a Wallet, you will enter the Password, and save the output as our node address.


Cüzdan Oluşturuyoruz, Şifre gireceksiniz, ve çıkan çıktıyı kaydedin bizim node adresimiz.


```
docker run -it -v "/privasea/config:/app/config"  \
privasea/acceleration-node-beta:latest ./node-calc new_keystore
```










