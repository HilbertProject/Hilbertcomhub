# Laporan Analisis Komparatif: 12 AI vs Problem Hilbert #10

**Siklus:** PR#10 (Apakah ada algoritma umum untuk menentukan solvabilitas persamaan Diophantine?)
**AI yang diproses:** Claude, Grok, DeepSeek, Kimi, Copilot, Gemini, Tera AI, Perplexity, GPT, Le Chat (Mistral), Meta AI, Qwen — 12/12
**Sumber data:** `Hilbert-PR10-Komparatif.xlsx` (Sheet 1–6), hasil Tahap 1 (ekstraksi + verifikasi Prep/Draft), Tahap 1.5 (audit fakta via web search), dan Tahap 2 (dedup & kanonikalisasi)

---

## 1. Ringkasan Eksekutif

Dua belas model AI diminta menjalani prompt bertingkat yang sama — dari pertanyaan pemantik, riset latar belakang, tabel topik/tokoh, sampai penyusunan *Minimum Viable Chapter* (MVC) lengkap dengan daftar pustaka — untuk topik yang identik: Problem Hilbert ke-10. Hasilnya diekstraksi menjadi 738 baris data mentah, diverifikasi faktanya lewat pencarian web langsung ke sumber primer, lalu dipadatkan menjadi 292 kelompok konsep kanonik untuk mengukur konsensus lintas-AI.

Temuan paling penting bukanlah soal siapa yang "menang", melainkan pola: **hampir semua AI sepakat pada tulang punggung sejarah PR#10 (Hilbert → Gödel/Turing/Church → Davis-Putnam-Robinson-Matiyasevich), tapi menyimpang tajam begitu narasi mendekati riset 2020-an** — beberapa mengeksekusinya dengan akurasi tinggi, satu draft (Tera AI) menelitinya lengkap di tabel riset lalu tidak pernah menuliskannya di bab manapun, dan satu draft lain (Le Chat) tidak menyentuhnya sama sekali.

Dari 12 draft, hanya **satu halusinasi murni yang terkonfirmasi** — dan justru dua klaim yang paling mencurigakan di awal audit (nama tunggal "Kai", dan klaim sangat spesifik soal bukti konstruktif via Rocq/Coq) **terbukti akurat** setelah dicek ke sumber primer, salah satunya karena papernya baru terbit setelah cutoff pengetahuan Claude sendiri.

---

## 2. Catatan Metodologi (baca sebelum menafsirkan angka)

- **Angka di laporan ini hanya berlaku untuk sesi ekstraksi ini.** Match Rate, jumlah kelompok kanonik, dan skor konsensus bergantung pada keputusan granularitas yang melibatkan *judgment* manusia (dieksekusi Claude), bukan pencarian string semata. Membandingkan angka-angka ini dengan hasil dari sesi/window lain — bahkan untuk draft AI yang identik — tidak valid kecuali metodologinya sama persis (lih. `references/komparabilitas-antar-sesi.md`).
- **Match Rate** = Match ÷ (Match + Prep only). *Draft only* sengaja dikeluarkan dari penyebut karena metrik ini mengukur kesetiaan eksekusi Tabel→MVC, bukan cakupan total.
- **"Kelompok kanonik"** = satu konsep/tokoh setelah varian ejaan dan frasa dari 12 AI digabung. Proses ini diaudit dua arah: dicek agar tidak *under-merge* (varian lolos tak tergabung) maupun *over-merge* (dua hal beda dipaksa satu) — lihat §5.
- Yang **paling layak dipercaya** lintas-AI: kategori Universal & Mayoritas (konsensus 7–12/12), karena kecil kemungkinan dedup salah menggeser hasilnya. Yang **paling rentan pada pilihan granularitas**: kategori Minoritas/Unik (1–3/12), yang jumlahnya 83% dari seluruh data — proporsi besar ini *diharapkan*, bukan tanda kegagalan dedup.

---

## 3. Pola Konsensus Lintas-AI

| Kategori | Rentang | Jumlah | % dari 292 |
|---|---|---|---|
| Universal | 11–12/12 | 13 | 4.5% |
| Mayoritas | 7–10/12 | 17 | 5.8% |
| Umum | 4–6/12 | 19 | 6.5% |
| Minoritas/Unik | 1–3/12 | 243 | 83.2% |

### 3.1 Inti yang disepakati (semua/nyaris semua AI)

