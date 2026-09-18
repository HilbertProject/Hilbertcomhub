# Atlas 23 Masalah Hilbert — Dokumen Master (v1.8)

> Dokumen ini menggabungkan seluruh rujukan arsitektur proyek: Status & Roadmap, Prinsip Arsitektur, Prinsip Proses, Cluster & Problem Registry, Taksonomi Proyek, dan Registry Notebook (Konsep, Hasil Besar, Tokoh). Berfungsi sebagai satu titik rujukan tunggal — sesuai Prinsip #1 di bawah — supaya tidak ada dua dokumen terpisah yang bisa saling menyimpang.
>
> **Status:** Fase A selesai (**Architecture Freeze**). PR-001 dan PR-002 tuntas penuh sebagai pilot Cluster A — Gerbang, Jalur Eksplorasi, Notebook, dan Atlas Entry semuanya selesai untuk keduanya. Living document, akan diperluas seiring Relay berikutnya.
>
> **Cara membaca proyek ini:** Atlas bukan sekadar buku, melainkan satu *view* dari sebuah knowledge graph. Node-nya adalah tiga jenis Notebook (Konsep, Hasil Besar, Tokoh); Cluster, Problem, dan Timeline adalah cara berbeda untuk menavigasi node-node yang sama.

---

## Riwayat Versi

Versi naik **hanya** saat ada perubahan struktural nyata — definisi yang sama persis dengan "kegagalan nyata saat implementasi" di Prinsip Proses. Menambah entri registry baru lewat siklus rutin Draft→Confirmed **tidak** menaikkan versi (itu urusan Roadmap & registry, bukan arsitektur) — kalau dihitung, nomor versi akan naik puluhan kali per Problem dan kehilangan makna.

