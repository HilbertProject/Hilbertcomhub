# PR-10 — Analisis Topik

**Fase:** 1 (Analisis Topik) — skill `hilbert-sintesa`
**Status Atlas Master:** baris Problem Registry PR-10 **belum diterima** — sesuai `timing-atlas.md`, seluruh penilaian di bawah murni independen dari sumber tersebut. Validasi silang eksplisit menyusul di Fase 1.5 begitu baris itu direlay.
**Sumber:** `W1_HilbertPR10Komparatif.xlsx` (Sheet "Konsensus 12 AI", 292 kelompok kanonik — 194 Tokoh + 98 Topik) dan `W1_Hilbert-PR10-Laporan-Naratif.md` (Baseline Sintesa, skill `hilbert-komparatif`). Bagian C juga memasukkan 1 temuan dari `W1 Old Fase 1 PR-10_Analisis_Topik.md` (lihat §6 laporan perbandingan).

> **Catatan koreksi (pasca cross-check thd `W1 Old Fase 1 PR-10_Analisis_Topik.md`):** draf pertama dokumen ini tidak sengaja melewatkan 1 dari 98 topik ("Kriptografi Pasca-Kuantum") dan salah menjumlah tally Rekomendasi di Bagian B. Keduanya baru ketahuan saat membandingkan baris-per-baris terhadap hasil jendela sintesa lain untuk PR-10 yang sama — bukan lewat baca-ulang manual dokumen ini sendiri. Kedua koreksi sudah diterapkan di bawah dan ditandai eksplisit, bukan ditimpa diam-diam. Lihat laporan perbandingan lengkap (`PR-10_Perbandingan_Fase1_W1baru_vs_W1lama.md`) untuk rincian.
>
> **Catatan revisi editorial (putaran kedua, menyusul arahan pemilik proyek):** W1-lama sudah padat konteks dan tak bisa dimintai putusan atas 43 perbedaan Rekomendasi yang ditemukan lewat perbandingan di atas — keputusan didelegasikan penuh ke W1-baru ("sah-sah saja jika ada perbedaan pendapat, yang penting konsistensi antar file"). 14 baris direvisi mengikuti rubrik eksplisit yang baru dirumuskan di `PR-10_Keputusan_Editorial_W1baru.md` (bukan lagi dinilai ad-hoc per baris) — termasuk memensiunkan "Evaluasi Ulang" sbg kategori ke-4, mengganti dgn 2 tag overlay (`⚠ Risiko Konflasi`, `⚠ Cek Granularitas`) yang ditempel ke salah satu dari 3 level Primer/Sekunder/Optional. Ini keputusan sadar W1-baru, bisa berbeda dari W1-lama — perbedaan itu justru bahan berguna saat pemasangan lintas-jendela nanti, bukan sesuatu yang perlu disembunyikan.

---

## Bagian A — Latar Belakang

### Apa itu PR-10

Masalah Hilbert ke-10 diajukan dalam ceramah "Mathematische Probleme" di Kongres Internasional Matematikawan (ICM) ke-2, Paris, 8 Agustus 1900, dan dimuat lengkap dalam versi cetak pidato itu. Rumusannya (diparafrasekan dari terjemahan standar): diberikan sebuah persamaan Diophantine dengan sejumlah bilangan tak diketahui berapa pun dan koefisien bilangan bulat rasional, carikan suatu **proses** (*Verfahren*) yang, dalam **sejumlah langkah terbatas**, dapat menentukan apakah persamaan itu mempunyai solusi dalam bilangan bulat rasional (ℤ).

Tiga hal literal dari rumusan ini penting untuk seluruh analisis berikutnya, dan sering kabur di ringkasan populer:
1. Yang diminta bukan cara **menyelesaikan** satu per satu persamaan Diophantine — itu sudah menjadi cabang teori bilangan sejak Diophantus (abad ke-3 M) dan berlanjut lewat Fermat, Euler, Lagrange. Yang diminta adalah **prosedur/algoritma tunggal** yang berlaku untuk *sembarang* persamaan seperti itu — soal *decidability*, bukan soal *solvability* satu kasus.
2. Domain solusi yang diminta secara literal adalah **bilangan bulat (ℤ)** ("rasional ganze Zahlen" dalam teks asli Jerman) — bukan bilangan rasional (ℚ), real (ℝ), atau kompleks (ℂ). Perluasan ke domain-domain itu adalah warisan editorial yang sah secara semangat, tapi bukan literal diminta Hilbert (lihat §"Cakupan" di bawah).
3. Istilah "proses" dan "sejumlah langkah terbatas" — dalam bahasa Jerman *Verfahren* — belum punya definisi formal di tahun 1900. Definisi formal "algoritma" baru muncul 1930-an lewat mesin Turing, kalkulus-λ Church, dan fungsi rekursif Gödel/Kleene — semuanya kemudian terbukti ekuivalen (Tesis Church-Turing). PR-10 karena itu adalah salah satu titik yang memaksa matematika mendefinisikan "algoritma" secara presisi, bukan cuma memakainya secara intuitif.

### Yang diharapkan/dikhawatirkan Hilbert

Ceramah 1900 dibuka dengan optimisme eksplisit Hilbert bahwa setiap masalah matematika yang dirumuskan dengan baik pasti punya jawaban pasti — pandangan yang tiga dekade kemudian ia rangkum lewat semboyan "*Wir müssen wissen, wir werden wissen*" (kita harus tahu, kita akan tahu), menolak "*ignorabimus*" (kita tidak akan pernah tahu) yang sebelumnya diucapkan fisikawan-fisiolog Emil du Bois-Reymond untuk soal-soal tertentu di sains alam. Untuk PR-10, kerangka optimisme ini secara implisit mengasumsikan algoritma yang diminta itu **ada** — pertanyaannya tinggal menemukannya. Hilbert tidak — dan secara struktural tidak bisa — mengantisipasi bahwa jawaban definitifnya justru **negatif**: pada 1970 Yuri Matiyasevich (melengkapi kerja Martin Davis, Hilary Putnam, Julia Robinson 1944–1961) membuktikan tidak ada algoritma seperti itu. Catatan penting: hasil negatif ini **tidak membatalkan** "wir werden wissen" — kita memang sampai *tahu* jawabannya, hanya saja jawabannya adalah pembuktian ketidakmungkinan, bukan penemuan prosedur. Ironi inilah yang membuat PR-10 sering dipakai sebagai studi kasus paling tajam tentang batas antara "belum terpecahkan" dan "tidak dapat dipecahkan".

### Kekhususan PR-10 dibanding Masalah Hilbert lain

