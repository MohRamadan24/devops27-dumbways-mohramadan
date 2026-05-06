**TASK WEEK 1 - DAY 1 BOOTCAMP DUMBWAYS DEVOPS BATCH 27**

**Task 1** : Secara konsep, jelaskan apa itu DevOps dengan bahasa kalian!

  DevOps ada posisi dalam suatu organisasi yang bertugas menjembatani atau menghubungkan proses kerja dari team developer dan team operational untuk mempercepat proses dari release. Dengan menerapkan metode CI/CD (Continuous Integration/Continuous Delivery), proses kerja akan saling berkesinambungan dan lebih efisien. Dengan menerapkan otomatisasi atau automation, proses kerja akan lebih efisien dengan mencegah adanya human error, dan proses menunggu pada setiap step manual. Selain itu, dengan menggunakan automation, issue dan error akan lebih cepat ditemukan yang berbading lurus dengan proses resolving issue.

**Task 2** : Install Ubuntu Server 22.04.x LTS menggunakan Virtualbox/VMware/Virtualization Tool pilihan kalian dan buat step-by-step langkah instalasinya!

Step - step instalasi Ubuntu Server 22.04.x LTS menggunakan VirtualBox pada Windows.
1. Download VirtualBox di link https://www.virtualbox.org/wiki/Downloads, pilih versi windows.
2. Download ubuntu server di link https://releases.ubuntu.com/22.04/?_ga=2.149898549.2084151835.1707729318-1126754318.1683186906, untuk mendapatkan "Ubuntu Server 22.04.x LTS". Pada halaman tersebut, scroll kebawah dan cari "ubuntu-22.04.5-live-server-amd64.iso", kemudian download file tersebut.
3. Install VirtualBox pada windows.
4. Jalan kan VirtualBox.
5. Pada VirtualBox, klik "New", dan kemudian isi form dengan detail sebagai berikut :
    - VM Name : dumbways
    - VM Folder : D:VirtualBox VMs
    - ISO Image : D:\Downloads\ubuntu-22.04.5-live-server-amd64.iso 
    - OS : Linux
    - OS Distribution : Ubuntu
    - OS Version : Ubuntu 22.04 LTS (Jammy Jellyfish) (64-bit)
    - Proceed with Unattended Installation : Unchecklist
    - Base Memory : 1024MB
    - Number of CPUs : 1
    - Disk Size : 10GB

    Pastikan ISO Image merujuk pada file ubuntu server yang telah di download, kemudian klik "finish"
