Nama    : Awan Abdillah Akbar Dhiya'ulhaq
NRP     : 3121600016
Kelas   : D4 IT A
# Laporan Pratikum Konsep Jaringan
# Cisco
---
# Case
1. Jelaskan proses mengirim data dari PC0 ke PC1
2. Apabila PC0 sudah pernah nge-_ping_ pada PC1, apakah melakukan _broadcast_ lagi?
3. Apabila PC0 sudah pernah mengirim data ke PC1 kemudian PC1 ingin mengirim data ke PC0 apakah perlu melakukan _broadcast_?
---
[![image.png](https://i.postimg.cc/nzn2nMZ7/image.png)](https://postimg.cc/HJPX2Yrs)
terdapat 3 pc yang masing2 memiliki ip : 192.168.1.1, 192.168.1.2, 192.168.1.3
[![image.png](https://i.postimg.cc/sxm2GjMt/image.png)](https://postimg.cc/gLwpfPqD)
simulation di filter untuk hanya menampilkan ICMP dan ARP
# Case 1
[![image.png](https://i.postimg.cc/zDc68m2B/image.png)](https://postimg.cc/hhVp1YBW)
pastikan tidak ada ARP yang tersimpan di pc
[![image.png](https://i.postimg.cc/nhyQJLBk/image.png)](https://postimg.cc/gxK0ymMX)
ping ke pc1
[![image.png](https://i.postimg.cc/J0SRks1Y/image.png)](https://postimg.cc/V0ByyL0X)
cek apa yang dikirim oleh PC1, dapat dilihat pada gambar diatas ini, terdapat Packet Boardcast yang dikirim yaitu _FFFF.FFFF.FFFF_, maksudnya PC1 mencari siapa yang memiliki _IP Address_ 192.168.1.3 pada _Network Devices_ dengan menggunakan _broadcast_
[![image.png](https://i.postimg.cc/YCMQG0hC/image.png)](https://postimg.cc/svHMbVYk)
setelah pc0 mengirim data ke pc1 ARP pc1 akan tercatat di pc0

# Case 2
[![image.png](https://i.postimg.cc/3x0HMX20/image.png)](https://postimg.cc/68KPnGjB)
ping lagi ke pc1
[![image.png](https://i.postimg.cc/YSjRDRFT/image.png)](https://postimg.cc/Mc21vydY)
packet tidak akan di broadcast lagi dikarenakan pc0 pernah melakukan ping ke pc1

# Case 3
[![image.png](https://i.postimg.cc/7YkkvGmK/image.png)](https://postimg.cc/bd3MkJXn)
dapat kita cek bahwa ip address pc0 telah tercatat di pc1, maka seharusnya packet dari pc1 tidak akan dibroadcast
[![image.png](https://i.postimg.cc/y8RYh4QG/image.png)](https://postimg.cc/mPbsRqG3)
ping dari pc1 ke pc0
[![image.png](https://i.postimg.cc/WpJNcPj1/image.png)](https://postimg.cc/Z04t62CG)
dikarenakan pc1 pernah menerima request packet dari pc0, maka ip address pc0 akan otomatis tersimpan ke pc1, dan packet tidak akan dibroadcast lagi.

