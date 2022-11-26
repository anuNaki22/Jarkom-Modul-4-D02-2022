# Jarkom-Modul-4-D02-2022
## Anggota Kelompok D02
| NRP | Nama | Kontribusi |
| :---:        |     :---:           | :---: |
| 5025201082   | Farrel Emerson      |      |
| 5025201087   | Daniel Hermawan     |      |
| 5025201003   | Rahmat Faris Akbar  |   CPT VLSM   | 

# Soal dan Jawaban
![image](https://user-images.githubusercontent.com/99629909/203712109-6de2410e-baaf-4ccb-9ecf-072a59427857.png)

- Soal shift dikerjakan pada Cisco Packet Tracer dan GNS3 menggunakan metode perhitungan CLASSLESS yang berbeda. Keterangan: Bila di CPT menggunakan VLSM, maka di GNS3 menggunakan CIDR atau Sebaliknya
- Jika tidak ada pemberitahuan revisi soal dari asisten, berarti semua soal BERSIFAT BENAR dan DAPAT DIKERJAKAN. Untuk di GNS3 CLOUD merupakan NAT1 jangan sampai salah agar bisa terkoneksi internet.
- Pembagian IP menggunakan Prefix IP yang telah ditentukan pada modul pengenalan.
- Pembagian IP dan routing harus SE-EFISIEN MUNGKIN.

Kami mengerjakan soal ini dengan menggunakan teknik VLSM pada CPT

# VLSM - CPT
## Pembagian Subnet
Pertama kami harus menentukan subnet yang ada pada topologi. Dikarenakan metode yang dipakai adalah VLSM. Kami mengelompokkan tiap host yang terhubung pada interface router dan menghitung IP yang dibutuhkan. Berikut adalah gambaran pembagian subnetnya

![image](https://user-images.githubusercontent.com/99629909/203527957-92092568-84ea-40e4-9045-349030c443a2.png)

## Jumlah IP
Setelah melakukan pembagian subnet kami melakukan penjumlahan pada ip, Sehingga didapatkan hasil penjumlahan ip berikut :

![image](https://user-images.githubusercontent.com/99629909/203711659-d002b4bb-c93c-4366-bd77-d20c702ee34a.png)

## VSLM-Tree
Setelah mendapatkan penjumlahan ip kita membuat tree yang terdapat pada topologi. pada subnet memiliki NID 10.16.0.0 dengan netmask /20 sehingga pembagian IP berdasarkan NID dan Netmask yang di dapat. Pada VLSM ini metode penurunannya adalah dengan menurunkan subnet dan kemudian dibagi menjadi 2 bagian, seperti subnet /20 akan diturunkan menjadi /21 dan dibagi menjadi 2 bagian. Lakukan hal tersebut secara berulang sampai semua host dapat tertampung. Hasil tree adalah sebagai berikut:

![image](https://user-images.githubusercontent.com/99629909/203712373-3fddee59-6474-40ed-9d37-8ba03d1988e2.png)


## Pembagian IP
Setelah diketahui Network ID dari pembagian subnet pada tree, maka kita bisa menghitung broadcast address, host min, host max, dll. Tabel rangkuman pembagiannya adalah sebagai berikut:

![image](https://user-images.githubusercontent.com/99629909/203712674-adaa1cae-6d0c-4ed2-be11-2013bc701189.png)

# Config VSLM
## Menambah Ethernet / Port
Karena default hanya memiliki 2 port ethernet, maka kita bisa menambah port pada tab physical untuk beberapa router yang memiliki cabang yang banyak.

![image](https://user-images.githubusercontent.com/99629909/203714466-b40c046f-31c1-4073-ae27-f6839d9aac30.png)

## Config IP Pada Node

![image](https://user-images.githubusercontent.com/99629909/203714677-19a605ff-9054-4c60-b57d-67a29644d468.png)

Contoh pada The Minister, kita menambahkan IP dan Subnet Mask sesuai dengan pembagian yang telah dilakukan. Selain itu kita tidak boleh lupa untuk menyalakan atau klik on pada router.

Pada server & Client ditambahkan juga gateway yang mengarah ke router terdekat.

![image](https://user-images.githubusercontent.com/99629909/203715024-ea623314-a4b1-48ff-aa12-c97efa32427a.png)

Kedua langkah di atas dilakukan juga pada seluruh node yang lain.

# Routing 
Pada routing berikut adalah config yang berada pada router. Untuk langkah nya bisa masuk kedalam router, lalu menekan menu static dan menambahkan IP, dll sehingga semua node dapat terhubung.

## The Resonance

![image](https://user-images.githubusercontent.com/99629909/204088478-82d99225-5035-4960-8963-fd6f21460300.png)

## The Order

![image](https://user-images.githubusercontent.com/99629909/204088509-75689f27-a083-4130-9024-8d35792c1fc7.png)

## The Minister

![image](https://user-images.githubusercontent.com/99629909/204088526-ea8dfd22-3db2-40aa-8908-2bca801962a4.png)

## The Dauntless

![image](https://user-images.githubusercontent.com/99629909/204088547-3d968cb7-da2e-44c8-8b0c-a67c111c445d.png)

## The Magical

![image](https://user-images.githubusercontent.com/99629909/204088571-874e82a5-0367-4cb4-9d34-ad3430feed8e.png)

## The Instrument

![image](https://user-images.githubusercontent.com/99629909/204088577-708a1592-0ee0-4921-98f7-cecd5a67daec.png)

## The Profound

![image](https://user-images.githubusercontent.com/99629909/204088626-e6d8a401-b73a-460e-8e20-c38f3afaa0c3.png)

## The Firefist

![image](https://user-images.githubusercontent.com/99629909/204088645-551259c4-0bb3-4488-a22c-d98b0c058846.png)

## The Queen

![image](https://user-images.githubusercontent.com/99629909/204088659-8a64afdb-8490-4198-9e1d-46665485c3d0.png)


*keterangan: 
1. 0.0.0.0 berarti mengambil semua pesan dan diarahkan ke next hop
2. untuk konfigurasi setiap node dan pengaturan routing dari setiap router yang lebih jelas bisa dilihat pada file .pkt

# Testing
Hasil dari message antar node.

![image](https://user-images.githubusercontent.com/99629909/204089356-d6f9466c-bb09-4130-8f50-b3c8b79b9d78.png)

# CIDR - GNS3
Berikut ini merupakan tabel setiap langkah metode CIDR

![image](https://user-images.githubusercontent.com/99629909/204090175-75581438-b99c-4e83-aa16-0ebdcd08ac92.png)
<br>

Berikut visualisasi tahapan setiap langkah 

## Langkah 1

![image](https://user-images.githubusercontent.com/99629909/204090240-6d1c2d71-2795-451b-b5d0-a0639820beae.png)
<br>

## Langkah 2

![image](https://user-images.githubusercontent.com/99629909/204090256-50532793-c6fe-4c2b-b89a-f2afc7550d80.png)
<br>

## Langkah 3

![image](https://user-images.githubusercontent.com/99629909/204090272-4aa1df91-71e0-4ed1-83bb-b00865d5a960.png)
<br>

## Langkah 4

![image](https://user-images.githubusercontent.com/99629909/204090285-943a34a4-47d4-477d-8b72-3067ba05ba4f.png)
<br>

## Langkah 5

![image](https://user-images.githubusercontent.com/99629909/204090298-f5fff5e1-f094-42f4-b691-8e4d7bb7bfc1.png)
<br>

## Langkah 6

![image](https://user-images.githubusercontent.com/99629909/204090310-8bda3910-8804-4459-a22c-7a7d3659fd32.png)
<br>

## Langkah 7

![image](https://user-images.githubusercontent.com/99629909/204090318-49ce27ad-829e-4d34-a40a-8fef04fa7f7f.png)
<br>


# Tree
...

<br>
Maka, telah didapatkan tabel NID subnet dengan metode CIDR

![image](https://user-images.githubusercontent.com/99629909/204090905-854f8a3f-6c6b-432a-97b0-1394dce229f6.png)
<br>

Dalam hal subnetting, CIDR sudah efisien, namun tidak efisien dalam hal range ip address yang digunakan dalam melakukan subnetting, yaitu perlu menggunakan netmask /17, padahal pada VLSM hanya butuh /20.
<br>
Hal itu bertujuan untuk memudahkan penambahan subnet baru pada jaringan komputer yang kita sudah buat

Berikut adalah topologi pada GNS3:

![image](https://user-images.githubusercontent.com/99629909/204090959-31e8ac6c-2593-4a82-a5b8-0094bc3df623.png)
<br>

Berikut adalah tabel rincian ip dari setiap node di GNS3 :

![image](https://user-images.githubusercontent.com/99629909/204090678-bf5ef36f-9772-4458-a79b-eeff842860ad.png)
<br>

Untuk menambahkan routing pada suatu router, dapat menggunakan perintah berikut:
```
route add -net [NID] netmask [netmask] gw [next hop]
```
Contoh pada device resonance :
```
route add -net 10.16.0.0 netmask 255.255.192.0 gw 10.16.32.2
```

Untuk melihat routing yang telah dikonfigurasi, dapat menggunakan perintah berikut:
```
ip route | grep "via"
```
- The Resonance
```
default via 192.168.122.1 dev eth0  metric 295 
10.16.0.0/18 via 10.16.32.2 dev eth4 
10.16.64.0/19 via 10.16.80.2 dev eth3 
10.16.96.0/19 via 10.16.98.2 dev eth2 
10.16.100.0/30 via 10.16.100.2 dev eth1 
```
- The Instruments
```
default via 10.16.80.1 dev eth0 
10.16.64.0/21 via 10.16.68.2 dev eth2 
10.16.72.0/21 via 10.16.73.2 dev eth1 
10.16.76.0/25 via 10.16.76.2 dev eth3
```
- The Magical
```
default via 10.16.98.1 dev eth0
```
- The Minister
```
default via 10.16.8.1 dev eth0 
10.16.0.0/22 via 10.16.0.2 dev eth1 
10.16.4.0/22 via 10.16.5.2 dev eth2 
```
- The Order
```
default via 10.16.32.1 dev eth0 
10.16.0.0/20 via 10.16.8.2 dev eth2 
10.16.16.0/26 via 10.16.16.2 dev eth1 
```
- The Profound
```
default via 10.16.73.1 dev eth0 
```
- The Dauntless
```
default via 10.16.5.1 dev eth0 
```
-The Firefist
```
default via 10.16.68.1 dev eth0 
10.16.64.0/23 via 10.16.64.3 dev eth2 
10.16.65.0/24 via 10.16.64.2 dev eth2 
10.16.66.0/23 via 10.16.66.2 dev eth1 
```
- The Queen
```
default via 10.16.64.1 dev eth0
```

Seluruh konfigurasi telah selesai sehingga semua device/node sudah saling terhubung dan dapat mengakses internet

# Kendala
1. Awalnya kami masih bingung dengan pengaturan routing di CPT sehingga masih ada beberapa ping antar node yang failed, namun setelah demo akhirnya kami tahu letak kesalahan kami saat routing.