Sembilan Tokoh dan empat Topik membentuk "tulang punggung" cerita PR#10 yang tidak pernah absen: **David Hilbert, Diophantus**, empat penuntas bukti 1970 (**Martin Davis, Hilary Putnam, Julia Robinson, Yuri Matiyasevich**), **Alan Turing** — semuanya 12/12 — plus **Persamaan Diophantine** dan **Program Hilbert & Formalisme** sebagai dua konsep universal.

Menariknya, **Alonzo Church** dan **Kurt Gödel** "hanya" 11/12 — keduanya sama-sama absen di draft **Copilot (CO)**, yang memang paling ringkas di antara 12 draft (39 baris Superset, MVC 17 bab) dan konsisten melewatkan tokoh-tokoh sekunder yang di draft lain otomatis disebut sebagai konteks latar.

Dua Topik lain nyaris universal: **"HTP atas Bilangan Rasional Q (masih terbuka)"** (11/12, absen di Le Chat — konsisten dengan temuan §4) dan **"Teori Komputabilitas & Mesin Turing"** (11/12, absen di Gemini).

### 3.2 Terobosan 2020-an sudah jadi "pengetahuan umum" lintas-AI

Fakta yang layak dicatat: **"Terobosan Koymans-Pagano (HTP semua ring finitely generated, 2024–2026)"** mencapai konsensus **10/12** — nyaris setara dengan Teorema Ketidaklengkapan Gödel dan Teorema MRDP itu sendiri (juga 10/12). Tim penelitinya (Koymans, Pagano di 9/12; Alpöge, Bhargava, Shnidman di 7/12) juga masuk kategori Mayoritas. Ini riset yang baru berumur 1–2 tahun pada saat prompt dijalankan, tapi liputannya di 12 AI independen sudah semendalam liputan hasil-hasil klasik 1970-an.

Ini membuat penyimpangan dua draft (Tera AI, Le Chat — lihat §4) semakin mencolok: bukan karena risetnya tidak tersedia atau esoterik, tapi karena keduanya secara spesifik gagal mengeksekusi/menyentuh sesuatu yang 10 AI lain berhasil tangani dengan baik.

---

## 4. Profil Gaya per AI

*(Match Rate dari Sheet 3 "Ringkasan per AI"; rata-rata lintas 12 AI = 78.5%)*

| AI | Match Rate | Ciri paling menonjol |
|---|---|---|
| **Meta AI** | **94.7%** (tertinggi) | Draft paling "bersih": tabel riset 2020-an paling akurat secara faktual, termasuk nama-nama teknis mendalam (Eisenträger, Dittmann, Daans) yang di AI lain sering hilang. Tak ada temuan kualitas mencurigakan sama sekali. |
| **Claude** | 91.7% | Naratif & runtut, MVC 20 bab. |
| **Grok** | 89.7% | Ringkas, gaya bullet-point per bab. |
| **Perplexity** | 88.4% | Gaya "search-grounded" — sitasi URL inline di sepanjang Latar Belakang & Tabel, berbeda dari 11 AI lain yang menulis lebih naratif. |
| **Qwen** | 82.8% | Gaya "panduan penulis" dengan banyak meta-komentar eksplisit. |
| **Le Chat (Mistral)** | 81.0% | **Lihat catatan khusus di bawah.** |
| **Gemini** | 79.2% | Daftar Pustaka dikelompokkan per Lapisan (format unik di antara 12 AI). |
| **Copilot** | 75.0% | Paling ringkas (17 bab, 10 sumber pustaka) — tapi memuat satu klaim paling spesifik & terkini di seluruh siklus (lih. §5). |
| **DeepSeek** | 71.1% | Bercorak akademis-kepustakaan, label topik tematik luas ketimbang spesifik. |
| **Tera AI** | 69.4% | **Lihat catatan khusus di bawah.** |
| **Kimi** | 68.5% | Draft **terbesar** (40 bab, tabel 36 baris, 39 sumber pustaka) — proporsi Prep-only tinggi karena banyak tokoh "pendukung tematik" di tabel yang tak pernah ditindaklanjuti di bab manapun. |
| **GPT** | **50.7%** (terendah) | **Lihat catatan khusus di bawah.** |

### 4.1 Tiga pola struktural yang layak disorot

