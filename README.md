# program manajemen nilai mahasiswa menggunkan dictonary
# codingan 
```
# Program Manajemen Nilai Mahasiswa
# Menggunakan dictionary untuk menyimpan data

# Dictionary untuk menyimpan data mahasiswa
mahasiswa = {}

# Fungsi untuk menghitung nilai akhir
def hitung_nilai_akhir(tugas, uts, uas):
    return (0.3 * tugas) + (0.35 * uts) + (0.35 * uas)

# Fungsi untuk menampilkan menu
def tampilkan_menu():
    print("\nMenu:")
    print("1. Tambah Data")
    print("2. Ubah Data")
    print("3. Hapus Data")
    print("4. Tampilkan Data")
    print("5. Cari Data")
    print("6. Keluar")

# Fungsi untuk menambahkan data mahasiswa
def tambah_data():
    nama = input("Masukkan nama mahasiswa: ")
    tugas = float(input("Masukkan nilai tugas: "))
    uts = float(input("Masukkan nilai UTS: "))
    uas = float(input("Masukkan nilai UAS: "))
    nilai_akhir = hitung_nilai_akhir(tugas, uts, uas)
    mahasiswa[nama] = {"Tugas": tugas, "UTS": uts, "UAS": uas, "Nilai Akhir": nilai_akhir}
    print(f"Data untuk {nama} berhasil ditambahkan.")

# Fungsi untuk mengubah data mahasiswa
def ubah_data():
    nama = input("Masukkan nama mahasiswa yang ingin diubah: ")
    if nama in mahasiswa:
        tugas = float(input("Masukkan nilai tugas baru: "))
        uts = float(input("Masukkan nilai UTS baru: "))
        uas = float(input("Masukkan nilai UAS baru: "))
        nilai_akhir = hitung_nilai_akhir(tugas, uts, uas)
        mahasiswa[nama] = {"Tugas": tugas, "UTS": uts, "UAS": uas, "Nilai Akhir": nilai_akhir}
        print(f"Data untuk {nama} berhasil diubah.")
    else:
        print(f"Data untuk {nama} tidak ditemukan.")

# Fungsi untuk menghapus data mahasiswa
def hapus_data():
    nama = input("Masukkan nama mahasiswa yang ingin dihapus: ")
    if nama in mahasiswa:
        del mahasiswa[nama]
        print(f"Data untuk {nama} berhasil dihapus.")
    else:
        print(f"Data untuk {nama} tidak ditemukan.")

# Fungsi untuk menampilkan semua data mahasiswa
def tampilkan_data():
    if mahasiswa:
        print("\nDaftar Nilai Mahasiswa:")
        print(f"{'Nama':<20} {'Tugas':<10} {'UTS':<10} {'UAS':<10} {'Nilai Akhir':<15}")
        print("-" * 65)
        for nama, nilai in mahasiswa.items():
            print(f"{nama:<20} {nilai['Tugas']:<10} {nilai['UTS']:<10} {nilai['UAS']:<10} {nilai['Nilai Akhir']:<15.2f}")
    else:
        print("Belum ada data mahasiswa.")

# Fungsi untuk mencari data mahasiswa
def cari_data():
    nama = input("Masukkan nama mahasiswa yang ingin dicari: ")
    if nama in mahasiswa:
        print(f"\nData untuk {nama}:")
        print(f"Tugas: {mahasiswa[nama]['Tugas']}")
        print(f"UTS: {mahasiswa[nama]['UTS']}")
        print(f"UAS: {mahasiswa[nama]['UAS']}")
        print(f"Nilai Akhir: {mahasiswa[nama]['Nilai Akhir']:.2f}")
    else:
        print(f"Data untuk {nama} tidak ditemukan.")

# Main program
while True:
    tampilkan_menu()
    pilihan = input("Pilih menu (1-6): ")
    
    if pilihan == "1":
        tambah_data()
    elif pilihan == "2":
        ubah_data()
    elif pilihan == "3":
        hapus_data()
    elif pilihan == "4":
        tampilkan_data()
    elif pilihan == "5":
        cari_data()
    elif pilihan == "6":
        print("Keluar dari program. Terima kasih!")
        break
    else:
        print("Pilihan tidak valid. Silakan coba lagi.")
```
# Output
```
Menu:
1. Tambah Data
2. Ubah Data
3. Hapus Data
4. Tampilkan Data
5. Cari Data
6. Keluar
Pilih menu (1-6): 1
Masukkan nama mahasiswa: afatih
Masukkan nilai tugas: 80
Masukkan nilai UTS: 85
Masukkan nilai UAS: 90
Data untuk Andi berhasil ditambahkan.

Menu:
1. Tambah Data
2. Ubah Data
3. Hapus Data
4. Tampilkan Data
5. Cari Data
6. Keluar
Pilih menu (1-6): 4

Daftar Nilai Mahasiswa:
Nama                 Tugas      UTS        UAS        Nilai Akhir    
-----------------------------------------------------------------
Andi                 80.0       85.0       90.0       85.25
```

