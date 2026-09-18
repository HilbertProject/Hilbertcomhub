# MEMORY CAPSULE — W1 (Window Komparatif Independen 1), Siklus PR-010

**Untuk:** jendela W1 baru yang melanjutkan pekerjaan ini
**Dari:** W1 lama (context window penuh, sesi ditutup)
**Status saat handoff:** Baseline Sintesa 100% selesai; Fase 1 (Analisis Topik) selesai; Fase 2 & 3 belum dimulai

---

## 1. File yang WAJIB direlay ke jendela baru

Upload keempat file ini di pesan pertama jendela baru:

| # | File | Kenapa penting |
|---|---|---|
| 1 | `Hilbert-PR10-Komparatif.xlsx` | **Sumber kebenaran utama.** 6 sheet: Superset Topik-Tokoh (738 baris), Konsistensi Prep vs Draft, Ringkasan per AI, Legend Tag AI, Konsensus 12 AI (292 kelompok kanonik), Ringkasan Final (5 bagian A–E via formula). |
| 2 | `Hilbert-PR10-Laporan-Naratif.md` | Laporan naratif Tahap 3 — insight lintas-AI, profil gaya 12 AI, kompilasi lengkap temuan kualitas data Tahap 1.5. |
| 3 | `PR-10_Analisis_Topik.md` | Output Fase 1 (skill `hilbert-sintesa`) — Bagian A (Latar Belakang), B (98 Topik dianalisis), C (2 Tabel Gap terverifikasi). |
| 4 | `hilbert-sintesa.skill` | **File skill itu sendiri.** Ini TIDAK ter-mount otomatis di environment — harus diupload ulang tiap jendela baru (format: zip berisi `SKILL.md` + `references/*.md`). |

**Opsional, hanya kalau perlu verifikasi ulang mendalam:**
- 12 draft mentah asli (`PR-010-Claude.md`, `PR-010-Deepseek.md`, dst.) — sudah terserap penuh ke Excel, cuma perlu direlay kalau ada audit ulang spesifik ke teks asli.
- `Prompt_Bertingkat.txt` — template prompt bertingkat asli, berguna kalau perlu ingat persis struktur permintaan yang menghasilkan 12 draft itu.

**Cek dulu sebelum upload:** skill `hilbert-komparatif` (untuk Baseline Sintesa) ada di `/mnt/skills/user/hilbert-komparatif/` — kemungkinan ini persisten di akun Anda dan otomatis tersedia di jendela baru tanpa upload ulang. Tapi **verifikasi dulu** di jendela baru (minta Claude cek `/mnt/skills/user/`) sebelum asumsi — kalau ternyata tidak ada, perlu diinstal ulang di luar chat ini.

---

## 2. Status pekerjaan persis

### Skill `hilbert-komparatif` (Baseline Sintesa) — **SELESAI TOTAL**
- Tahap 1: ekstraksi 12/12 AI (CL, DE, GR, KI, CO, GE, TE, PE, GP, LE, ME, QW)
- Tahap 1.5: audit fakta via web search — 1 halusinasi terkonfirmasi (LE, sitasi "Rao, A."), beberapa galat sitasi/atribusi diperbaiki (lihat Sheet Ringkasan Final Bagian D atau Laporan Naratif §5)
- Tahap 2: dedup & kanonikalisasi — 738 baris mentah → 292 kelompok kanonik (194 Tokoh, 98 Topik)
- Tahap 3: laporan naratif — selesai, sudah direview & diperbaiki (ada 1 bug urutan Match Rate yang sempat salah, sudah dikoreksi)

### Skill `hilbert-sintesa` — **Fase 1 selesai, Fase 2 & 3 belum**
- Fase 1 (Analisis Topik): selesai — lihat `PR-10_Analisis_Topik.md`
- Fase 2 (Draft Usulan MVC — Gerbang+Lapisan+Bab+Registry): **belum dimulai**
- Fase 3 (Verifikasi Mandiri): **belum dimulai**
- Tahap pemasangan/pairing dengan jendela sintesa lain: di luar scope `hilbert-sintesa`, governed oleh protokol terpisah yang belum pernah diberikan ke W1 — kalau relevan nanti, perlu dokumen protokolnya dulu.

---

## 3. Angka kunci (untuk konteks cepat — TAPI selalu re-derive dari Excel kalau dipakai untuk keputusan penting, jangan percaya begitu saja dari sini)

- 12 AI, 738 baris mentah, 292 kelompok kanonik (194 Tokoh + 98 Topik)
- Rata-rata Match Rate: 78.5% | Tertinggi: Meta AI (94.7%) | Terendah: GPT (50.7%)
- Kategori konsensus Topik: Universal 4, Mayoritas 9, Umum 10, Minoritas/Unik 75 (dari 98)
- Insight terbesar: 2 AI (Tera AI, Le Chat) menyimpang tajam soal riset HTP 2020-an — satu meneliti lengkap tapi tak pernah menuliskannya ke MVC, satu lagi tak menyentuhnya sama sekali dan malah scope-creep ke topik CS populer (blockchain/AI/kuantum)

---

## 4. Lensa kerja & gaya yang dipakai W1 lama — PENTING untuk konsistensi

Ini bagian paling penting dari capsule ini. Kalau jendela baru melanjutkan tanpa lensa ini, hasilnya bisa konsisten secara *output* tapi tidak secara *rigor*.

### 4.1 Prinsip inti: verifikasi sebelum percaya — termasuk percaya ke diri sendiri

