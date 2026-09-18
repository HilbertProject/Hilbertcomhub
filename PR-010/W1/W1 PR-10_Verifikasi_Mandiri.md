# PR-10 — Verifikasi Mandiri (Solo)

**Fase:** 3, skill `hilbert-sintesa` — mengikuti `format-verifikasi-mandiri.md`
**Cakupan:** hanya klaim **faktual** (nama, tanggal, atribusi, angka) dari `PR-10_Draft_Usulan_MVC.md` — pilihan editorial (Primer/Sekunder/Optional dari Fase 1) **tidak** masuk di sini.
**Metode:** sisir sistematis bab-per-bab (bukan cuma klaim yang kebetulan diverifikasi sambil menulis Fase 2) — pencarian aktif dijalankan untuk tiap klaim berisiko, bukan mengandalkan ingatan.

**Ringkasan hasil:** dari sekitar 55 klaim faktual disisir, **4 terbukti keliru dan sudah diperbaiki langsung di Draft MVC** (bukan cuma dicatat di ledger — lihat aturan `format-verifikasi-mandiri.md` §"Kalau klaim gagal verifikasi"), 2 butuh catatan presisi tambahan (✅ Akurat, tapi...), sisanya terverifikasi atau fakta mapan.

---

## Gerbang

Tidak ada klaim faktual — sesuai aturan Gerbang (tanpa jargon bernama, tanpa nama tokoh, lihat Atlas §2.6). Tidak diperiksa.

---

## LAPISAN I — FONDASI

| # | Klaim | Status | Sumber/Catatan |
|---|---|---|---|
| 1 | Diophantus menulis *Arithmetica* di Alexandria, ~abad ke-3 M | ✅ Akurat, tapi... | Tanggal Diophantus genuinely tak pasti dalam sejarah matematika — rentang estimasi 150 SM–350 M, "abad ke-3 (fl. ~250 M)" adalah estimasi terbaik/standar (MacTutor, Wikipedia), bukan fakta pasti. Draft sudah pakai kata "sekitar" — cukup hati-hati, tak perlu diubah. |
| 2 | Fermat menuliskan FLT di margin salinan *Arithmetica*, abad ke-17 (~1637) | ✅ Terverifikasi | Wikipedia "Fermat's Last Theorem"; tanggal standar ~1637. |
| 3 | Wiles membuktikan FLT 358 tahun kemudian | ✅ Terverifikasi | Wikipedia: "After 358 years of effort..." — 1637→1995 = 358. Cocok persis. |
| 4 | Euler, Lagrange mengasah teknik persamaan Diophantine tertentu | 🔵 Fakta mapan | Pengetahuan standar sejarah teori bilangan, tak dicari khusus. |
| 5 | Hilbert mengajukan PR-10 dlm ceramah "Mathematische Probleme", Paris 1900 | ✅ Terverifikasi | MacTutor, Wikisource (teks asli Jerman); ICM ke-2, 6–12 Agustus 1900. |
| 6 | Domain literal PR-10 adalah ℤ (bukan ℚ) | ✅ Terverifikasi | Sudah diverifikasi Fase 1 (terjemahan standar rumusan asli) + dikonfirmasi ulang dari abstrak paper Koymans-Pagano 2024/2026 yang mengutip rumusan sama persis. |
| 7 | Istilah asli Jerman "Verfahren", belum berdefinisi formal 1900 | 🔵 Fakta mapan | Konsisten dgn seluruh literatur sejarah logika; sudah dibahas mendalam Fase 1. |
| 8 | Cross-reference NB-CON-0025 (Program Hilbert, dari PR-002) | 🔷 Reuse Registry | Dicek thd Atlas Master v1.7 §3 — entri ada, Confirmed, Framework, PR-002. Cocok. |
| 9 | Kutipan "Wir müssen wissen — wir werden wissen", pidato radio Königsberg | ✅ Terverifikasi | MAA (James T. Smith), transkrip asli Jerman + rekaman audio dikonfirmasi ada. Tanggal presisi: 8 September 1930 (draft tak menyebut tanggal spesifik, jadi tak ada klaim tanggal yg perlu dicek ulang). |
| 10 | Emil du Bois-Reymond sbg pengucap "ignorabimus" yg ditolak Hilbert | ✅ Akurat | Wikipedia "Ignoramus et ignorabimus" — pidato 1872 "Über die Grenzen des Naturerkennens". |
| 11 | Du Bois-Reymond adalah "fisikawan-fisiolog" | ❌ **Terbantahkan** — **sudah diperbaiki di Draft** | Ia dokter/fisiolog Jerman (perintis elektrofisiologi), **bukan fisikawan**. Sumber: Wikipedia, Encyclopedia.com, wehd.com — semua konsisten menyebut "German physiologist/physician". Draft direvisi jadi "dokter-fisiolog Jerman". |
| 12 | Entscheidungsproblem dirumuskan Hilbert & Ackermann, 1928 | ✅ Terverifikasi | *Grundzüge der theoretischen Logik*, Springer 1928, edisi pertama — dikonfirmasi lewat 4+ katalog buku langka independen & Wikipedia. |