- **Objek statis vs dinamis**: PR-10 murni matematika (teori bilangan + logika) — tidak seperti PR-6 (aksiomatisasi fisika), yang terus bergeser tiap kali fisika menemukan teori baru, rumusan PR-10 tidak berubah seiring waktu. Namun perluasannya (ke ℚ, ke ring/field lain) tetap aktif — lihat poin berikutnya.
- **Selesai secara definitif, tapi melahirkan riset yang masih hidup**: bersama PR-2 (konsistensi aritmetika, dijawab negatif oleh Gödel 1931) dan berbeda dari PR-8 (Hipotesis Riemann, masih terbuka) atau PR-1 (Hipotesis Kontinum, terbukti *independen* dari ZFC — bukan "ya" atau "tidak", tapi "tak dapat diputuskan dalam sistem aksioma itu sendiri"), PR-10 punya jawaban **negatif dan definitif** atas ℤ sejak 1970. Yang membuatnya berbeda dari problem "selesai" lain (mis. PR-3, Dehn, selesai 1900 dan sejak itu relatif dorman): kemenangan 1970 justru **membuka** program riset baru — HTP untuk ring/field selain ℤ — yang sampai saat data ini dikumpulkan (pertengahan 2020-an) masih menghasilkan terobosan besar (Koymans–Pagano; Alpöge–Bhargava–Ho–Shnidman). PR-10 karena itu punya status ganda: *closed as posed*, *open as generalized*.
- **Pola "hasil negatif" yang berulang**: PR-10 berdiri di tengah rangkaian hasil negatif era 1930–1970 yang saling menguatkan secara struktural — Ketidaklengkapan Gödel (1931), Entscheidungsproblem tak terpecahkan (Church–Turing, 1936), dan MRDP (1970) — ketiganya memakai teknik pengkodean/representasi yang berkerabat (nomor Gödel, mesin Turing, himpunan Diophantine). Ini bukan kebetulan tapi konsekuensi: begitu Gödel/Turing/Church menunjukkan ada batas mekanis pada apa yang bisa dibuktikan/dihitung, PR-10 menjadi kandidat kuat untuk turut tak terpecahkan — dugaan itu sendiri sudah diutarakan Emil Post pada 1944, lebih dari 25 tahun sebelum terbukti.

### Cakupan/skop relevan

Perluasan berikut **bukan** literal diminta Hilbert 1900, tapi diterima luas sebagai pewaris sah semangat PR-10 (ditandai eksplisit di sini, bukan disamarkan sebagai bagian asli soal):
- **HTP atas ℚ** — apakah ada algoritma serupa untuk solusi rasional? Masih terbuka hingga sumber terkini (2026) yang diverifikasi dalam analisis ini.
- **HTP atas ring/field lain** — ring bilangan bulat aljabar, ring finitely generated, dll. — inilah domain terobosan Koymans–Pagano dan Alpöge–Bhargava–Ho–Shnidman 2024–2026.
- **HTP atas ℝ/ℂ** — secara kontras, domain ini justru **decidable** (Tarski–Seidenberg, teori kuantifier-eliminasi untuk *real closed fields*/medan tertutup aljabar) — kontras yang tajam dan sering hilang dari ringkasan populer.

### Kenapa PR-10 (belum) "selesai" seperti problem lain

PR-10 dalam bentuk literalnya (atas ℤ) **sudah selesai secara definitif** sejak 1970 — bukan kandidat "belum selesai". Yang membuatnya tetap relevan untuk siklus riset 2020-an bukan soal literalnya, melainkan program generalisasi yang ia lahirkan. Ini beda karakter dari kebanyakan Masalah Hilbert lain yang "belum selesai" (PR-8) atau "selesai lama dan dorman" (PR-3) — PR-10 duduk di kategori ketiga: *selesai, dan justru karena itu jadi generatif*.

---

## Bagian B — Tabel Topik

*Kolom **Konsensus** diambil langsung dari Sheet "Konsensus 12 AI" (Baseline Sintesa) — tidak dihitung ulang. Kolom **Relevansi** dinilai independen dari Konsensus (lihat metodologi §format-analisis-topik.md). Kolom **Rekomendasi** diturunkan mekanis dari Relevansi+Konsensus mengikuti rubrik eksplisit di `PR-10_Keputusan_Editorial_W1baru.md` §2 — bukan lagi judgment call independen per baris, supaya konsisten lintas 98 topik dan lintas fase berikutnya. Pengelompokan ke dalam empat "Lapisan" (Fondasi/Revolusi/Frontier/Refleksi) di bawah ini murni untuk navigasi baca — disimpulkan dari pola konten dan istilah "Frontier" yang sudah muncul di Laporan Naratif §4.1, bukan memengaruhi penilaian.*

### B.1 Lapisan Fondasi — asal-usul, rumusan, konteks

| Topik | Tokoh Terkait | Konsensus | Relevansi | Fungsi dalam PR-10 | Rekomendasi |
|---|---|---|---|---|---|
| Persamaan Diophantine | Diophantus | 12/12 | Tinggi | Objek matematis inti yang menjadi subjek seluruh problem | Keep: Primer |
| Program Hilbert & Formalisme (Aksiomatisasi, 1900) | David Hilbert | 12/12 | Tinggi | Motivasi filosofis di balik pengajuan PR-10 — bagian dari proyek formalisasi besar Hilbert | Keep: Primer |
| Perumusan Masalah Hilbert #10 (Paris 1900) | David Hilbert | 5/12 | Tinggi | Teks & konteks asal soal itu sendiri | Keep: Primer |
| Teori Himpunan & Krisis Fondasi Matematika (Cantor, Russell, dll.) | Georg Cantor, Bertrand Russell | 5/12 | Sedang | Konteks intelektual akhir abad-19 yang mendorong proyek formalisasi Hilbert | Keep: Sekunder |
| Teori Bilangan Kuadratik & kasus decidable (Lagrange) | Joseph-Louis Lagrange | 4/12 | Sedang | Kontras penting: kelas persamaan *khusus* (kuadratik, Pell) sudah lama diketahui decidable jauh sebelum pertanyaan umum PR-10 dijawab | Keep: Sekunder |
| Teorema Fermat Terakhir (contoh motivasi historis) | Pierre de Fermat, Andrew Wiles | 8/12 | Rendah | Contoh populer persamaan Diophantine termasyhur lain, tak terkait mekanisme PR-10 — tapi disebut 8/12 AI shg layak konteks singkat (rubrik §2: Rendah+Konsensus≥4 → Sekunder) | Keep: Sekunder |
| Semboyan Hilbert "Wir müssen wissen" (menolak ignorabimus) | David Hilbert | 3/12 | Tinggi | Bingkai filosofis optimisme Hilbert; ironis-relevan mengingat jawaban PR-10 akhirnya negatif | Keep: Primer |
| "Mathematische Probleme" (judul asli pidato Hilbert) | David Hilbert | 2/12 | Sedang | Detail bibliografis yang menegaskan sumber primer | Keep: Sekunder |
| Klaim "ignorabimus" du Bois-Reymond (ditolak Hilbert) | Emil du Bois-Reymond | 2/12 | Sedang | Foil filosofis yang memberi makna penuh pada semboyan Hilbert (baris di atas) | Keep: Sekunder |
| Finitisme | David Hilbert | 1/12 | Sedang | Aliran filsafat matematika yang dianut Hilbert, melandasi caranya memandang "bukti yang sah" dalam programnya | Keep: Sekunder |
| Pidato radio Königsberg 1930 | David Hilbert | 1/12 | Sedang | Sumber langsung kutipan "wir müssen wissen" — melengkapi konteks baris semboyan Hilbert di atas | Keep: Sekunder |

