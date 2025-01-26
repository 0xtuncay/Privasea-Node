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

We change the name of the Wallet we created. Copy the name that will appear when you enter the file. I wrote mine as an example.

Oluşturduğumuz Cüzdanın ismini değiştiriyoruz. Dosyanın içine girince gözükecek ismi kopyalayın.
Ben Örnek olsun diye kendiminkini yazdim.

```
cd /privasea/config && ls
```

![Screenshot_2025-01-26-13-17-25-672-edit_com server auditor ssh client](https://github.com/user-attachments/assets/20fd6148-9eac-46d6-9620-a23d950cb667)




```
mv ./UTC--2025-01-26T10-10-23.913157088Z--41dfad103d814260b2c91ac5bd0815756e5cb1df  ./wallet_keystore 
```

```
cd /privasea/config && ls
```












