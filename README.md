# MINI-PROJECT-DDP-1-AUL
MINPRO 1 AUL  
Nama : AULIA ASHYLLA ANANDA PUTRI HARIAWAN  
NIM : 2509116076  
Kelas : SISTEM INFORMASI B'  

                      Sistem Pengelolaan Jadwal Ruangan Kampus bagian C Gedung Baru Fakultas Teknik Universitas Mulawarman 
Sistem Pengelolaan Jadwal Ruangan Kampus bagian C Gedung Baru FT Unmul adalah sebuah sistem sederhana yang di rancang untuk memudahkan pengguna/mahasiswa untuk membantu atau mengatur pemakaian ruang kuliah atau seminar terkhususnya gedung baru bagian C FT Unmul.  Di harapkan dengan adanya sistem ini dapat mengurangi terjadinya bentrok jadwal, salah pencatatan, atau kesulitan mencari ruangan yang kosong sehingga semua data jadwal bisa dikelola dengan lebih rapi dan mudah diakses.  

                  Flowchart Sistem Pengelolaan Jadwal Ruangan Kampus bagian C Gedung Baru Fakultas Teknik Universitas Mulawarman 
<img width="1024" height="1052" alt="FIX BISMILLAH drawio" src="https://github.com/user-attachments/assets/b2fdaa3c-851b-4ae0-bc66-a4d953ea4524" />  

                                            Penjelasan Alur Sistem Pengelolaan Jadwal Ruangan    
