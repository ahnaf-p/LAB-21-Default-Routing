# LAB-21-Default-Routing
Jumat 15 Agustus 2025  
  
# Default Routing  

# Router 2  
  1. Buat username dan password sesuai perintah di Topologi.  
     USN : ahnaf  
     PASS: Jaringan  
![a](usradd.PNG)  
  2. Login mengunakan user yang telah dibuat.  
![b](logon.PNG)  
  3. Ganti Identitas RB menjadi **R2**.  

         system identity set name=R2
  4. Tambahkan IP Address untuk ether1 dan ether2.  
     ether1 = 12.12.12.2/30 (untuk koneksi R2 ke R1)  
     ether2 = 12.12.12.5/30 (untuk koneksi R2 ke R3)  
![c]()  
  5. Sekarang konfigurasi static routing  
     dst addrs=11.11.11.0/27 gateway=12.12.12.1  
     dst addrs=22.22.22.0/29 gateway=12.12.12.6  
![e]()  
![m]()

# Router 3
  1. Buat username dan password sesuai perintah di Topologi.  

         user add name=ahnaf password=jaringan group=full  
  2. Login mengunakan user yang telah dibuat.  
![g](logon.PNG)  
  3. Ganti Identitas RB menjadi **R4**.  

          system identity set name=R3  
  4. Tambahkan IP Address untuk ether1 dan ether2.  
     ether1 = 12.12.12.6/30 (untuk koneksi R3 ke R2)  
     ether2 = 22.22.22.1/29 (untuk koneksi R3 ke Laptop B)

          
          ip address add interface=ether1 address=12.12.12.6/30  
          ip address add interface=ether2 address=22.22.22.1/29
  5. Sekarang konfigurasi static routing  
     dst addrs=11.11.11.0/27 gateway=12.12.12.5

          ip route add dst-address=11.11.11.0/27 gateway=12.12.12.5  
