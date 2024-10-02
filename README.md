# Laporan Resmi Praktikum Jarkom Modul 1 2024

---
### Anggota Kelompok
- Rafika Az Zahra Kusumastuti  (5027231050)
- Johanes Edward Nathanael     (5027231067)

### Daftar Isi
- [Soal-1](#soal-1)
- [Soal-2](#soal-2)
- [Soal-3](#soal-3)
- [Soal-4](#soal-4)
- [Soal-5](#soal-5)
- [Soal-6](#soal-6)
- [Soal-7](#soal-7)
- [Soal-8](#soal-8)
- [Soal-9](#soal-9)
- [Soal-10](#soal-10)
- [Soal-11](#soal-11)
- [Soal-12](#soal-12)
- [Soal-13](#soal-13)
- [Soal-14](#soal-14)
- [Soal-15](#soal-15)
- [Soal-16](#soal-17)
- [Soal-18](#soal-18)
- [Soal-19](#soal-19)
- [Soal-20](#soal-20)

-----
Sebuah kerajaan besar di Indonesia sedang mengalami pertempuran dengan penjajah. Kerajaan tersebut adalah **Sriwijaya**. Karena merasa terdesak **Sriwijaya** meminta bantuan pada **Majapahit** untuk mempertahankan wilayahnya. Pertempuran besar tersebut berada di **Nusantara**. Untuk topologi (3)
## Topologi
![Screenshot 2024-10-02 003021](https://github.com/user-attachments/assets/97f1801f-dcd0-45be-ad3d-e8b4991522e0)

### Network Configuration
Nusantara (Router)
```
auto eth0
iface eth0 inet static

auto eth1
iface eth1 inet static
	address 192.236.1.1
	netmask 255.255.255.0

auto eth2
iface eth2 inet static
	address 192.236.2.1
	netmask 255.255.255.0
```

Samaratungga (Client)
```
auto eth0
iface eth0 inet static
	address 192.236.1.2
	netmask 255.255.255.0
	gateway 192.236.1.1
```

GrahamBell (Client)
```
auto eth0
iface eth0 inet static
	address 192.236.1.3
	netmask 255.255.255.0
	gateway 192.236.1.1
```

Mulawarman (Client)
```
auto eth0
iface eth0 inet static
	address 192.236.1.4
	netmask 255.255.255.0
	gateway 192.236.1.1
```

Majapahit (DNS Slave)
```
auto eth0
iface eth0 inet static
	address 192.236.1.5
	netmask 255.255.255.0
	gateway 192.236.1.1
```

Bedahulu (Web Server)
```
auto eth0
iface eth0 inet static
	address 192.236.2.2
	netmask 255.255.255.0
	gateway 192.236.2.1
```

Tanjungkulai (Web Server)
```
auto eth0
iface eth0 inet static
	address 192.236.2.3
	netmask 255.255.255.0
	gateway 192.236.2.1
```

Sriwijaya (DNS Master)
```
auto eth0
iface eth0 inet static
	address 192.236.2.4
	netmask 255.255.255.0
	gateway 192.236.2.1
```

Srikandi (Client)
```
auto eth0
iface eth0 inet static
	address 192.236.2.5
	netmask 255.255.255.0
	gateway 192.236.2.1
```

Solok (Load Balancer)
```
auto eth0
iface eth0 inet static
	address 192.236.2.6
	netmask 255.255.255.0
	gateway 192.236.2.1
```

Kotalingga (Web Server)
```
auto eth0
iface eth0 inet static
	address 192.236.2.7
	netmask 255.255.255.0
	gateway 192.236.2.1
```


### Set .bashrc
Nusantara (Router)
```
iptable -t nat -A POSTROUTING -o eth0 -j MASQUERADE -s 192.236.0.0/16
```

Sriwijaya (DNS Master)
```
apt-get update
apt-get install bind9 -y
```

Majapahit (DNS Slave)
```
apt-get update
apt-get install bind9 -y
```



## Soal 1
Untuk mempersiapkan peperangan World War MMXXIV (Iya sebanyak itu), **Sriwijaya** membuat dua kotanya menjadi web server yaitu **Tanjungkulai**, dan **Bedahulu**, serta **Sriwijaya** sendiri akan menjadi DNS Master. Kemudian karena merasa terdesak, **Majapahit** memberikan bantuan dan menjadikan kerajaannya (**Majapahit**) menjadi **DNS Slave**.

## Soal 2
Karena para pasukan membutuhkan koordinasi untuk melancarkan serangannya, maka buatlah sebuah domain yang mengarah ke **Solok** dengan alamat **sudarsana.xxxx.com** dengan alias **www.sudarsana.xxxx.com**, dimana xxxx merupakan kode kelompok. Contoh: **sudarsana.it01.com.**

## Set Up DNS pada DNS Master (Sriwijaya)
a. Instalasi dependencies yang diperlukan