START : Program dimulai   
MENU UTAMA - Sistem menampilkan 4 pilihan:  
1. Tambah Jadwal (Create): Menambahkan jadwal ruangan yang ingin di pakai, termasuk input data jadwal baru    
2. Lihat Jadwal (Read): Menampilkan data seluruh jadwal ruangan atau pada hari dan jam tertentu    
3. Ubah Jadwal (Update): Mengedit atau memperbarui jadwal ruangan    
4. Hapus Jadwal (Delete): Menghapus atau mengganti jadwal ruangan apabila ada kondisi tertentu  
Menu tambahan:   
5. pengulangan (Looping) : Yaitu fitur yang di tambahkan setelah output dari kelima fitur utama dengan opsi “Aapakah ingin Kembali ke Menu Utama?” Ya/Tidak. Jika Ya maka       sistem akan kembali ke fitur menu utama, jika Tidak sistem akan selesai.  
END : Bearkhirnya Program

                                          PROGRAM PHYTON SISTEM PENJADWALAN

  ```phyton
print ("Sistem Pengelolaan Jadwal Ruangan Kampus bagian C Gedung Baru Fakultas Teknik Universitas Mulawarman ")

print ("Nama: Aulia Ashylla Ananda Putri Hariawan")

print ("NIM: 2509116076")

print ("Kelas: Sistem Informasi B'")

jadwal_ruangan = [{"ruangan": "C402", "tanggal": "01/08/2025", "jam": "09:30 - 10:30", "kegiatan": "Mata Kuliah Dasar Pemrograman"},
    {"ruangan": "C402", "tanggal": "04/08/2025", "jam": "10:40 - 11:40", "kegiatan": "Mata Kuliah Dasar Pemrograman"},
    {"ruangan": "C402", "tanggal": "05/08/2025", "jam": "13:00 - 15:00", "kegiatan": "Seminar Mata Kuliah"},
    {"ruangan": "C202", "tanggal": "01/08/2025", "jam": "13:00 - 15:00", "kegiatan": "Mata Kuliah Dasar Pemrograman"},
    {"ruangan": "C302", "tanggal": "02/08/2025", "jam": "14:00 - 16:00", "kegiatan": "Seminar Public Speaking"},
    {"ruangan": "C402", "tanggal": "01/08/2025", "jam": "13:00 - 15:00", "kegiatan": "Seminar Mata Kuliah"}]

Menu_Utama= ["Tambah Jadwal", "Lihat Jadwal", "Ubah Jadwal", "Hapus Jadwal"]

while True:
    print ("== Menu Utama Sistem Pengelolaan Jadwal Ruangan Kampus bagian C ==")
    for menu in Menu_Utama:
            print ("-", menu)


    menu = input ("Menu Utama: ")

    if menu == "Tambah Jadwal":

        print ("= Tambah Jadwal Baru =")

        nama_ruangan = input ("ID Ruangan: ")

        tanggal = input ("tanggal jadwal (DD/MM/YYYY): ")

        jam = input ("jam (HH/MM): ")

        kegiatan = input ("Nama kegiatan: ")

        print (" == Data berhasil di tambahkan ==")
        print (f"ID Ruangan: {nama_ruangan}")
        print (f"tanggal jadwal (DD/MM/YYYY): {tanggal}")
        print (f"jam (HH/MM): {jam}")
        print (f"Nama kegiatan: {kegiatan}")

        jadwal_baru = {
            "ID Ruangan": nama_ruangan, 
            "tanggal jadwal (DD/MM/YYYY)": tanggal,
            "jam (HH/MM)":  jam, 
            "Nama kegiatan": kegiatan}

        jadwal_ruangan.append(jadwal_baru)

        print(f"== Data berhasil di tambahkan, Jadwal Terbaru: {(jadwal_ruangan)} ==")

    elif menu == "Lihat Jadwal":

        print ("= Lihat Jadwal =")

        pilihan_filter = input ("Apakah ingin menggunakan filter? (Ya/Tidak): ")

        if pilihan_filter  == "Ya":

            print ("= Menggunakan Filter =")

            nama_ruangan = input ("ID Ruangan: ")

            tanggal = input ("tanggal jadwal (DD/MM/YYYY): ")


            ketemu = False
            for jadwal in jadwal_ruangan:
                if (jadwal ['ruangan'] == nama_ruangan and 
                jadwal ['tanggal'] == tanggal):
                    print("Jadwal Berdasarkan Filter")
                    print(f"- Ruangan : {jadwal['ruangan']}")
                    print(f" - Tanggal : {jadwal['tanggal']}")
                    print(f" - Jam     : {jadwal['jam']}")
                    print(f" - Kegiatan: {jadwal['kegiatan']}")

            ketemu = True
            if not ketemu:
                print ("Jadwal tidak ditemukan berdasarkan ID Ruangan dan Tanggal.")
    
        elif pilihan_filter == "Tidak":

            print (f"Seluruh Jadwal Ruangan: '{[jadwal_ruangan]}' ")

        else: 
            print ("Input Tidak Valid")

    elif menu == "Ubah Jadwal":
        print ("= Ubah Jadwal =")
        nama_ruangan = input ("ID Ruangan: ")
        tanggal = input ("tanggal jadwal (DD/MM/YYYY): ")

        ketemu = False
        for jadwal in jadwal_ruangan:
            if (jadwal["ruangan"] == nama_ruangan and 
                jadwal["tanggal"] == tanggal):

                print(f"Jadwal Ruangan berdasarkan ID Ruangan '{nama_ruangan}' tanggal '{tanggal}': ")
                print(f"- Ruangan : {jadwal['ruangan']}")
                print(f"- Tanggal : {jadwal['tanggal']}")
                print(f"- Jam     : {jadwal['jam']}")
                print(f"- Kegiatan: {jadwal['kegiatan']}")

                print("= Masukkan data baru =")
                ruangan_baru = input("ID Ruangan baru: ")
                tanggal_baru = input("Tanggal baru (DD/MM/YYYY): ")
                jam_baru = input("Jam baru (HH:MM - HH:MM): ")
                kegiatan_baru = input("Kegiatan baru: ")
                ketemu = True

                print("= Jadwal berhasil diubah =")
                jadwal_baru = {
                "ID Ruangan": ruangan_baru, 
                "tanggal jadwal (DD/MM/YYYY)": tanggal_baru,
                "jam (HH/MM)":  jam_baru, 
                "Nama kegiatan": kegiatan_baru}

    elif menu == "Hapus Jadwal":
        print ("= Hapus Jadwal =")
        nama_ruangan = input ("ID Ruangan: ")
        tanggal = input ("tanggal jadwal (DD/MM/YYYY): ")
        jam = input ("jam (HH/MM): ")

        jadwal_filter = []
        for jadwal in jadwal_ruangan:
            if (jadwal["ruangan"] == nama_ruangan and 
                jadwal["tanggal"] == tanggal and 
                jadwal["jam"] == jam):
                jadwal_filter.append(jadwal)

        if jadwal_filter:
            print(f"Jadwal Ruangan berdasarkan ID Ruangan '{nama_ruangan}', tanggal '{tanggal}' dan jam '{jam}':")
        for jadwal in jadwal_filter:
            print(f"- Ruangan: {jadwal['ruangan']}")
            print(f"- Tanggal: {jadwal['tanggal']}")
            print(f"- Jam: {jadwal['jam']}")
            print(f"- Kegiatan: {jadwal['kegiatan']}")
            print("-", jadwal_filter)

            for jadwal in jadwal_filter:
                jadwal_ruangan.remove(jadwal)
                print("Jadwal berhasil dihapus!")
                break

        if ketemu:

            print("== Berhasil Hapus Jadwal ==")

        if not ketemu:

            print ("== Jadwal tidak ditemukan berdasarkan ID Ruangan, Tanggal, dan Jam. ==")

    else:
        print("= INPUT TIDAK VALID =")
        menu_utama = input ("Apakah ingin kembali ke Menu Utama? (Ya/Tidak): ")

        if menu_utama == "Ya":
            print ("= Kembali ke Menu Utama =")
            continue

        elif menu_utama == "Tidak":
            print ("== Terima kasih sudah menggunakan sistem pengelolaan jadwal ==")
            break
        break
```