### B.2 Lapisan Revolusi — logika & komputabilitas 1930–1970, jalan menuju MRDP

| Topik | Tokoh Terkait | Konsensus | Relevansi | Fungsi dalam PR-10 | Rekomendasi |
|---|---|---|---|---|---|
| Teori Komputabilitas & Mesin Turing (Church-Turing, 1936) | Alan Turing, Alonzo Church | 11/12 | Tinggi | Fondasi definisi formal "algoritma" yang dibutuhkan untuk menyatakan PR-10 secara presisi | Keep: Primer |
| Teorema Ketidaklengkapan Gödel (1931) | Kurt Gödel | 10/12 | Tinggi | Pembuka jalan pesimisme terhadap program Hilbert; teknik pengkodeannya jadi cikal-bakal metode MRDP | Keep: Primer |
| Teorema MRDP (bukti final 1970) | Martin Davis, Hilary Putnam, Julia Robinson, Yuri Matiyasevich | 10/12 | Tinggi | **Jawaban negatif definitif PR-10 atas ℤ** — inti mutlak dari seluruh narasi | Keep: Primer |
| Konjektur Davis (Himpunan RE = Himpunan Diophantine) | Martin Davis | 9/12 | Tinggi | Hipotesis kunci (1953) yang, begitu terbukti benar, otomatis menjadi Teorema MRDP | Keep: Primer |
| Entscheidungsproblem | David Hilbert, Wilhelm Ackermann, Alonzo Church, Alan Turing | 8/12 | Sedang | Problem "sepupu" 1928 yang memicu kerja Turing/Church — konteks penting tapi bab PR-10 tetap solid tanpa menamainya eksplisit (rubrik §1: pemicu/mekanisme, bukan hasil inti) | Keep: Sekunder |
| Hipotesis Julia Robinson (fungsi eksponensial Diophantine) | Julia Robinson | 7/12 | Tinggi | Syarat teknis kunci (1952) yang jika dipenuhi otomatis menyelesaikan reduksi ke MRDP — dipenuhi Matiyasevich 1970 | Keep: Primer |
| Halting Problem (Masalah Berhenti) | Alan Turing | 6/12 | Sedang | Analog populer paling umum untuk menjelaskan konsep *undecidability* ke pembaca awam | Keep: Sekunder |
| Persamaan Pell | Pierre de Fermat | 6/12 | Sedang | Alat teknis kunci: pertumbuhan eksponensial solusi Pell dipakai Matiyasevich menunjukkan eksponensial itu Diophantine | Keep: Sekunder |
| Kalkulus Lambda (Church, 1936) | Alonzo Church | 5/12 | Sedang | Formalisasi computability jalur alternatif dari mesin Turing; dasar Tesis Church-Turing | Keep: Sekunder |
| Tesis Church-Turing | Alonzo Church, Alan Turing | 5/12 | Tinggi | Menyamakan "algoritma" formal modern dengan "prosedur efektif" informal yang dimaksud Hilbert 1900 — jembatan konseptual wajib | Keep: Primer |
| Batas variabel/derajat pada persamaan universal (9-11 unknowns) | Yuri Matiyasevich, James P. Jones | 4/12 | Sedang | Hasil kuantitatif lanjutan pasca-1970 (mempersempit berapa variabel minimum dibutuhkan) | Keep: Sekunder |
| Teori Kompleksitas Komputasi (P vs NP) | — | 4/12 | Rendah | Sering disandingkan populer dengan PR-10, tapi secara teknis beda level (P vs NP soal *efisiensi* algoritma yang *ada*; PR-10 soal *eksistensi* algoritma sama sekali) — kontras bernilai (rubrik §2: Rendah+Konsensus≥4→Sekunder), asal dijelaskan hati-hati | Keep: Sekunder ⚠ Risiko Konflasi |
| Barisan Fibonacci (kunci teknis bukti 1970) | Yuri Matiyasevich | 3/12 | Sedang | Alat teknis konkret Matiyasevich untuk menunjukkan relasi eksponensial adalah Diophantine | Keep: Sekunder |
| Kolaborasi matematika lintas Tirai Besi (Perang Dingin) | Julia Robinson, Yuri Matiyasevich | 3/12 | Sedang | Catatan historis-manusiawi: penyelesaian akhir 1970 menyatukan kerja matematikawan AS (Davis-Putnam-Robinson) dan Soviet (Matiyasevich) di tengah Perang Dingin — nilai naratif kuat | Keep: Sekunder |
| Persamaan Diophantine Eksponensial | Julia Robinson | 3/12 | Tinggi | Konsep teknis inti — definisi yang dipakai dalam Hipotesis J.R. dan Teorema MRDP | Keep: Primer |
| Reduksi Davis-Putnam (bentuk normal, eliminasi) | Martin Davis, Hilary Putnam | 3/12 | Tinggi | Langkah teknis 1961 (bentuk normal Davis-Putnam-Robinson) yang jadi kerangka kerja menuju MRDP | Keep: Primer |
| Aritmetika Peano | Giuseppe Peano | 2/12 | Sedang | Sistem aksioma rujukan Gödel & konteks Entscheidungsproblem — **ditunjuk kanonik primer** atas pasangannya "Aksioma Peano" (Keputusan Editorial §4) | Keep: Sekunder |
| Konsep "prosedur efektif" (Verfahren) | David Hilbert | 2/12 | Tinggi | Istilah asli Jerman dalam rumusan 1900 — jembatan langsung ke definisi algoritma modern (lihat Bagian A) | Keep: Primer |
| Persamaan Diophantine Universal (bounded variables) | James P. Jones | 2/12 | Sedang | Hasil konkret pasca-1970: persamaan tunggal berparameter yang "universal" untuk semua himpunan RE | Keep: Sekunder |
| Teorema DPR (Davis-Putnam-Robinson, 1961) | Martin Davis, Hilary Putnam, Julia Robinson | 2/12 | Sedang | **Ditunjuk alias** dari "Reduksi Davis-Putnam" di atas (hasil 1961 yang sama, framing beda) — kanonik primer tetap "Reduksi Davis-Putnam" (Keputusan Editorial §4) | Keep: Sekunder ⚠ Cek Granularitas |
| Undecidability (konsep umum) | — | 2/12 | Tinggi | Konsep payung yang MENJADI jawaban akhir PR-10 itu sendiri — bab tak solid tanpanya (rubrik §1: definisi inti, bukan sekadar pendukung) | Keep: Primer |
| Aksioma Peano | — | 1/12 | Rendah | **Ditunjuk alias** dari "Aritmetika Peano" di atas — kanonik primer tetap "Aritmetika Peano" (Keputusan Editorial §4; catatan: W1-lama mempertahankan status setara utk kedua sisi, W1-baru memilih menunjuk salah satu skrg) | Optional ⚠ Cek Granularitas |
| Arithmetical hierarchy | — | 1/12 | Sedang | Kerangka klasifikasi kompleksitas himpunan RE/Diophantine dalam hierarki logis | Keep: Sekunder |
| Batas Kompleksitas & Pasangan Universal (nu,delta) | — | 1/12 | Sedang | Hasil kuantitatif spesifik pasca-1970 soal pasangan parameter universal | Keep: Sekunder |
| Degree of unsolvability | — | 1/12 | Sedang | Konsep derajat Turing — perluasan langsung dari gagasan undecidability | Keep: Sekunder |
| Fungsi rekursif | Kurt Gödel | 1/12 | Sedang | Formalisasi computability jalur ketiga (selain Turing & Church) — melengkapi Tesis Church-Turing | Keep: Sekunder |
| Matiyasevich's theorem | Yuri Matiyasevich | 1/12 | Sedang | **Ditunjuk alias** dari "Teorema MRDP" di atas (framing sempit utk kontribusi spesifik Matiyasevich 1970 dlm hasil gabungan) — kanonik primer tetap "Teorema MRDP" (Keputusan Editorial §4) | Keep: Sekunder ⚠ Cek Granularitas |
| Nomor Gödel (Gödel numbering) | Kurt Gödel | 1/12 | Sedang | Teknik pengkodean penting yang dipakai lintas bukti undecidability (Gödel, Turing, dan tak langsung MRDP) | Keep: Sekunder |
| Post's Correspondence Problem (PCP) | Emil Post | 1/12 | Sedang | Problem undecidable klasik lain yang sering disandingkan sebagai analog PR-10 | Keep: Sekunder |
| Saran awal unsolvability (Emil Post 1944) | Emil Post | 1/12 | Tinggi | Prediksi eksplisit tahun 1944 bahwa PR-10 kemungkinan berjawaban negatif — lebih dari 25 tahun sebelum terbukti; layak disorot sebagai antisipasi ilmiah yang tepat | Keep: Primer |
| Teori Automata | — | 1/12 | Rendah | Konteks computability umum, tak spesifik ke PR-10 | Optional |
| Word Problem for Groups | — | 1/12 | Sedang | Problem undecidable klasik lain (dalam teori grup) — analog struktural PR-10 di cabang aljabar berbeda | Keep: Sekunder |

