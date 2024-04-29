# billy
class Rekening:
    def __init__(self, nama, pin, saldo=0):
        self.nama = nama
        self.pin = pin
        self.saldo = saldo

    def setor(self, jumlah):
        self.saldo += jumlah
        print("Setoran berhasil. Saldo saat ini:", self.saldo)

    def tarik(self, jumlah):
        if jumlah > self.saldo:
            print("Saldo tidak mencukupi.")
        else:
            self.saldo -= jumlah
            print("Penarikan berhasil. Saldo saat ini:", self.saldo)

    def cek_saldo(self):
        print("Saldo saat ini:", self.saldo)

def main():
    print("Selamat datang di Bank XYZ")
    nama = input("Masukkan nama Anda: ")
    pin = input("Masukkan PIN Anda: ")
    rekening = Rekening(nama, pin)

    while True:
        input_pin = input("Masukkan PIN Anda: ")
        if input_pin != rekening.pin:
            print("PIN salah. Silakan coba lagi.")
            continue

        print("\nPilih opsi:")
        print("1. Setor Uang")
        print("2. Tarik Uang")
        print("3. Cek Saldo")
        print("4. Keluar")

        pilihan = input("Masukkan nomor opsi: ")

        if pilihan == "1":
            jumlah = float(input("Masukkan jumlah yang akan disetor: "))
            rekening.setor(jumlah)
        elif pilihan == "2":
            jumlah = float(input("Masukkan jumlah yang akan ditarik: "))
            rekening.tarik(jumlah)
        elif pilihan == "3":
            rekening.cek_saldo()
        elif pilihan == "4":
            print("Terima kasih telah menggunakan layanan kami.")
            break
        else:
            print("Pilihan tidak valid. Silakan pilih opsi yang benar.")

if __name__ == "__main__":
    main()
