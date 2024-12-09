# labpy08
Nama : Afdhal Agislam <p>
NIM : 312410445 <p>
Kelas : TI.24.A.5 <p>
Mata Kuliah: Bahasa Pemrograman <p>
# Program Input Nilai
## Diagram Class
![gambar 7](https://github.com/user-attachments/assets/2a0c969d-a942-4d24-a609-334fcf3eb0ea)
## Flowchart
![gambar 3](https://github.com/user-attachments/assets/fc63f406-2385-4f50-b5ca-05a673febd7f)
![gambar 4](https://github.com/user-attachments/assets/525a3ee1-815b-4f72-ab9d-9cbe08b566d4)

## Program Python
![gambar 5](https://github.com/user-attachments/assets/6bfecd4c-6f3c-4370-9d2b-a0ca01b1be05)
![gambar 6](https://github.com/user-attachments/assets/895430ce-350b-4149-939b-4b641165012b)

### Penjelasan Program
1. Kelas Student:
   
        class Student:
            def __init__(self, nim, nama, tugas, uts, uas):
               self.nim = nim
               self.nama = nama
               self.tugas = tugas
               self.uts = uts
               self.uas = uas
               self.akhir = self.calculate_final_grade()
   - Kelas ini menyimpan informasi tentang mahasiswa, seperti NIM, nama, nilai tugas, UTS, dan UAS.
   - Metode calculate_final_grade menghitung nilai akhir mahasiswa berdasarkan bobot yang diberikan (30% tugas, 35% UTS, dan 35% UAS).

2. Fungsi display_menu:

        def display_menu():
            print("\n[(L)ihat, (T)ambah, (U)bah, (H)apus, (K)eluar]: ", end=' ')
   - Fungsi ini menampilkan menu pilihan kepada pengguna dengan opsi untuk melihat, menambah, mengubah, menghapus, atau keluar.
3. Fungsi display_students:

       def display_students(students):
          print("\nDaftar Nilai")
          print("=" * 84)
          print(f"| {'NO':<3} | {'NIM':<10} | {'NAMA':<30} | {'TUGAS':<6} | {'UTS':<4} | {'UAS':<4} | {'AKHIR':<5} |")
          print("=" * 84)
          if not students:
              print(f"| {'TIDAK ADA DATA':^80} |")
          else:
              for i, student in enumerate(students, start=1):
                  print(f"| {i:<3} | {student.nim:<10} | {student.nama:<30} | {student.tugas:<6} | {student.uts:<4} | {student.uas:<4} | {student.akhir:<5} |")
          print("=" * 84)
    - Fungsi ini menampilkan daftar mahasiswa beserta nilai-nilainya dalam format tabel.
4. Fungsi find_student_index:
   
         def find_student_index(students, nama):
             for index, student in enumerate(students):
                 if student.nama == nama:
                     return index
             return None
   - Fungsi ini mencari indeks mahasiswa dalam daftar berdasarkan Nama yang diberikan. Jika ditemukan, mengembalikan indeks tersebut; jika tidak, mengembalikan None.
5. Fungsi main:
   
    
         def main():
             students = []
             while True:
                 display_menu()
                 choice = input().lower()
                 if choice == 't':
                     nim = input("\nNIM: ")
                     nama = input("Nama: ")
                     tugas = int(input("Nilai Tugas: "))
                     uts = int(input("Nilai UTS: "))
                     uas = int(input("Nilai UAS: "))
                     students.append(Student(nim, nama, tugas, uts, uas))
                 elif choice == 'l':
                     display_students(students)
                 elif choice == 'u':
                     display_students(students)
                     nama = input("\nMasukkan nama mahasiswa yang akan diubah: ")
                     index = find_student_index(students, nama)
                     if index is not None:
                         print("Data baru:")
                         nama = input("Nama: ")
                         tugas = int(input("Nilai Tugas: "))
                         uts = int(input("Nilai UTS: "))
                         uas = int(input("Nilai UAS: "))
                         students[index] = Student(nim, nama, tugas, uts, uas)
                     else:
                         print("Mahasiswa dengan nama tersebut tidak ditemukan.")
                 elif choice == 'h':
                     display_students(students)
                     nama = input("\nMasukkan nama mahasiswa yang akan dihapus: ")
                     index = find_student_index(students, nama)
                     if index is not None:
                         del students[index]
                         print("Data mahasiswa berhasil dihapus.")
                     else:
                         print("Mahasiswa dengan nama tersebut tidak ditemukan.")
                 elif choice == 'k':
                     break
                 else:
                     print("Pilihan tidak valid!")
   - Fungsi utama yang menjalankan program.
   - Di dalamnya terdapat loop yang terus berjalan menampilkan menu dan memproses pilihan pengguna:
     - t: Menambah data mahasiswa baru.
     - l: Menampilkan daftar mahasiswa.
     - u: Mengubah data mahasiswa berdasarkan Nama.
     - h: Menghapus data mahasiswa berdasarkan Nama.
     - k: Keluar dari program.
## Hasil Program
![gambar 1](https://github.com/user-attachments/assets/25e99881-b12d-4242-be99-992402970f79)
![gambar 2](https://github.com/user-attachments/assets/24bc8fa1-6ce3-40a2-8eea-39bd3be8c9fe)