**Tera AI — riset kaya yang tak pernah dieksekusi.** Tabel risetnya mencakup detail 2020-an paling lengkap dari 12 AI (Koymans-Pagano, formal verifikasi via Coq, Hipotesis Mazur, kasus ℝ/ℂ via Tarski-Seidenberg) — tapi diverifikasi lewat pencarian teks langsung, **nol** dari istilah-istilah ini muncul di 21 bab MVC-nya. Pola "Prep kaya, Draft tidak menindaklanjuti" ada di semua draft dalam skala kecil, tapi di Tera AI polanya paling ekstrem: bab-bab yang seharusnya jadi "Frontier" malah berisi topik generik (polinomial universal 1976, hierarki kompleksitas) alih-alih riset paling mutakhir yang sudah ditelitinya sendiri.

**Le Chat — scope creep menggantikan riset yang sebenarnya diminta.** Ini satu-satunya draft yang **sama sekali tidak menyebut** terobosan HTP 2020-an (Koymans, Pagano, Alpöge, Bhargava, Ho, Shnidman — nol kemunculan). Saat diminta memperbarui tabel sampai 2026, alih-alih mengisi kekosongan riset HTP, draft ini menambah topik yang hanya bersinggungan tangensial dengan PR#10: komputasi kuantum, kriptografi pasca-kuantum, AI/ML terkini, blockchain. Konsekuensinya juga tercermin di Daftar Pustaka: 37 dari 61 Tokoh-nya (jumlah Draft-only terbanyak di 12 AI) berasal dari buku populer/teknis yang tak terkait langsung — termasuk whitepaper Bitcoin dan Ethereum.