TAMPILAN AWAL   
<img width="1920" height="1080" alt="TAMPILAN AWAL" src="https://github.com/user-attachments/assets/bd53f607-5d76-4894-9b65-9c8900158b47" />  
Merupakan tampilan awal sistem jika dibuka, yang menampilkan menu-menu yang ada pada Menu Utama

                                                                CONDITIONAL STATEMENTS

1. KONDISI 1 (if)
<img width="1920" height="1080" alt="MENU TAMBAH JADWAL" src="https://github.com/user-attachments/assets/95e76a42-2460-4b3d-96bc-1359a62666c2" />  
Kondisi pertama dimana ketika pengguna menggunakan menu "Tambah Jadwal". Pengguna akan diminta untuk mengisi ID Ruangan, tanggal jadwal (DD/MM/YYYY) ,jam (HH/MM), dan Nama kegiatan.


          
2.1 KONDISI 2 (Elif)      
<img width="1920" height="1080" alt="MENU LIHAT JADWAL PAKE FILTER" src="https://github.com/user-attachments/assets/bb5eb821-0bb2-484f-a86d-10892f21832b" />    
Kondisi kedua adalah komdisi dimana pengguna memilih menu "Lihat Jadwal". Setelah mengetik menu pengguna akan diberi pilihan untuk melihat jadwal dalam kondisi memakai filter atau tidak. Dan dalam gambar diatas adalah kondisi dimana pengguna memilih "Ya" yaitu memakai filter, sehingga sistem hanya menampilkan jadwal sesuai dengan data yang diinput pengguna.


2.2 KONDISI 2 (Elif)       
<img width="1920" height="1080" alt="MENU LIHAT JADWAL TDK FILTER" src="https://github.com/user-attachments/assets/6ee3d98b-263f-4f27-9423-b7072432f55c" />  
Ini adalah tampilan jika pengguna memilih "Tidak" dimana sistem menampilkan seluruh jadwal yang berada di database.    