6. Virtual Machine akan selesai dibuat dan siap di jalankan, klik "Start" untuk menjalankan.
7. Ketika VM sudah berjalan, step berikutnya adalah install dan set config ubuntu, ikuti langkah di bawah ini :<br><br>
   7.1 <img width="1560" height="777" alt="image" src="https://github.com/user-attachments/assets/804b8b0b-cb0a-4bd9-9a1e-b0b00caa181f" />
       Enter pada pilihan tersebut.<br><br>
   7.2 <img width="1516" height="862" alt="image" src="https://github.com/user-attachments/assets/a5cf03fb-9d21-418f-890d-ee06b6e3f64c" />
       Pilih opsi bahasa English kemudian enter<br><br>
   7.3 <img width="1516" height="862" alt="image" src="https://github.com/user-attachments/assets/9abaa4a0-d244-44a0-b19f-4b23cc64a9f0" />
       Pilih "Continue Without Updating" kemudia enter<br><br>
   7.4 <img width="1516" height="862" alt="image" src="https://github.com/user-attachments/assets/c316c642-668b-421d-9041-7c3e369a5e79" />
       Arahkan ke done, kemudian enter.<br><br>
   7.5 <img width="1516" height="862" alt="image" src="https://github.com/user-attachments/assets/06935c0f-fd92-4bff-b8b7-db290fdc401c" />
       Klik Dono<br><br>
   7.6 <img width="1516" height="862" alt="image" src="https://github.com/user-attachments/assets/7a690a52-3be1-43e2-b9c5-e12f8e97caf3" />
       Arahkan ke atas dengan panah ke "enp0s3", tekan enter<br><br>
   7.7 <img width="1516" height="862" alt="image" src="https://github.com/user-attachments/assets/73147817-673f-4235-af44-5b4262434f58" />
       Pilih "Edit IPv4"<br><br>
   7.8 <img width="1516" height="862" alt="image" src="https://github.com/user-attachments/assets/dc9405ea-0034-4645-ad22-1cab306b4f35" />
       Pilih "Manual"<br><br>
   7.9 <img width="1661" height="862" alt="image" src="https://github.com/user-attachments/assets/9aebdfc6-308b-414a-a2aa-9ad7b75828ef" />
       Isi form seperti gambar di atas, kemudian save (diisi menggunakan subnet wifi dan ping google.com)<br><br>
   7.10 <img width="1661" height="862" alt="image" src="https://github.com/user-attachments/assets/86f66119-540a-4c9a-b77e-debf8d4fb5a8" />
       Arahkan ke done, kemudian enter.<br><br>
   7.11 <img width="1661" height="862" alt="image" src="https://github.com/user-attachments/assets/defb56e1-1bc8-45b7-9242-d9512a2c7f20" />
       Arahkan ke done, kemudian enter. <br><br>
   7.12 <img width="1661" height="862" alt="image" src="https://github.com/user-attachments/assets/81f30ec3-09f2-4a16-9c96-94a69c73dee5" />
       Skip proses, Arahkan ke done, kemudian enter. <br><br>
   7.13 <img width="1661" height="862" alt="image" src="https://github.com/user-attachments/assets/75e488dd-3450-4047-b252-f90148089073" />
       Arahkan pada "custom storage layout", enter, kemudian arah kan ke done, kemudian enter<br><br>
   7.14 <img width="1661" height="862" alt="image" src="https://github.com/user-attachments/assets/a0ceac89-702f-459f-946d-5249c6f0cb0c" />
       Arahkan pada "Free storage", enter, arahkan pada "Add GPT Partition"<br><br>
   7.15 <img width="1661" height="862" alt="image" src="https://github.com/user-attachments/assets/3c316993-693c-4113-92e0-1904473fb682" />
       Isi size max "7G" kemudian "ext4" sebagai format nya, klik Arahkan ke create, kemudian enter.<br><br>
   7.16 Ulangi step 7.14
   7.17 <img width="1661" height="862" alt="image" src="https://github.com/user-attachments/assets/7b85740a-1171-4ba1-9207-662ccaa15515" />
       Isi size max "2.8G" kemudian "swap" sebagai format nya, Arahkan ke create, kemudian enter.<br><br>
   7.18 <img width="1661" height="862" alt="image" src="https://github.com/user-attachments/assets/b2f6ac02-af79-488c-90c5-81824de132ba" />
       Arahkan ke done, kemudian enter.<br><br>
   7.19 <img width="1661" height="862" alt="image" src="https://github.com/user-attachments/assets/269d0cf8-a96c-48a7-82bc-8bf9b7e08699" />
       Isi semua form sesuai dengan gambar, dengan pasword : 12345, Arahkan ke done, kemudian enter.<br><br>
   7.20 <img width="1661" height="862" alt="image" src="https://github.com/user-attachments/assets/fb97f4cf-5432-4047-a503-811266711f3c" />
       Arahkan ke done, kemudian enter.<br><br>
   7.21 <img width="1661" height="862" alt="image" src="https://github.com/user-attachments/assets/82d8da54-9d71-4eac-95ae-4fa0a66e899b" />
       Arahkan ke done, kemudian enter. Proses instalasi akan berlangsung, tolong tunggu hingga benar benar selesai.<br><br>
   7.22 <img width="1661" height="862" alt="image" src="https://github.com/user-attachments/assets/b9a3c8b0-7119-44af-b5ec-ef43dbf3b4a1" />
       Setelah instalasi selesai, arah kan ke Reboot Now, kemudian enter.
   7.23 <img width="1661" height="862" alt="image" src="https://github.com/user-attachments/assets/2fa96f72-93f8-4d1b-a06a-736dd09c9aaf" />
       Tekan enter. Tunggu hingga reboot selesai.
8. Proses instalasi ubuntu pada VirtualBox di Windows selesai. Untuk check koneksi yang digunakan. Ketik "Ping 8.8.8.8" untuk memonitor hasil ping ke google.com.
  









   



       



       






