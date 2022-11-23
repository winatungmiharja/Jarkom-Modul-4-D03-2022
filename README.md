# Jarkom-Modul-4-D03-2022

### Kelompok D03

| **No** | **Nama**                   | **NRP**    |
| ------ | -------------------------- | ---------- |
| 1      | Antonio Taifan Montana     | 5025201219 |
| 2      | Wina Tungmiharja           | 5025201242 |
| 3      | Vania Rizky Juliana Wachid | 5025201215 |

```PREFIX IP Kelompok = 192.186```  

### Direktori Jawaban

<details>
  <summary>Expand</summary>
  
 1. [CIDR dengan GNS](https://github.com/winatungmiharja/Jarkom-Modul-3-D03-2022/#CIDR)
 2. [VLSM dengan CPT](https://github.com/winatungmiharja/Jarkom-Modul-3-D03-2022/#VLSM)
 
</details>
 
![soal shift 4 1](https://user-images.githubusercontent.com/64743796/203558222-0a3ce77a-3009-43d8-bb4d-c9777d5a7b04.png)

## CIDR
 
dengan metode ini, kita akan menggabungkan subnet dari node yang paling jauh dari sumber NAT (internet), kemudian kita akan menggabungkan satu per satu sampai semua node menjadi satu grup.
 
### Penggabungan Node
 
1. Kondisi Node Awal
 
![A](https://user-images.githubusercontent.com/64743796/203560354-7584e30d-2b07-423b-b567-b4a200a1e421.jpg)

 
| Subnet | Alias                         | Jumlah IP | Netmask |
| ------ | ----------------------------- | --------- | ------- |
| A1     | guideau-the minister          | 1001      | 22      |
| A2     | the minister-the order        | 2         | 30      |
| A3     | the order-asnaf               | 51        | 26      |
| A4     | the order-the reisnonace      | 2         | 30      |
| A5     | the reisnonace-the beast      | 2         | 30      |
| A6     | the reisnonace-the magical    | 2         | 30      |
| A7     | the magical-haines-corvekt    | 271       | 23      |
| A8     | minister-dauntless            | 2         | 30      |
| A9     | matt cugat-the instrument     | 121       | 25      |
| A10    | the reisonance-the instrument | 2         | 30      |
| A11    | the dountless-phanora-johan   | 251       | 24      |
| A12    | the instrument-the profound   | 2         | 30      |
| A13    | the profound-spendrow         | 121       | 25      |
| A14    | keith-the firefist-the queen  | 211       | 24      |
| A15    | the instrument-the firefist   | 2         | 30      |
| A16    | heiga-the profound            | 71        | 25      |
| A17    | the queen-the witch           | 2         | 30      |
| A18    | the firefist-oakleave         | 501       | 23      |
 
2. Penggabungan Node Pertama (B)
![B](https://user-images.githubusercontent.com/64743796/203560367-42d32637-2d58-4967-9aaa-62556c49f60a.jpg)

| Subnet | Alias   | Jumlah IP | Netmask |
| ------ | ------- | --------- | ------- |
| B1     | A8,A11  | 251       | 23      |
| B2     | A14,A17 | 211       | 23      |
| B3     | A13,A16 | 121       | 24      |

3. Penggabungan Node Kedua (C)
![C](https://user-images.githubusercontent.com/64743796/203560401-69b3c36f-08b6-44a5-bf0c-20c6418a085d.jpg)

| Subnet | Alias  | Jumlah IP | Netmask |
| ------ | ------ | --------- | ------- |
| C1     | B1,A1  | 1001      | 21      |
| C2     | B2,A18 | 501       | 22      |
| C3     | B3,A12 | 121       | 23      |

4. Penggabungan Node Ketiga (D)
![D](https://user-images.githubusercontent.com/64743796/203560413-60c6fd69-e241-4f5c-9e0a-80fd54ad0b99.jpg)

| Subnet | Alias  | Jumlah IP | Netmask |
| ------ | ------ | --------- | ------- |
| D1     | C1,A2  | 1001      | 20      |
| D2     | C2,A15 | 501       | 21      |
| D3     | C3,A9  | 121       | 22      |

5. Penggabungan Node Keempat (E)
![E](https://user-images.githubusercontent.com/64743796/203560422-8bf59dd8-7459-464a-b8d1-a3cd8d55d701.jpg)

| Subnet | Alias | Jumlah IP | Netmask |
| ------ | ----- | --------- | ------- |
| E1     | D1,A3 | 1001      | 19      |
| E2     | D2,D3 | 501       | 20      |

6. Penggabungan Node Kelima (F)
![F](https://user-images.githubusercontent.com/64743796/203560433-680a8310-5906-4478-9e10-955e65540551.jpg)

| Subnet | Alias  | Jumlah IP | Netmask |
| ------ | ------ | --------- | ------- |
| F1     | E1,A4  | 1001      | 18      |
| F2     | E2,A10 | 501       | 19      |

7. Penggabungan Node Keenam (G)
![G](https://user-images.githubusercontent.com/64743796/203560442-474617ff-dea5-45a1-b128-6210c86830cd.jpg)

| Subnet | Alias | Jumlah IP | Netmask |
| ------ | ----- | --------- | ------- |
| G1     | F1,A5 | 1001      | 17      |
| G2     | F2,A6 | 501       | 18      |

8. Penggabungan Node Ketujuh (H)
![H](https://user-images.githubusercontent.com/64743796/203560457-bcc0e50e-360a-4996-b850-eddf371ab062.jpg)

| Subnet | Alias | Jumlah IP | Netmask |
| ------ | ----- | --------- | ------- |
| H1     | G2,A7 | 501       | 17      |

9. Penggabungan Node Kedelapan (I)
![i](https://user-images.githubusercontent.com/64743796/203560469-a5e43913-5a79-4b1b-a219-25421b6b2707.jpg)

 | Subnet | Alias | Jumlah IP | Netmask |
| ------ | ----- | --------- | ------- |
| I1     | H1,G1 | 1001      | 16      |
 
### Pohon IP
 
![image](https://user-images.githubusercontent.com/64743796/203561580-e646c761-909c-49fd-a225-8d80f22cdc3d.png)

### Tabel Pembagian IP

| Subnet | Alias                         | IP              | Subnet Mask     | Length |
| ------ | ----------------------------- | --------------- | --------------- | ------ |
| A1     | guideau-the minister          | 192.186.0.0     | 255.255.252.0   | 22     |
| A2     | the minister-the order        | 192.186.8.0     | 255.255.255.252 | 30     |
| A3     | the order-asnaf               | 192.186.16.0    | 255.255.255.192 | 26     |
| A4     | the order-the reisnonace      | 192.186.32.0    | 255.255.255.252 | 30     |
| A5     | the reisnonace-the beast      | 192.186.64.0    | 255.255.255.252 | 30     |
| A6     | the reisnonace-the magical    | 192.186.160.0   | 255.255.255.252 | 30     |
| A7     | the magical-haines-corvekt    | 192.186.192.0   | 255.255.254.0   | 23     |
| A8     | minister-dauntless            | 192.186.5.0     | 255.255.255.252 | 30     |
| A9     | matt cugat-the instrument     | 192.186.138.0   | 255.255.255.128 | 25     |
| A10    | the reisonance-the instrument | 192.186.144.0   | 255.255.255.252 | 30     |
| A11    | the dountless-phanora-johan   | 192.186.4.0     | 255.255.255.0   | 24     |
| A12    | the instrument-the profound   | 192.186.137.0   | 255.255.255.252 | 30     |
| A13    | the profound-spendrow         | 192.186.136.0   | 255.255.255.128 | 25     |
| A14    | keith-the firefist-the queen  | 192.186.130.0   | 255.255.255.0   | 24     |
| A15    | the instrument-the firefist   | 192.186.132.0   | 255.255.255.252 | 30     |
| A16    | heiga-the profound            | 192.186.136.128 | 255.255.255.128 | 25     |
| A17    | the queen-the witch           | 192.186.131.0   | 255.255.255.252 | 30     |
| A18    | the firefist-oakleave         | 192.186.128.0   | 255.255.254.0   | 23     |
 
 
## VLSM
