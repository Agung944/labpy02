Tugas Pertemuan Ke 6

Nama:

Kelas: TI 24 A3

NIM: 312410377

1. Tiket Bioskop
Program tiket bioskop ini adalah program untuk menghitung harga Tiket bioskop. Konsepnya adalah jika user memiliki kartu member maka user akan mendapatkan diskon 20%

Flowchart dari Program tersebut

![bioskop drawio](https://github.com/user-attachments/assets/dea013de-65bc-4c79-88de-b3b3f8b91e82)

Program akan meminta user untuk menginputkan tipe tiket

![BIOSKOP](https://github.com/user-attachments/assets/ccf0faec-8c5b-4cb1-a410-b539cc7fe943)

Program akan menanyakan status member

![diskon1](https://github.com/user-attachments/assets/23f44fa4-8831-4b4e-b71b-522cf6a59551)

Jika user memiliki kartu member maka akan dapat diskon 20%

Output apabila input yang dimasukkan user adalah N atau tidak memiliki member

![nodiskon1](https://github.com/user-attachments/assets/bfc0ddca-8da5-4cb6-9d70-0851992cc679)

Penjelasan dari code program tiket bioskop

1. Perintah dibawah adalah untuk menampilkan judul program dan pilihan tiket yang tersedia.

print("=== Program Hitung Harga Tiket Bioskop ===")
print("1. Reguler (Rp50.000)")
print("2. VIP (Rp100.000)")

2. Input tipe tiket

tipe_tiket = input("Pilih tipe tiket (1/2): ")

Input status member

3. status_member = input("Apakah anda memiliki kartu member? (y/n): ")

status_member = input("Apakah anda memiliki kartu member? (y/n): ")

Program akan meminta input status member dari user.

4. Harga dasar tiket menggunakan operator ternary

harga_dasar = 50000 if tipe_tiket == "1" else 100000

Jika tipe_tiket="1" maka harga=50000 , jika tidak maka harga=100000

5. Hitung Diskon

diskon = 0.2 if status_member.lower() == "y" else 0

Jika status_member="y" maka diskon=0.2 (20%), jika tidak maka diskon=0

6. Menghitung total harga

total_harga = harga_dasar - (harga_dasar * diskon)

Menghitung total harga setelah diskon

7. Menampilkan output dari input yang dimasukkan user

print("\n=== Detail Pembayaran ===")
print(f"Tipe Tiket: {'Reguler' if tipe_tiket == '1' else 'VIP'}")
print(f"Status Member: {'Ya' if status_member.lower() == 'y' else 'Tidak'}")
print(f"Harga Dasar: Rp{harga_dasar:,.0f}")
print(f"Diskon: {diskon*100:.0f}%")
print(f"Total Harga: Rp{total_harga:,.0f}")

2. Kalkulator sederhana
Program ini adalah program Kalkulator sederhana yang berfungsi untuk menghitung dua angka sesuai dengan operasi hitung yang dipilih.

Flowchart dari Program Kalkulator sederhana

![kalkulator drawio](https://github.com/user-attachments/assets/5053fca3-2be4-461f-84d4-a98bdd0a686b)

Program akan meminta input angka dan Operator perhitungan

![KALKULATOR](https://github.com/user-attachments/assets/c1901cfb-0780-456e-be9d-ecc76f62c034)

Contoh apabila kita memilih Operasi hitung Penjumlahan

![penjumlahan](https://github.com/user-attachments/assets/c51777ed-b55e-4739-8f6d-a6484e7c3b4f)

Contoh apabila kita memilih Operasi hitung Pengurangan

![pengurangan](https://github.com/user-attachments/assets/a72d284d-dc68-41f0-87a9-efba430398af)

Contoh apabila kita memilih Operasi hitung Perkalian

![perkalian](https://github.com/user-attachments/assets/8ce958cb-b070-46a2-93b2-6a74bf5d7ed0)

Contoh apabila kita memilih Operasi hitung Pembagian

![pembagian](https://github.com/user-attachments/assets/a4f07ab5-1de8-400e-ba8e-017741614056)

Contoh apabila kita memilih Operasi hitung Pembagian namun dibagi 0

![pembagian0](https://github.com/user-attachments/assets/f13e90ba-c30f-4299-9814-92ecbf0a26d3)

Apabila angka kedua adalah 0 maka pembagian akan error.

Penjelasan code dari program Kalkulator

1. Perintah untuk menampilkan Judul dan Operator yang tersedia

print("=== Program Kalkulator Sederhana ===")
print("Operator yang tersedia:")
print("+ : Penjumlahan")
print("- : Pengurangan")
print("* : Perkalian")
print("/ : Pembagian")

2. Mulai blok try untuk menangani Error yang mungkin terjadi

try:

3. Memulai section untuk input angka dan juga Operasi hitung

  # Input angka pertama
    angka1 = float(input("\nMasukkan angka pertama: "))

    # Input operator
    operator = input("Masukkan operator (+, -, *, /): ")

    # Input angka kedua
    angka2 = float(input("Masukkan angka kedua: "))

4. Memulai proses perhitungan menggunakan if elif else

  if operator == '+':                    # Jika operator adalah +
        hasil = angka1 + angka2           # Lakukan penjumlahan
        operasi = "Penjumlahan"          # Set nama operasi
    elif operator == '-':                 # Jika operator adalah -
        hasil = angka1 - angka2          # Lakukan pengurangan
        operasi = "Pengurangan"          # Set nama operasi
    elif operator == '*':                 # Jika operator adalah *
        hasil = angka1 * angka2          # Lakukan perkalian
        operasi = "Perkalian"            # Set nama operasi
    elif operator == '/':                 # Jika operator adalah /
        if angka2 == 0:                  # Cek jika angka kedua adalah 0
            raise ZeroDivisionError("Pembagian dengan nol tidak diperbolehkan!")  # Raise error jika pembagian dengan 0
        hasil = angka1 / angka2          # Lakukan pembagian
        operasi = "Pembagian"            # Set nama operasi
    else:
        raise ValueError("Operator tidak valid!")  # Raise error jika operator tidak valid

5. Menampilkan Hasil

    print("\n=== Hasil Perhitungan ===")                   # Menampilkan header hasil
    print(f"Operasi: {operasi}")                          # Menampilkan jenis operasi
    print(f"{angka1} {operator} {angka2} = {hasil}")      # Menampilkan perhitungan dan hasilnya

6. Membuat penanganan Error

except ValueError as e:                                    # Menangkap error nilai tidak valid
    if str(e) == "Operator tidak valid!":
        print("\nError: Operator yang dimasukkan tidak valid!")
    else:
        print("\nError: Mohon masukkan angka yang valid!")
except ZeroDivisionError as e:                            # Menangkap error pembagian dengan nol
    print(f"\nError: {e}")
except Exception as e:                                     # Menangkap error lainnya
    print(f"\nTerjadi kesalahan: {e}")

Sekian Penjelasan dari dua Program yang sudah saya buat... Terimakasihh!!! 

