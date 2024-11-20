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
