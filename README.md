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
    #metode hapusJalan untuk menghapus jarak yang udah ada di dalam list daftar kota
    def hapusJalan(self, kota1, kota2):
        if kota1 and kota2 in self.daftarKota:
            del self.daftarKota[kota1][kota2]
            del self.daftarKota[kota2][kota1]

    #metode ruteTempuh untuk menampilkan jarak tempuh dari kota1 ke kota2
    def ruteTempuh(self, kota1, kota2):
        #jika kota1 dan kota2 didalam daftarKota maka menampilkan jaraknya  
        if kota1 and kota2 in self.daftarKota: 
            #jika tidak ada yang menghubungkan kota1 ke kota2
            if kota1 not in self.daftarKota [kota2] or kota2 not in self.daftarKota [kota1]:
                #maka akan muncul harus memasukkan sesuai daftar kota
                print("kamu harus memasukkan sesuai daftar kota") 
            else :
                print(self.daftarKota[kota1][kota2])
        #jika user menempuh antar kota yang tidak sesuai dengan daftar kota 
        else :
            print ("kamu harus melewati beberapa kota")
        
#variabel untuk list dari nama nama kota di peta Jawa Timur
KotaJawaTimur = ["Surabaya", "Sidoarjo", "Malang", "Blitar", "Tulungagung", "Trenggalek", "Ponorogo", "Madiun", "Ngawi", "Bojonegoro"]
#variabel untuk memanggil class
JawaTimur = Peta() 
#untuk memasukkan nama kota di dalam class
for kota in KotaJawaTimur : 
    JawaTimur.tambahKota(kota) 

#aturan untuk input nama kota