- **Setiap** ekstraksi topik/tokoh dari draft mentah diverifikasi programatik (grep literal ke teks), bukan cuma dibaca sekilas. Ini berulang kali menangkap false positive/negative yang tak kelihatan dari baca manual (contoh: term pendek "rsa" ternyata substring dari kata "peRSAmaan"; term "Ng," ternyata cocok kata Indonesia "yang,").
- **Setiap** klaim mencurigakan (nama asing tunggal, sitasi sangat spesifik) dicek via web search/fetch langsung ke sumber primer sebelum divonis halusinasi. Pelajaran W1: 2 klaim yang PALING dicurigai ("Kai", "Jonathan Brossard") justru terbukti akurat — satu papernya terbit setelah cutoff pengetahuan Claude sendiri. **Jangan pernah memvonis halusinasi hanya dari kecurigaan intuitif — selalu cek dulu.**
- **Setiap** temuan dari "jendela QC" (proses eksternal user yang mengaudit balik pekerjaan W1) dicek ulang mandiri sebelum diterapkan — tidak langsung dieksekusi, tidak langsung ditolak. Kadang QC benar (Lipshitz/Lipschitz — bahkan W1 lama sendiri sempat salah arah duluan lalu dibalik setelah dicek sumber primer Purdue), kadang butuh didiskusikan sebagai judgment call (kasus Howlett/Wolchover — W1 menahan diri utk TIDAK menggabung meski QC awalnya usul begitu, dengan alasan prinsipil yang dijelaskan & akhirnya disepakati bareng user).
- **Setelah** bikin formula Excel atau tabel besar, JANGAN percaya "0 error" dari recalc sebagai bukti benar — itu cuma bukti formula bisa dieksekusi, bukan bukti hasilnya benar. W1 lama menemukan 3 bug referensi sel (kutip satu vs dua, hardcode row range yang salah, `$B$7` vs `$B$8` tertukar) justru dengan mengecek NILAI aktual hasil recalc, bukan cuma status errornya.
- **Setelah** menulis tabel/daftar besar (mis. 98 baris Analisis Topik), selalu cross-check otomatis: (a) kelengkapan (semua item sumber benar-benar tertulis, tak ada yang kececer), (b) konsistensi label vs angka (mis. kategori "Mayoritas" vs angka n/12-nya beneran cocok range-nya). W1 lama menemukan 2 baris dengan label kategori salah ("6/12 Mayoritas" harusnya "6/12 Umum") lewat cross-check ini — sesuatu yang nyaris mustahil ketangkep baca manual di tabel sepanjang itu.

### 4.2 Prinsip kedua: transparansi audit trail, jangan diam-diam mengubah apa pun

- Kalau ada koreksi (ejaan, atribusi, angka), koreksinya **ditambahkan sebagai catatan**, bukan menimpa data lama tanpa jejak. Semua "CEK", "TERVERIFIKASI", "KOREKSI" ditulis eksplisit di kolom Konteks/Catatan Excel.
- Kalau W1 sendiri salah (bukan cuma AI draft yang salah), itu diakui eksplisit juga — bukan cuma AI-draft-quality yang diaudit, tapi proses W1 sendiri juga kena audit yang sama ketatnya.

### 4.3 Prinsip ketiga: pembedaan yang tajam antar hal yang terlihat mirip

- "Varian ejaan/penulisan dari referent yang sama" (Lipshitz/Lipschitz, Katrina/Kirsten Eisenträger) → sah digabung kanonik.
- "Substitusi ke entitas nyata yang benar-benar berbeda" (Wolchover ≠ Howlett — dua jurnalis sungguhan berbeda, satu di antaranya salah dikutip) → **tidak sah digabung**, karena akan menyembunyikan temuan galatnya sendiri.
- Prinsip serupa dipakai di Fase 1 hilbert-sintesa: Konsensus dan Relevansi sengaja diperlakukan sebagai **dua sumbu independen** — jangan biarkan salah satu diam-diam mempengaruhi yang lain, dan jangan biarkan skema Fase/Lapisan navigasi mempengaruhi skor Rekomendasi.

### 4.4 Gotcha teknis yang perlu diwaspadai

- **Environment container bisa ter-reset di tengah sesi** (pernah terjadi persis di W1 lama — folder kerja `/home/claude/work` hilang total, tapi `/mnt/user-data/outputs/` selamat). Simpan file final di `/mnt/user-data/outputs/` sesegera mungkin setelah selesai, jangan cuma di folder kerja sementara.
- Formula Excel: string literal butuh kutip **dua** (`"CL"`), kutip satu di Excel dipakai utk nama sheet. Nama sheet berspasi wajib dibungkus kutip satu (`'Ringkasan per AI'!A1`).
- Skill `hilbert-sintesa` bukan skill bawaan environment — harus diupload ulang sbg file `.skill` (format zip) di tiap jendela baru.

---

## 5. Rekomendasi langkah pertama di jendela baru

1. Upload 4 file wajib di §1.
2. Minta Claude baca `SKILL.md` hilbert-sintesa (dari file yang diupload) + capsule ini sebelum mulai apa pun.
3. Konfirmasi mau lanjut ke **Fase 2 (Draft Usulan MVC)** atau **Fase 3 (Verifikasi Mandiri)** — kedua-duanya belum disentuh, jadi urutan terserah Anda kecuali `SKILL.md` hilbert-sintesa punya urutan wajib (cek ulang bagian alur di sana).
