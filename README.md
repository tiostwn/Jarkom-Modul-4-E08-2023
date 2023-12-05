# Jarkom-Modul-4-E08-2023

**Anggota Kelompok ``E08`` ``192.210``** 
| No | Nama | NRP |
| --- | --- | --- |
| 1 | Samuel Berkat Hulu | 5025201055 |
| 2 | Hanafi Satriyo Utomo Setiawan | 5025211195 |

## Rute

Hasil dari `rute` yang kami dapatkan adalah sebagai berikut

| Nama Subnet | Rute                                    | Jumlah IP | Netmask |
|-------------|-----------------------------------------|-----------|---------|
| A1          | Fern-Switch4-AppetitRegion-LaubHills    | 1023      | /21     |
| A2          | Frieren-Switch3-Lakekorridor            | 25        | /27     |
| A3          | Fern-Flamme                             | 2         | /30     |
| A4          | Flamme-Switch5-RohrRoad                 | 1001      | /22     |
| A5          | Flamme-Frieren                          | 2         | /30     |
| A6          | Frieren-Aura                            | 2         | /30     |
| A7          | Aura-Denken                             | 2         | /30     |
| A8          | Denken-Switch2-RoyalCapital-WilleRegion | 127       | /24     |
| A9          | Himmel-Switch6-SchwerMountains          | 6         | /29     |
| A10         | Himmel-Flamme                           | 2         | /30     |
| A11         | Eisen-Switch1-Richter-Revolte           | 3         | /29     |
| A12         | Aura-Eisen                              | 2         | /30     |
| A13         | Eisen-Switch0-Stark                     | 2         | /30     |
| A14         | Eisen-Lugner                            | 2         | /30     |
| A15         | Lugner-Switch10-TurkRegion              | 1001      | /22     |
| A16         | Lugner-Switch9-GrobeForest              | 251       | /24     |
| A17         | Eisen-Linie                             | 2         | /30     |
| A18         | Lawine-Heiter-Switch7-BredtRegion       | 31        | /26     |
| A19         | Lawine-Linie                            | 2         | /30     |
| A20         | Haiter-Switch8-Sein-RiegelCanyon        | 512       | /22     |
| A21         | Linie-Switch11-GranzChannel             | 255       | /23     |
| Total       | -                                       | 4255      | /19     |



## CIDR
CIDR atau biasa dikenal *Classless Inter-Domain* Routing adalah suatu metode ``pengalamatan dan pengelompokan alamat IP`` yang memungkinkan penggunaan lebih efisien dari ruang alamat IP yang tersedia di Internet. Sebelum diperkenalkannya ``CIDR``, pengalamatan IP didasarkan pada kelas-kelas, seperti ``kelas A, kelas B, dan kelas C``. Setiap kelas memiliki ``ukuran tetap`` untuk jaringan dan host, yang seringkali mengakibatkan pemborosan alamat IP. 

**CIDR** menggantikan ``pendekatan kelas`` dengan memperkenalkan notasi format baru yang memungkinkan ``fleksibilitas`` lebih besar dalam pengelompokan dan alokasi alamat IP. Format notasi CIDR terdiri dari alamat IP dan prefiks (subnet mask) yang diwakili dalam ``format bilangan biner``, seperti contoh berikut:
```
192.173.0.0 / 24
```
Dalam contoh ini, ``"192.210.0.0"`` adalah alamat jaringan, dan ``"/24"`` menunjukkan bahwa ``24 bit pertama`` dari alamat ini digunakan sebagai ``netmask`` (subnet mask). Dengan menggunakan CIDR, ``administrator jaringan`` dapat menentukan ukuran subnet yang sesuai dengan kebutuhan tanpa terikat pada batasan kelas tradisional.

**Keuntungan utama** CIDR melibatkan ``penghematan alamat IP dan pengurangan pemborosan``. Dengan CIDR, tidak perlu lagi mengalokasikan blok alamat IP dengan ukuran yang tetap berdasarkan kelas. Sebagai contoh, jika suatu jaringan ``memerlukan 300 alamat IP``, administrator dapat menggunakan CIDR untuk mengalokasikan subnet dengan panjang netmask yang sesuai tanpa harus memilih kelas yang lebih besar dari yang dibutuhkan.

