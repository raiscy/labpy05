# labpy05

# Praktikum 5 

# Tugas Praktikum 
Buat program sederhana yang akan menampilkan daftar nilai mahasiswa, dengan ketentuan : 
1. Program dibuat dengan menggunakan Dictionary
2. Tampilkan menu pilihan: (Tambah Data, Ubah Data, Hapus Data, Tampilkan Data, Cari Data)
3. Nilai Akhir diambil dari perhitungan 3 komponen nilai (tugas: 30%, uts: 35%, uas: 35%)
4. Buat flowchart dan penjelasan programnya

        def hitung_nilai_akhir(tugas, uts, uas):
            return (tugas * 0.3) + (uts * 0.35) + (uas * 0.35)

        def tambah_data(mahasiswa):
            nim = input("Masukkan NIM: ")
            nama = input("Masukkan Nama: ")
            tugas = float(input("Masukkan Nilai Tugas: "))
            uts = float(input("Masukkan Nilai UTS: "))
            uas = float(input("Masukkan Nilai UAS: "))
    
            nilai_akhir = hitung_nilai_akhir(tugas, uts, uas)
            mahasiswa[nim] = {'nama': nama, 'tugas': tugas, 'uts': uts, 'uas': uas, 'nilai_akhir': nilai_akhir}
            print("Data berhasil ditambahkan.")

        def ubah_data(mahasiswa):
            nim = input("Masukkan NIM yang ingin diubah: ")
            if nim in mahasiswa:
                nama = input("Masukkan Nama baru: ")
                tugas = float(input("Masukkan Nilai Tugas baru: "))
                uts = float(input("Masukkan Nilai UTS baru: "))
                uas = float(input("Masukkan Nilai UAS baru: "))
        
                nilai_akhir = hitung_nilai_akhir(tugas, uts, uas)
                mahasiswa[nim] = {'nama': nama, 'tugas': tugas, 'uts': uts, 'uas': uas, 'nilai_akhir': nilai_akhir}
                print("Data berhasil diubah.")
          else:
                print("NIM tidak ditemukan.")

        def hapus_data(mahasiswa):
            nim = input("Masukkan NIM yang ingin dihapus: ")
            if nim in mahasiswa:
                del mahasiswa[nim]
                print("Data berhasil dihapus.")
            else:
                print("NIM tidak ditemukan.")

        def tampilkan_data(mahasiswa):
            if not mahasiswa:
                print("Tidak ada data mahasiswa.")
                return
            print("Daftar Data Mahasiswa:")
            print("================================================")
            print("| No | NIM | Nama | Tugas | UTS | UAS | Akhir |")
            print("================================================")
            for i, (nim, data) in enumerate(mahasiswa.items()):
                print(f"| {i + 1} | {nim} | {data['nama']} | {data['tugas']} | {data['uts']} | {data['uas']} | {data['nilai_akhir']:.2f} |")
            print("================================================")

        def cari_data(mahasiswa):
            nim = input("Masukkan NIM yang ingin dicari: ")
            if nim in mahasiswa:
                data = mahasiswa[nim]
                print(f"NIM: {nim}, Nama: {data['nama']}, Tugas: {data['tugas']}, UTS: {data['uts']}, UAS: {data['uas']}, Nilai Akhir: {data['nilai_akhir']:.2f}")
            else:
                print("NIM tidak ditemukan.")
    
        def main():
            mahasiswa = {}
            while True:
                  print("\nMenu:")
                  print("1. Tambah Data")
                  print("2. Ubah Data")
                  print("3. Hapus Data")
                  print("4. Tampilkan Data")
                  print("5. Cari Data")
                  print("6. Keluar")
        
                  pilihan = input("Pilih menu (1-6): ")
        
                  if pilihan == '1':
                      tambah_data(mahasiswa)
                  elif pilihan == '2':
                      ubah_data(mahasiswa)
                  elif pilihan == '3':
                      hapus_data(mahasiswa)
                  elif pilihan == '4':
                      tampilkan_data(mahasiswa)
                  elif pilihan == '5':
                      cari_data(mahasiswa)
                  elif pilihan == '6':
                      print("Terima kasih!")
                      break
                  else:
                      print("Pilihan tidak valid. Silakan coba lagi.")

        if __name__ == "__main__":
              main()

