# Tugas_2_Struktur_Data
#class node 
class Peta:
    #metode init (inisiasi)
    def __init__(self):
        self.daftarKota = {}
    
    #metode tambahKota untuk menambah kota
    def tambahKota(self, kota):
        if kota not in self.daftarKota:
            self.daftarKota[kota] = {} 
    
    #metode printKota untuk menampilkan kota
    def printKota(self):
        for kota in self.daftarKota:
            print(f"{kota} -- {self.daftarKota[kota]}")
    
    #metode tambahJalan untuk menambah jarak
    def tambahJalan(self, kota1, kota2, jarak):
        #jika kota1 dan kota2 ada di dalam daftarKota maka ditambahkan jaraknya
        if kota1 and kota2 in self.daftarKota:
            self.daftarKota[kota1][kota2] = jarak
            self.daftarKota[kota2][kota1] = jarak
    
    #metode hapusKota untuk menghapus kota yang di dalam list daftar kota
    def hapusKota(self, kotaDihapus):
        if kotaDihapus in self.daftarKota:
            for kota in self.daftarKota:
                if kotaDihapus in self.daftarKota[kota]:
                    del self.daftarKota[kota][kotaDihapus]
            del self.daftarKota[kotaDihapus]
    
