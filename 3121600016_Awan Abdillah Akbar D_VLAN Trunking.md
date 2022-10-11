Nama    : Awan Abdillah Akbar Dhiya'ulhaq
NRP     : 3121600016
Kelas   : D4 IT A


# **VLAN Trunking**
 
## Tugas
3 switch yang diletakkan pada masing masing lantai kantor yang mana tiap lantai mempunyai 3 VLAN untuk memisahkan jaringan antara Admin, Developer dan Manager

[![image.png](https://i.postimg.cc/VNYzv95b/image.png)](https://postimg.cc/dhSbSy2q)

konfigurasi dari tiap PC
[![image.png](https://i.postimg.cc/vBnCLckW/image.png)](https://postimg.cc/R6MPvVMF)

konfigurasi dari switch dan router
### Router
```powershell
!
interface GigabitEthernet0/0
 no ip address
 duplex auto
 speed auto
!
interface GigabitEthernet0/1
 no ip address
 duplex auto
 speed auto
 shutdown
!
interface GigabitEthernet0/1.10
 encapsulation dot1Q 10
 ip address 192.168.1.1 255.255.255.0
!
interface GigabitEthernet0/1.20
 encapsulation dot1Q 20
 ip address 192.168.2.1 255.255.255.0
!
interface GigabitEthernet0/1.30
 encapsulation dot1Q 30
 ip address 192.168.3.1 255.255.255.0
!
interface Vlan1
 no ip address
 shutdown
```

### Switch lantai 1
```powershell
!
interface FastEthernet0/1
 switchport trunk allowed vlan 10,20,30
 switchport mode trunk
!
interface FastEthernet0/6
 switchport access vlan 10
!
interface FastEthernet0/7
 switchport access vlan 10
!
interface FastEthernet0/8
 switchport access vlan 10
!
interface FastEthernet0/9
 switchport access vlan 10
!
interface FastEthernet0/10
 switchport access vlan 10
!
interface FastEthernet0/11
 switchport access vlan 20
!
interface FastEthernet0/12
 switchport access vlan 20
!
interface FastEthernet0/13
 switchport access vlan 20
!
interface FastEthernet0/14
 switchport access vlan 20
!
interface FastEthernet0/15
 switchport access vlan 20
!
interface FastEthernet0/16
 switchport access vlan 30
!
interface FastEthernet0/17
 switchport access vlan 30
!
interface FastEthernet0/18
 switchport access vlan 30
!
interface FastEthernet0/19
 switchport access vlan 30
!
interface FastEthernet0/20
 switchport access vlan 30
!
interface Vlan1
 no ip address
 shutdown
```
### Switch lantai 2
```powershell
!
interface FastEthernet0/1
 switchport trunk allowed vlan 10,20,30
 switchport mode trunk
!
interface FastEthernet0/2
 switchport trunk allowed vlan 10,20,30
 switchport mode trunk
!
interface FastEthernet0/6
 switchport access vlan 10
!
interface FastEthernet0/7
 switchport access vlan 10
!
interface FastEthernet0/8
 switchport access vlan 10
!
interface FastEthernet0/9
 switchport access vlan 10
!
interface FastEthernet0/10
 switchport access vlan 10
!
interface FastEthernet0/11
 switchport access vlan 20
!
interface FastEthernet0/12
 switchport access vlan 20
!
interface FastEthernet0/13
 switchport access vlan 20
!
interface FastEthernet0/14
 switchport access vlan 20
!
interface FastEthernet0/15
 switchport access vlan 20
!
interface FastEthernet0/16
 switchport access vlan 30
!
interface FastEthernet0/17
 switchport access vlan 30
!
interface FastEthernet0/18
 switchport access vlan 30
!
interface FastEthernet0/19
 switchport access vlan 30
!
interface FastEthernet0/20
 switchport access vlan 30
!
interface GigabitEthernet0/1
 switchport trunk allowed vlan 10,20,30
 switchport mode trunk
!
interface Vlan1
 no ip address
 shutdown
```
### Switch lantai 3
```powershell
!
interface FastEthernet0/2
 switchport trunk allowed vlan 10,20,30
 switchport mode trunk
!
interface FastEthernet0/6
 switchport access vlan 10
!
interface FastEthernet0/7
 switchport access vlan 10
!
interface FastEthernet0/8
 switchport access vlan 10
!
interface FastEthernet0/9
 switchport access vlan 10
!
interface FastEthernet0/10
 switchport access vlan 10
!
interface FastEthernet0/11
 switchport access vlan 20
!
interface FastEthernet0/12
 switchport access vlan 20
!
interface FastEthernet0/13
 switchport access vlan 20
!
interface FastEthernet0/14
 switchport access vlan 20
!
interface FastEthernet0/15
 switchport access vlan 20
!
interface FastEthernet0/16
 switchport access vlan 30
!
interface FastEthernet0/17
 switchport access vlan 30
!
interface FastEthernet0/18
 switchport access vlan 30
!
interface FastEthernet0/19
 switchport access vlan 30
!
interface FastEthernet0/20
 switchport access vlan 30
!
interface Vlan1
 no ip address
 shutdown
```

## Test
1. VLAN yang sama
   [![image.png](https://i.postimg.cc/25WfTcBb/image.png)](https://postimg.cc/CZwtx47S)
2. Beda VLAN
   [![image.png](https://i.postimg.cc/k4DKkSqb/image.png)](https://postimg.cc/cgyv3rKx)