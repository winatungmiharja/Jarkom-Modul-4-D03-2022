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
  
 1. [CIDR dengan GNS](https://github.com/winatungmiharja/Jarkom-Modul-4-D03-2022/#CIDR)
 2. [VLSM dengan CPT](https://github.com/winatungmiharja/Jarkom-Modul-4-D03-2022/#VLSM)
 
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
 
![image](https://user-images.githubusercontent.com/64743796/203562242-64138541-6cd4-4e26-b045-ec8dc4545440.png)

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
 

### Network Configuration

1. Guideau
```
auto eth0
iface eth0 inet static
address 192.186.0.2
netmask 255.255.252.0
gateway 192.186.0.1
```

2. The Minister
```
auto lo
iface lo inet loopback

auto eth0
iface eth0 inet static
address 192.186.8.2
netmask 255.255.255.252
gateway 192.186.8.1

auto eth1
iface eth1 inet static
address 192.186.0.1
netmask 255.255.252.0

auto eth2
iface eth2 inet static
address 192.186.5.1
netmask 255.255.255.252
```

3. The Dauntless
```
auto lo
iface lo inet loopback

auto eth0
iface eth0 inet static
address 192.186.5.2
netmask 255.255.255.252
gateway 192.186.5.1

auto eth1
iface eth1 inet static
address 192.186.4.1
netmask 255.255.255.0
```

4. Phanora
```
auto eth0
iface eth0 inet static
address 192.186.4.2
netmask 255.255.255.0
gateway 192.186.4.1
```

5. Johan
```
auto eth0
iface eth0 inet static
address 192.186.4.3
netmask 255.255.255.0
gateway 192.186.4.1
```

6. The Order
```
auto lo
iface lo inet loopback

auto eth0
iface eth0 inet static
address 192.186.32.2
netmask 255.255.255.252
gateway 192.186.32.1

auto eth1
iface eth1 inet static
address 192.186.16.1
netmask 255.255.255.192

auto eth2
iface eth2 inet static
address 192.186.8.1
netmask 255.255.255.252
```

7. Ashaf
```
auto eth0
iface eth0 inet static
address 192.186.16.2
netmask 255.255.255.192
gateway 192.186.16.1
```

8. The Resonance
```
auto lo
iface lo inet loopback

auto eth0
iface eth0 inet dhcp

auto eth1
iface eth1 inet static
address 192.186.32.1
netmask 255.255.255.252

auto eth2
iface eth2 inet static
address 192.186.144.1
netmask 255.255.255.252

auto eth3
iface eth3 inet static
address 192.186.160.1
netmask 255.255.255.252

auto eth4
iface eth4 inet static
address 192.186.64.1
netmask 255.255.255.252
```


9. The Instrument
```
auto lo
iface lo inet loopback

auto eth0
iface eth0 inet static
address 192.186.144.2
netmask 255.255.255.252
gateway 192.186.144.1

auto eth1
iface eth1 inet static
address 192.186.138.1
netmask 255.255.255.128

auto eth2
iface eth2 inet static
address 192.186.132.1
netmask 255.255.255.252

auto eth3
iface eth3 inet static
address 192.186.137.1
netmask 255.255.255.252
```

10. Matt Cugat
```
auto eth0
iface eth0 inet static
address 192.186.138.2
netmask 255.255.255.128
gateway 192.186.138.1
```

11. The Firefist
```
auto lo
iface lo inet loopback

auto eth0
iface eth0 inet static
address 192.186.132.2
netmask 255.255.255.252
gateway 192.186.132.1

auto eth1
iface eth1 inet static
address 192.186.130.1
netmask 255.255.255.0

auto eth2
iface eth2 inet static
address 192.186.128.1
netmask 255.255.254.0
```

12. Keith
```
auto eth0
iface eth0 inet static
address 192.186.130.2
netmask 255.255.255.0
gateway 192.186.130.1
```


13. The Queen
```
auto lo
iface lo inet loopback

auto eth0
iface eth0 inet static
address 192.186.130.3
netmask 255.255.255.0
gateway 192.186.130.1

auto eth1
iface eth1 inet static
address 192.186.131.1
netmask 255.255.255.252
```

14. The Witch
```
auto eth0
iface eth0 inet static
address 192.186.131.2
netmask 255.255.255.252
gateway 192.186.131.1
```

15. Oakleave
```
auto eth0
iface eth0 inet static
address 192.186.128.2
netmask 255.255.254.0
gateway 192.186.128.1
```


16. The Profound
```
auto lo
iface lo inet loopback

auto eth0
iface eth0 inet static
address 192.186.137.2
netmask 255.255.255.252
gateway 192.186.137.1

auto eth1
iface eth1 inet static
address 192.186.136.129
netmask 255.255.255.128

auto eth2
iface eth2 inet static
address 192.186.136.1
netmask 255.255.255.128
```

17. Helga
```
auto eth0
iface eth0 inet static
address 192.186.136.130
netmask 255.255.255.128
gateway 192.186.136.129
```

18. Spendrow
```
auto eth0
iface eth0 inet static
address 192.186.136.2
netmask 255.255.255.128
gateway 192.186.136.1
```

19. The Magical
```
auto lo
iface lo inet loopback

auto eth0
iface eth0 inet static
address 192.186.160.2
netmask 255.255.255.252
gateway 192.186.160.1

auto eth1
iface eth1 inet static
address 192.186.192.1
netmask 255.255.254.0
```

20. Corvekt
```
auto eth0
iface eth0 inet static
address 192.186.192.2
netmask 255.255.254.0
gateway 192.186.192.1
```

21. Haines
```
auto eth0
iface eth0 inet static
address 192.186.192.3
netmask 255.255.254.0
gateway 192.186.192.1
```

22. The Beast
```
auto eth0
iface eth0 inet static
address 192.186.64.2
netmask 255.255.255.252
gateway 192.186.64.1
```

### Routing


1. The Minister
```
route add -net 0.0.0.0 netmask 0.0.0.0 gw 192.186.8.1
route add -net 192.186.4.0 netmask 255.255.255.0 gw 192.186.5.2

route add -net 192.186.5.0 netmask 255.255.255.252 gw 192.186.5.2
```

2. The dauntless
```
route add -net 0.0.0.0 netmask 0.0.0.0 gw 192.186.8.2
```

3. The Order
```
route add -net 0.0.0.0 netmask 0.0.0.0 gw 192.186.32.1
route add -net 192.186.0.0 netmask 255.255.252.0 gw 192.186.8.2
route add -net 192.186.5.0 netmask 255.255.255.252 gw 192.186.8.2
route add -net 192.186.4.0 netmask 255.255.255.0 gw 192.186.8.2

route add -net 192.186.8.0 netmask 255.255.255.252 gw 192.186.8.2
```

4. The resonance
```
# The Order
route add -net 192.186.0.0 netmask 255.255.252.0 gw 192.186.32.2
route add -net 192.186.8.0 netmask 255.255.255.252 gw 192.186.32.2
route add -net 192.186.16.0 netmask 255.255.255.192 gw 192.186.32.2
route add -net 192.186.5.0 netmask 255.255.255.252 gw 192.186.32.2
route add -net 192.186.4.0 netmask 255.255.255.0 gw 192.186.32.2

# The Instrument 
route add -net 192.186.138.0 netmask 255.255.255.128 gw 192.186.144.2
route add -net 192.186.137.0 netmask 255.255.255.252 gw 192.186.144.2
route add -net 192.186.136.0 netmask 255.255.255.128 gw 192.186.144.2
route add -net 192.186.130.0 netmask 255.255.255.0 gw 192.186.144.2
route add -net 192.186.132.0 netmask 255.255.255.252 gw 192.186.144.2
route add -net 192.186.136.128 netmask 255.255.255.128 gw 192.186.144.2
route add -net 192.186.131.0 netmask 255.255.255.252 gw 192.186.144.2
route add -net 192.186.128.0 netmask 255.255.254.0 gw 192.186.144.2

# The Magical
route add -net 192.186.192.0 netmask 255.255.254.0 gw 192.186.160.2
```

5. The Instrument
```
route add -net 0.0.0.0 netmask 0.0.0.0 gw 192.186.144.1
route add -net 192.186.130.0 netmask 255.255.255.0 gw 192.186.132.2
route add -net 192.186.131.0 netmask 255.255.255.252 gw 192.186.132.2
route add -net 192.186.128.0 netmask 255.255.254.0 gw 192.186.132.2

route add -net 192.186.132.0 netmask 255.255.255.252 gw 192.186.132.2
```

6. The Firefist
```
route add -net 0.0.0.0 netmask 0.0.0.0 gw 192.186.144.2
route add -net 192.186.131.0 netmask 255.255.255.252 gw 192.186.130.3

route add -net 192.186.130.0 netmask 255.255.255.252 gw 192.186.130.3
```

7. The Queen
```
route add -net 0.0.0.0 netmask 0.0.0.0 gw 192.186.132.2
```

8. The Profound
```
route add -net 0.0.0.0 netmask 0.0.0.0 gw 192.186.144.2
```

9. The Magical
```
route add -net 0.0.0.0 netmask 0.0.0.0 gw 192.186.160.1
```

### Hasil Topologi pada GNS3

<img width="960" alt="image" src="https://user-images.githubusercontent.com/64743796/203577204-0220cd7f-2b7f-4007-9952-cb0a8b5dc034.png">

## Hasil IP per komputer

1. Haines
<img width="378" alt="image" src="https://user-images.githubusercontent.com/64743796/203580381-169e9de2-0dfc-47ac-95d8-d77fe994574c.png">

2. Helga
<img width="322" alt="image" src="https://user-images.githubusercontent.com/64743796/203580413-b2fe88c5-e031-4ab9-b32d-5c5fafffb43b.png">

3. Spendrow
<img width="326" alt="image" src="https://user-images.githubusercontent.com/64743796/203580433-22d2ca6b-0d55-4168-8e32-99d44d39fcf0.png">

4. Asahf
<img width="338" alt="image" src="https://user-images.githubusercontent.com/64743796/203580448-5c65387e-52c3-48d5-8f52-c3724c422a61.png">

5. Keith
<img width="327" alt="image" src="https://user-images.githubusercontent.com/64743796/203580467-7480be73-c1cb-4a54-a2dd-208a6b55b821.png">

6. Johan
<img width="336" alt="image" src="https://user-images.githubusercontent.com/64743796/203580484-5e489703-3b57-473d-ae6b-695667251a12.png">

7. Phanora
<img width="350" alt="image" src="https://user-images.githubusercontent.com/64743796/203580556-5705cfc4-4383-49fc-8f4a-65460a8e4742.png">

8. The Beast
<img width="336" alt="image" src="https://user-images.githubusercontent.com/64743796/203580578-1ee81fcf-e6af-41d5-a9a7-3730cea050c9.png">

9. Corvekt
<img width="345" alt="image" src="https://user-images.githubusercontent.com/64743796/203580606-0a252e76-ef9f-4810-acef-d3b0983eb59d.png">

10. Oakkleave
<img width="348" alt="image" src="https://user-images.githubusercontent.com/64743796/203580688-bbedd91f-eb07-4266-941e-21910c755acb.png">

11. MattCugat
<img width="348" alt="image" src="https://user-images.githubusercontent.com/64743796/203580719-0d5f9815-3bce-44a8-a36a-b9bd9ffdf0e3.png">

12. The Witch
<img width="335" alt="image" src="https://user-images.githubusercontent.com/64743796/203580738-4a9dee92-9418-4540-9d10-41650d9615e7.png">

13. Guideau
<img width="344" alt="image" src="https://user-images.githubusercontent.com/64743796/203580769-87676a92-bcc4-482a-a3b1-822c550699a0.png">


## VLSM

Perhitungan IP  
| Subnet    | Alias                         | Jumlah IP | Netmask |
| --------- | ----------------------------- | --------- | ------- |
| A1        | guideau - the minister        | 1001      | 22      |
| A2        | the minister - the order      | 2         | 30      |
| A3        | the order - asnaf             | 51        | 26      |
| A4        | the order - the reisnonace    | 2         | 30      |
| A5        | the reisnonace - server       | 2         | 30      |
| A6        | the reisnonace - server       | 2         | 30      |
| A7        | magical-haines-corvekt        | 271       | 23      |
| A8        | minister-dauntless            | 2         | 30      |
| A9        | mtt cugat-the instrument      | 121       | 25      |
| A10       | the reisonance-the instrument | 2         | 30      |
| A11       | the dountless-phanora-johan   | 251       | 24      |
| A12       | the instrument-the profound   | 2         | 30      |
| A13       | the profound-spendrow         | 121       | 25      |
| A14       | keith-the firefist-the queen  | 211       | 24      |
| A15       | the instrument-the firefist   | 2         | 30      |
| A16       | heiga-the profound            | 71        | 25      |
| A17       | the witch - the queen         | 2         | 30      |
| A18       | The firefirst-oakleave        | 501       | 23      |
| Jumlah IP | 2617                          | 20        |

Pohon IP  
<img width="897" alt="Screenshot 2022-11-23 at 21 31 10" src="https://user-images.githubusercontent.com/57696730/203572473-c614bdb7-c565-4ec3-9e07-83d0953a4e31.png">  

Hasil Pembagian IP per node  
| Subnet | Node           | IP            | Length | Netmask         |
| ------ | -------------- | ------------- | ------ | --------------- |
| A1     | The Minister   | 192.186.0.1   | /22    | 255.255.252.0   |
| A1     | Guideau        | 192.186.0.2   |        | 255.255.252.0   |
| A2     | The Minister   | 192.186.9.194 | /30    | 255.255.255.252 |
| A2     | The Order      | 192.186.9.193 |        | 255.255.255.252 |
| A3     | The Order      | 192.186.9.129 | /26    | 255.255.255.192 |
| A3     | Asnaf          | 192.186.9.130 |        | 255.255.255.192 |
| A4     | The Order      | 192.186.9.197 | /30    | 255.255.255.252 |
| A4     | The Resinonace | 192.186.9.198 |        | 255.255.255.252 |
| A5     | The Resinonace | 192.186.9.201 | /30    | 255.255.255.252 |
| A5     | Server         | 192.186.9.202 |        | 255.255.255.252 |
| A6     | The Resinonace | 192.186.9.205 | /30    | 255.255.255.252 |
| A6     | The Magical    | 192.186.9.206 |        | 255.255.255.252 |
| A7     | The Magical    | 192.186.4.1   | /23    | 255.255.254.0   |
| A7     | Haines         | 192.186.4.2   |        | 255.255.254.0   |
| A7     | Corvekt        | 192.186.4.3   |        | 255.255.254.0   |
| A8     | The Minister   | 192.186.9.209 | /30    | 255.255.255.252 |
| A8     | The Dauntless  | 192.186.9.210 |        | 255.255.255.252 |
| A9     | Matt Cugatt    | 192.186.8.2   | /25    | 255.255.255.128 |
| A9     | The Instrument | 192.186.8.1   |        | 255.255.255.128 |
| A10    | The Instrument | 192.186.9.213 | /30    | 255.255.255.252 |
| A10    | The Resinonace | 192.186.9.214 |        | 255.255.255.252 |
| A11    | The Dauntless  | 192.186.6.1   | /24    | 255.255.255.0   |
| A11    | Phanora        | 192.186.6.2   |        | 255.255.255.0   |
| A11    | Johan          | 192.186.6.3   |        | 255.255.255.0   |
| A12    | The Instrument | 192.186.9.217 | /30    | 255.255.255.252 |
| A12    | The Profound   | 192.186.9.218 |        | 255.255.255.252 |
| A13    | The Profound   | 192.186.8.129 | /25    | 255.255.255.128 |
| A13    | Spendrow       | 192.186.8.130 |        | 255.255.255.128 |
| A14    | The Firefirst  | 192.186.6.1   | /24    | 255.255.255.0   |
| A14    | The Queen      | 192.186.6.2   |        | 255.255.255.0   |
| A14    | Keith          | 192.186.6.3   |        | 255.255.255.0   |
| A15    | The Instrument | 192.186.9.221 | /30    | 255.255.255.252 |
| A15    | The FIrefirst  | 192.186.9.222 |        | 255.255.255.252 |
| A16    | Heiga          | 192.186.9.1   | /25    | 255.255.255.128 |
| A16    | The Profound   | 192.186.9.2   |        | 255.255.255.128 |
| A17    | The Witch      | 192.186.9.225 | /30    | 255.255.255.252 |
| A17    | The Queen      | 192.186.9.226 |        | 255.255.255.252 |
| A18    | The FIrefirst  | 192.186.10.1  | /23    | 255.255.254.0   |
| A18    | Oakleave       | 192.186.10.2  |        | 255.255.254.0   |