CIDR juga ``mendukung agregasi rute``, yang memungkinkan penyederhanaan tabel routing di Internet. Dengan ``menggabungkan beberapa blok alamat IP ke dalam satu entri routing``, CIDR membantu mengurangi ukuran tabel routing dan efektif meningkatkan efisiensi dalam pengelolaan lalu lintas jaringan global.

### Penggabungan IP

### Kondisi Node Awal
Berikut merupakan inisialisasi kami yang akan digunakan untuk melakukan penggabungan IP
![Slide 16_9 - 1](https://github.com/tiostwn/Jarkom-Modul-4-E08-2023/assets/53292102/e3da187f-4193-458f-9ddf-e50a2b8943b7)

### Penggabungan I
<table><thead><tr><th rowspan="3">Subnet</th><th colspan="4">Gabungan dari</th><th rowspan="3">Netmask Akhir</th></tr><tr><th colspan="2">1</th><th colspan="2">2</th></tr><tr><th>Subnet</th><th>Netmask</th><th>Subnet</th><th>Netmask</th></tr></thead><tbody><tr><td>B1</td><td>A18</td><td>/26</td><td>A20</td><td>/22</td><td>/21</td></tr><tr><td>B2</td><td>A9</td><td>/29</td><td>A10</td><td>/22</td><td>/21</td></tr><tr><td>B3</td><td>A1</td><td>/21</td><td>A3</td><td>/30</td><td>/20</td></tr></tbody></table>

![Slide 16_9 - 2](https://github.com/tiostwn/Jarkom-Modul-4-E08-2023/assets/53292102/4e01c192-a1f3-4ea2-9910-d7adc6a84215)

### Penggabungan II

<table>
<thead>
  <tr>
    <th rowspan="3">Subnet</th>
    <th colspan="4">Gabungan dari</th>
    <th rowspan="3">Netmask Akhir</th>
  </tr>
  <tr>
    <th colspan="2">1</th>
    <th colspan="2">2</th>
  </tr>
  <tr>
    <th>Subnet</th>
    <th>Netmask</th>
    <th>Subnet</th>
    <th>Netmask</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td>C1</td>
    <td>B1</td>
    <td>/21</td>
    <td>A19</td>
    <td>/30</td>
    <td>/20</td>
  </tr>
  <tr>
    <td>C2</td>
    <td>B3</td>
    <td>/20</td>
    <td>A6</td>
    <td>/22</td>
    <td>/19</td>
  </tr>
  <tr>
    <td>C3</td>
    <td>A15</td>
    <td>/22</td>
    <td>A16</td>
    <td>/24</td>
    <td>/21</td>
  </tr>
</tbody>
</table>

![Slide 16_9 - 3](https://github.com/tiostwn/Jarkom-Modul-4-E08-2023/assets/53292102/9d8ceab3-7c62-4c6b-8c64-bfa9ec01869e)

### Penggabungan III

<table>
<thead>
  <tr>
    <th rowspan="3">Subnet</th>
    <th colspan="4">Gabungan dari</th>
    <th rowspan="3">Netmask Akhir</th>
  </tr>
  <tr>
    <th colspan="2">1</th>
    <th colspan="2">2</th>
  </tr>
  <tr>
    <th>Subnet</th>
    <th>Netmask</th>
    <th>Subnet</th>
    <th>Netmask</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td>D1</td>
    <td>C1</td>
    <td>/20</td>
    <td>A21</td>
    <td>/23</td>
    <td>/19</td>
  </tr>
  <tr>
    <td>D2</td>
    <td>C2</td>
    <td>/19</td>
    <td>B2</td>
    <td>/21</td>
    <td>/18</td>
  </tr>
  <tr>
    <td>D3</td>
    <td>C3</td>
    <td>/21</td>
    <td>A14</td>
    <td>/30</td>
    <td>/20</td>
  </tr>
  <tr>
    <td>D4</td>
    <td>A9</td>
    <td>/30</td>
    <td>A10</td>
    <td>/24</td>
    <td>/23</td>
  </tr>
</tbody>
</table>

![Slide 16_9 - 9](https://github.com/tiostwn/Jarkom-Modul-4-E08-2023/assets/53292102/065b1e05-0906-49b3-b934-f231f372e064)

### Penggabungan IV

<table>
<thead>
  <tr>
    <th rowspan="3">Subnet</th>
    <th colspan="4">Gabungan dari</th>
    <th rowspan="3">Netmask Akhir</th>
  </tr>
  <tr>
    <th colspan="2">1</th>
    <th colspan="2">2</th>
  </tr>
  <tr>
    <th>Subnet</th>
    <th>Netmask</th>
    <th>Subnet</th>
    <th>Netmask</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td>E1</td>
    <td>D2</td>
    <td>/18</td>
    <td>A3</td>
    <td>/30</td>
    <td>/17</td>
  </tr>
  <tr>
    <td>E2</td>
    <td>D1</td>
    <td>/19</td>
    <td>A17</td>
    <td>/30</td>
    <td>/18</td>
  </tr>
  <tr>
    <td>E3</td>
    <td>A13</td>
    <td>/30</td>
    <td>D3</td>
    <td>/20</td>
    <td>/19</td>
  </tr>
</tbody>
</table>

![Slide 16_9 - 10](https://github.com/tiostwn/Jarkom-Modul-4-E08-2023/assets/53292102/533ea34c-e3e1-48ca-9eca-207ed525f8e6)

### Penggabungan V

<table>
<thead>
  <tr>
    <th rowspan="3">Subnet</th>
    <th colspan="4">Gabungan dari</th>
    <th rowspan="3">Netmask Akhir</th>
  </tr>
  <tr>
    <th colspan="2">1</th>
    <th colspan="2">2</th>
  </tr>
  <tr>
    <th>Subnet</th>
    <th>Netmask</th>
    <th>Subnet</th>
    <th>Netmask</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td>F1</td>
    <td>E1</td>
    <td>/17</td>
    <td>A2</td>
    <td>/27</td>
    <td>/16</td>
  </tr>
  <tr>
    <td>F2</td>
    <td>E2</td>
    <td>/18</td>
    <td>A12</td>
    <td>/29</td>
    <td>/17</td>
  </tr>
</tbody>
</table>

![Slide 16_9 - 11](https://github.com/tiostwn/Jarkom-Modul-4-E08-2023/assets/53292102/229780f7-fc71-4ff7-95ce-a03d6e8d9abb)

### Penggabungan VI

<table>
<thead>
  <tr>
    <th rowspan="3">Subnet</th>
    <th colspan="4">Gabungan dari</th>
    <th rowspan="3">Netmask Akhir</th>
  </tr>
  <tr>
    <th colspan="2">1</th>
    <th colspan="2">2</th>
  </tr>
  <tr>
    <th>Subnet</th>
    <th>Netmask</th>
    <th>Subnet</th>
    <th>Netmask</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td>G1</td>
    <td>F1</td>
    <td>/16</td>
    <td>A1</td>
    <td>/30</td>
    <td>/15</td>
  </tr>
  <tr>
    <td>G2</td>
    <td>F2</td>
    <td>/17</td>
    <td>E3</td>
    <td>/19</td>
    <td>/16</td>
  </tr>
</tbody>
</table>

![Slide 16_9 - 12](https://github.com/tiostwn/Jarkom-Modul-4-E08-2023/assets/53292102/ddf26ed5-3733-4629-805f-90ab1b20e09d)

### Penggabungan VII
<table>
<thead>
  <tr>
    <th rowspan="3">Subnet</th>
    <th colspan="4">Gabungan dari</th>
    <th rowspan="3">Netmask Akhir</th>
  </tr>
  <tr>
    <th colspan="2">1</th>
    <th colspan="2">2</th>
  </tr>
  <tr>
    <th>Subnet</th>
    <th>Netmask</th>
    <th>Subnet</th>
    <th>Netmask</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td>H1</td>
    <td>G1</td>
    <td>/15</td>
    <td>D4</td>
    <td>/23</td>
    <td>/14</td>
  </tr>
  <tr>
    <td>H2</td>
    <td>A11</td>
    <td>/30</td>
    <td>G2</td>
    <td>/16</td>
    <td>/15</td>
  </tr>
</tbody>
</table>

![Slide 16_9 - 13](https://github.com/tiostwn/Jarkom-Modul-4-E08-2023/assets/53292102/7083cc54-0af4-409f-be9b-8dbaea6ebfac)

### Penggabungan VIII

<table>
<thead>
  <tr>
    <th rowspan="3">Subnet</th>
    <th colspan="4">Gabungan dari</th>
    <th rowspan="3">Netmask Akhir</th>
  </tr>
  <tr>
    <th colspan="2">1</th>
    <th colspan="2">2</th>
  </tr>
  <tr>
    <th>Subnet</th>
    <th>Netmask</th>
    <th>Subnet</th>
    <th>Netmask</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td>I1</td>
    <td>H1</td>
    <td>/14</td>
    <td>H2</td>
    <td>/15</td>
    <td>/13</td>
  </tr>
</tbody>
</table>

![Slide 16_9 - 14](https://github.com/tiostwn/Jarkom-Modul-4-E08-2023/assets/53292102/c0aeb31c-2ffa-4647-9ec4-1de073fb0405)

### Tree

Setelah dilakukannya penggabungan IP, sekarang kita melakukan pembagian IP dengan menggunakan tree pada masing-masing kelompok yang telah dibuat sebelumnya sebagai berikut

![CIDR TREE](https://github.com/tiostwn/Jarkom-Modul-4-E08-2023/assets/53292102/54890b53-f059-4120-ae0e-dece7aa201d9)

### Pembagian IP

Berikut merupakan hasil dari pembagian IP berdasarkan Tree yang telah dibuat sebelumnya

Subnet | Network ID | Netmask | Broadcast
--- | --- | --- | --- 
A1 | 192.211.0.0 | 255.255.255.252 | 192.211.0.3 
A2 | 192.210.128.0/27 | 255.255.255.224 | 192.210.128.32 
A3 | 192.210.64.0/30 | 255.255.255.252 | 192.210.64.3 
A4 | 192.210.8.0/30 | 255.255.255.252 | 192.210.8.3 
A5 | 192.210.0.0/21 | 255.255.255.248 | 192.210.7.255 
A6 | 192.210.16.0/22 | 255.255.252.0 | 192.210.19.255 
A7 | 192.210.32.8/30 | 255.255.255.252 | 192.210.32.11 
A8 | 192.210.32.0/29 | 255.255.255.248 | 192.210.32.7 
A9 | 192.212.1.0/30 | 255.255.255.252 | 192.212.1.3 
A10 | 192.212.0.0/24 | 255.255.255.0 | 192.212.0.255
A11 | 192.215.0.0/30 | 255.255.255.252 | 192.215.0.3 
A12 | 192.214.64.0/29 | 255.255.255.248 | 192.214.64.7
A13 | 192.214.144.0/30 | 255.255.255.252 | 192.214.144.3
A14 | 192.214.136.0/30 | 255.255.255.252 | 192.214.136.3
A15 | 192.214.128.0/22 | 255.255.252.0 | 192.214.131.255
A16 | 192.214.132.0/24 | 255.255.255.0 | 192.214.132.255
A17 | 192.214.32.0/30 | 255.255.255.252 | 192.214.32.3 
A18 | 192.214.4.0/26 | 255.255.255.192 | 192.214.4.63
A19 | 192.214.8.0/30 | 255.255.255.252 | 192.214.8.3
A20 | 192.214.0.0/22 | 255.255.252.0 | 192.214.3.255
A21 | 192.214.16.0/23 | 255.255.254.0 | 192.214.17.255 


