# TAE Widget Kit

32 widget statis untuk The Academic Era. Cuma satu file (`index.html`): tanpa server, tanpa API key, tanpa membaca data Notion pengguna.

## Link embed

Format: `https://NAMA-AKUN.github.io/tae-widget-kit/?w=ID`
Tanpa `?w=` → halaman galeri (preview semua widget + tombol salin link).

| Kategori | Widget | `?w=` | Tinggi |
|---|---|---|---|
| **Andalan** | Header Hari Ini | `header-hari-ini` | ±250 px (HP ±330) |
| | Generator Pesan Sopan | `pesan-sopan` | ±560 px |
| | Ruang Fokus (Pomodoro + suara latar) | `pomodoro` | ±520 px |
| | Mulai Kapan? | `mulai-kapan` | ±560 px |
| | Riset Kit | `riset-kit` | ±560 px |
| | Radar Tanggal Merah | `tanggal-merah` | ±460 px |
| | Kalkulator IP & Target IPK | `kalkulator-ip` (`&tab=ipk` untuk langsung ke Target IPK) | ±460 px |
| **Markas Skripsi** | Kalkulator Sampel | `sampel` | ±480 px |
| | Pesan ke Dosen Pembimbing | `pesan-sopan&mode=dospem` | ±560 px |
| | Target per Bab | `mulai-kapan&mode=bab` | ±640 px |
| **Waktu** | Jam Digital · Jam Analog · Progres Hari Ini · Progres Waktu · Kalender · Hitung Mundur · Zona Waktu | `jam-digital` `jam-analog` `progres-hari` `progres-waktu` `kalender` `hitung-mundur` `zona-waktu` | 200–400 px |
| **Timer** | Timer · Jam Pasir · Stopwatch · Jam Tidur & Reset | `timer` `jam-pasir` `stopwatch` `tidur-reset` | 320–430 px |
| **Kalkulator** | Kalkulator · Ilmiah · Cek Paylater · Split Bill · Konverter · IMT/BMI | `kalkulator` `kalkulator-ilmiah` `paylater` `split-bill` `konverter` `bmi` | 380–480 px |
| **Belajar** | Penghitung Kata · Papan Coretan · QR Code · Acak Kelompok · Roda Pembagi Tugas · Shortcut · Kutipan | `hitung-kata` `scratchpad` `qr-code` `acak-kelompok` `roda-tugas` `shortcut` `kutipan` | 260–440 px |

## Opsi di link

- `&palet=` → warna widget: `monokrom` (default), `terang`, `kertas`, `sage`, `blush`, `navy`, `mocha`, `hutan`
- `&pola=` → pola latar: `polos` (default), `titik`, `garis` (garis buku), `kotak`, `gradasi`, `grain`
- `&bg=transparan` → latar transparan (ikut warna halaman Notion). `&tema=terang` lama tetap jalan (= `palet=terang`).
- Cara termudah: pilih palet & pola di bagian atas galeri, lalu klik "Salin link". Gayanya otomatis ikut di link.
- `&nama=Nadia` → Header Hari Ini menyapa dengan nama
- `&nama=…&nim=…&prodi=…` → Generator Pesan langsung terisi (dibuat otomatis lewat tombol "Salin link pribadi")
- `&fokus=45&istirahat=7&panjang=15&putaran=4` → durasi Ruang Fokus (dibuat otomatis lewat ⚙ Atur → Salin link)
- `&mulai=6&selesai=22` → Progres Hari Ini dihitung dari jam aktif
- `&tgl=2027-01-12&label=UAS` → Hitung Mundur · `&menit=2` → Jam Pasir · `&os=mac|win` → Shortcut · `&detik=0` → Jam Digital tanpa detik

## Perawatan rutin

- **Data libur (wajib, 1×/tahun):** array `LIBUR` di `index.html` berisi SKB 3 Menteri 2026 & 2027. Setelah SKB 2028 terbit (biasanya September), tambahkan barisnya dan ubah `LIBUR_AKHIR`. Kalau tidak diupdate, Radar & Header akan menampilkan "data belum diperbarui" mulai 2028.
- **Link Riset Kit:** format pencarian tiap situs bisa berubah. Tes 7 tombolnya setelah hosting, dan cek lagi tiap semester.

## Catatan teknis

- Nama/NIM, durasi Ruang Fokus, daftar matkul IP, dan daftar bab disimpan di browser masing-masing (localStorage). Nggak sinkron antar perangkat; pakai fitur "Salin link" supaya sama di HP & laptop.
- Bunyi & suara latar baru aktif setelah tombol diklik (aturan browser). Suara latar dibuat langsung oleh browser (tanpa file musik).
- Predikat kelulusan memakai ambang yang umum dipakai kampus (>3,50 Pujian). Aturan nasional terbaru tidak lagi mengatur predikat, jadi widget selalu menyarankan cek pedoman kampus.
- Kalkulator Paylater memakai bunga flat; bunga efektif dihitung dari arus cicilan. Widget tidak menyebut batas bunga OJK karena aturannya beda untuk pinjaman daring dan paylater perusahaan pembiayaan.
- Kalau situs mati, kotak embed cuma kosong. Data Notion pengguna tidak terpengaruh.
