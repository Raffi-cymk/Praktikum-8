# Praktikum-8

![](<Flowchart Nilai Mahasiswa_20241204_090619_089_65.jpg>)

class Mahasiswa:
    def __init__(self):
        self.data_mahasiswa = []

    def tambah(self, nama, nim, nilai):
        mahasiswa = {
            'nama': nama,
            'nim': nim,
            'nilai': nilai
        }
        self.data_mahasiswa.append(mahasiswa)

    def tampilkan(self):
        if not self.data_mahasiswa:
            print("Data mahasiswa kosong.")
            return
        print("Daftar Nilai Mahasiswa:")
        for idx, mhs in enumerate(self.data_mahasiswa, start=1):
            print(f"{idx}. Nama: {mhs['nama']}, NIM: {mhs['nim']}, Nilai: {mhs['nilai']}")

    def hapus(self, nama):
        for mhs in self.data_mahasiswa:
            if mhs['nama'] == nama:
                self.data_mahasiswa.remove(mhs)
                print(f"Data mahasiswa dengan nama {nama} berhasil dihapus.")
                return
        print(f"Data mahasiswa dengan nama {nama} tidak ditemukan.")

    def ubah(self, nama, nim=None, nilai=None):
        for mhs in self.data_mahasiswa:
            if mhs['nama'] == nama:
                if nim:
                    mhs['nim'] = nim
                if nilai:
                    mhs['nilai'] = nilai
                print(f"Data mahasiswa dengan nama {nama} berhasil diubah.")
                return
        print(f"Data mahasiswa dengan nama {nama} tidak ditemukan.")

# Contoh penggunaan
if __name__ == "__main__":
    daftar_mahasiswa = Mahasiswa()
    
    # Tambah data
    daftar_mahasiswa.tambah("Ari", "123", 85)
    daftar_mahasiswa.tambah("Dina", "124", 90)
    
    # Tampilkan data
    daftar_mahasiswa.tampilkan()
    
    # Ubah data
    daftar_mahasiswa.ubah("Ari", nilai=88)
    
    # Hapus data
    daftar_mahasiswa.hapus("Dina")
    
    # Tampilkan data lagi
    daftar_mahasiswa.tampilkan()

Diagram Kelas

Diagram kelas menjelaskan hubungan antara class dan atribut atau metode yang digunakan:

Mahasiswa

Attributes: data_mahasiswa

Methods: tambah(), tampilkan(), hapus(), ubah()  