---

## LAPISAN II — REVOLUSI

| # | Klaim | Status | Sumber/Catatan |
|---|---|---|---|
| 13 | Cross-reference NB-RES-0011/0012 (Ketaklengkapan Gödel, dari PR-002) | 🔷 Reuse Registry | Dicek thd Atlas §4 — ada, Confirmed, Theorem, 1931. Cocok. |
| 14 | Turing 1936, "On Computable Numbers, with an Application to the Entscheidungsproblem" | ✅ Terverifikasi | *Proc. London Math. Soc.* 42 (1936), 230–265 — dikonfirmasi banyak sumber independen. |
| 15 | Church 1936, kalkulus-λ, jawaban independen Entscheidungsproblem | ✅ Terverifikasi | Church submit 15 April 1936, terbit lebih dulu beberapa bulan drpd Turing — "nyaris bersamaan" di Draft sudah tepat framing-nya. |
| 16 | Turing, Church, & fungsi rekursif "belakangan terbukti setara" | ✅ Akurat, tapi... | Bukti penuh kesetaraan 3-arah (Turing–Church–Kleene/rekursif) baru formal di paper Turing 1937 "Computability and λ-Definability", bukan 1936. Draft sengaja tak menyebut tahun spesifik ("belakangan") jadi tak ada klaim salah — dicatat di sini demi presisi kalau nanti diperluas. |
| 17 | Konjektur Davis, 1953, "Arithmetical problems and recursively enumerable predicates" | ✅ Terverifikasi | *J. Symbolic Logic* 18 (1953), 33–41 — abstrak paper eksplisit menyebut kaitan langsung ke "the tenth problem... proposed by Hilbert in 1900". |
| 18 | Julia Robinson, hipotesis eksponensial, awal 1950-an | 🔵 Fakta mapan | Konsisten dgn "Existential Definability in Arithmetic" (1952), dikonfirmasi berulang di berbagai sumber sekunder yg sudah dilihat. |
| 19 | Persamaan Pell dikenal sejak matematikawan India, diteliti Fermat & Lagrange | 🔵 Fakta mapan | Sejarah standar; tak dicari khusus. |
| 20 | Davis, Putnam, Robinson, 1961, "The decision problem for exponential diophantine equations" | ✅ Terverifikasi | *Ann. of Math.* 74 (1961), 425–436 — dikonfirmasi 4+ sumber independen (Mathnet.ru, arXiv references dari 3 paper berbeda). |
| 21 | Reduksi Davis-Putnam disebut sbg hasil "1961" tunggal | ✅ Akurat, tapi... | Ada JUGA paper Davis-Putnam (2 nama saja, tanpa Robinson) 1958 "Reductions of Hilbert's tenth problem", *J. Symb. Logic* 23 (1958) — jadi "reduksi" sesungguhnya rentang 1958–1961, bukan momen tunggal 1961. Draft atribusi Bab 8 sudah benar (Davis-Putnam-**Robinson**, 1961, sesuai paper yg dirujuk), tapi nama registry "Reduksi Davis-Putnam" (2 nama) sedikit tak lengkap dibanding isi bab (3 nama) — dicatat sbg nuansa, tak fatal. |
| 22 | Matiyasevich menutup celah 1970, usia 22-23 tahun | ✅ Terverifikasi | Lahir 2 Maret 1947 (Wikipedia, MacTutor) → di tahun 1970 (sebelum/sesudah Maret) usianya 22 atau 23. Draft menyebut "22 tahun" tanpa bulan spesifik — masuk rentang benar, tak perlu diubah. |
| 23 | Matiyasevich matematikawan Soviet, Leningrad | ✅ Terverifikasi | MacTutor, Wikipedia — lahir & bekerja di Leningrad (LOMI/Steklov Institute). |
| 24 | Nama "MRDP" disusun sesuai urutan alfabet, bukan kronologis | ❌ **Terbantahkan** — **sudah diperbaiki di Draft** | MRDP (M-R-D-P) **bukan** urutan alfabetis (alfabetis: D-M-P-R). Faktanya ada 2 akronim bersaing di literatur — MRDP dan DPRM — Matiyasevich sendiri lebih suka DPRM (kronologis), Davis lebih suka MRDP. Sumber: arXiv:2311.09464 ("Matiyasevich favors the latter and Davis the former"), dikonfirmasi 3 sumber independen lain. Draft direvisi total, sekarang menjelaskan nuansa yg benar. |
| 25 | Emil Post, 1944, "Recursively enumerable sets of positive integers and their decision problems" | ✅ Terverifikasi | *Bull. Amer. Math. Soc.* 50 (1944), 284–316 — paper & tahun dikonfirmasi (AMS, arXiv sejarah H10). |
| 26 | Post secara spesifik menduga PR-10 (bukan cuma unsolvability secara umum) akan berujung negatif | 🔶 Diklaim | Sumber yg ditemukan mengonfirmasi paper 1944 Post ttg RE sets & Post's problem secara umum, dan artikel sejarah terpisah (Stillwell, "Emil Post and His Anticipation of Gödel and Turing") mengonfirmasi Post memang mengantisipasi banyak hasil unsolvability — tapi kutipan langsung yg menyebut PR-10 secara spesifik dlm paper 1944 itu sendiri tak berhasil dikonfirmasi verbatim dlm pencarian sesi ini. Klaim ini berasal dari superset Baseline Sintesa (1/12, sumber tunggal) — diwariskan, belum di-cross-check independen sampai level ini. **Tidak diubah di Draft** (klaim inti soal antisipasi Post thd unsolvability umum tetap kuat), tapi ditandai jujur sbg belum 100% terverifikasi utk detail spesifik "PR-10 by name". |

