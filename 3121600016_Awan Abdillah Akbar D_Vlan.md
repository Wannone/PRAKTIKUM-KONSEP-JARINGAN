Nama    : Awan Abdillah Akbar Dhiya'ulhaq
NRP     : 3121600016
Kelas   : D4 IT A

VLAN

[![image.png](https://i.postimg.cc/QdZWpBQ2/image.png)](https://postimg.cc/HV3xmkPz)

Pada rangkaian diatas, buat 2 grup dengan asumsi group 1 (PC0 - PC3) berada pada ruang 1 (VLAN 100) dan group 2 (PC4 - PC7) berada pada ruang 2 (VLAN 200)

### **Konfigurasi PC**

alokasi IP masing masing PC sebagai berikut:
| **PC** |    **IP**     | **Port pada switch** |
| :----: | :-----------: | :------------------: |
|  PC0   | `192.168.1.1` |   FastEthernet0/1    |
|  PC1   | `192.168.1.2` |   FastEthernet0/2    |
|  PC2   | `192.168.1.3` |   FastEthernet0/3    |
|  PC3   | `192.168.1.4` |   FastEthernet0/4    |
|  PC4   | `192.168.1.5` |   FastEthernet0/11   |
|  PC5   | `192.168.1.6` |   FastEthernet0/12   |
|  PC6   | `192.168.1.7` |   FastEthernet0/13   |
|  PC7   | `192.168.1.8` |   FastEthernet0/14   |

Untuk membuktikan bahwa semua dapat komputer terhubung , kita bisa tes `ping` antar PC, semisal kita akan ping PC dengan IP `192.168.1.8` dari PC dengan IP `192.168.1.1`. Disini masih bisa terhubung dikarenakan belum ada pembatas yang membatasi akses antar ruang.

### **Konfigurasi switch**

Setelah semua PC sudah tersambung dengan switch, maka sekarang kita akan masuk ke konfigurasi dari switch

Pertama kita akan setup untuk VLAN 100 , masuk ke CLI pada switch dan masukkan perintah pada gambar berikut

[![image.png](https://i.postimg.cc/gkm1TsH4/image.png)](https://postimg.cc/ThNkyrSW)

Lakukan hal yang sama dengan VLAN 200.

Setelah itu kita lanjutkan dengan membatasi port yang digunakan, kita asumsikan `fa0/1 - fa0/10` akan digunakan pada ruang 1 dan `fa0/11 - fa0/20` digunakan pada ruang 2.

Gunakan perintah dibawah ini untuk melakukan pembatasan port

[![image.png](https://i.postimg.cc/XYcq0QRJ/image.png)](https://postimg.cc/jD2tHQd0)

Setelah konfigurasi switch selesai, kita bisa `exit`.
Untuk memastikan bahwa konfigurasi sudah berhasil dilakukan, gunakan perintah `show vlan brief` untuk melihat port mana saja yang sudah terhubung

[![image.png](https://i.postimg.cc/xdpmb99h/image.png)](https://postimg.cc/rdWsBX0N)

Tes `ping` PC pada ruang 2 dari PC di ruang 1

[![image.png](https://i.postimg.cc/J4THF1kn/image.png)](https://postimg.cc/F7LKdXG5)

Bisa dilihat jika proses gagal karena akses ruang sudah dibatasi oleh V-LAN