**TASK WEEK 1 - DAY 1 BOOTCAMP DUMBWAYS DEVOPS BATCH 27
**

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
7. Ketika VM sudah berjalan, step berikutnya adalah install dan set config ubuntu, ikuti langkah di bawah ini :
   7.1 <img width="1560" height="777" alt="image" src="https://github.com/user-attachments/assets/804b8b0b-cb0a-4bd9-9a1e-b0b00caa181f" />
       Enter pada pilihan tersebut.
   7.2 <img width="1516" height="862" alt="image" src="https://github.com/user-attachments/assets/a5cf03fb-9d21-418f-890d-ee06b6e3f64c" />
       Pilih opsi bahasa English kemudian enter
   7.3 <img width="1516" height="862" alt="image" src="https://github.com/user-attachments/assets/9abaa4a0-d244-44a0-b19f-4b23cc64a9f0" />
       Pilih "Continue Without Updating" kemudia enter
   7.4 <img width="1516" height="862" alt="image" src="https://github.com/user-attachments/assets/c316c642-668b-421d-9041-7c3e369a5e79" />
       Klik Done
   7.5 <img width="1516" height="862" alt="image" src="https://github.com/user-attachments/assets/06935c0f-fd92-4bff-b8b7-db290fdc401c" />
       Klik Dono
   7.6 <img width="1516" height="862" alt="image" src="https://github.com/user-attachments/assets/7a690a52-3be1-43e2-b9c5-e12f8e97caf3" />
       Arahkan ke atas dengan panah ke "enp0s3", klik enter

       <img width="1516" height="862" alt="image" src="https://github.com/user-attachments/assets/73147817-673f-4235-af44-5b4262434f58" />
       Pilih "Edit IPv4"

       <img width="1516" height="862" alt="image" src="https://github.com/user-attachments/assets/dc9405ea-0034-4645-ad22-1cab306b4f35" />
       Pilih "Manual"

       <img width="1661" height="862" alt="image" src="https://github.com/user-attachments/assets/9aebdfc6-308b-414a-a2aa-9ad7b75828ef" />
       Isi form seperti gambar di atas, kemudian save

       



       