---

## LAPISAN III — FRONTIER

| # | Klaim | Status | Sumber/Catatan |
|---|---|---|---|
| 27 | Julia Robinson, disertasi PhD Berkeley 1948, hasil terbit 1949, ℤ definabel first-order di ℚ via Hasse-Minkowski | ✅ Terverifikasi | Sudah diverifikasi di Fase 1 (Gap table) — dikonfirmasi ulang konsisten di sesi ini via referensi "in 1949 J. [Robinson]..." di paper Garcia-Fritz/Pasten/Vidaux. |
| 28 | Jochen Koenigsmann, 2016, definisi universal ℤ di ℚ | ✅ Terverifikasi | Sudah diverifikasi Fase 1 ("Defining Z in Q", *Ann. of Math.* 183 (2016)) — muncul lagi konsisten di daftar referensi paper Koymans-Pagano. |
| 29 | Konjektur Mazur — closure topologis solusi rasional | ✅ Terverifikasi | Mazur, "The Topology of Rational Points", *Experiment. Math.* 1 (1992). |
| 30 | Tahun Konjektur Mazur "~1990-an" | ✅ Akurat, tapi... | Presisinya 1992 (bukan cuma "~1990-an" generik) — draft tak salah tapi bisa lebih presisi. |
| 31 | **Arah logis Konjektur Mazur: mendukung dugaan HTP(ℚ) undecidable** | ❌ **Terbantahkan** — **sudah diperbaiki di Draft** | **Faktanya kebalikan**: Mazur mengajukan konjektur ini dlm "a contrarian mood" (math.mit.edu/Poonen) — kalau konjektur ini BENAR, itu justru menunjukkan ℤ **tidak** Diophantine-definable di ℚ, sehingga **menutup/menghalangi** jalur "reduksi ke HTP(ℤ)", bukan mendukungnya. Draft Bab 11 direvisi total utk mencerminkan arah yg benar — sekarang menjelaskan Konjektur Mazur sbg alasan kenapa arah jawaban HTP(ℚ) masih genuinely terbuka, bukan sbg alat menuju jawaban negatif. |
| 32 | Bjorn Poonen, teknik kurva eliptik/descent, "sejak awal 2000-an" | ✅ Terverifikasi | Poonen, "Using elliptic curves of rank one...", 2002 — cocok persis "awal 2000-an". |
| 33 | Jan Denef, hasil parsial, "sejak akhir 1970-an" | ✅ Akurat, tapi... | Paper Denef paling awal yg ditemukan: 1975 ("Hilbert's tenth problem for quadratic rings"), lalu Denef-Lipshitz 1978, Denef 1980. "Akhir 1970-an" sedikit terlambat — lebih presisi "pertengahan-akhir 1970-an" (dimulai 1975). Nuansa kecil, tak fatal. |
| 34 | Alexandra Shlapentokh, "1990-2000an" | 🔵 Fakta mapan, tapi rentang luas | Dikonfirmasi aktif di area ini sejak 1990-an-2000-an (banyak paper terdaftar di referensi berbagai sumber yg ditemukan), tapi kontribusi paling relevan langsung ke narasi Bab 12 (kurva eliptik) lebih spesifik ~2008. Rentang di Draft cukup aman krn luas. |
| 35 | Koymans-Pagano, 2024, "Hilbert's tenth problem via additive combinatorics", HTP tak-decidable utk semua ring finitely generated atas ℤ | ✅ Terverifikasi | arXiv:2412.01768, submit 2 Des 2024. Abstrak persis cocok dgn klaim Draft. |
| 36 | Mekanisme: kurva eliptik tanpa pertumbuhan rank + kombinatorika aditif + 2-descent | ✅ Terverifikasi | Abstrak paper: "elliptic curves E without rank growth... combine techniques from additive combinatorics with 2-descent". |
| 37 | Wataru Kai, perluasan Green-Tao ke number fields, dipakai Koymans-Pagano & ABHS | ✅ Terverifikasi (ulang dari Fase 1) | Dikonfirmasi ulang: [Kai23]/[Kai25] "Linear patterns of prime elements in number fields", arXiv:2306.16983, dirujuk eksplisit di kedua paper (Koymans-Pagano & Zywina 2025). |
| 38 | Alpöge, Bhargava, Ho, Shnidman, 2025, bukti independen kestabilan rank | ✅ Terverifikasi | arXiv:2501.18774, "Rank stability in quadratic extensions and Hilbert's tenth problem..." — nama 4 penulis persis cocok. |
| 39 | Timing ABHS relatif thd Koymans-Pagano: "setahun kemudian" | ❌ **Terbantahkan** — **sudah diperbaiki di Draft** | Koymans-Pagano preprint awal: 2 Des 2024. ABHS preprint: 30 Jan 2025. Jarak **~2 bulan**, bukan setahun — cuma beda tahun kalender krn Desember→Januari. Draft direvisi menyebut "sekitar dua bulan", justru memperkuat poin ttg betapa cepatnya konfirmasi independen datang. |
| 40 | Cross-reference NB-RES-0002 (Transfer Principle Tarski, dari PR-017), Named Bridge #17↔#10 | 🔷 Reuse Registry | Dicek thd Atlas §4 — ada, Confirmed, Theorem, 1948. Cocok, dan penggunaan ulang ke PR-10 memenuhi Prinsip #3 (memakai teorema bernama yg sama, bukan cuma kesamaan tokoh). |
| 41 | Tarski, teori *real closed fields*, eliminasi kuantifier, 1948 | 🔷 Reuse Registry | Tahun 1948 diwarisi dari entri Atlas yg sudah Confirmed (PR-017) — bukan klaim baru yg perlu verifikasi ulang. Catatan tambahan (bukan koreksi): 1948 adalah laporan teknis RAND; versi terbit resminya 1951 (UC Press) — kedua tahun dipakai bergantian di literatur, entri Atlas memilih 1948, konsisten dipertahankan di sini. |

