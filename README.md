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

## The Refonance

![image](https://user-images.githubusercontent.com/99629909/203715484-d56ddb15-a26b-410d-acc4-df2b837fb9c7.png)

## The Order

![image](https://user-images.githubusercontent.com/99629909/203715720-947d6b74-de9b-4336-8387-405d5f37748e.png)

## The Minister

![image](https://user-images.githubusercontent.com/99629909/203715836-9ad5a44c-2c07-4b67-b99c-2d62db49d299.png)

## The Daundless

![image](https://user-images.githubusercontent.com/99629909/203715925-c3df0cec-5a92-450f-b3ec-3ad90220b113.png)

## The Megical

![image](https://user-images.githubusercontent.com/99629909/203716091-8a4564b2-e3d0-4d72-ab70-61f018246e8a.png)

## The Instrument

![image](https://user-images.githubusercontent.com/99629909/203716150-6198143c-c190-4a68-b94a-60d8d029bc7e.png)

## The Poofound

![image](https://user-images.githubusercontent.com/99629909/203716236-c65c4fae-b5bc-4be1-9a16-f7bc87b3ecb8.png)

## The Etefist

![image](https://user-images.githubusercontent.com/99629909/203716314-774d8dc3-8576-4d2c-9dd0-4ac81b0df620.png)

## The Queen

![image](https://user-images.githubusercontent.com/99629909/203716367-05aa04f0-3bb3-4531-978b-85ac0b0d715a.png)


*keterangan: 0.0.0.0 berarti mengambil semua pesan dan diarahkan ke next hop.

# Testing
Hasil dari message antar node.

![image](https://user-images.githubusercontent.com/99629909/203716968-2f518c15-413b-44c1-a23e-1119a9e78e6f.png)


# CIDR - GNS3
