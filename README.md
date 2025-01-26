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

# Cüzdanımızı Metamaska İmport edeceğiz.

We will import our wallet to Metamask.


wallet_keystore Dosyasını sftp ile cihazımıza kaydediyoruz.
Ardından metamaska gelerek yeni cüzdan Ekle seçeneğinden json olarak import et seçeneğine basacağız. Şifremizi girip cüzdanı metamaska import etmiş olacağız.

We save the wallet_keystore file to our device via sftp. Then, we will go to Metamask and click on the import as json option from the Add new wallet option. We will enter our password and import the wallet into Metamask.

# Daha sonra,
Site Linki: https://deepsea-beta.privasea.ai/privanetixNode

Arbitrum sepolia Faucet alıyoruz, Siteden Token faucet alıyoruz, Node Etkinleştirme kısmından komisyonu ve İsmimizi Yazıyoruz, Ve Kaydediyoruz.

# Son işlemler.

Kodu girerek Node başlatıcaz.

```
cd /privasea/
```


Burada 123456 yazan yere cüzdan sifrenizi girin.

```
docker run  -d   -v "/privasea/config:/app/config" \
  -e KEYSTORE_PASSWORD=123456 \
  privasea/acceleration-node-beta:latest
```


Onra size uzun bir çıktı verecek onunla birlikte node sağlığına bakacağız.

```
docker logs -f uzunciktiyiburayayapistirin
```

En Son Böyle Gözükecek.


![Screenshot_2025-01-27-01-47-25-681-edit_com server auditor ssh client](https://github.com/user-attachments/assets/a2fc3eeb-5c38-4528-91b9-8937a73e3b1f)



Anlamadığız Takıldığınız bir yer olursa sorun.