---

## LAPISAN IV — REFLEKSI

| # | Klaim | Status | Sumber/Catatan |
|---|---|---|---|
| 42 | Presburger, 1929, decidability aritmetika penjumlahan-saja | ✅ Akurat, tapi... | Dipresentasikan 1929 (Kongres Matematikawan Slavia, Warsawa), diterbitkan dlm prosiding 1930. Draft pakai "1929" (tahun presentasi) — konsisten dgn konvensi umum (Wikipedia, dll. jg sering sebut 1929), sudah diverifikasi sama persis di Fase 1. Tak diubah, dicatat nuansa presentasi/publikasi. |
| 43 | Larchey-Wendling & Forster, formalisasi "H10 in Coq" | ✅ Terverifikasi | FSCD 2019, *LIPIcs* vol 131, Feb 2019 — dikonfirmasi 6+ sumber independen (Dagstuhl, HAL, arXiv versi extended 2022). Dominik Kirst dikonfirmasi HANYA disebut di ucapan terima kasih ("helpful discussion"), BUKAN co-author — mengonfirmasi ulang koreksi yg sudah dibuat Baseline Sintesa (Laporan Naratif §5.3). |
| 44 | Referensi ke paper 2026 penghubung Rice's theorem (disinggung tanpa nama eksplisit di Bab 16) | ✅ Terverifikasi (ulang dari Fase 1) | Draft sengaja tak menyebut nama "Jonathan Brossard" scr eksplisit di prosa (beda dari tabel Fase 1) — hanya deskripsi umum "menghubungkan PR-10 dgn Rice's theorem". Deskripsi ini dikonfirmasi ulang cocok dgn arXiv:2604.16477 yg muncul di hasil pencarian sesi ini juga (via referensi silang paper lain), memperkuat verifikasi Fase 1. |
| 45 | Makalah ekspositori Koymans-Pagano, Feb 2026 | ✅ Terverifikasi (ulang dari Fase 1) | arXiv:2602.04468, "Hilbert's tenth problem for finitely generated rings", tanggal 5 Feb 2026 — dikonfirmasi ulang, isinya persis survei 1900→2026 sesuai deskripsi Draft. |
| 46 | Perbandingan PR-1 (independen dari ZFC) vs PR-10 (tak-decidable secara algoritmik) sbg 2 jenis "tak terputuskan" berbeda | 🔵 Fakta mapan | Sudah dibangun mendalam sepanjang seluruh proyek ini (Atlas, MVC PR-001) — bukan klaim baru. |
| 47 | P vs NP: beda level dgn PR-10 (eksistensi vs efisiensi algoritma) | 🔵 Fakta mapan | Definisi standar ilmu komputer teoretis, tak dicari khusus. |
| 48 | Komputasi kuantum tak mengubah *decidability*, hanya *complexity* (BQP dsb.) | 🔵 Fakta mapan | Konsekuensi langsung extended Church-Turing thesis (kuantum tak menambah himpunan fungsi computable) — pengetahuan standar teori komputasi, tak dicari khusus. |