PROSES INPUT DATA 
![Screenshot 2024-11-20 183548](https://github.com/user-attachments/assets/308e3c2d-3de3-43f5-b844-9563cf622462)
![Screenshot 2024-11-20 184257](https://github.com/user-attachments/assets/92c75000-248c-4457-a6fa-85de8c1dfebb)
![Screenshot 2024-11-20 184418](https://github.com/user-attachments/assets/674f247f-c042-4648-ae44-14761dd553ea)
![Screenshot 2024-11-20 184513](https://github.com/user-attachments/assets/7bac16ad-4719-459d-b419-e6828493081c)

HASIL OUTPUT 
![Screenshot 2024-11-20 184748](https://github.com/user-attachments/assets/f4cb8241-3974-4544-9dd0-bb4b29050f89)
![Screenshot 2024-11-20 184827](https://github.com/user-attachments/assets/8c5daadf-234a-47ac-b9df-8221b973aaa3)
![Screenshot 2024-11-20 184908](https://github.com/user-attachments/assets/655cb1c3-6831-4b7d-9457-2939de32d68c)
![Screenshot 2024-11-20 185147](https://github.com/user-attachments/assets/b5278795-5077-4c64-b9be-57619bfd44b4)

PENJELASAN : 

1. Fungsi hitung_nilai_akhir(tugas, uts, uas):
        Fungsi ini menerima tiga parameter: nilai tugas, UTS, dan UAS.
        Menghitung nilai akhir berdasarkan bobot yang telah ditentukan (30% tugas, 35% UTS, dan 35% UAS).
        Mengembalikan nilai akhir sebagai hasil.

2. Fungsi tambah_data(mahasiswa):
        Mengambil input dari pengguna untuk NIM, nama, nilai tugas, UTS, dan UAS.
        Menghitung nilai akhir dengan memanggil fungsi hitung_nilai_akhir.
        Menyimpan data mahasiswa dalam dictionary mahasiswa dengan NIM sebagai kunci dan data lainnya sebagai nilai.
        Menampilkan pesan bahwa data berhasil ditambahkan.

3. Fungsi ubah_data(mahasiswa):
        Mengambil input NIM yang ingin diubah.
        Memeriksa apakah NIM tersebut ada dalam dictionary mahasiswa.
        Jika ada, meminta pengguna untuk memasukkan data baru (nama, nilai tugas, UTS, dan UAS).
        Menghitung nilai akhir dan memperbarui data mahasiswa di dictionary.
        Menampilkan pesan bahwa data berhasil diubah atau bahwa NIM tidak ditemukan.

4. Fungsi hapus_data(mahasiswa):
        Mengambil input NIM yang ingin dihapus.
        Memeriksa apakah NIM tersebut ada dalam dictionary mahasiswa.
        Jika ada, menghapus data mahasiswa dari dictionary dan menampilkan pesan bahwa data berhasil dihapus.
        Jika tidak ada, menampilkan pesan bahwa NIM tidak ditemukan.

5. Fungsi tampilkan_data(mahasiswa):
        Memeriksa apakah ada data mahasiswa dalam dictionary.
        Jika tidak ada, menampilkan pesan bahwa tidak ada data mahasiswa.
        Jika ada, menampilkan daftar data mahasiswa dalam format tabel dengan kolom NIM, Nama, Tugas, UTS, UAS, dan Nilai Akhir.

6. Fungsi cari_data(mahasiswa):
        Mengambil input NIM yang ingin dicari.
        Memeriksa apakah NIM tersebut ada dalam dictionary mahasiswa.
        Jika ada, menampilkan semua data mahasiswa yang sesuai dengan NIM tersebut.
        Jika tidak ada, menampilkan pesan bahwa NIM tidak ditemukan.

7. Fungsi main():
        Inisialisasi dictionary mahasiswa untuk menyimpan data mahasiswa.
        Menggunakan loop while untuk menampilkan menu kepada pengguna.
        Pengguna dapat memilih opsi untuk menambah, mengubah, menghapus, menampilkan, atau mencari data mahasiswa.
        Berdasarkan pilihan pengguna, fungsi yang sesuai akan dipanggil.
        Jika pengguna memilih untuk keluar, program akan menampilkan pesan terima kasih dan menghentikan eksekusi.

8. Penggunaan if __name__ == "__main__"::
        Memastikan bahwa fungsi main() hanya dijalankan ketika file ini dieksekusi sebagai program utama, bukan ketika diimpor sebagai modul di file lain.

FLOWCHART 


# Latihan 

1. Buat Dictionary daftar kontak ( Nama sebagai key, dan nomor sebagai value )
2. Tampilkan kontaknya Ari
3. Tambah kontak baru dengan nama Riko, nomor 087654544
4. Ubah kontak Dina dengan nomor baru 088999776
5. Tampilkan semua Nama
6. Tampilkan semua Nomor
7. Tampilkan daftar Nama dan nomornya
8. Hapus kontak Dina.


        # 1. Buat Dictionary daftar kontak
        daftar_kontak = {
            "Ari": "08123456789",
            "Dina": "08234567890",
            "Budi": "08345678901"
        }

        # 2. Tampilkan kontaknya Ari
        print("Kontak Ari:", daftar_kontak.get("Ari"))

        # 3. Tambah kontak baru dengan nama Riko, nomor 087654544
        daftar_kontak["Riko"] = "087654544"
                print("Kontak Riko telah ditambahkan.")

        # 4. Ubah kontak Dina dengan nomor baru 088999776
        daftar_kontak["Dina"] = "088999776"
                print("Kontak Dina telah diubah.")

        # 5. Tampilkan semua Nama
        print("Semua Nama:", list(daftar_kontak.keys()))

        # 6. Tampilkan semua Nomor
        print("Semua Nomor:", list(daftar_kontak.values()))

        # 7. Tampilkan daftar Nama dan nomornya
        print("Daftar Nama dan Nomornya:")
                for nama, nomor in daftar_kontak.items():
                    print(f"{nama}: {nomor}")

        # 8. Hapus kontak Dina
        if "Dina" in daftar_kontak:
            del daftar_kontak["Dina"]
                    print("Kontak Dina telah dihapus.")
        else:
            print("Kontak Dina tidak ditemukan.")

PROSES INPUT DATA 
![Screenshot 2024-11-20 192312](https://github.com/user-attachments/assets/234d9807-cf2b-4e83-8b85-c9ce9ac40d6e)
![Screenshot 2024-11-20 194027](https://github.com/user-attachments/assets/420b738a-cb00-4d72-8649-bf78dabe847a)

HASIL OUTPUT 
![Screenshot 2024-11-20 194141](https://github.com/user-attachments/assets/bbc0d924-e4c7-4028-b0b4-054ba8b06ff2)

PENJELASAN : 
1. Membuat Dictionary: daftar_kontak adalah dictionary yang menyimpan nama sebagai key dan nomor sebagai value.
2. Menampilkan Kontak Ari: Menggunakan daftar_kontak.get("Ari") untuk mengambil nomor Ari.
3. Menambah Kontak Riko: Menambahkan entry baru dengan nama "Riko" dan nomor "087654544".
4. Mengubah Kontak Dina: Mengupdate nomor untuk key "Dina" menjadi "088999776".
5. Menampilkan Semua Nama: Menggunakan list(daftar_kontak.keys()) untuk mendapatkan semua nama.
6. Menampilkan Semua Nomor: Menggunakan list(daftar_kontak.values()) untuk mendapatkan semua nomor.
7. Menampilkan Daftar Nama dan Nomor: Menggunakan loop untuk mencetak setiap nama dan nomor.
8. Menghapus Kontak Dina: Menghapus entry untuk key "Dina" jika ada.