### B.3 Lapisan Frontier — perluasan HTP pasca-ℤ, riset 2020-an

| Topik | Tokoh Terkait | Konsensus | Relevansi | Fungsi dalam PR-10 | Rekomendasi |
|---|---|---|---|---|---|
| HTP atas Bilangan Rasional Q (masih terbuka) | Julia Robinson, Jochen Koenigsmann, Alexandra Shlapentokh, Bjorn Poonen | 11/12 | Tinggi | Perluasan terbuka paling penting dan paling lama — garis depan riset sejak 1949 (J. Robinson) hingga kini | Keep: Primer |
| Terobosan Koymans-Pagano (HTP semua ring finitely generated, 2024-2026) | Peter Koymans, Carlo Pagano | 10/12 | Tinggi | Hasil generalisasi paling signifikan pasca-1970 — inti "Frontier" siklus ini | Keep: Primer |
| Formal Verification & Automated Reasoning (Coq/Isabelle) | Dominique Larchey-Wendling, Yannick Forster, Jonathan Brossard | 7/12 | Sedang | Verifikasi/formalisasi ulang bukti klasik & kontemporer dengan alat pembuktian modern (termasuk bukti Coq terkonfirmasi asli, arXiv:2604.16477, per Laporan Naratif §5.2) | Keep: Sekunder |
| Kombinatorika Aditif & Kurva Eliptik (teknik Koymans-Pagano) | Peter Koymans, Carlo Pagano, Levent Alpöge, Manjul Bhargava, Ari Shnidman | 7/12 | Sedang | Alat teknis inti di balik terobosan 2024–2026 | Keep: Sekunder |
| Kurva Eliptik & Kriteria Poonen (descent, Pell) | Bjorn Poonen | 7/12 | Sedang | Teknik kunci untuk generalisasi HTP ke ring/field lain sejak awal 2000-an | Keep: Sekunder |
| Generalisasi HTP ke ring/field lain (pra-2020, kasus parsial) | Jan Denef, Alexandra Shlapentokh, Bjorn Poonen | 5/12 | Tinggi | Jembatan historis antara MRDP 1970 dan terobosan 2020-an — tanpa ini lompatan ke Koymans-Pagano terasa tiba-tiba | Keep: Primer |
| Bukti independen kestabilan rank (Alpöge-Bhargava-Ho-Shnidman, 2025) | Levent Alpöge, Manjul Bhargava, Wei Ho, Ari Shnidman | 3/12 | Tinggi | Hasil independen sejalan Koymans-Pagano — dua kelompok riset berbeda sampai kesimpulan serupa, memperkuat validitas terobosan 2020-an | Keep: Primer |
| Konjektur/Dugaan Mazur (closure topologis solusi atas Q) | Barry Mazur | 3/12 | Sedang | Prasyarat konjektural (masih dugaan, belum terbukti) untuk salah satu strategi menuju HTP(ℚ) — bab tetap solid tanpanya krn baru satu dari beberapa jalur yg mungkin (rubrik §1) | Keep: Sekunder |
| Grup/Teori Selmer & Descent (kurva eliptik) | — | 2/12 | Sedang | Alat teknis pendukung riset kurva eliptik 2020-an | Keep: Sekunder |
| Makalah ekspositori Koymans-Pagano (Feb 2026) | Peter Koymans, Carlo Pagano | 2/12 | Sedang | Sumber sekunder yang menjelaskan terobosan secara lebih mudah diakses — dikonfirmasi riil (arXiv:2602.04468) lewat pencarian pada jendela ini | Keep: Sekunder |
| Pendekatan Teori Iwasawa (Garcia-Fritz-Pasten dkk.) | Natalia Garcia-Fritz, Hector Pasten | 2/12 | Sedang | Jalur teknis alternatif menuju hasil ketakputusan HTP di ring tertentu (mis. ℚ(∛p, √-q)) | Keep: Sekunder |
| Konjektur Birch-Swinnerton-Dyer (BSD) | — | 3/12 | Sedang | Konjektur besar teori bilangan lain yang bersinggungan lewat kurva eliptik — bukan dependency langsung tapi sering disandingkan sebagai "tetangga" riset | Keep: Sekunder |
| Baker's theory / effective Diophantine approximation | Alan Baker | 1/12 | Sedang | Alat analitik penting untuk hasil-hasil efektivitas Diophantine yang lebih luas | Keep: Sekunder |
| Hasil terkait function fields & derajat rendah | — | 1/12 | Sedang | Hasil parsial HTP di kasus lain (medan fungsi) | Keep: Sekunder |
| Model theory & Diophantine geometry | — | 1/12 | Sedang | Kerangka teoretis pendukung riset generalisasi ke field lain — lihat juga "Teori Model" (kandidat gabung) | Keep: Sekunder |
| Mordell/Faltings theorem | Louis Mordell, Gerd Faltings | 1/12 | Sedang | Hasil besar soal finitude titik rasional pada kurva — latar penting untuk riset kurva eliptik terkait HTP | Keep: Sekunder |
| PR#10 utk Bilangan Real & Kompleks | Alfred Tarski | 1/12 | Tinggi | Kontras krusial: atas ℝ dan ℂ, masalah analog justru **decidable** (teorema Tarski–Seidenberg, eliminasi kuantifier) — diverifikasi akurat lewat pencarian pada jendela ini | Keep: Primer |
| Pendekatan Sistematis untuk Persamaan Diophantine (Grechuk) | Bogdan Grechuk | 1/12 | Rendah | Pendekatan katalogisasi/klasifikasi kontemporer, bernilai tapi tak sentral pada pertanyaan algoritma umum | Optional |
| Tate-Shafarevich (grup) | — | 1/12 | Rendah | Objek teknis kurva eliptik, relevansi tak langsung ke narasi utama PR-10 | Optional |
| Teorema Roth | Klaus Roth | 1/12 | Rendah | Teori aproksimasi Diophantine — tangensial, cabang berbeda dari pertanyaan decidability | Optional |
| Teori Bilangan Aljabar | — | 1/12 | Sedang | Alat matematis umum yang mendasari hampir seluruh riset generalisasi HTP kontemporer | Keep: Sekunder |
| Teori Model | — | 1/12 | Sedang | Kandidat gabung dengan "Model theory & Diophantine geometry" di atas | Keep: Sekunder |
| Teori Varietas Abelian | — | 1/12 | Sedang | Objek matematis lanjutan dalam riset kurva eliptik generalisasi HTP | Keep: Sekunder |
| abc conjecture | — | 1/12 | Rendah | Konjektur besar teori bilangan yang kadang disinggung dalam konteks Diophantine luas, tapi bukan dependency langsung riset HTP | Optional |