---

## Lampiran — Registry (Cross-check thd Atlas Master, bukan web search)

| Klaim registry | Status | Catatan |
|---|---|---|
| Semua 46 entri baru (`xxx01`–`xxx23` gabungan Konsep/Hasil/Tokoh) belum bentrok ID dgn Atlas Master v1.7 | 🔷 Reuse Registry | Dicek: seluruh ID existing tertinggi di Atlas adalah NB-CON-0034, NB-RES-0014, NB-PER-0026 — placeholder `xxx` di draf ini tidak akan bentrok penomoran final asal proses assignment resmi berjalan sesudahnya (bukan dinomori manual sekarang, sesuai instruksi format-draft-mvc.md). |
| Klasifikasi Jenis "Theorem" (bukan "Independence Result") utk Teorema MRDP | 🔷 Reuse Registry | Konsisten dgn preseden NB-RES-0011/0012 (Ketaklengkapan Gödel) yg diregistrasi Theorem meski juga hasil "impossibility" — argumen lengkap di Fase 1.5 §B. |
| 3 entri Hasil Besar ditandai tentatif "Conjecture" (Konjektur Davis, Hipotesis J.R., Konjektur Mazur) | 🔷 Reuse Registry | Dicek thd vocab resmi §2.3 Atlas (`Theorem · Lemma · Counterexample · Independence Result · Construction · Classification · Algorithm`) — genuinely tak ada kategori cocok, bukan kelalaian. |

