# 🏁 Tugas Akhir (TA) - Final Project

**Nama Mahasiswa**: Jawahirul Wildan  
**NRP**: 5025211150  
**Judul TA**: INTEGRASI ARTEFAK DISCORD DAN INSTAGRAM PADA LINIMASA FORENSIK  
**Dosen Pembimbing**: Hudan Studiawan, S.Kom., M.Kom., Ph.D.  
**Dosen Ko-pembimbing**: Baskoro Adi Pratomo, S.Kom., M.Kom., Ph.D.

---

## 📺 Demo Aplikasi  
Embed video demo di bawah ini (ganti `VIDEO_ID` dengan ID video YouTube Anda):  

[![Demo Aplikasi](https://i.ytimg.com/vi/zIfRMTxRaIs/maxresdefault.jpg)](https://www.youtube.com/watch?v=VIDEO_ID)  
*Klik gambar di atas untuk menonton demo*

---

## 🛠 Panduan Instalasi & Menjalankan Software  

### Prasyarat  
- Daftar dependensi (contoh):
  - Python 3.10+

### Langkah-langkah  
1. **Clone Repository log2timeline/plaso**  
   ```bash
   git clone https://github.com/log2timeline/plaso.git
   ```
   
2. **Clone Repository**  
   ```bash
   git clone https://github.com/Informatics-ITS/ta-jawahirulwildan.git
   ```
   
3. **Copy/move file pada Repository ini ke Repository log2timeline/plaso**
- Untuk Parser iOS Discord

| File Asal                            | Tujuan di Repositori Plaso                      |
|-------------------------------------|-------------------------------------------------|
| `ios_discord/parser/ios_discord.py` | `plaso/parsers/ios_discord.py`                 |
| `ios_discord/unit_test/ios_discord.py` | `tests/parsers/ios_discord.py`               |
| `ios_discord/test_data/*`           | `test_data/` |
| `ios_discord/ios.yaml`              | Tambahkan ke `data/ios.yaml`                   |
| `ios_discord/timeliner.yaml`        | Tambahkan ke `data/timeliner.yaml`             |

- Untuk Plugin Parser iOS Instagram

| File Asal                                      | Tujuan di Repositori Plaso                      |
| ---------------------------------------------- | ----------------------------------------------- |
| `ios_instagram/plugin_parser/ios_instagram.py` | `plaso/parsers/sqlite_plugins/ios_instagram.py` |
| `ios_instagram/unit_test/ios_instagram.py`     | `tests/parsers/sqlite_plugins/ios_instagram.py` |
| `ios_instagram/test_data/*`                    | `test_data/`                                    |
| `ios_instagram/ios.yaml`                       | Tambahkan ke `data/ios.yaml`                    |
| `ios_instagram/timeliner.yaml`                 | Tambahkan ke `data/timeliner.yaml`              |

4. **Menyiapkan Virtual Environment**
   ```bash
   virtualenv plaso-test
   source plaso-test/bin/activate
   ```
   
5. **Instalasi Dependensi pada Repositori log2timeline/plaso**
   ```bash
   cd plaso
   pip install -r requirements.txt
   ```
   
6. **Build & Install Plaso**
   ```bash
   python setup.py build
   python setup.py install
   ``` 
   
7. **Jalankan Plaso**
   ```bash
   log2timeline --storage-file path/to/output.plaso /path/to/artifact/ # Membuat plaso storage file
   psort -o dynamic -w path/to/output.csv path/to/file.plaso # Ekstrak Plaso Storage file ke CSV
   ```
   
8. **Hasil**

   Hasil dari menjalankan Plaso ini adalah file CSV yang berisi informasi mengenai sebuah aplikasi yang berbasis lini masa. Contoh hasil untuk aplikasi Discord dan Instagram pada iOS dapat dilihat pada folder output. 
   
---

## 📚 Dokumentasi Tambahan

- [[Dokumentasi Plaso]](https://plaso.readthedocs.io/en/latest/)

---

## ✅ Validasi

Pastikan proyek memenuhi kriteria berikut sebelum submit:
- Source code dapat di-build/run tanpa error
- Video demo jelas menampilkan fitur utama
- README lengkap dan terupdate
- Tidak ada data sensitif (password, API key) yang ter-expose

---

## ⁉️ Pertanyaan?

Hubungi:
- Penulis: jawahirulwildan@gmail.com
- Pembimbing Utama: hudan@its.ac.id
- Ko-pembimbing : baskoro@its.ac.id