### B.4 Lapisan Refleksi — filsafat, perbandingan lintas-problem, aplikasi & konteks populer

| Topik | Tokoh Terkait | Konsensus | Relevansi | Fungsi dalam PR-10 | Rekomendasi |
|---|---|---|---|---|---|
| Problem Hilbert #2 (Konsistensi Aritmetika) -- perbandingan | Kurt Gödel | 3/12 | Sedang | Perbandingan lintas-problem: pola hasil negatif yang serupa (Gödel 1931 vs Matiyasevich 1970) | Keep: Sekunder |
| Kriptografi & Persamaan Diophantine (aplikasi) | — | 3/12 | Rendah | Aplikasi tangensial teori bilangan, tak terkait langsung pertanyaan decidability PR-10 | Optional |
| PR#10 & batas Artificial Intelligence modern | — | 3/12 | Rendah | Klaim kontemporer bernada pop-sains — rawan *overclaim* (mis. menyamakan batas AI dengan batas komputabilitas secara longgar) kalau dipakai tanpa penjelasan hati-hati | Optional ⚠ Risiko Konflasi |
| Teori Bilangan (bidang umum) | — | 3/12 | Rendah | Label generik yang tumpang-tindih dengan banyak topik lebih spesifik di tabel ini (Teori Bilangan Aljabar/Analitik/Transendental/Algoritmik/Komputasional dst.) — tak berdiri sendiri secara substantif | Optional ⚠ Cek Granularitas |
| Filosofi Matematika & Batas Formalisme | — | 2/12 | Sedang | Payung filosofis umum yang menaungi Program Hilbert & krisis fondasi | Keep: Sekunder |
| Komputasi Kuantum & implikasi bagi (un)decidability | — | 2/12 | Rendah | Secara teknis, komputasi kuantum mengubah *kompleksitas* (BQP dsb.), bukan batas *decidability* — mengklaim ia mengubah status ketakputusan PR-10 adalah kekeliruan konseptual bila tak diluruskan eksplisit | Optional ⚠ Risiko Konflasi |
| Problem Hilbert #1 (Hipotesis Kontinuum) -- perbandingan | Georg Cantor, Paul Cohen | 2/12 | Sedang | Perbandingan pola "independence/undecidability" lintas problem — kontras penting: PR-1 tak-terputuskan *dalam sistem aksioma*, PR-10 tak-terputuskan *secara algoritmik*; dua jenis "tak terputuskan" yang berbeda dan mudah tertukar | Keep: Sekunder |
| Problem Hilbert #6 (Aksiomatisasi Fisika) -- perbandingan | — | 2/12 | Sedang | Kontras eksplisit "objek dinamis" (fisika terus berkembang) vs PR-10 "objek statis" — relevan langsung untuk Bagian A soal kekhususan PR-10 | Keep: Sekunder |
| Teori Bilangan Algoritmik | — | 2/12 | Rendah | Label cabang umum, relevansi tak spesifik ke PR-10 | Optional |
| Analogi Teorema Empat Warna (Appel-Haken, 1976) | — | 1/12 | Rendah | Analogi soal bukti berbantuan-komputer — tangensial tapi valid sebagai ilustrasi metodologis | Optional |
| Analogi prinsip ketidakpastian Heisenberg | — | 1/12 | Rendah | Analogi populer lintas-domain (fisika vs matematika) yang berisiko menyesatkan jika disamakan secara literal — perlu kehati-hatian eksplisit bila dipakai | Optional ⚠ Risiko Konflasi |
| Aplikasi dalam Blockchain | — | 1/12 | Rendah | Tangensial jauh dari pertanyaan inti PR-10 — pola *scope creep* yang sama seperti dicatat pada draft Le Chat (Laporan Naratif §4.1) | Optional |
| Computer algebra & Diophantine solving | — | 1/12 | Rendah | Praktik komputasi terapan, bukan soal decidability teoretis | Optional |
| Dampak terhadap teori komputer | — | 1/12 | Rendah | Klaim umum tanpa detail spesifik yang bisa diverifikasi | Optional |
| Filsafat matematika: batas pengetahuan | — | 1/12 | Sedang | **Ditunjuk alias** dari "Filosofi Matematika & Batas Formalisme" di atas — kanonik primer tetap yang itu (Keputusan Editorial §4) | Keep: Sekunder ⚠ Cek Granularitas |
| Hubungan dengan Problem #7 (transcendence) | Alexander Gelfond | 1/12 | Rendah | Kontras kontributor teorema transendensi (dicatat di Laporan Naratif §4.1 sebagai daftar nama tangensial GPT) | Optional |
| Kriptografi Kunci Publik (RSA) | Ron Rivest, Adi Shamir, Leonard Adleman | 1/12 | Rendah | Aplikasi tangensial teori bilangan, populer tapi tak terkait langsung PR-10 | Optional |
| Kriptografi Pasca-Kuantum *(KOREKSI — sempat terlewat saat penulisan pertama, ditambahkan setelah cross-check thd file lama, lih. catatan di atas tabel)* | — | 2/12 | Rendah | Tren keamanan siber kontemporer, tangensial jauh dari pertanyaan decidability PR-10 — pola serupa "Kriptografi Pasca-Kuantum" di Laporan Naratif §4.1 soal scope creep Le Chat | Optional |
| Number theory <-> logic <-> computation | — | 1/12 | Sedang | Tema payung interdisipliner yang menangkap esensi PR-10 secara ringkas | Keep: Sekunder |
| Perdebatan filosofis Platonisme/Formalisme/Konstruktivisme | — | 1/12 | Sedang | Bingkai filsafat matematika lebih luas yang menaungi motivasi Hilbert | Keep: Sekunder |
| Polinomial penghasil bilangan prima | — | 1/12 | Rendah | Spin-off menarik dari rumus MRDP (polinomial yang himpunan nilai positifnya persis bilangan prima), tapi bukan inti argumen | Optional |
| Problem Hilbert #8 (Hipotesis Riemann) | — | 1/12 | Rendah | Perbandingan lintas-problem (kasus "masih terbuka" berbeda karakter dari PR-10) | Optional |
| Reverse Mathematics | — | 1/12 | Sedang | Program logika terkait kekuatan aksioma minimal untuk membuktikan teorema tertentu — relevan tak langsung ke kekuatan sistem yang dibutuhkan MRDP | Keep: Sekunder |
| SMT/SAT/symbolic computation | — | 1/12 | Rendah | Aplikasi komputasi modern, tangensial | Optional |
| Teorema Abel-Ruffini (analogi) | Niels Abel, Paolo Ruffini | 1/12 | Sedang | Analogi kuat & akurat: preseden "tidak ada solusi umum" jenis lain dalam matematika (persamaan derajat ≥5 lewat radikal) — pola argumen mirip PR-10 meski domain beda total | Keep: Sekunder |
| Teorema Fermat Kecil | Pierre de Fermat | 1/12 | Rendah | Teori bilangan dasar, tak langsung terkait pertanyaan algoritma umum | Optional |
| Teori Bilangan Analitik | — | 1/12 | Rendah | Cabang matematika umum, relevansi tak spesifik | Optional |
| Teori Bilangan Komputasional | — | 1/12 | Rendah | Label generik, tumpang tindih dengan topik lain yang lebih spesifik | Optional |
| Teori Bilangan Transendental | — | 1/12 | Rendah | Cabang tersendiri, tangensial ke PR-10 | Optional |
| Teori Kategori | — | 1/12 | Rendah | Tidak berkaitan langsung dengan argumen inti PR-10 di korpus manapun | Optional |
| Zero-knowledge proofs | — | 1/12 | Rendah | Aplikasi kriptografi tangensial | Optional |