---

## ⚠️ Peringatan Aktif (eksklusi yang harus dijaga)

| Item | Kenapa dikecualikan |
|---|---|
| "MRDP disusun alfabetis" | Terbantahkan (#24) — JANGAN reintroduksi frasa ini dlm revisi/perluasan bab manapun ke depan, termasuk saat MVC diperluas dgn detail tambahan. |
| "Konjektur Mazur mendukung ketakputusan HTP(ℚ)" | Terbantahkan (#31) — arah yg benar adalah kebalikannya (lihat catatan #31). Risiko tinggi diulang keliru krn framing "mendukung X" terasa naratif-logis, jadi mudah "kembali" tanpa sadar saat menulis ulang/memperluas. |
| "Fisikawan-fisiolog" utk du Bois-Reymond | Terbantahkan (#11) — istilah yg benar: dokter/fisiolog Jerman. |
| "Setahun kemudian" utk jarak Koymans-Pagano→ABHS | Terbantahkan (#39) — jarak sebenarnya ~2 bulan. |

---

## Catatan Penutup

Dari 4 klaim yang terbantahkan, pola yang menonjol: **3 dari 4 adalah klaim "warna"/interpretif yang ditambahkan jendela ini sendiri saat menulis prosa Fase 2** (bukan diwariskan dari Baseline Sintesa atau Fase 1) — bukti bahwa proses menulis naratif yang mengalir lancar bisa menghasilkan detail yang terasa masuk akal ("MRDP pasti alfabetis", "setahun kemudian" sbg framing dramatis, arah logis Mazur yang terasa "mendukung" cerita) padahal keliru begitu benar-benar ditantang mencari sumbernya — persis peringatan eksplisit di `format-verifikasi-mandiri.md`: "klaim yang lolos berkali-kali saat ditulis bisa saja tetap salah sampai benar-benar ditantang langsung." Verifikasi ad hoc sambil menulis (yang sudah dilakukan utk sebagian besar tanggal/nama saat Fase 2 disusun) **tidak menangkap** keempat error ini — baru ketahuan lewat pass sistematis terpisah ini.