| Versi | Pemicu |
|---|---|
| v1.0 | Fase A — Architecture Freeze: 6 Prinsip Arsitektur, Cluster & Problem Registry, Taksonomi dasar, Registry Notebook terisi contoh dari PR-017 |
| v1.1 | Paket perubahan struktural dari review pasca-freeze + pilot PR-001: node Gerbang (Level 0) & pensiun Peta Alur; Atlas Entry eksplisit di taksonomi dan jadi penutup wajib Fase C; siklus B→C→D didefinisikan ulang sebagai satu siklus per-Problem (bukan sekuensial 23 Problem); konvensi Era-rentang; Jenis "Axiom" (informal, belum resmi di vocab §2.2); pola induk/anak untuk hasil gabungan (NB-RES-0004/0004a/0004b); reklasifikasi Large Cardinals Object→Field; ambang masuk Notebook Tokoh (nama+kontribusi+tahun); Prosedur Audit Registry 5-Langkah |
| v1.2 | Atlas Entry PR-001 ditulis, memicu satu perbaikan struktural: **Legenda Diagram Genealogi** (§2.7) dipusatkan sebagai rujukan tunggal dengan 2 simbol baru (○ Objek, ↻ Teknik) — sebelumnya legenda didefinisikan inline per Atlas Entry, dan PR-017 kebetulan tidak pernah butuh simbol untuk Jenis Object/Technique sehingga gap-nya baru kelihatan di Problem kedua |
| v1.3 | Verifikasi silang lintas-sesi menemukan dua utang provenance lama: (1) judul §2.7 diperbaiki jadi "Legenda Diagram **Pohon Evolusi Konsep**" (nama resmi template, bukan "Genealogi Ide"); (2) **§2.8 Legenda Status** baru — meresmikan ✅/⊘ (masing-masing teruji di PR-017/PR-001) sebagai vocab Section 1 Atlas Entry, dengan ❌/⚠/↺ dari genesis proyek yang sama ditahan sebagai kandidat sampai ada Problem yang benar-benar mengeksekusinya |
| v1.4 | Siklus penuh PR-002 (pilot kedua, Cluster A): **Audit Jahitan Bab** baru di Prinsip Proses (dua sisi jahitan tiap transisi bab — forward/backward/synthesis); **§2.3** diformalkan (pola induk/anak hanya untuk klaim emergent, bukan otomatis tiap dua hasil dari paper yang sama); **§2.6** dapat aturan keempat (konvensi cliffhanger Gerbang, diuji 2× PR-001/PR-002); **§2.8** meresmikan **⚠** (titik data kedua, dari PR-002) — tersisa ❌/↺ sebagai kandidat |
| v1.5 | **Koreksi terhadap v1.4**, ditemukan lewat verifikasi silang Atlas Entry PR-002: formalisasi ⚠ **dibatalkan** — PR-002 ternyata data point ambigu (tiga pembacaan sama masuk akal: ⚠/↺/✅-dengan-catatan), bukan titik data bersih seperti ⊘ dari PR-001. §2.8 dikembalikan ke ✅/⊘ saja; PR-006 dicatat sebagai kandidat data pembanding yang lebih jernih untuk ⚠. Juga memperbaiki kesalahan kategori di Atlas Entry PR-002 §8 (klaim "revelasi batas sistem formal" 1940 keliru — L Gödel hasil positif satu-arah, bukan revelasi batas; paralel yang benar untuk Problem #1 baru lengkap 1963 via Cohen) |
| v1.6 | Dua hal dari audit sinkronisasi lanjutan + pelajaran proses PR-002: (1) **celah dokumentasi §2.7 ditambal** — cakupan ⬢ (Metode/Aplikasi) sudah ada sejak v1.2 tapi tidak pernah dijelaskan di Catatan asal, ditambal retroaktif; (2) **Audit Jahitan Bab dapat 4 penajaman** dari pengalaman lanjutan PR-002: epistemik vs naratif, penyisipan bab = jahitan baru, konvergensi independen ≠ pengulangan relay, uji kandidat bab disederhanakan jadi satu pertanyaan. Protokol MVC 25-section yang diusulkan pihak eksternal (GPT) ditinjau dan **ditolak** — melanggar Prinsip Proses-nya sendiri (membangun aparatus besar dari 2 data point) dan membalik urutan yang sudah terbukti (outline dibekukan sebelum prosa, bukan prosa duluan) |
| v1.7 | Dua gap kecil ditemukan lewat **audit sinkronisasi Master↔Draft** (jendela ketiga, insidental — bukan langkah wajib tiap siklus): (1) Era NB-PER-0024/0025 (Paris, Harrington) diperbaiki dari "Contemporary" tunggal jadi "Modern → Contemporary" — kontribusi terdaftar (1977) jatuh di Modern per §2.4, format rentang wajib begitu karier melampaui era itu, konsisten preseden Hilbert/Krivine/Cohen; (2) cross-reference NB-RES-0007 (Paradoks Russell) diperbarui `+= PR-002` — permintaan eksplisit di Draft PR-002 sempat tereksekusi cuma separuh (NB-PER-0016 terupdate, NB-RES-0007 terlewat) |
| v1.8 | Dua broken cross-reference ditambal, ditemukan lewat audit lintas-jendela (siklus revisi skill pendamping, insidental — bukan langkah wajib siklus): (1) **Ambang masuk Notebook Tokoh** — teks definisi resmi sejak v1.1, dipakai operasional dengan benar (Fraenkel/Skolem lolos meski tanpa bab sendiri; Kunen/Silver/Dodd-Jensen/Mitchell ditahan karena tahun cuma perkiraan), tapi tak pernah dieksekusi ke badan §2.4 — cuma dua rujukan balik (Prosedur Audit Langkah 3, Catatan Terbuka) yang mengasumsikan definisinya ada di sana. Dikonfirmasi lewat tiga jalur independen (pembacaan langsung arsip relay lama, ingatan struktural jendela terpisah, verifikasi file + penelusuran changelog v1.1) sebelum dipulihkan. Kebalikan tepat dari pola insiden ⬢ (v1.6): di situ perubahan terjadi tapi tak tercatat; di sini tercatat rapi di changelog tapi teksnya sendiri tak pernah ditulis ke tempat yang dirujuk. (2) **Timeline "(Level 4, lihat Relay 1)"** — sitasi genesis, bukan drift antar-versi kami: ditelusuri sampai diagram hierarki 5-tingkat dari sesi arsitektur pra-v1.0 bersama GPT (Atlas→Dossier→Notebook Konsep→Notebook Tokoh→Timeline Sejarah, Timeline di kedalaman ke-4 dihitung dari Atlas sebagai akar). "Relay 1" bukan nama dokumen formal — istilah kerja deiktik GPT untuk "putaran pertama" sesi itu, disisipkan sbg catatan-pengingat-untuk-diri-sendiri saat menulis draft revisi, lalu ikut membeku jadi sitasi permanen begitu draft itu diadopsi jadi dokumen genesis berdiri sendiri. Kategori kegagalan cross-reference ketiga, berbeda dari (1) dan dari insiden ⬢: *istilah kerja sesi yang valid cuma dalam konteks percakapan aslinya, ikut membeku jadi sitasi permanen tanpa konteksnya*. Skema Level 0–4 diformalkan eksplisit di §2.1 (menyambung "Gerbang = Level 0" yang sudah resmi sejak v1.1); sitasi di §2.4 diarahkan ulang ke §2.1, bukan ke dokumen luar yang tak tertelusuri |

Versi berikutnya (v1.2, v1.3, ...) dicatat di baris baru tiap kali ada perubahan struktural yang lolos syarat Prinsip Proses — bukan diputuskan sebelumnya.

---

## Status Proyek & Roadmap

**Fase A — Arsitektur: ✅ Architecture Freeze**

Enam Prinsip Arsitektur, Cluster, Problem Registry, Taksonomi, dan tiga Registry Notebook sudah cukup stabil untuk jadi fondasi. Ini bukan klaim "sempurna selamanya" — ini klaim "cukup stabil untuk mulai dipakai". Perubahan struktural berikutnya tunduk pada Prinsip Proses di bawah, bukan lagi soal selera desain.

| Fase | Isi | Status |
|---|---|---|
| A — Arsitektur | Prinsip, Cluster, Registry, Taksonomi, Decision Log | ✅ Selesai — *Architecture Freeze* |
| B — Data Layer | Mengisi node & edge untuk Problem (belum ada narasi); entri baru berstatus `Draft` (lihat 2.5) | ✅ PR-001, PR-002 selesai |
| C — Jalur Eksplorasi | Menulis narasi penuh per Problem (Gerbang → Bab-bab) **ditutup dengan Atlas Entry 8-section**; entri `Draft` naik status jadi `Confirmed` di sepanjang jalan | ✅ PR-001, PR-002 selesai — Gerbang, bab, Atlas Entry |
| D — Notebook | Memperdalam Notebook Konsep/Hasil Besar/Tokoh dari akumulasi Jalur Eksplorasi | ✅ PR-001, PR-002 selesai — lihat Bagian 3–5 |
| E — Atlas Final | Atlas jadi pintu masuk; Notebook jadi ensiklopedia; Timeline jadi sejarah | Menunggu — baru 2 dari 23 Problem selesai |

**Catatan skop — B, C, dan D bukan tiga fase berurutan yang masing-masing menuntaskan seluruh 23 Problem sebelum lanjut ke fase berikutnya.** Ketiganya membentuk **satu siklus per Problem**. Siklus itu pertama kali dijalankan penuh di PR-001 sebagai *stress test* arsitektur. Begitu siklus PR-001 selesai dan tidak ditemukan kegagalan arsitektur (lihat Prinsip Proses), siklus yang sama direplikasi ke Problem berikutnya — mengikuti urutan Cluster (Cluster A dulu, lalu B, dst.), bukan urutan nomor PR. Alasannya dua: efisiensi penulisan (konsep-konsep dalam satu cluster saling membangun), dan kemungkinan rilis nanti berbentuk **volume per Cluster**, bukan satu buku 23-Problem yang membengkak — buku akhirnya tetap tersusun per nomor Hilbert (lihat keputusan "Nomor jadi struktur utama, Cluster jadi struktur editorial"), tapi proses penulisan dan kemasan rilis mengikuti Cluster. Fase E baru dimulai setelah seluruh 23 Problem (atau jumlah representatif yang disepakati di kemudian hari) menyelesaikan siklusnya masing-masing.

**Hasil pilot PR-001:** siklus selesai tanpa kegagalan arsitektur fatal — tiga penyesuaian granularitas ditemukan (AC, NB-RES-0004, Large Cardinals) dan semuanya tertampung oleh Prinsip Proses tanpa perlu mendesain ulang taksonomi. Prosedur Audit Registry 5-Langkah (lihat Prinsip Proses) lahir dari pilot ini dan sekarang jadi bagian tetap siklus.

**Hasil pilot PR-002 (proses kolaborasi 3-arah: GPT + dua sesi Claude independen):** registry datang "pre-stress-tested" — nol tegangan klasifikasi Jenis (beda dari AC/Large Cardilas di PR-001), karena proses collision menguji struktur *sebelum* narasi final ditulis, bukan lewat narasi itu sendiri. Tiga seam bab butuh patch (ditemukan lewat **Audit Jahitan Bab**, metode baru yang lahir dari pilot ini — lihat Prinsip Proses). Status Atlas Entry PR-002 sempat memicu percobaan formalisasi ⚠ di §2.8, tapi **dibatalkan** setelah verifikasi silang menemukan PR-002 data point yang ambigu (lihat §2.8 dan catatan v1.5) — PR-002 memakai ✅-dengan-catatan sebagai gantinya.

**Celah yang sebelumnya ditemukan lewat cross-check, sekarang ditutup:** definisi Fase B/C/D sebelumnya tidak pernah menugaskan secara eksplisit *kapan* Atlas Entry (8-section) ditulis untuk sebuah Problem — deskripsi lama cuma bicara Data Layer, narasi, dan Notebook. Sekarang diperjelas: Atlas Entry ditulis sebagai **penutup** Fase C per-Problem (sesudah narasi lengkap, supaya ringkasannya akurat merefleksikan hasil akhir). Atlas Entry PR-001 dan PR-002 sudah ditulis, memakai template resmi Problem #17.

PR-001 dan PR-002 sekarang tuntas penuh. Berikutnya: replikasi siklus B→C→D ke Problem terakhir Cluster A (PR-006).

---

## Prinsip Arsitektur

Aturan yang tidak boleh dilanggar selama proyek berkembang — "konstitusi teknis" proyek. Mengatur **bagaimana pengetahuan disusun**.

1. **Single Source of Truth** — setiap pengetahuan memiliki satu rumah utama.
2. **Concepts Before People** — struktur dibangun di atas konsep; tokoh adalah anotasi historis (karena itu Notebook Tokoh dibiarkan flat, tanpa rak Cluster — lihat 2.4).
3. **Named Bridges Only** — hubungan antar-problem hanya dibuat melalui teorema, metode, atau objek matematika yang bernama.
4. **One Primary Home** — setiap notebook memiliki satu rak utama; keterkaitan lintas-cluster dicatat sebagai metadata, bukan duplikasi.
5. **Atlas Is a Map** — Atlas hanya merangkum dan menunjuk; pembahasan mendalam berada di Jalur Eksplorasi dan Notebook.
6. **Results Are Not Concepts** — konsep menjelaskan cara berpikir (alat, objek, metode, teori, bidang), sedangkan hasil menjelaskan apa yang telah dicapai (teorema, lemma, kontraeksempel, konstruksi, klasifikasi, atau algoritma penting, termasuk hasil independensi). Keduanya memiliki rumah berbeda — Notebook Konsep dan Notebook Hasil Besar — dan tidak boleh diduplikasi.

---

## Prinsip Proses (Kebijakan Perubahan)

Berbeda dari Prinsip Arsitektur di atas — ini mengatur **kapan aturan penyusunan itu sendiri boleh berubah**, bukan bagaimana pengetahuan disusun.

> **Tidak ada perubahan arsitektur tanpa ditemukan kegagalan nyata saat implementasi.**

Setelah Fase A dibekukan, struktur tidak diubah hanya karena muncul ide yang terasa lebih elegan. Perubahan hanya dilakukan jika, saat mengisi registry atau menulis Jalur Eksplorasi, ditemukan kasus nyata yang benar-benar tidak bisa ditampung oleh arsitektur sekarang.

### Prosedur Audit Registry (5 Langkah)

Dijalankan setiap kali satu Problem menyelesaikan seluruh siklus Jalur Eksplorasi-nya (lahir dari pengalaman pilot PR-001, yang menemukan beberapa node terlewat lewat cara ini):

1. **Concept audit** — adakah konsep yang disebut naratif tapi belum diregistrasi, atau salah Jenis?
2. **Result audit** — adakah teorema, kontraeksempel, atau hasil independensi yang lolos tak tercatat?
3. **Person audit** — adakah tokoh yang memenuhi ambang masuk (nama + kontribusi spesifik + tahun — lihat 2.4) tapi belum tercatat?
4. **Cross-reference audit** — apakah entri lama yang dipakai ulang sudah diperbarui kolom `Terkait Problem`-nya (bukan diduplikasi jadi entri baru)?
5. **Granularity audit** — adakah node yang ternyata terlalu besar (payung yang menaungi banyak instance konkret) atau terlalu kecil (dua pencapaian berbeda dipaksa satu entri)?

### Audit Jahitan Bab (Seam Audit)

Dijalankan di **Fase C**, sebelum Prosedur Audit Registry (Fase D) — lahir dari pilot PR-002, terbukti dua kali menangkap sesuatu yang audit lain lewatkan (termasuk gap nyata di seam Bab 16→17 akibat penyisipan bab belakangan). Untuk tiap pasangan bab N→N+1, periksa **dua sisi jahitan** (penutup N *dan* pembuka N+1 — bukan cuma salah satu), lalu klasifikasikan:

- **Pola A (Forward)** — penutup N bertanya eksplisit, dijawab pembuka N+1.
- **Pola B (Backward)** — penutup N netral/deklaratif, pembuka N+1 menoleh balik ke N.
- **Pola C (Synthesis)** — pembuka N+1 mensintesis beberapa bab sebelumnya sekaligus, menutup satu sub-arc (bukan mewarisi satu bab tunggal).

Seam yang tidak cocok pola manapun di kedua sisi adalah kandidat patch. Prioritaskan audit penuh (Tier A) untuk seam antar-lapisan dan seam di sekitar bab yang disisipkan belakangan; seam yang sudah jelas secara epistemik atau murni dramaturgis cukup sanity-check cepat (Tier B/C) — bukan ritual penuh untuk semua N→N+1.

**Empat penajaman (v1.6, dari pengalaman lanjutan PR-002):**

1. **Epistemik vs naratif** — seam yang berfungsi dramaturgis/historis itu sah, tidak perlu dipaksa jadi dependency epistemik palsu (contoh: Bab 7→8 PR-002, Completeness→Königsberg).
2. **Penyisipan = jahitan baru** — bab yang disisipkan di antara A dan B membuat seam A→baru dan baru→B otomatis belum teruji, terlepas kekuatan A→B sebelumnya (contoh: Bab 16→17 PR-002).
3. **Konvergensi independen ≠ pengulangan relay** — hitung "suara" yang sepakat hanya kalau genuinely diturunkan independen; relay/laporan tanpa verifikasi sendiri bukan suara tambahan (contoh: kekeliruan status "konvergensi" Cut-Elimination PR-002).
4. **Uji kandidat bab** — satu pertanyaan: jika bab ini dihapus, apa yang hilang dari perjalanan pembaca? Kalau jawabannya "cuma konteks/sejarah", itu bukan bab, itu paragraf konteks di bab lain (contoh: Principia PR-002).

---

## Daftar Isi

1. [Cluster & Problem Registry](#1-cluster--problem-registry)
2. [Taksonomi Proyek](#2-taksonomi-proyek)
3. [Registry — Notebook Konsep](#3-registry--notebook-konsep)
4. [Registry — Notebook Hasil Besar](#4-registry--notebook-hasil-besar)
5. [Registry — Notebook Tokoh](#5-registry--notebook-tokoh)
6. [Catatan Terbuka](#6-catatan-terbuka)

---

## 1. Cluster & Problem Registry

### 1.1 Daftar Cluster

| CL-ID | Nama | Anggota (No. Problem) |
|---|---|---|
| **CL-A** | Foundations, Logic & Set Theory | 1, 2, 6 |
| **CL-B** | Algebra & Number Theory | 7, 8, 9, 10, 11, 12, 14, 17 |
| **CL-C** | Geometry & Topology | 3, 4, 5, 15, 16, 18, 22 |
| **CL-D** | Analysis | 13, 19, 20, 21, 23 |
| **CL-E** | Mathematical Physics | 6, 19, 20, 23 |
| **CL-F** | Computability & Algorithms | 10, 2, 24 |
| **CL-G** | Complexity, Information & Computation | *(tidak bernomor — lihat 1.3)* |

**Soal ID formal:** `CL-A`…`CL-G` adalah ID resmi Cluster untuk keperluan lintas-sistem (Obsidian graph, database, dsb). Di seluruh dokumen ini, huruf polos (A, B, C, …) tetap dipakai sebagai singkatan pada tabel dan catatan lain — persis seperti "Problem #17" dipakai sebagai singkatan dari `PR-017`. Kemunculan lama tidak diganti satu-satu karena itu cuma menambah kebisingan tanpa menambah informasi.

**Catatan:** beberapa problem tergabung di lebih dari satu cluster (misalnya #6 masuk A dan E; #10 masuk B dan F; #19, #20, #23 masuk D dan E). Ini mencerminkan sifat interdisipliner masalah tersebut, bukan kesalahan penomoran.

### 1.2 Problem Registry — Tabel Referensi Lengkap

Setiap Problem sekarang punya ID resmi (`PR-XXX`), bukan hanya "Problem 1". Nomor lama tetap dipertahankan di kolom **No** untuk kemudahan baca.

| PR-ID | No | Judul Asli (Ringkas) | Cluster | Status Penyelesaian |
|----|----|----|----|----|
| PR-001 | 1 | Continuum Hypothesis | A | Terbukti *independent* dari ZFC — Gödel (1940), Cohen (1963) |
| PR-002 | 2 | Consistency of Arithmetic | A, F | Diperumit oleh Teorema Ketaklengkapan Gödel (1931); bukti konsistensi relatif oleh Gentzen (1936) di luar sistem itu sendiri |
| PR-003 | 3 | Equality of Volumes of Tetrahedra (Dehn's Problem) | C | Terpecahkan — Dehn (1900/1901), masalah Hilbert pertama yang selesai |
| PR-004 | 4 | Straight Line as Shortest Distance (Foundations of Geometry) | C | Dianggap terlalu terbuka/kabur untuk diselesaikan secara definitif |
| PR-005 | 5 | Lie Groups tanpa Asumsi Diferensiabilitas | C | Terpecahkan — Gleason, Montgomery & Zippin (1950-an) |
| PR-006 | 6 | Mathematical Treatment of the Axioms of Physics | A, E | Sebagian — aksiomatisasi probabilitas selesai (Kolmogorov, 1933); derivasi atomistik→fluida selesai untuk kasus bola-keras (Deng–Hani–Ma, 2024–2025; Fields Medal 2026), cakupan generalitas penuh masih diperdebatkan (kritik "Dilute-to-Dense Paradox"); aksiomatisasi QFT masih berlangsung |
| PR-007 | 7 | Irrationality & Transcendence of Certain Numbers | B | Terpecahkan — Teorema Gelfond–Schneider (1934) |
| PR-008 | 8 | Problem of Prime Numbers (RH, Goldbach, Twin Primes) | B | Terbuka — Riemann Hypothesis, Goldbach, dan bilangan prima kembar semuanya belum terpecahkan |
| PR-009 | 9 | General Reciprocity Law | B | Sebagian besar terpecahkan — Hukum Timbal-Balik Artin (1927) |
| PR-010 | 10 | Solvability of Diophantine Equations | B, F | Terjawab negatif — Matiyasevich/MRDP (1970): tak ada algoritma umum |
| PR-011 | 11 | Quadratic Forms with Algebraic Coefficients | B | Sebagian besar terpecahkan — teori Hasse–Minkowski |
| PR-012 | 12 | Extension of Kronecker's Theorem | B | Masih terbuka secara umum; kasus khusus (lapangan CM) sudah terpecahkan |
| PR-013 | 13 | 7th Degree Equations via Functions of Two Variables | D | Terpecahkan (berlawanan dugaan Hilbert) — Kolmogorov–Arnold (1957) |
| PR-014 | 14 | Finiteness of Invariant Rings | B | Terjawab negatif — kontraeksempel Nagata (1959) |
| PR-015 | 15 | Rigor for Schubert's Enumerative Calculus | C | Sebagian besar terpecahkan — teori interseksi modern (Fulton, 1984) |
| PR-016 | 16 | Topology of Algebraic Curves & Limit Cycles | C | Sebagian besar masih terbuka |
| PR-017 | 17 | Definite Forms as Sums of Squares | B | Terpecahkan — Artin (1927), fondasi *real algebraic geometry* |
| PR-018 | 18 | Space-Filling by Congruent Polyhedra (termasuk Kepler Conjecture) | C | Terpecahkan — Kepler Conjecture oleh Hales (1998; diverifikasi formal 2014) |
| PR-019 | 19 | Analyticity of Solutions in Calculus of Variations | D, E | Terpecahkan — De Giorgi (1957) & Nash (1958) |
| PR-020 | 20 | General Problem of Boundary Values | D, E | Sebagian besar terpecahkan — metode langsung dalam kalkulus variasi |
| PR-021 | 21 | ODEs with Prescribed Monodromy (Riemann–Hilbert) | D | Terpecahkan dengan catatan — Plemelj (1908); kontraeksempel Bolibrukh (1989) |
| PR-022 | 22 | Uniformization of Analytic Relations | C | Terpecahkan — Koebe & Poincaré (1907) |
| PR-023 | 23 | Further Development of Calculus of Variations | D, E | Program riset terbuka, bukan satu pertanyaan tunggal |
| PR-024* | 24 | Criteria of Simplicity of Proofs | F | Terbuka — ditemukan Thiele (2000/2003) dari catatan pribadi Hilbert; cikal-bakal *proof complexity* |

*\*PR-024 bukan bagian resmi dari 23 Masalah Hilbert 1900 — dimasukkan sebagai catatan sejarah, bukan status setara.*

**Soal field "Keluarga":** semua PR-001–PR-023 berkeluarga *Hilbert (1900)*; PR-024 berkeluarga *Hilbert (tidak resmi)*. Kolom Keluarga sengaja **belum** ditambahkan sebagai kolom permanen — karena baru ada satu nilai, menambah kolom sekarang cuma menambah kebisingan tabel. Begitu daftar kedua benar-benar masuk sistem (mis. Millennium Problems, Smale Problems), kolom Keluarga baru diaktifkan dan skema ID `PR-XXX` tetap dipakai — cukup rentang nomor atau prefiks baru ditentukan saat itu terjadi.

### 1.3 Cluster G — Complexity, Information & Computation

Tidak bernomor. Bukan bagian dari daftar Hilbert 1900 — murni ekstrapolasi modern yang berakar secara tematik dari PR-002, PR-010, dan PR-024.

- **P vs NP** — terbuka, salah satu Clay Millennium Prize Problems
- **Proof Complexity** — berakar dari PR-024, aktif diteliti
- **Quantum Computing** — bidang aktif, banyak sub-masalah terbuka
- **Cryptography** — terus berkembang (mis. keamanan pasca-kuantum)
- **AI / Machine Learning Theory** — banyak pertanyaan terbuka soal generalisasi & fondasi teoretis
- **Formal Verification** — aktif diteliti, terkait langsung ke PR-024

---

## 2. Taksonomi Proyek

### 2.1 Struktur Utama Atlas

```text
Atlas 23 Masalah Hilbert
│
├── Problem (Problem Registry, ID: PR-001–PR-023, + PR-024 catatan sejarah)
│      │
│      ├── Gerbang (ad hoc, Level 0) → pemantik rasa ingin tahu sebelum Atlas Entry; tidak wajib semua Problem; ID: GB-PR-XXX (lihat 2.6)
│      ├── Atlas Entry (8-section) → ringkasan resmi satu halaman, format identik tiap Problem; lihat dokumen contoh Problem #17 sebagai template
│      ├── Jalur Eksplorasi        → satu dokumen naratif per Problem
│      ├── Notebook Konsep         → rujukan ke Registry NB-CON (banyak-ke-banyak)
│      ├── Notebook Hasil Besar    → rujukan ke Registry NB-RES (banyak-ke-banyak)
│      ├── Notebook Tokoh          → rujukan ke Registry NB-PER (banyak-ke-banyak)
│      ├── Timeline                → entri kronologi terkait Problem ini
│      └── Referensi               → sumber akademik
│
├── Cluster (CL-A—CL-G)             → pengelompokan tematik lintas-Problem (lihat Bagian 1)
│
├── Notebook Konsep                 → rak = Cluster; alat/objek/bidang yang dipakai berulang
├── Notebook Hasil Besar            → rak = Cluster; teorema/hasil bernama, dicapai sekali
└── Notebook Tokoh                  → flat + tag Era; anotasi historis (Prinsip #2)
```

**Skema kedalaman Level 0–4** (v1.8 — dipulihkan dari sesi arsitektur pra-v1.0 bersama GPT, lihat Riwayat Versi): Level 0 = Gerbang, Level 1 = Atlas Entry (8-section), Level 2 = Jalur Eksplorasi (naratif per-bab), Level 3 = Notebook (Konsep/Hasil Besar/Tokoh, digabung satu tingkat), Level 4 = Timeline (sintesis otomatis dari Era+tahun Notebook Tokoh — lihat 2.4). Referensi berada di luar skema kedalaman ini — murni daftar sumber, bukan lapisan penyajian bertingkat.

### 2.2 Notebook Konsep — rak mengikuti Cluster A–G

Prinsip: **Cluster bukan sekadar label Problem, tapi juga rak resmi Notebook Konsep** (Prinsip #4). Setiap entri juga diberi **Jenis**, untuk memperkuat pencarian lintas-rak (mis. "tampilkan semua Method"):

```text
Theory · Technique · Object · Method · Framework · Field
```

Catatan: `Theorem` sengaja **tidak** ada di vocab ini — hasil bernama punya rumah sendiri di Notebook Hasil Besar (Prinsip #6, lihat 2.3).

Sebagian konsep secara alami berbatasan dengan lebih dari satu Cluster (persis seperti PR-006, PR-010, PR-019, PR-020, PR-023 di Bagian 1.1). Aturannya sama seperti Problem: **satu konsep, satu rak utama**, cluster lain dicatat sebagai "terkait" di kolom catatan — tidak menduplikasi entri.

### 2.3 Notebook Hasil Besar — teorema & hasil bernama

Rak yang sama (Cluster A–G) dipakai untuk konsistensi, tapi isinya berbeda jenis: bukan alat yang dipakai berulang, melainkan **pencapaian tunggal** — teorema, kontraeksempel, hasil independensi, dsb.

```text
Theorem · Lemma · Counterexample · Independence Result · Construction · Classification · Algorithm
```

Ini persis pembedaan ◆ (Teori/Kerangka) vs ● (Teorema/Hasil Utama) yang sudah ada di legenda pohon evolusi Problem #17 — dokumen ini hanya meresmikannya jadi dua registry terpisah.

**Pola induk/anak** (satu entri sintesis + entri anak per kontribusi) dipakai **hanya** ketika kombinasi dua atau lebih hasil melahirkan klaim baru yang *emergent* — tidak hidup penuh pada salah satu cabang saja jika berdiri sendiri. Diuji dan dikonfirmasi lewat dua kasus kontras:

- **Dipakai** — Independensi CH (NB-RES-0004, induk) dari NB-RES-0004a (Gödel, konsistensi relatif CH) + NB-RES-0004b (Cohen, konsistensi relatif ¬CH). "CH independen dari ZFC" baru benar begitu kedua arah digabung — tidak hidup penuh di salah satu cabang saja.
- **Tidak dipakai** — Teorema Ketaklengkapan Pertama dan Kedua (NB-RES-0011, NB-RES-0012, PR-002). Second dibangun langsung di atas First (kertas sama, 1931), tapi masing-masing pencapaian utuh berdiri sendiri — tidak melahirkan klaim ketiga yang emergent. Keduanya tetap dua entri terpisah tanpa induk.

---

### 2.4 Notebook Tokoh — flat, tanpa hierarki Cluster

Sesuai Prinsip #2 (*Concepts Before People*), tokoh tidak dipaksa masuk satu Cluster karena banyak tokoh berkontribusi lintas bidang (mis. Tarski: logika sekaligus aljabar). Setiap entri tokoh diberi dua tag metadata pencarian (bukan rak):

- **Cluster Terkait** — bidang kontribusinya
- **Era** — `Classical` (aktif sebelum ~1900), `Modern` (~1900–1980), `Contemporary` (setelah 1980)

**Ambang masuk registry** (resmi sejak v1.1, teks dipulihkan v1.8 — lihat Riwayat Versi): seorang tokoh layak diregistrasi hanya jika memenuhi nama + kontribusi spesifik + tahun — atau terikat langsung ke satu entri Notebook Hasil Besar yang datanya sudah lengkap — bukan sekadar "disebut" dalam narasi, dan bukan pula "mendapat bab/paragraf berdiri sendiri" (standar yang terbukti keliru saat diuji: Fraenkel dan Skolem lolos ambang ini meski tidak punya bab sendiri, sementara nama dengan tahun cuma perkiraan kasar — Kunen, Silver, Dodd–Jensen, Mitchell — ditahan sebagai kandidat di Catatan Terbuka, bukan langsung diregistrasi).

Era bukan sekadar gaya — begitu cukup banyak entri terisi, Timeline (Level 4, lihat §2.1) bisa mulai disusun otomatis dari kombinasi Era + tahun kontribusi, bukan ditulis manual dari nol.

**Konvensi Era rentang:** untuk tokoh yang karier aktifnya benar-benar melintasi batas dua Era (bukan cuma satu kontribusi bertahun tunggal), Era boleh ditulis sebagai rentang, mis. `Classical → Modern`. Nilai pertama menandai Era saat tokoh mulai dikenal/berkontribusi; tanda panah menunjukkan kariernya berlanjut ke Era berikutnya. Ini dipakai secukupnya — kebanyakan tokoh cukup satu nilai Era tunggal.

```text
Notebook Tokoh (flat)
│
├── NB-PER-0001 ...
├── NB-PER-0002 ...
└── ...
```

### 2.5 Status Entri: Draft vs Confirmed

Setiap entri di ketiga registry (Konsep, Hasil Besar, Tokoh) punya field **Status**:

- **`Confirmed`** — lahir dari narasi Jalur Eksplorasi penuh (seperti seluruh entri Problem #17 di dokumen ini). Klasifikasi Cluster dan Jenis sudah teruji lewat konteks nyata.
- **`Draft`** — baru terdaftar sebagai node dari daftar istilah (Fase B, sebelum narasi ditulis). Klasifikasi Cluster/Jenis adalah tebakan terbaik, belum diuji.

Alasan field ini ada: registry Problem #17 di bawah berhasil menangkap bahwa Positivstellensatz bukan konsep melainkan hasil (Prinsip #6) — dan itu ketahuan justru karena dikerjakan lewat narasi penuh, bukan lewat daftar nama telanjang. Fase B akan mengisi banyak entri dari daftar nama telanjang (mis. daftar Notebook untuk PR-001), sehingga kesalahan klasifikasi serupa kemungkinan terjadi lagi di sana. Status `Draft` membuat itu aman: entri tetap segera bisa dipakai untuk cross-reference, tapi ditandai jelas belum tervalidasi, dan wajib ditinjau ulang saat Jalur Eksplorasi problem terkait ditulis (naik status ke `Confirmed`).

### 2.6 Gerbang — pemantik sebelum Jalur Eksplorasi

Gerbang adalah node **Level 0** — altitude paling lunak dalam taksonomi, hidup sebelum Atlas Entry. Fungsinya tunggal: membangkitkan kebutuhan epistemik pembaca lewat rantai pertanyaan, di mana setiap paragraf meninggalkan "utang intelektual" yang dibayar paragraf berikutnya, sampai berujung pada pertanyaan asli Problem tersebut.

Tiga aturan yang membedakan Gerbang dari Jalur Eksplorasi:

- **Tanpa jargon, tanpa registry** — Gerbang tidak menyebut istilah teknis bernama (mis. "ZF", "AC", "model" diganti frasa generik seperti "sistem aksioma", "dunia matematika") dan tidak menunjuk NB-CON/NB-RES/NB-PER manapun.
- **Presisi historis boleh disederhanakan** — detail seperti tahun ganda sebuah pembuktian tetap jadi tanggung jawab Jalur Eksplorasi, bukan Gerbang.
- **Tanpa nama tokoh** — Cantor, Gödel, Zermelo, Cohen, dsb. sengaja tidak disebut di Gerbang. Mereka diperkenalkan pertama kali di bab Jalur Eksplorasi yang relevan, supaya kemunculan mereka berdampak lebih besar — panggung pertama tokoh adalah bab yang membahas kontribusinya, bukan Gerbang.
- **Cliffhanger tanpa menyebut nomor/nama resmi Problem** *(v1.4 — diuji 2×, PR-001 & PR-002, konvergensi tiga arah independen tiap kali)* — Gerbang berakhir sebagai pertanyaan terbuka; pembaca sampai ke pengenalan Problem itu sendiri lewat konteks Atlas di sekelilingnya, bukan diberi tahu langsung lewat kalimat penutup ("...dan inilah Problem #2").

**Skop:** per-Problem, **ad hoc** (ID: `GB-PR-XXX`) — tidak wajib ada untuk semua 23 Problem. Hanya ditulis kalau pertanyaan pembuka Problem tersebut genuinely tidak intuitif bagi pembaca awam.

**Status saat ini:** GB-PR-001 dan GB-PR-002 (final) — keduanya langsung diikuti Bab 1 Jalur Eksplorasi tanpa dokumen penyambung lain di antaranya.

**Keputusan tertutup:** kandidat layer "Peta Alur" (versi awal Gerbang yang masih menyebut istilah teknis bernama dan label bab eksplisit) dipertimbangkan, lalu dipensiunkan — fungsinya sepenuhnya terserap oleh Gerbang versi final begitu Gerbang berhasil mengerjakan dua fungsi sekaligus (memantik rasa ingin tahu dan menjelaskan rantai kebutuhan antar-bab) dalam satu dokumen. Tidak ada dokumen terpisah untuk fungsi itu.

**Kegagalan nyata yang memicu node ini (jejak alasan, sesuai standar Prinsip Proses):** draf pembuka PR-001 yang jargon-free diuji terhadap dua slot yang sudah ada, dan gagal di keduanya. (1) Dicoba sebagai bagian dari Bab 1 Jalur Eksplorasi — gagal, karena Bab 1 yang sudah ditulis dan Confirmed sudah mengasumsikan pembaca siap membangun kosakata teknis (bijeksi, kardinal) segera, bukan pembangunan rasa ingin tahu yang lebih lambat. (2) Dicoba dilebur ke Atlas Entry — gagal, karena format 8-section adalah ringkasan terstruktur/rujukan, bukan narasi mengalir dengan bangunan emosional bertahap. Karena gagal di kedua slot yang sudah ada, node Level 0 baru dibutuhkan — ini kegagalan nyata yang sama jenisnya dengan yang memicu keputusan AC, split NB-RES-0004, dan reklasifikasi Large Cardinals, hanya belum tertulis eksplisit sampai sekarang.

### 2.7 Legenda Diagram Pohon Evolusi Konsep

Setiap Atlas Entry (Section 4 di file masing-masing, "Pohon Evolusi Konsep") memakai satu legenda simbol yang sama — didefinisikan di sini sebagai rujukan tunggal (Prinsip #1), bukan didefinisikan ulang panjang lebar per file. Atlas Entry baru cukup merujuk balik ke section ini.

| Simbol | Makna | Jenis Notebook terkait |
|---|---|---|
| ■ | Masalah | — (Problem Registry) |
| ◆ | Teori / Kerangka Konseptual | Theory, Framework |
| ○ | Objek Matematika | Object |
| ↻ | Teknik / Prosedur | Technique |
| ● | Teorema / Hasil Utama | seluruh Jenis di Notebook Hasil Besar (Theorem, Lemma, Counterexample, Independence Result, Construction, Classification, Algorithm) |
| ▲ | Bidang | Field |
| ⬢ | Metode / Aplikasi | Method |

**Catatan asal (v1.2):** ○ dan ↻ ditambahkan saat menyusun Atlas Entry PR-001. Atlas Entry PR-017 (legenda pertama yang ditulis) kebetulan tidak pernah butuh node berjenis Object atau Technique di diagramnya sendiri, sehingga gap ini baru terlihat lewat implementasi nyata Problem kedua — pola yang sama seperti AC dan Large Cardinals: arsitektur tidak salah, cuma belum teruji lengkap. File Atlas Entry PR-017 sendiri tidak perlu diedit ulang (kontennya tetap benar, cuma tidak pernah mengeksekusi dua simbol yang baru ditambahkan ini).

**Catatan asal ⬢ (v1.6, retroaktif ke v1.2):** kolom Jenis untuk ⬢ di tabel di atas sudah mencakup **Method** sejak §2.7 pertama ditulis (v1.2) — bukan drift belakangan. Tapi entri Riwayat Versi v1.2 hanya menyebut penambahan ○/↻ secara eksplisit, tidak pernah menyebut bahwa cakupan ⬢ turut diperjelas dari "Aplikasi" (istilah asli legenda inline PR-017) menjadi "Metode / Aplikasi" pada saat bersamaan. Celah dokumentasi ini ditemukan lewat audit sinkronisasi PR-002, bukan lewat implementasi baru — dicatat di sini dan di Riwayat Versi (v1.6) supaya jejak alasannya lengkap, mengikuti standar yang sama dipakai untuk ○/↻. Alasan substantifnya: Method dan Aplikasi sama-sama kategori "instrumental" (apa yang dilakukan dengan sebuah teori/hasil), berbeda dari Object/Technique yang memang perlu simbol terpisah tegas.

**Catatan penamaan section:** nama "Pohon Evolusi Konsep" menggemakan item "6. Pohon Evolusi" di draft 11-section paling awal — meski isinya sendiri sebenarnya hasil peleburan beberapa section genesis yang redundan (4 Garis Waktu Tokoh, 5 Terobosan, 6 Pohon Evolusi, 8 Warisan Modern, 11 Resonansi Historis), bukan satu section tunggal yang dipakai apa adanya. Sempat disebut "Genealogi Ide" di tahap konsolidasi 11→8 section, lalu kembali ke salah satu nama aslinya (diperluas jadi "...Konsep") begitu template resmi PR-017 ditulis.

### 2.8 Legenda Status (Atlas Entry Section 1)

Sama seperti §2.7, legenda status untuk field **Status** di Section 1 tiap Atlas Entry juga berasal dari genesis proyek (draft 11-section paling awal, sebelum Problem #17 ditulis) — tapi baru diformalkan resmi di sini setelah ada dua titik data nyata untuk diuji.

| Simbol | Makna | Dipakai di |
|---|---|---|
| ✅ | Selesai (terbukti benar/salah secara definitif) | PR-017 |
| ⊘ | Terbukti independen (terbukti tidak bisa diputuskan dari sistem aksioma) | PR-001 |

**Status ❌ (Belum selesai), ⚠ (Sebagian selesai), ↺ (Direformulasi)** — bagian dari daftar genesis yang sama, tapi **belum diformalkan** di sini karena belum ada satu Atlas Entry pun yang benar-benar mengeksekusinya dengan bersih. Problem Registry (§1.2) menunjukkan kandidat kuat: PR-008 (Terbuka) untuk ❌, persis sesuai definisi "belum selesai". Satu ambiguitas yang perlu diperhatikan saat memformalkan nanti: PR-014 (Nagata, "terjawab negatif") kemungkinan **bukan** kandidat ❌ — ia hasil definitif, cuma jawabannya "tidak", jadi konseptual lebih dekat ke ✅ (selesai, meski negatif) daripada ke "belum ada kemajuan" seperti PR-008. Konsisten dengan disiplin yang sama seperti §2.7: formalkan hanya yang teruji lewat implementasi nyata, bukan yang cuma pernah diusulkan. Dicatat sebagai kandidat di Catatan Terbuka §6.

**Percobaan v1.4 dan koreksinya (v1.5):** ⚠ sempat diformalkan berdasarkan PR-002 sendirian, lalu **dibatalkan** setelah ditemukan genuinely ambigu — bukan penyelesaian tunggal, PR-002 menyisakan tiga pembacaan yang sama masuk akal: **⚠** (sebagian terjawab), **↺** (pertanyaan direformulasi setelah versi asli terbukti mustahil tuntas — pola yang secara struktural lebih pas untuk PR-002: "buktikan Con(PA) murni finitary" dijawab TUNTAS dengan tidak-mungkin oleh Gödel, baru kemudian pertanyaan baru "berapa kekuatan tambahan dibutuhkan" dijawab sukses oleh Gentzen), dan **✅-dengan-catatan** (mengikuti pola yang sudah ada di teks bebas §1.2 untuk PR-021: "Terpecahkan dengan catatan"). Tiga pembacaan yang sama masuk akal adalah sinyal bahwa PR-002 **bukan** titik data yang cukup bersih untuk memformalkan simbol ketiga apa pun — beda dari PR-001 yang bersih memicu ⊘. Ditunda sampai Problem yang genuinely ⚠ murni (kandidat: **PR-006**, aksiomatisasi probabilitas selesai tapi QFT belum — pola "sebagian dari pertanyaan yang sama terjawab, sebagian belum", bukan "pertanyaan diganti") memberi data pembanding yang lebih jernih. Atlas Entry PR-002 sendiri memakai ✅-dengan-catatan sebagai jalan tengah paling aman untuk sekarang.

---

## 3. Registry — Notebook Konsep

| ID | Status | Nama Konsep | Jenis | Cluster (Rak) | Terkait Problem | Catatan |
|---|---|---|---|---|---|---|
| NB-CON-0001 | Confirmed | Bentuk Kuadratik (Quadratic Forms) | Object | B | PR-017 | Domain asal Problem #17 |
| NB-CON-0002 | Confirmed | Ordered Fields | Theory | B | PR-017 | Fondasi menuju Real Closed Fields |
| NB-CON-0003 | Confirmed | Real Closed Fields | Theory | B *(tentatif)* | PR-017 | Artin–Schreier (1926); berbatasan kuat dengan Cluster A lewat Model Theory |
| NB-CON-0004 | Confirmed | Model Theory | Field | A | PR-017, PR-001, PR-002 | Pemakaian ke-3 berturut-turut — Tarski (PR-017), konstruksi model ZFC (PR-001 Bab 9), sintaks/semantik (PR-002 Bab 6). Bukti nyata ketiga Prinsip #1 |
| NB-CON-0007 | Confirmed | Real Algebraic Geometry | Field | C *(tentatif)* | PR-017 | Ditandai "bidang modern" (▲) di pohon evolusi; bisa jadi lebih tepat di B — perlu diputuskan saat Jalur Eksplorasi #1 |
| NB-CON-0008 | Confirmed | Sum-of-Squares (SOS) | Method | B *(tentatif)* | PR-017 | Aplikasi kuat ke Cluster G (optimisasi/komputasi) — cek silang saat Notebook G mulai diisi |
| NB-CON-0009 | Confirmed | Semidefinite Programming (SDP) | Method | G *(tentatif — ikut SOS)* | PR-017 | Parrilo (2000) |
| NB-CON-0010 | Confirmed | Polynomial Optimization | Method | G *(tentatif — ikut SOS)* | PR-017 | Lasserre (2001); turunan langsung dari SOS |
| NB-CON-0011 | Confirmed | Diagonal Argument | Technique | A | PR-001 | Cantor 1874 (interval bersarang) / 1891 (diagonal) — Bab 2 |
| NB-CON-0012 | Confirmed | Cardinal | Object | A | PR-001 | Bab 3 |
| NB-CON-0013 | Confirmed | Ordinal | Object | A | PR-001 | Bab 4 |
| NB-CON-0014 | Confirmed | Teori Himpunan (Set Theory) | Field | A | PR-001 | Bab 5 |
| NB-CON-0015 | Confirmed | ZF (Zermelo–Fraenkel) | Framework | A | PR-001 | Bab 6 |
| NB-CON-0016 | Confirmed | Axiom of Choice (AC) | Axiom *(informal — belum masuk vocab resmi §2.2, lihat Catatan Terbuka)* | A | PR-001 | Bab 7; diuji lewat Bab 7 & 12, keduanya tidak menampung AC sebagai Framework maupun Object |
| NB-CON-0017 | Confirmed | ZFC | Framework | A | PR-001 | Bab 8 |
| NB-CON-0018 | Confirmed | Constructible Universe (L) | Object | A | PR-001 | Bab 10; sebelumnya tentatif, sekarang tidak lagi |
| NB-CON-0019 | Confirmed | Forcing | Technique | A | PR-001 | Bab 12; mengonfirmasi prediksi §6 sebelumnya (Technique, bukan Result) |
| NB-CON-0020 | Confirmed | Large Cardinals | Field *(direklasifikasi dari Object)* | A | PR-001 | Bab 15; payung hierarki, menaungi NB-CON-0023/0024 |
| NB-CON-0021 | Confirmed | Inner Models | Object | A | PR-001 | Bab 16 |
| NB-CON-0022 | Confirmed | Ultimate L | Framework | A | PR-001 | Bab 17; program riset, bukan objek tunggal |
| NB-CON-0023 | Confirmed | Measurable Cardinal | Object | A | PR-001 | Bab 15; instance di bawah NB-CON-0020 |
| NB-CON-0024 | Confirmed | Woodin Cardinal | Object | A | PR-001 | Bab 18; instance di bawah NB-CON-0020 |
| NB-CON-0025 | Confirmed | Program Hilbert | Framework | A | PR-002 | Bab 1; konvergensi 3-arah independen (GPT, Claude 1, Claude 2) |
| NB-CON-0026 | Confirmed | Metode Finitary | Method | A | PR-002 | Bab 2 |
| NB-CON-0027 | Confirmed | Formalisasi | Technique | A | PR-002 | Bab 3 |
| NB-CON-0028 | Confirmed | Peano Arithmetic (PA) | Framework | A | PR-002 | Bab 4; Peano 1889 — first-order (model nonstandar) vs second-order (kategoris) |
| NB-CON-0029 | Confirmed | Gödel Numbering | Technique | A | PR-002 | Bab 9 |
| NB-CON-0030 | Confirmed | Diagonal Lemma | Technique | A | PR-002 | Bab 10; bertetangga dekat Diagonal Argument (NB-CON-0011) — tujuan beda, bentuk mirip |
| NB-CON-0031 | Confirmed | Induksi Transfinit | Technique | A | PR-002 | Bab 14; instrumen teknis bukti Gentzen |
| NB-CON-0032 | Confirmed | Analisis Ordinal | Method | A | PR-002 | Bab 15; generalisasi metode Gentzen |
| NB-CON-0033 | Confirmed | Reverse Mathematics | Field | A | PR-002 | Bab 17; Friedman ~1970-an, Simpson |
| NB-CON-0034 | Confirmed | Con(PA) | Object | A | PR-002 | Dipakai berulang Bab 5/9/12/14 — ditemukan lewat person/concept audit |

> **Migrasi:** `NB-CON-0005` (Transfer Principle) dan `NB-CON-0006` (Positivstellensatz) telah dipindahkan ke Notebook Hasil Besar — lihat `NB-RES-0002` dan `NB-RES-0003` di Bagian 4. ID lama sengaja **tidak dipakai ulang**, sesuai praktik registry yang baik, agar rujukan silang di masa depan tidak membingungkan.

---

## 4. Registry — Notebook Hasil Besar

| ID | Status | Nama Hasil | Jenis | Tahun | Cluster | Tokoh Terkait | Terkait Problem | Catatan |
|---|---|---|---|---|---|---|---|---|
| NB-RES-0001 | Confirmed | Solusi Problem #17 (Artin) | Theorem | 1927 | B | NB-PER-0002 (Artin) | PR-017 | Representasi sbg jumlah kuadrat fungsi rasional; bersifat non-konstruktif |
| NB-RES-0002 | Confirmed | Transfer Principle (Tarski) | Theorem | 1948 | A | NB-PER-0004 (Tarski) | PR-017 | Dipindahkan dari NB-CON-0005; decidability medan real tertutup |
| NB-RES-0003 | Confirmed | Positivstellensatz | Theorem | 1964 / 1974 | B | NB-PER-0005 (Krivine), NB-PER-0006 (Stengle) | PR-017 | Dipindahkan dari NB-CON-0006 |
| NB-RES-0004 | Confirmed | Independensi CH dari ZFC | Independence Result | 1940 & 1963 | A | NB-PER-0011 (Gödel), NB-PER-0012 (Cohen) | PR-001 | Sintesis 0004a+0004b — independensi baru lahir begitu keduanya digabung, bukan dari salah satu saja |
| NB-RES-0004a | Confirmed | Konsistensi Relatif CH (via L) | Theorem | 1940 | A | NB-PER-0011 (Gödel) | PR-001 | Con(ZF) → Con(ZFC+CH); anak dari NB-RES-0004 |
| NB-RES-0004b | Confirmed | Konsistensi Relatif ¬CH (via Forcing) | Theorem | 1963 | A | NB-PER-0012 (Cohen) | PR-001 | Con(ZFC) → Con(ZFC+¬CH); anak dari NB-RES-0004 |
| NB-RES-0005 | Confirmed | Ketakterhitungan ℝ | Theorem | 1874 / 1891 | A | NB-PER-0014 (Cantor) | PR-001 | Tidak ada bijeksi ℕ↔ℝ; Bab 2 |
| NB-RES-0006 | Confirmed | Teorema Cantor (\|P(S)\|>\|S\|) | Theorem | 1891 | A | NB-PER-0014 (Cantor) | PR-001 | Himpunan kuasa selalu berkardinal lebih besar; Bab 3 |
| NB-RES-0007 | Confirmed | Paradoks Russell | Counterexample | 1901 | A | NB-PER-0016 (Russell) | PR-001, PR-002 | Kontraeksempel terhadap teori himpunan naif; Bab 5 |
| NB-RES-0008 | Confirmed | Teorema Scott (V≠L) | Theorem | 1961 | A | NB-PER-0020 (Scott) | PR-001 | Measurable cardinal menyiratkan V≠L; Bab 15 |
| NB-RES-0009 | Confirmed | Martin–Steel–Woodin | Theorem | 1988–1989 | A | NB-PER-0021 (Martin), NB-PER-0022 (Steel), NB-PER-0013 (Woodin) | PR-001 | Large cardinals cukup banyak → Projective Determinacy; Bab 18 |
| NB-RES-0010 | Confirmed | Teorema Kelengkapan Gödel | Theorem | 1929/1930 | A | NB-PER-0011 (Gödel) | PR-002 | Disertasi Wina; logika orde-pertama lengkap secara semantik-sintaktik; Bab 7 |
| NB-RES-0011 | Confirmed | Teorema Ketaklengkapan Pertama | Theorem | 1931 | A | NB-PER-0011 (Gödel) | PR-002 | Tanpa induk (lihat §2.3) — Bab 11 |
| NB-RES-0012 | Confirmed | Teorema Ketaklengkapan Kedua | Theorem | 1931 | A | NB-PER-0011 (Gödel) | PR-002 | Dibangun di atas First, tetap tanpa induk (lihat §2.3) — Bab 12 |
| NB-RES-0013 | Confirmed | Bukti Konsistensi PA (Gentzen) | Theorem | 1936 | A | NB-PER-0023 (Gentzen) | PR-002 | Via induksi transfinit ε₀ — Bab 14 |
| NB-RES-0014 | Confirmed | Teorema Paris–Harrington | Theorem | 1977 | A | NB-PER-0024 (Paris), NB-PER-0025 (Harrington) | PR-002 | Independensi "alami", bukan self-reference — Bab 16 |

---

## 5. Registry — Notebook Tokoh

| ID | Status | Nama Tokoh | Peran/Kontribusi Utama | Era | Terkait Problem | Cluster Terkait (tag) |
|---|---|---|---|---|---|---|
| NB-PER-0001 | Confirmed | David Hilbert | Mengajukan 23 masalah (1900); menyelesaikan kasus khusus 2-variabel PR-017 (1893) | Classical → Modern | PR-017 (dan semua), PR-001, PR-002 | A–G |
| NB-PER-0002 | Confirmed | Emil Artin | Solusi PR-017 (1927); fondasi Real Algebraic Geometry | Modern | PR-017 | B |
| NB-PER-0003 | Confirmed | Otto Schreier | Ordered Fields & Real Closed Fields (bersama Artin, 1926) | Modern | PR-017 | B |
| NB-PER-0004 | Confirmed | Alfred Tarski | Transfer Principle, decidability medan real (1948) | Modern | PR-017 | A |
| NB-PER-0005 | Confirmed | Jean-Louis Krivine | Positivstellensatz (1964) | Modern → Contemporary | PR-017 | B |
| NB-PER-0006 | Confirmed | Gilbert Stengle | Positivstellensatz (1974) | Modern | PR-017 | B |
| NB-PER-0007 | Confirmed | Charles Delzell | Prosedur konstruktif atas solusi Artin (1984) | Contemporary | PR-017 | B |
| NB-PER-0008 | Confirmed | Konrad Schmüdgen | Positivstellensatz tanpa penyebut pada himpunan kompak (1991) | Contemporary | PR-017 | B |
| NB-PER-0009 | Confirmed | Pablo Parrilo | Polynomial optimization via SOS/SDP (2000) | Contemporary | PR-017 | G |
| NB-PER-0010 | Confirmed | Jean B. Lasserre | Moment methods, polynomial optimization (2001) | Contemporary | PR-017 | G |
| NB-PER-0011 | Confirmed | Kurt Gödel | Konsistensi relatif CH via L (1938/1940); Kelengkapan (1929) & Ketaklengkapan (1931) | Modern | PR-001, PR-002 | A |
| NB-PER-0012 | Confirmed | Paul Cohen | Forcing, independensi ¬CH (1963); Fields Medal 1966 | Modern → Contemporary | PR-001 | A |
| NB-PER-0013 | Confirmed | W. Hugh Woodin | Kardinal Woodin; Ultimate L; Martin–Steel–Woodin (1988–89) | Contemporary | PR-001 | A |
| NB-PER-0014 | Confirmed | Georg Cantor | Diagonal argument, kardinal, ukuran tak hingga (1874–1897) | Classical | PR-001 | A |
| NB-PER-0015 | Confirmed | Leopold Kronecker | Penentang tak hingga aktual, konteks historis Bab 5 | Classical | PR-001 | A |
| NB-PER-0016 | Confirmed | Bertrand Russell | Paradoks Russell (1901) | Modern | PR-001, PR-002 | A |
| NB-PER-0017 | Confirmed | Ernst Zermelo | ZF awal (1908), AC & Well-Ordering Theorem (1904) | Modern | PR-001 | A |
| NB-PER-0018 | Confirmed | Abraham Fraenkel | Aksioma Replacement pada ZF (~1922) | Modern | PR-001 | A |
| NB-PER-0019 | Confirmed | Thoralf Skolem | Penyempurna ZF bersama Fraenkel (~1922) | Modern | PR-001 | A |
| NB-PER-0020 | Confirmed | Dana Scott | Teorema Scott, V≠L dari measurable cardinal (1961) | Modern | PR-001 | A |
| NB-PER-0021 | Confirmed | Donald A. Martin | Martin–Steel–Woodin (1988–89) | Contemporary | PR-001 | A |
| NB-PER-0022 | Confirmed | John R. Steel | Martin–Steel–Woodin (1988–89) | Contemporary | PR-001 | A |
| NB-PER-0023 | Confirmed | Gerhard Gentzen | Bukti konsistensi PA via induksi transfinit ε₀ (1936); wafat 1945 usia 35 | Modern | PR-002 | A |
| NB-PER-0024 | Confirmed | Jeff Paris | Teorema Paris–Harrington (1977) | Modern → Contemporary | PR-002 | A |
| NB-PER-0025 | Confirmed | Leo Harrington | Teorema Paris–Harrington (1977) | Modern → Contemporary | PR-002 | A |
| NB-PER-0026 | Confirmed | Giuseppe Peano | Aksioma Peano Arithmetic (1889) | Classical | PR-002 | A |

---

## 6. Catatan Terbuka

**Penempatan tentatif** — tiga entri di Bagian 3 masih genuinely lintas-cluster, baru bisa diputuskan setelah ada konten Problem kedua sebagai pembanding:

1. **Real Closed Fields (NB-CON-0003)** — home di B (Algebra) atau A (Foundations/Logic)?
2. **Real Algebraic Geometry (NB-CON-0007)** — home di C (Geometry) atau B (Algebra)?
3. **Sum-of-Squares (NB-CON-0008)** — home di B (Algebra) atau G (Complexity/Computation)?
4. **Semidefinite Programming (NB-CON-0009) & Polynomial Optimization (NB-CON-0010)** — saat ini ikut ditempatkan di G mengikuti SOS, tapi karena keduanya turunan langsung dari SOS yang sendiri masih tentatif (poin 3), keputusan final soal rumah SOS otomatis menentukan follow-up untuk keduanya juga — jangan diputuskan terpisah dari SOS.

**Uji nyata pertama untuk Single Source of Truth — SELESAI.** NB-CON-0004 (Model Theory) disebut lagi di PR-001 Bab 9 seperti diantisipasi; ditangani lewat cross-reference (kolom Terkait Problem diperbarui), bukan entri baru. Lihat Bagian 3.

**Terbuka — vocab resmi "Axiom" di Section 2.2.** NB-CON-0016 (AC) sekarang Confirmed dengan Jenis "Axiom", tapi "Axiom" **belum** ditambahkan ke daftar vocab resmi (`Theory · Technique · Object · Method · Framework · Field`) — dipakai dulu secara informal untuk satu entri ini, mengikuti preseden penundaan yang sama seperti kolom Keluarga (1.2) dan skema ID Timeline: jangan formalkan kategori baru dari satu titik data. Begitu ada Problem lain yang memunculkan aksioma individual bermasalah serupa (kandidat: Replacement, Foundation, Infinity — bukan cuma disebut, tapi diuji naratif seperti AC), baru "Axiom" masuk resmi ke vocab §2.2.

**Terbuka — tokoh tingkat kedua yang ditahan.** Ambang resmi Notebook Tokoh (2.4): **nama + kontribusi spesifik + tahun** (atau terikat langsung ke entri NB-RES berdata lengkap) — bukan "dapat bab/paragraf berdiri sendiri" (Fraenkel/Skolem sendiri tidak memenuhi standar itu, tapi lolos standar yang benar). Diuji ketat ke tokoh Bab 16, hasilnya: Kunen dan Silver (kontribusi L[U] jelas, tapi tahun cuma perkiraan "akhir 1960-an–awal 1970-an") serta Dodd–Jensen dan Mitchell (disebut kolektif, tanpa tahun individual) — keempatnya **ditahan**, belum diregistrasi, sampai narasi problem lain memberi mereka data setahun-spesifik yang lebih presisi.

**Calon entri baru dari Lapisan IV (Bab 19), belum diregistrasi:**
- **Forcing Axioms (PFA, Martin's Axiom)** — kemungkinan Concept (Framework/Technique), rumahnya belum jelas tanpa narasi lebih dalam
- **Multiverse view (Hamkins)** — kemungkinan NB-PER baru (Joel David Hamkins) kalau nanti dibahas lebih dalam sebagai kontributor, bukan cuma nama pandangan

**Terbuka — status ❌/⚠/↺ belum diformalkan.** §2.8 sudah meresmikan ✅ dan ⊘ (masing-masing teruji lewat PR-017 dan PR-001). Tiga simbol lain dari genesis proyek (❌ Belum selesai, ⚠ Sebagian selesai, ↺ Direformulasi) masih kandidat — ditunda sampai Atlas Entry Problem yang benar-benar berstatus demikian ditulis (kandidat dari Problem Registry §1.2: PR-008 untuk ❌, PR-004/PR-012 untuk ⚠). **PR-014 bukan kandidat ❌ yang tepat** — hasilnya definitif (kontraeksempel Nagata), cuma jawabannya negatif, jadi konseptual lebih dekat ke ✅ daripada ke "belum ada kemajuan"; lihat §2.8 untuk penjelasan lengkap ambiguitas ini.

**Terbuka — Cluster utama untuk keperluan volume rilis.** Kalau rilis per volume Cluster benar-benar terjadi (lihat rasionalisasi urutan tulis di Roadmap), beberapa Problem yang sudah terdaftar di lebih dari satu Cluster (PR-006 di A & E, PR-010 di B & F, PR-019/020/023 di D & E) perlu tahu masuk volume yang mana — Problem Registry (1.2) saat ini cuma mendaftar cluster tanpa urutan prioritas. Ditunda sampai datanya nyata (baru 1 dari 23 Problem yang punya konten), mengikuti pola yang sama seperti penundaan kolom Keluarga (1.2) dan skema ID Timeline.

**Calon entri Notebook Hasil Besar berikutnya** — sudah terlihat di tabel Bagian 1.2 walau belum diregistrasi (menunggu Jalur Eksplorasi masing-masing Problem ditulis penuh): ~~Gödel Incompleteness (PR-002)~~ *(selesai — NB-RES-0011/0012)*, MRDP Theorem (PR-010, Jenis: *Independence Result*), Nagata's Counterexample (PR-014, Jenis: *Counterexample*), Gelfond–Schneider (PR-007), Kolmogorov–Arnold (PR-013), Hasse–Minkowski (PR-011).

**Kandidat belum diregistrasi dari PR-002** (dicatat, bukan diberi ID — sama pola dengan kandidat PR-001): J. Barkley Rosser (perbaikan konstruksi Gödel 1936, memenuhi ambang nama+kontribusi+tahun), John von Neumann (kontribusi "hampir menemukan sendiri" di Königsberg, mirip kasus Kunen/Silver), Wilhelm Ackermann (disebut Bab 8 tanpa tahun eksplisit di teks — tahun sebenarnya 1924, dissertasi di bawah Hilbert, siap dipakai kalau diregistrasi nanti), Teorema Goodstein (Kirby–Paris, 1982) + Laurie Kirby, korespondensi Curry–Howard, Cut-Elimination Theorem (Hauptsatz Gentzen — diuji lewat Audit Jahitan Bab seam 14→15, terbukti tidak dibutuhkan narasi, status non-blocking), dan jembatan #2↔#10 lewat Entscheidungsproblem/Turing (1936) — ditahan sampai PR-010 ditulis.

**Terbuka — Daftar Isi polos untuk Jalur Eksplorasi?** Sekarang Peta Alur pensiun (lihat 2.6), belum ada tempat yang menunjukkan daftar bab (nomor + judul) Jalur Eksplorasi secara literal — Gerbang sengaja tidak menyebut nomor bab, dan itu sudah benar untuk fungsinya. Pertanyaannya murni navigasi: apakah Jalur Eksplorasi butuh Daftar Isi polos (bukan naratif, cuma daftar bab, persis seperti Daftar Isi di bagian awal dokumen master ini) di bagian paling atas, sesudah Gerbang dan sebelum Bab 1? Ini bukan mengulang fungsi Gerbang — Daftar Isi murni alat rujuk-cepat, Gerbang adalah pengalaman baca.

**Catatan kecil untuk Fase B** — Timeline belum punya skema ID (`TL-XXX`) karena belum ada entri nyata untuk dijadikan acuan; akan ditentukan begitu Fase B mulai mengisi Timeline PR-001, dengan alasan yang sama seperti penundaan kolom Keluarga di 1.2 (jangan bangun struktur sebelum ada datanya).

**Keputusan ditunda (decision log)** — nama *Notebook Hasil Besar* / prefix `NB-RES` dipertahankan untuk sekarang, walau istilah "Hasil" dinilai terlalu umum untuk menangkap kesamaan sebenarnya. Kesamaan sesungguhnya bukan "hasil", melainkan **milestone dalam sejarah matematika** — sesuatu yang bisa mencakup teorema, lemma penting, kontraeksempel, konstruksi, klasifikasi, maupun algoritma penting sekaligus. Mengubah nama sekarang dinilai prematur tanpa cukup data pembanding.

| Keputusan | Status | Alasan Ditunda | Kondisi Peninjauan |
|---|---|---|---|
| Nama "Notebook Hasil Besar" / prefix `NB-RES` | Dipertahankan | "Hasil" terlalu umum untuk menangkap sifat *milestone* dari isinya | Tinjau ulang setelah registry ini berisi ~50–100 entri |

Kandidat nama alternatif yang sudah terlintas dan dicatat untuk saat itu tiba: *Notebook Tonggak*, *Notebook Milestone* — supaya tidak perlu dipikirkan ulang dari nol.

---

*Dokumen master ini adalah rujukan tunggal untuk seluruh arsitektur proyek. Fase A dinyatakan **Architecture Freeze**; perubahan struktural berikutnya tunduk pada Prinsip Proses di atas (Bagian awal dokumen). PR-001 dan PR-002 telah menuntaskan seluruh siklus B→C→D — Gerbang, Jalur Eksplorasi, Notebook, dan Atlas Entry semuanya selesai untuk keduanya. Langkah berikutnya: replikasi siklus ke PR-006 (Mathematical Treatment of the Axioms of Physics), Problem terakhir di Cluster A.*
