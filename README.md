# Kabar Pendakian Khusyuk

Berkas `kabar.json` di repositori **publik** ini dibaca aplikasi *Pendakian Khusyuk*
saat HP tersambung internet (paling sering sekali per 6 jam). Aplikasi **tidak mengirim
data apa pun**; tanpa internet, aplikasi tetap berjalan seperti biasa.

## Mengumumkan versi baru
Naikkan `versi_terbaru` dan `kode_terbaru` (angka sesudah `+` di `pubspec.yaml`), lalu
isi `catatan` (ringkasan perubahan; `id` wajib, bahasa lain boleh). Pengguna dengan versi
lebih lama melihat kotak **"Versi baru tersedia"** di beranda.

## Mengirim pengumuman
Tambahkan butir ke `pesan`:

```json
{
  "id": "2026-10-10-koreksi-gerbang",      // unik; pengguna bisa menutupnya
  "judul": {"id": "Koreksi isi", "en": "Content correction"},
  "isi": {"id": "Ada perbaikan teks di Gerbang Kedamaian. Mohon perbarui aplikasi."},
  "tautan": "",                            // opsional: alamat yang dibuka tombol "Buka"
  "untuk": "semua",                        // semua | langsung | play
  "sampai": "2026-12-31",                  // opsional: berhenti tampil sesudah tanggal ini
  "versi_maks": 0                          // opsional: tampil hanya untuk kode versi <= angka ini
}
```

(Hapus komentar `// …` — JSON tidak mengizinkan komentar.)

## Unduhan APK dan versi baru
Diterbitkan otomatis dari repo aplikasi: **Actions → Bangun APK → Run workflow → centang
"Terbitkan"**. Langkah itu mengunggah `pendakian-khusyuk-v<versi>.apk` ke **Releases**
repositori ini, lalu memperbarui `versi_terbaru`, `kode_terbaru`, dan `catatan` di
`kabar.json` (bagian `pesan` tidak disentuh). `unduh.langsung` menunjuk ke rilis terbaru.

Pengumuman (`pesan`) tetap diisi dengan menyunting `kabar.json` langsung di sini.
