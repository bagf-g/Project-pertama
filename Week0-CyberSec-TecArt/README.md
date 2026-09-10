# Nama   : Arya Bhayangkara Sangker

# NIM    : 260530911083

# Divisi : Forensik

## Langkah-langkah penginstalan tools & Penyelesaian Challenge CTF

## Tools umum

### 1.WSL

WSL atau Windows Subsystem for Linux adalah sebuah fitur bawaan dari Microsoft yang memungkinkan kita untuk menjalankan sistem operasi Linux (seperti Debian, Ubuntu, atau Kali Linux) secara langsung di dalam Windows, tanpa memerlukan reboot atau memakai virtual machine.

Berikut langkah-langkah menginstall wsl di Sistem Operasi Windows 10 :

1. ![Langkah1](img/wsl1.png)

   Buka Command Prompt dengan menekan windows key dan ketik command prompt, jangan lupa run as administrator.




2. ![Langkah2](img/wsl2.png)

   Akan terlihat tampilan Command Promptnya dan jalankan command "wsl --install" dan tunggu hingga selesai.




3. ![Langkah3](img/wsl3.png)

   Setelah itu lakukan Restart.



4. ![Langkah4](img/wsl4.png)

   Buka lagi Command promptnya (jangan lupa run as administrator) terus jalankan lagi command "wsl -- install" disini
   perintah ini akan otomatis menginstall linux Ubuntu secara Default



5. ![Langkah5](img/wsl5.png)

   Setelah proses download selesai akan muncul teks untuk membuat user account untuk linux kita tadi.



6. ![Langkah6](img/wsl7.png)

   Disini untuk user saya adalah bagf, dan setelah mengisi user akan muncul teks untuk mengisi passwrd.



7. ![Langkah7](img/wsl8.png)

    Setelah mengisi user dan password kita, nantinya akan ada pertannyaan permintaan izin dari Ubuntu untuk
    mengumpulkan data spesifikasi komputer kita untuk meningkatkan fitur dan kecocokan sistem mereka. bisa jawab Y (Yes)
    atau n (no). saya sih no no ya.. :>



 8. ![Langkah8](img/wsl9.png)

    Dan beginilah tampilan WSLnya.





    ### 2. Python

    Python Adalah bahasa pemrograman.

    ![Langkah1](img/tespython.png)

    Disini kita mengecek apakah python berjalan dengan baik. Caranya dengan jalakan perintah python3, nantinya akan ada
    simbol >>>
    untuk mengetesnya bisa dengan line sederhana seperti print ("Hello TecArt") dan nantinya terminal akan print
    "Hello TecArt"





### 3. Challenge

   Disini kita akan mengerjakan Challenge "Undo" pada platform CYLAB Academy:  
    https://learn.cylabacademy.org/library/766

 Berikut Langkah_langkahnya :


1. ![Langkah1](img/Undo1.png)

   Buka halaman challenge "Undo" dan connect ke server menggunakan command "nc foggy-cliff.picoctf.net 57244"
   Pada WSL kita.



2. ![Langkah2](img/Undo2.png)

   Setelah terhubung, muncul Step 1 dengan flag yang sudah di-encode Base64. Diminta memasukkan command untuk membalikkan
   encoding tersebut.



3. ![Langkah3](img/Undo3.png)

   Masukkan command "base64 -d" untuk mendecode string Base64 tadi.



4. ![Langkah4](img/Undo4.png)

   Step 1 berhasi, lanjut ke Step 2 dimana teksnya sudah di reverse, jadi kita gunakan command rev untuk mengembalikannya.



5. ![Langkah5](img/Undo5.png)

   Step 4 berhasil pakai "tr '()' '{}'". Lanjut Step 5, teks di-ROT13



6. ![Langkah6](img/Undo6.png)

   Step 4 berhasil dengan command "tr '()' '{}". Lanjut ke Step 5, teks terakhir di-ROT13, harus dibalikkan pakai command "tr".



7. ![Langkah7](img/Undo7.png)

   Masukkan command "tr 'A-Za-z' 'N-ZA-Mn-za-m'" untuk membalikkan ROT13, dan ada muncul flagnya : "picoCTF{Revers1ng_t3xt_Tr4nsf0rm@t10ns_0ea42cd0}".



8. ![Langkah8](img/Undo8.png)

   Tinggal submit flagnya dan selesai.


### 3. Forensics

Disini kita akan menginstall dan melakukan pengujian ExifTool pada WSL
dan mengerjakan challenge "Information".
https://learn.cylabacademy.org/library/186


1. ![Langkah1](img/information1.png)

   Disini kita disuruh mencari flag dari file gambar cat.jpg



2. ![Langkah2](img/information2.png)

   Ini tampilan gambar dari file cat.jpg hanya ada gambar kucing lucu🐈.
   Tapi sebenarnya flagnya berada pada metadata filenya, kita bisa memakai ExifTool untuk
   melihat metadata suatu file.
   



3. ![Langkah3](img/information4.png)

   Untuk menginstallnya bisa dengan menggunakan command "sudo apt install libimage-exiftool-perl -y"


   
4. ![Langkah4](img/information5.png)

   Setelah itu kita bisa pindah ke direktori dimana file kucing itu berada, kalau di saya berada pada direktori
   Downloads.



5. ![Langkah5](img/information6.png)

   setelah itu kita bisa jalankan command exiftool cat.jpg



6. ![Langkah6](img/information7.png)

   Disini kita bisa melihat detail filenya, dan untuk bagian License ada string panjang yang mencurigakan



7. ![Langkah7](img/information9.png)

    Kita langsung sja mendecode string itu dengan command "echo "Masukkan String" | base64 -d".
    dan muncul flagnya.

   

8. ![Langkah8](img/information10.png)

     Masukkan Flag dan selesai.



   
    


    

    
     

     