**Ringkasan Bagian B (pasca-revisi editorial — lihat `PR-10_Keputusan_Editorial_W1baru.md`):** 98 topik dinilai (11 Fondasi, 32 Revolusi, 24 Frontier, 31 Refleksi). Rekomendasi dihitung ulang programatik dari rubrik mekanis (Relevansi+Konsensus → level, lihat Keputusan Editorial §2): **20 Primer**, **50 Sekunder**, **28 Optional**. "Evaluasi Ulang" tidak lagi jadi level ke-4 — dipensiunkan jadi 2 tag overlay yang menempel ke salah satu dari 3 level di atas: **5 bertanda `⚠ Cek Granularitas`** (dianggap alias/tumpang-tindih kanonik dgn topik lain: Aksioma Peano→Aritmetika Peano; Teorema DPR→Reduksi Davis-Putnam; Matiyasevich's theorem→Teorema MRDP; Filsafat matematika: batas pengetahuan→Filosofi Matematika & Batas Formalisme; Teori Bilangan bidang umum berdiri sendiri tanpa pasangan spesifik) dan **4 bertanda `⚠ Risiko Konflasi`** (valid disebut tapi rawan disalahpahami tanpa penjelasan hati-hati: P vs NP, PR-10 & AI modern, Komputasi Kuantum, analogi Heisenberg).

---

## Bagian C — Tabel Gap (digabung dgn temuan W1-lama)

Topik yang **tidak muncul sama sekali** (0/12) di superset Baseline Sintesa, tapi dinilai relevan. Per Keputusan Editorial §5, tabel ini **menggabung** temuan independen W1-baru (4 item) dan W1-lama (1 item) — bukan memilih salah satu dokumen — karena kelima-limanya sudah sama-sama diverifikasi lewat pencarian aktif di jendela masing-masing.

| Topik Penting | Ditemukan Oleh | Catatan/Alasan |
|---|---|---|
| **Aritmetika Presburger (1929) sebagai kasus kontras yang *decidable*** | **W1-baru DAN W1-lama, independen** ⭐ | Mojżesz Presburger menunjukkan (1929) bahwa teori bilangan asli dengan **hanya penjumlahan** (tanpa perkalian) bersifat decidable — kontras langsung dengan PR-10 yang melibatkan perkalian dan karenanya tak-decidable. **Konvergensi independen** dua jendela sintesa yang tak saling tahu isi satu sama lain saat proses berjalan — sinyal validasi terkuat di seluruh Bagian C ini, pola yang sama seperti kasus "Kai"/"Brossard" di Baseline Sintesa. Diverifikasi via Wikipedia dan AMS Math Grad Blog. |
| **Tesis Julia Robinson 1949** (ℤ terdefinisi *first-order* di ℚ via Hasse-Minkowski) | W1-lama | Mendahului & berbeda dari kontribusi J. Robinson yang sudah tercatat di Bagian B (Hipotesis J.R. era 1950-an) — hasil 1949 inilah alasan teknis kenapa banyak matematikawan menduga HTP(ℚ) mungkin juga undecidable, akar historis dari kontribusi Poonen & Koenigsmann yang sudah disebut Bagian B. Diverifikasi via disertasi PhD Robinson 1948 (UC Berkeley, pembimbing Tarski). |
| **Bukti sederhana Jones-Matiyasevich lewat mesin register (1984)** | W1-baru | Bukti ulang yang jauh lebih sederhana dari bukti 1970 asli, menggunakan model mesin-register untuk hasil "representasi Diophantine eksponensial untuk himpunan enumerable" — *Journal of Symbolic Logic* 49(3):818–829. Rute pedagogis yang lebih mudah diikuti, relevan utk bab yang menjelaskan *mengapa* teorema itu benar. Diverifikasi via Cambridge Core, PhilPapers, profil resmi James P. Jones (University of Calgary). |
| **Hilbert hanya membacakan 10 dari 23 problem di pidato lisan 1900 — dan PR-10 BUKAN salah satunya** | W1-baru | Dari 23 problem yang akhirnya dipublikasikan, Hilbert secara lisan di podium Sorbonne (8 Agustus 1900) hanya sempat membacakan 10 problem — nomor 1, 2, 6, 7, 8, 13, 16, 19, 21, dan 22. **PR-10 tidak termasuk yang dibacakan lisan** — ia hanya muncul di naskah cetak lengkap. Berpotensi mengoreksi kekeliruan implisit kalau ada draft yang menganggap PR-10 dibacakan langsung di podium. Diverifikasi via Wikipedia ("Hilbert's problems") dan MacTutor History of Mathematics. |
| **Booker & Sutherland (2019), penyelesaian x³+y³+z³=42** | W1-baru | Kasus populer-kontemporer sbg *contoh kontras* pedagogis: mencari solusi persamaan **spesifik** (butuh superkomputer + *Charity Engine*) adalah soal *solvability satu kasus* — beda level dari *decidability umum* yang ditanyakan PR-10. Menegaskan poin literal #1 di Bagian A dgn contoh yang mudah diakses awam. Diverifikasi via rilis pers University of Bristol dan liputan independen (ScienceDaily, Aperiodical). |

Catatan metodologis: 4 dari 5 gap ini murni hasil penjelajahan independen satu jendela saja (bukan dari korpus 12 draft AI) — wajar kalau jendela sintesa lain menemukan gap yang berbeda lagi, sesuai catatan `format-analisis-topik.md`. Presburger adalah pengecualian penting: ditemukan dua kali secara independen, jadi kandidat terkuat utk benar-benar dimasukkan ke MVC Fase 2, bukan sekadar dicatat sbg gap.

---

## Fase 1.5 — Validasi Silang thd Atlas Master v1.7 & Contoh MVC (PR-001, PR-002)

*Per `timing-atlas.md`: ini langkah validasi, bukan penyerapan diam-diam. Temuan Bagian A/B/C di atas TIDAK diubah mengikuti Atlas kecuali ada alasan eksplisit dicatat di sini.*

### A. Baris Problem Registry PR-10 vs temuan independen — COCOK

Atlas: `PR-010 | Solvability of Diophantine Equations | Cluster B, F | Terjawab negatif — Matiyasevich/MRDP (1970): tak ada algoritma umum`.

- **Status & jawaban negatif 1970** — cocok persis dgn Bagian A ("jawaban negatif dan definitif atas ℤ sejak 1970").
- **Dual cluster B (Algebra & Number Theory) + F (Computability & Algorithms)** — cocok dgn kerangka Bagian A yang menempatkan PR-10 di persimpangan teori bilangan dan logika/komputabilitas.
- **Cluster F mengelompokkan PR-10 bersama PR-2 dan PR-24** — validasi kuat utk poin independen di Bagian A §"Pola hasil negatif yang berulang" (Gödel/Entscheidungsproblem/MRDP berbagi teknik pengkodean berkerabat). **Catatan kejujuran:** MVC-PR-002 (salah satu dari 2 contoh yang direlay) sudah eksplisit menyebut kandidat "jembatan #2↔#10 lewat Entscheidungsproblem/Turing" di Bab 19-nya — dokumen itu ada di konteks jendela ini sejak awal, jadi konfirmasi ini **bukan** penemuan buta spt kasus Presburger vs W1-lama, melainkan kesesuaian dgn petunjuk yang sudah tersedia. Tetap dicatat jujur, bukan diklaim sbg independen.

**Tindak lanjut wajib Fase 2**: PR-10 punya kewajiban mengeksekusi *Named Bridge* #2↔#10 ini di Section 5 Atlas Entry-nya nanti (format sama spt jembatan #1↔#17) — sudah "dipesan" sejak PR-002 ditulis, bukan opsional.

### B. Temuan substantif: kemungkinan kesalahan klasifikasi Jenis "MRDP Theorem"

Atlas §6 mendaftar kandidat: *"MRDP Theorem (PR-010, Jenis: **Independence Result**)."* Ini layak dipertanyakan sebelum diregistrasi resmi:

- **Independence Result** (per vocab §2.3 Atlas) secara teknis berarti "terbukti tak bisa dibuktikan maupun dibantah dari sistem aksioma tertentu" — persis kasus CH (NB-RES-0004). MRDP bukan hasil semacam itu — ia adalah teorema recursion-theory yang mengkarakterisasi himpunan Diophantine = himpunan RE, dengan korolari "tak ada algoritma umum" (undecidability, bukan independence).
- **Preseden yang sudah ada di Atlas sendiri**: Teorema Ketaklengkapan Pertama & Kedua Gödel (NB-RES-0011, NB-RES-0012) — sama-sama hasil "batas/impossibility" — justru diregistrasi sbg **Theorem** biasa, bukan Independence Result. Menjadikan MRDP "Independence Result" akan **tidak konsisten** dgn preseden ini tanpa alasan struktural baru yang dicatat.
- **Rekomendasi**: saat registrasi resmi (Fase 2/3 PR-10), pertimbangkan Jenis **Theorem** utk "Teorema MRDP" (konsisten dgn preseden Ketaklengkapan) kecuali ada pertimbangan lain yang belum tercatat. Ini bukan koreksi yang saya buat sepihak — murni menandai utk didiskusikan mengikuti Prosedur Audit Registry 5-Langkah §5 (granularity/classification audit) saat siklus Fase C PR-10 berjalan.

### C. Cluster G (ekstrapolasi modern) vs rating Optional/⚠ saya — tak ada mismatch, tapi perlu nuansa

Atlas §1.3 mendaftar Cluster G (tak bernomor) — P vs NP, Proof Complexity, Quantum Computing, Cryptography, AI/ML Theory, Formal Verification — eksplisit "berakar secara tematik dari PR-002, PR-010, dan PR-024."

| Topik di Bagian B | Rating saya | Status di Cluster G |
|---|---|---|
| Teori Kompleksitas Komputasi (P vs NP) | Keep:Sekunder ⚠ Risiko Konflasi | Terdaftar tematik |
| Formal Verification & Automated Reasoning | Keep:Sekunder | Terdaftar tematik ("aktif diteliti, terkait PR-024") |
| Kriptografi & Persamaan Diophantine / RSA / Pasca-Kuantum | Optional | Terdaftar tematik ("Cryptography") |
| Komputasi Kuantum & implikasi (un)decidability | Optional ⚠ Risiko Konflasi | Terdaftar tematik |
| PR#10 & batas Artificial Intelligence modern | Optional ⚠ Risiko Konflasi | Terdaftar tematik ("AI/ML Theory") |

**Ini BUKAN mismatch yang perlu mengubah Rekomendasi** — Cluster G eksplisit ditandai Atlas sendiri sbg "ekstrapolasi modern" **tanpa satu pun entri Notebook Konsep terdaftar** ("tidak bernomor... murni ekstrapolasi"). Artinya Cluster G adalah rak taksonomi tingkat-proyek utk kemungkinan pengembangan lintas-Problem di masa depan, bukan klaim bahwa topik itu harus dielaborasi dalam bab PR-10 itu sendiri (konsisten dgn Prinsip Arsitektur #5, "Atlas Is a Map"). Formal Verification paling dekat konfirmasinya (Rekomendasi saya sudah Sekunder, sejalan). Untuk empat lainnya, rating Optional+tag kehati-hatian saya **tetap dipertahankan** — Cluster G memberi sinyal "topik ini ada tempatnya di suatu tempat dalam proyek", bukan sinyal "topik ini penting di bab PR-10".

### D. Registry yang SUDAH ada — wajib cross-reference di Fase 2, bukan bikin entri baru

Beberapa topik di Bagian B ternyata sudah py entri Confirmed dari siklus PR-002 — kalau muncul lagi di bab PR-10 nanti, ini pemakaian ke-2 (nambah `Terkait Problem`), bukan entri baru (Prinsip #1, persis pola Model Theory PR-017→PR-001→PR-002):

| Topik Bagian B | Entri Atlas yang sudah ada | Jenis |
|---|---|---|
| Aritmetika Peano / Aksioma Peano | NB-CON-0028 "Peano Arithmetic (PA)" | Framework |
| Giuseppe Peano (tokoh) | NB-PER-0026 | — |
| Nomor Gödel (Gödel numbering) | NB-CON-0029 "Gödel Numbering" | Technique |
| Kurt Gödel (tokoh, kalau disebut lagi) | NB-PER-0011 | — |

"Entscheidungsproblem" **belum** punya entri Atlas tersendiri (di PR-002 ia dibahas sbg konteks Bab 19, bukan diregistrasi) — kemungkinan jadi entri BARU genuine saat PR-10 diregistrasi, kecuali diputuskan cukup tercakup lewat entri Turing/computability yang sudah ada.

### E. Pelajaran gaya dari 2 contoh MVC (utk Fase 2 nanti — prinsip, bukan ditiru literal)

- **4 Lapisan (Fondasi/Revolusi/Frontier/Refleksi)** yang dipakai Bagian B di atas **cocok independen** dgn struktur 4-Lapisan PR-001 & PR-002 (Fondasi/Revolusi/Frontier/Refleksi) — validasi tambahan utk pilihan navigasi yang sudah dibuat sebelum contoh ini diterima.
- **Header registry per-bab**: `*Registry: NB-CON-XXXX (Status, Jenis) · ...*` langsung di bawah judul bab — format wajib dipakai konsisten Fase 2.
- **Cross-reference vs entri baru** ditulis eksplisit (`*Cross-reference: NB-CON-0004...*`) saat menggunakan ulang entri Problem lain — bukan disembunyikan.
- **Gerbang**: rantai pertanyaan berutang-piutang intelektual, TANPA jargon bernama, TANPA nama tokoh, cliffhanger di akhir tanpa menyebut nomor/nama Problem eksplisit. Satu metafora sentral konsisten (tak hingga/pendakian di PR-001; kejujuran-diri/saksi di PR-002).
- **Ritme bab**: dibuka hook historis/konteks singkat → bangun satu konsep teknis → tutup dgn kalimat yang secara genuine membuka pertanyaan bab berikutnya (bukan sekadar "selanjutnya kita akan membahas X").
- **Kehati-hatian epistemik**: catatan presisi historis ditandai eksplisit dlm kurung miring (mis. "Catatan presisi historis: versi asli Gödel 1931 mensyaratkan ω-konsisten...") — pola yang sudah konsisten dgn kehati-hatian yang saya terapkan di Bagian A/B/C dokumen ini.
- **Bukan ditiru**: judul bab spesifik, metafora sentral spesifik (tak hingga, kejujuran-diri), dan pilihan retoris tunggal PR-001/PR-002 — ini spesifik ke topik itu, PR-10 perlu metafora/framing sendiri saat Gerbang-nya ditulis di Fase 2.

### Ringkasan Fase 1.5

Tidak ada temuan yang mengharuskan revisi Rekomendasi Bagian B atau isi Bagian C saat ini. Dua hal dibawa maju sbg catatan kerja utk Fase 2: (1) usulkan Jenis "Theorem" (bukan "Independence Result") utk MRDP saat registrasi resmi, (2) eksekusi wajib Named Bridge #2↔#10 di Atlas Entry Section 5 PR-10 nanti. Siap lanjut ke Fase 2 (Draft Usulan MVC) kapan pun diarahkan.