**GPT — dua tahap yang saling mengoreksi diri.** Satu-satunya draft yang menulis peta MVC lengkap 37-bab, lalu secara eksplisit mengkritik strukturnya sendiri ("kalau tujuan kita benar-benar MVC, saya malah akan memangkasnya cukup brutal") dan mengusulkan versi final 15 bab. Tabelnya juga unik: 58 baris, banyak berisi daftar "dkk." nama tangensial (mis. kontributor teorema transendensi sbg kontras Problem #7) yang nyaris semuanya tak disebut ulang di MVC manapun — rasio Match:Prep-only-nya nyaris 50:50, jauh paling rendah dari 12 AI. Ini BUKAN indikasi draft berkualitas rendah — justru mencerminkan riset tabel yang sangat luas dikombinasikan dengan disiplin menjaga bab tetap ramping pada *core cast*.

---

## 5. Temuan Kualitas Data (Tahap 1.5)

Semua temuan berikut sudah diverifikasi via pencarian web dan/atau *fetch* langsung ke sumber primer (bukan dugaan) sebelum dicatat di sini.

### 5.1 Halusinasi terkonfirmasi (1 dari 12 draft)

**Le Chat** mengutip *"Rao, A. (2018). The Limits of Mathematics... AMS"*. Ini sitasi keliru: karya aslinya adalah **Gregory J. Chaitin**, *"The Limits of Mathematics"*, terbit di Springer (bukan AMS, bukan "Rao, A."). Temuan ini dikonfirmasi ganda — via pencarian web Claude, **dan** via klarifikasi langsung user ke Le Chat sendiri, yang mengonfirmasi kekeliruannya dan menyarankan rujukan pengganti yang benar.

### 5.2 Dua "alarm palsu" yang justru terbukti akurat

Dua klaim yang tampak paling mencurigakan di seluruh 12 draft — sebelum verifikasi — ternyata **akurat**:

- **"Kai"** — disebut independen di draft Kimi ("Kai, peneliti") dan Copilot ("Kai, 2026") sebagai kontributor perluasan Teorema Green-Tao untuk *number fields*, tanpa nama belakang atau konteks jelas. Setelah dicek: **Wataru Kai**, Asisten Profesor di Tohoku University — hasilnya (arXiv:2306.16983) memang dikutip di kedua paper asli Koymans-Pagano *dan* Alpöge-Bhargava-Ho-Shnidman.
- **"Jonathan Brossard"** (Copilot) — klaim paling spesifik & terisolasi di seluruh siklus: bukti konstruktif PR#10 via Rocq/Coq terkait Rice's theorem, tahun 2026. Ternyata paper riil, **arXiv:2604.16477**, terbit April 2026 — *setelah* batas pengetahuan Claude, sehingga sama sekali tidak bisa diverifikasi dari memori model saat pertama kali diperiksa.

Pelajaran metodologis: kecurigaan intuitif (nama asing tunggal, klaim sangat spesifik dan baru) tidak berkorelasi kuat dengan halusinasi — terutama untuk riset yang sangat mutakhir, di mana verifikasi lewat pencarian aktif jauh lebih andal daripada penilaian *plausibility* semata.

### 5.3 Galat sitasi & atribusi (bukan halusinasi total, tapi tetap keliru)

| AI | Galat | Detail |
|---|---|---|
| Kimi | Nomor arXiv salah | `2401.05904` (dikutip utk paper Koymans-Pagano) sebenarnya paper fisika nuklir tak terkait. Nomor benar: `2412.01768`. |
| Copilot | Placeholder tak terisi + 2 paper tercampur | `arXiv:2503.xxxxx` adalah placeholder literal yang tak pernah diisi. Judul yang dikutip ternyata milik paper ekspositori Feb 2026 (`2602.04468`), bukan paper hasil asli Des 2024. |
| Claude | Salah atribusi jurnalis | Mengutip "Natalie Wolchover" untuk artikel Quanta soal terobosan HTP — byline aslinya **Joseph Howlett**. Draft Grok mengutip artikel yang sama dengan atribusi yang benar. |
| Grok, Meta AI | Salah nama depan | "Katrina Eisenträger" — nama yang benar **Kirsten** Eisenträger (Penn State). |
| Perplexity | Salah inisial (konsisten) | "C. Ho" ditulis di Tabel *maupun* Daftar Pustaka — nama benar **Wei Ho**. |
| Tera AI | Atribusi perlu nuansa | "Dominik Kirst, Yannick Forster" untuk paper formalisasi Coq — Kirst kontributor riil proyek terkait, tapi paper spesifik "H10 in Coq" penulisnya **Larchey-Wendling & Forster** (sesuai draft Meta AI). |

### 5.4 Satu keputusan editorial yang sengaja *tidak* digabung

Selama Tahap 2, sempat dipertimbangkan menggabung "Joseph Howlett" (Grok) dan "Natalie Wolchover" (Claude) menjadi satu kelompok kanonik, karena keduanya merujuk artikel yang sama. Keputusan akhir: **tidak digabung**. Prinsip pembedanya: varian ejaan dari orang yang sama (mis. Lipshitz/Lipschitz, Katrina/Kirsten Eisenträger) sah digabung karena kedua AI jelas *bermaksud* merujuk individu yang sama — tapi Wolchover dan Howlett adalah dua orang sungguhan yang berbeda; Claude tidak salah eja nama Howlett, ia menyebut orang lain yang salah. Menggabungnya akan menyembunyikan temuan itu sendiri (seolah dua AI "sepakat" padahal satu benar dan satu keliru). Nama kanonik "J. Howlett" tetap dilengkapi jadi "Joseph Howlett" untuk kejelasan, tanpa menggabung kelompoknya dengan Wolchover.

---

## 6. Batasan Analisis

- Ekstraksi Tahap 1 memakai verifikasi Prep-vs-Draft berbasis kemunculan **literal** nama/istilah, bukan kesamaan makna. Ini disengaja (lihat metodologi skill) tapi berarti beberapa status "Prep only" mencerminkan *parafrase* di Draft, bukan benar-benar hilang secara substansi — masing-masing kasus sudah dicatat dengan keterangan di Sheet 2.
- Kategori Minoritas/Unik (83% dari data) tidak diaudit satu-satu secara individual untuk akurasi faktual — hanya sampel yang dicurigai/menonjol yang diverifikasi di Tahap 1.5. Ada kemungkinan galat kecil serupa (salah eja, salah inisial) yang belum terdeteksi di long-tail Daftar Pustaka 1-AI.
- Keputusan kanonikalisasi Tahap 2 (termasuk kasus Howlett/Wolchover di atas) melibatkan *judgment* yang didiskusikan dan disepakati bersama user — bukan aturan mekanis tunggal. Sesi ekstraksi lain berpotensi mengambil keputusan granularitas berbeda pada kasus serupa.

---

## 7. Rujukan Data

Seluruh angka di laporan ini bersumber dari `Hilbert-PR10-Komparatif.xlsx`:
- **Sheet 1–2**: 738 baris data mentah per-AI (ekstraksi Tahap 1, dgn catatan verifikasi Tahap 1.5 di kolom Catatan)
- **Sheet 3**: Match Rate & ringkasan per AI
- **Sheet 5 "Konsensus 12 AI"**: 292 kelompok kanonik dgn skor konsensus
- **Sheet 6 "Ringkasan Final"**: statistik teragregasi via formula (Bagian A–E)