2.3 KONDISI 2 (Elif)   
<img width="1920" height="1080" alt="MENU 2 YA TDK VALID" src="https://github.com/user-attachments/assets/3542c097-261f-409a-b5c2-ffcdd3919580" />    
adalah kondisi dimana jika pengguna memilih menggunakan filter tetapi data yang di input tidak ada/valid.   


3.1 KONDISI 3 (Elif)        
<img width="1920" height="1080" alt="MENU UBAH JADWAL" src="https://github.com/user-attachments/assets/4fda69ac-ceb6-4532-b9de-72e036b58e96" />    
Kondsi ketiga adalah kondisi saat pengguna memilih menu "Ubah Jadwal", kegunaan menu ini untuk mengubaha jadwal yang sudah tersimpan di datavase. Pengguna akan diminta untuk mengisi format jadwal baru. Setelah berhasil mengisi data jadwal yang di ubah maka data akan di simpan di database.

    
3.2 KONDISI 3 (Elif)         
<img width="1920" height="1080" alt="UBAH JADWAL TDK VALID" src="https://github.com/user-attachments/assets/5ea68d2c-7ae9-443a-96d6-24b6bc3938ad" />     
adalah kondisi dimana pengguna memasukan data tetapi data yang di input tidak ada/valid.    


4. KONDISI 4 (Elif)      
<img width="1909" height="683" alt="MENU HAPUS JADWAL" src="https://github.com/user-attachments/assets/c252759e-2a0f-4cac-b152-a9f4d0e34a7d" />        
Kondisi keempat adalah kondisi saat pengguna memilih menu "Hapus Jadwal", Menu ini di gunakan untuk menghapus data jadwal ruagan yang tersimpan di database. Pada tampilan awalnya pengguna akan diminta mengisi ID Ruangan, tanggal dan jam agar sistem dapat mencari jadwal ruangan yang di maksud.


5.1 KONDISI 5 (Else)      
<img width="1920" height="1080" alt="TAMPILAN MENU UTAMA JIKA TDK VALID" src="https://github.com/user-attachments/assets/9f0d770d-f482-470b-8f5d-de86a0aa0301" />   
Kondisi kelima adalah ketika pengguna memasukan variabel yang tidak ada dalam sistem, ketika dalam kondisi seperti itu sistem akan menunjukan bahwa input tidak valid dan  pengguna akan di beri pilihan untuk kembali ke menu utama atau tidak.     


5.2 KONDISI 5 (else)      
<img width="1920" height="1080" alt="TAMPILAN MENU UTAMA TDK VALID YA" src="https://github.com/user-attachments/assets/2565024c-4fd9-4799-b712-b2d109006c06" />    
adalah kondisi lanjutan dimana jika pengguna memilih "Ya", sistem akan mengarahkan kembali ke menu utama.  


5.3 KONDISI 5 (else)      
<img width="1920" height="1080" alt="TAMPILAN MENU UTAMA JIKA TDK VALID TDK" src="https://github.com/user-attachments/assets/8475c530-c806-44ec-97b2-74f413a878df" />
adalah kondisi lanjutan jika pengguna memilih "Tidak", sistem akan selesai dijalankan.     


                                                                    LIST 

<img width="1661" height="282" alt="LIST DALAM PROGRAM" src="https://github.com/user-attachments/assets/c2686951-6ba8-4c10-8ac9-a37bef8dc0da" />  
Merupakan contoh LIST dalam program yang di jalankan

                                                                  TUPLE
<img width="1419" height="228" alt="TUPLE DALAM PROGRAM" src="https://github.com/user-attachments/assets/fa407a73-afdd-4e9e-9c60-8e393353a412" />  
Merupakan contoh TUPLE dalalam program yang saya jalankan   



   




