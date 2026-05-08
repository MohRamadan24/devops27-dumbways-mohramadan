**TASK WEEK 1 - DAY 1 BOOTCAMP DUMBWAYS DEVOPS BATCH 27**

**TASK 1** : Akses server menggunakan terminal (Windows Terminal/PuTTY/etc.)

<img width="1482" height="762" alt="image" src="https://github.com/user-attachments/assets/810487c2-9350-411d-b79d-439654ac7284" />
<br><br>

**Task 2** : Konfigurasi ssh kalian agar bisa di akses hanya menggunakan publickey (password opsional, bisa dimatikan)

<img width="1482" height="762" alt="image" src="https://github.com/user-attachments/assets/07a23b23-0458-4bcf-8fe9-5434fd92b3eb" />
<br><br>

**Task 3** : Buat step by step penggunaan text manipulation! (grep, sed, cat, echo)
**cat** : 

Template : cat [list of file] > file_baru
Kondisi : 
  - ketika list of file tidak di isi, akan membuka text input yang akan di masukkan ke file_baru.
  - ketika list of file di isi, isi dari file file tersebut akan di masukkan ke file_baru.
Contoh penggunaan :
  - cat file1 > file baru
  - cat file1 file 2 > file baru
  - cat > file_baru
  - cat file1 (command untuk menampilkan isi file1)
  <br><br>

**sed** :

Template : sed 's/[word1]/[word2]/g' file1
Kondisi : 
  - System akan mencari word1 pada file1, dan jika ditemukan, akan di replace menjadi word2
Contoh penggunaan :
  - sed 's/hello/hai/g' file3 (replace "hello" menjadi "hai")
  <br><br>

**grep** : 

Template : 
  - grep [word] [file]
  - grep -c [word] [file]
Kondisi : 
  - ketika semua parameter di isi, system akan mencari "word" di dalam file dan akan di tampilkan dalam kondisi "word' i highlight.
  - Jika menambahkan -c, outpun berupa list dari file dan menampilkan jumlah "word" yang ada di dalam file.
  <br><br>

Contoh Penegunaan : 
  - grep hai file1
  - grep hai * (dicari pada semua file yang ada di repository yang sedang dibuka)
  - grep -c hai file1
  - manampilkan jumlah "hai" yang ada di dalam file1
  <br><br>

**sort** :

Template :
  - sort [file]
  - sort -r [file]
Kondisi : 
  - System akan membaca file dan mengurutkan isi di dalam nya dari kecil ke besar dan menampilkannya.
  - Jika menggunakan -r, system akan membaca file dan mengurutkan isi di dalamnya dari besar ke kecil dan menampilkannya.
Contoh penggunaan :
  - sort file1
  - sort -r file1
  <br><br>

**echo** : 

Template :
  - echo [file]
  - echo [input] > [file]
  - echo [input] >> [file]
Kondisi :
  - Jika command diikuti dengan "input" saja, input akan di terima dan ditampilkan.
  - Jika > hanya 1, system akan mengambil file, mengosongkan isi nya, dan menulis "input" kedalam file.
  - Jika > ada 2, system akan mengambil file, dan menambahkan "input" kedalam file.
Contoh penggunaan :
  - echo halo dunia
  - echo halo > file1
  - echo halo >> file2
  <br><br>

**Task 4** : Nyalakan ufw dengan memberikan akses untuk port 22, 80, 443, 3000, 5000 dan 6969!
<img width="1482" height="762" alt="image" src="https://github.com/user-attachments/assets/a0ec6330-e85b-4a89-a740-a23b535f5d92" />



