# PR-10 — Draft Usulan MVC

**Status:** Draft (Fase 2, skill `hilbert-sintesa`) — belum lulus Prosedur Audit Registry 5-Langkah, belum disinkronkan ke Atlas Master. Nomor registry di bawah semuanya placeholder (`xxx`), bukan final.
**Fase sebelumnya:** Fase 1 (`PR-10_Analisis_Topik.md`) + Fase 1.5 (validasi silang Atlas v1.7) — 20 topik Keep:Primer jadi tulang punggung struktur bab di bawah; topik Keep:Sekunder dianyam sbg materi pendukung di dalam bab yang relevan (bukan dpt bab sendiri, mengikuti disiplin *Minimum Viable Chapter*); topik Optional sengaja tidak masuk draf ini — lihat Catatan Seleksi di Lampiran.
**Mengikuti konvensi gaya** yang diekstrak dari MVC-PR-001/PR-002 (Fase 1.5 §E): 4 Lapisan, header registry per-bab, cross-reference eksplisit saat memakai ulang entri Problem lain, transisi antar-bab yang genuinely membangun pertanyaan (bukan sekadar "selanjutnya").

---

## Gerbang PR-10

### Janji yang Tidak Bisa Ditagih

Ada satu jenis teka-teki yang sudah dikenal manusia sejak lama: carilah bilangan-bilangan yang, kalau dimasukkan ke sebuah persamaan, membuat kedua ruas persamaan itu sama persis. Kadang jawabannya cepat ditemukan. Kadang pencarian berlangsung lama sekali — berhari-hari, bertahun-tahun, kadang berabad-abad — tanpa satu pun bilangan yang cocok.

Di titik itu muncul pertanyaan yang sebenarnya tidak nyaman untuk dihadapi: kalau sebuah pencarian belum juga membuahkan hasil, apakah itu karena jawabannya memang tidak ada, atau karena kita belum cukup lama, belum cukup cerdik, mencarinya?

Bayangkan seandainya ada satu metode tunggal — bukan untuk menyelesaikan teka-teki itu satu per satu, tapi untuk menjawab, untuk *teka-teki jenis apa pun* dari keluarga ini, pertanyaan yang lebih sederhana: apakah teka-teki ini punya jawaban sama sekali? Bukan mencari bilangannya, cukup memastikan ada-tidaknya. Dan metode itu dijanjikan bisa memberi jawaban itu dalam waktu terbatas — tidak peduli seberapa rumit teka-tekinya, tidak peduli seberapa besar bilangan yang terlibat.

Kalau metode semacam itu benar-benar ada, dampaknya luar biasa. Seluruh keluarga teka-teki — yang jumlahnya tak terhingga banyak variasinya — akan langsung jinak sekaligus. Tidak akan ada lagi pencarian tanpa akhir yang menggantung tanpa kepastian. Setiap kali seseorang menghadapi teka-teki baru dari keluarga ini, mereka tinggal menjalankan metode itu, dan dalam waktu terbatas mendapat jawaban pasti: ada solusinya, atau tidak akan pernah ada.

Tapi begitu janji itu dituliskan secara presisi, sesuatu yang janggal mulai terasa. Bagaimana mungkin satu metode tunggal — yang harus selesai dalam waktu terbatas — sanggup menangani keluarga teka-teki yang variasinya tak terhingga, yang sebagian anggotanya bahkan belum pernah dibayangkan siapa pun? Bukankah ada jarak yang aneh antara "tak terhingga banyak kemungkinan" dan "jawaban pasti dalam waktu terbatas"?

Dan kalau jarak itu ternyata tidak bisa dijembatani — bukan karena belum ada yang cukup cerdik menemukan metodenya, tapi karena permintaan itu sendiri, dari awal, menuntut sesuatu yang mustahil dipenuhi metode manapun — maka yang runtuh bukan cuma satu metode yang gagal ditemukan. Yang runtuh adalah keyakinan bahwa metode semacam itu, dalam bentuk apa pun, memang mungkin ada.

Pertanyaannya sekarang bukan lagi "bagaimana menemukan metode itu". Pertanyaannya adalah: apakah janji seperti itu — janji untuk selalu bisa memastikan ada-tidaknya jawaban, untuk teka-teki apa pun dari keluarga ini, dalam waktu terbatas — pada dasarnya bisa ditagih sama sekali?

---

## LAPISAN I — FONDASI

### Bab 1 — Diophantus dan Teka-Teki yang Diwariskan Berabad-abad
*Registry: NB-CON-xxx01 (Draft, Object) — Persamaan Diophantine · NB-PER-xxx01 (Draft) — Diophantus*

Sekitar abad ke-3 Masehi, di Alexandria, seorang matematikawan bernama Diophantus menulis *Arithmetica* — kumpulan soal yang meminta bilangan bulat atau pecahan yang memenuhi berbagai hubungan aljabar. Soal-soal semacam ini, yang menuntut solusi berupa bilangan bulat (bukan sembarang bilangan real), sejak itu disebut **persamaan Diophantine** — mengabadikan namanya meski Diophantus sendiri tidak pernah merumuskan pertanyaan tentang persamaan seperti itu secara umum, ia cuma memecahkan kasus-kasus spesifik satu demi satu.

Warisannya bertahan panjang. Pierre de Fermat, di margin salinan *Arithmetica* miliknya pada abad ke-17, menuliskan klaim terkenal soal tak-adanya solusi bulat positif untuk sebuah keluarga persamaan pangkat tinggi — klaim yang baru terbukti benar 358 tahun kemudian oleh Andrew Wiles, lewat jalur teknis yang sama sekali berbeda dari apa pun yang tersedia di zaman Fermat. Antara Fermat dan Wiles, generasi demi generasi matematikawan — Euler, Lagrange, dan banyak lainnya — mengasah teknik demi teknik untuk kelas-kelas persamaan Diophantine tertentu: kadang berhasil menyelesaikannya, kadang terbukti tak ada solusi, kadang harus menunggu berabad-abad seperti Fermat.

Pola inilah yang, sampai akhir abad ke-19, dianggap wajar: setiap persamaan Diophantine adalah tantangan tersendiri, diselesaikan (atau dibuktikan tak terselesaikan) dengan kecerdikan khusus untuk kasus itu — tidak ada yang berpikir untuk mencari satu metode tunggal yang berlaku untuk semuanya sekaligus. Butuh satu pertanyaan yang diajukan dengan cara sama sekali berbeda untuk mengubah arah itu — bukan lagi "bagaimana menyelesaikan persamaan ini", melainkan "apakah ada cara umum untuk memastikan ada-tidaknya solusi, untuk persamaan Diophantine apa pun".

### Bab 2 — Program Hilbert dan Rumusan Presis 1900
*Registry: Cross-reference NB-CON-0025 (Confirmed, Framework, dari PR-002) — Program Hilbert, pemakaian ke-2 · Cross-reference NB-PER-0001 (Confirmed) — David Hilbert*

Pertanyaan itu diajukan David Hilbert dalam ceramah "Mathematische Probleme" di Paris, 1900 — bagian dari ambisi besarnya untuk meletakkan seluruh matematika di atas fondasi yang bisa diperiksa secara formal (Program Hilbert, sudah dibahas mendalam di Jalur Eksplorasi PR-2 — di sini cukup dicatat: PR-10 lahir dari cabang yang sama, semangat yang sama, tapi objek yang sangat berbeda: bukan konsistensi seluruh aritmetika, melainkan satu kelas pertanyaan konkret soal persamaan).

Rumusan Hilbert, diparafrasekan dari terjemahan standar: diberikan sebuah persamaan Diophantine dengan berapa pun banyaknya bilangan tak diketahui dan koefisien bilangan bulat, carikan sebuah **proses** yang, lewat **langkah berhingga**, bisa menentukan apakah persamaan itu punya solusi dalam bilangan bulat.

Dua detail dalam rumusan ini gampang terlewat kalau dibaca cepat, tapi menentukan seluruh cerita berikutnya. Pertama: yang diminta bukan cara *menyelesaikan* persamaan — itu sudah dikerjakan Diophantus dan penerusnya kasus demi kasus (Bab 1). Yang diminta adalah satu prosedur tunggal yang menjawab pertanyaan ada-tidaknya solusi, untuk *persamaan apa pun* dari keluarga ini — persis "metode universal" yang dibayangkan di Gerbang. Kedua: domain solusinya secara literal adalah bilangan bulat (ℤ) — bukan pecahan, bukan bilangan real. Perluasan ke domain lain, seperti akan terlihat di Lapisan III, adalah warisan pasca-1970, bukan permintaan asli Hilbert.

Hilbert sendiri tidak punya kosakata untuk mendefinisikan "proses" atau "langkah berhingga" secara presisi matematis — istilah Jerman yang ia pakai, *Verfahren*, masih bertumpu pada intuisi umum soal "prosedur mekanis", bukan definisi formal. Definisi formal itu baru datang tiga dekade kemudian, dan justru ketiadaannya di 1900 inilah yang membuat PR-10 sulit dijawab — bagaimana mungkin membuktikan sesuatu *tidak ada* kalau "sesuatu" itu sendiri belum punya definisi presis?

### Bab 3 — "Wir müssen wissen" dan Ekspektasi yang Terbalik

*(Tidak ada entri registry baru — bab ini murni framing naratif/filosofis, mengikuti pola Bab 8 PR-002 "Usaha Awal & Optimisme 1930 — Königsberg". Du Bois-Reymond dicatat di Lampiran sbg Kandidat Belum Diregistrasi, bukan diberi entri penuh — kontribusinya nyata tp perannya di sini murni sbg foil retoris satu-kalimat.)*

Tiga dekade setelah 1900, dalam pidato radio dari Königsberg, Hilbert merangkum optimisme yang melandasi bukan cuma PR-10 tapi seluruh programnya: *"Wir müssen wissen — wir werden wissen"* — kita harus tahu, kita akan tahu. Ini penolakan eksplisit terhadap *ignorabimus* — sikap "kita tak akan pernah tahu" yang sebelumnya diucapkan dokter-fisiolog Jerman Emil du Bois-Reymond — perintis elektrofisiologi eksperimental — untuk pertanyaan-pertanyaan tertentu di sains alam.

Nada rumusan PR-10 sendiri — "carikan sebuah proses" bukan "buktikan apakah proses itu ada" — mencerminkan optimisme yang sama: Hilbert tampaknya mengasumsikan proses semacam itu memang ada, tinggal ditemukan siapa yang cukup cerdik. Ini ekspektasi yang persis sejalan dengan janji yang dibayangkan di Gerbang — bukan keraguan apakah janji itu bisa ditagih, melainkan keyakinan tinggal soal waktu sampai seseorang menagihnya.

Yang tidak — dan secara struktural tidak bisa — diantisipasi Hilbert adalah kemungkinan bahwa "kita akan tahu" bisa terwujud lewat jawaban **negatif**: bukan menemukan prosedurnya, melainkan membuktikan prosedur semacam itu mustahil ada. Ironi inilah yang akan terbayar penuh di penghujung Lapisan II — dan yang membuat PR-10, bersama krisis yang menimpa Program Hilbert secara umum, jadi salah satu pembalikan ekspektasi paling dramatis dalam sejarah matematika abad ke-20.

---

## LAPISAN II — REVOLUSI

### Bab 4 — Entscheidungsproblem: Pertanyaan Sepupu yang Memicu Definisi Algoritma
*Registry: NB-CON-xxx02 (Draft, Framework) — Entscheidungsproblem*

Delapan tahun setelah 1900, benih keraguan terhadap optimisme Hilbert mulai muncul dari arah yang tidak terduga — bukan dari PR-10 sendiri, melainkan dari sepupunya yang lebih umum. Pada 1928, Hilbert dan Wilhelm Ackermann merumuskan *Entscheidungsproblem* (masalah keputusan): apakah ada prosedur mekanis untuk menentukan, bagi *sembarang* pernyataan dalam logika predikat orde-pertama, apakah pernyataan itu valid secara logis?

Pola pertanyaannya identik dengan PR-10 — bukan menyelesaikan satu pernyataan logis tertentu, melainkan mencari satu prosedur universal yang menjawab pertanyaan itu untuk *pernyataan apa pun*. Bedanya, Entscheidungsproblem beroperasi di ranah logika murni, sementara PR-10 di ranah aritmetika konkret. Kesamaan pola inilah yang membuat kedua problem, tiga dekade kemudian, jatuh lewat mekanisme yang berkerabat dekat — meski jawaban PR-10 sendiri baru datang jauh lebih lambat, 1970, empat dekade setelah Entscheidungsproblem terjawab.

Untuk menjawab Entscheidungsproblem — ke arah manapun jawabannya — dibutuhkan sesuatu yang belum tersedia tahun 1928: definisi presisi tentang apa itu "prosedur mekanis". Pertanyaan inilah yang, tanpa direncanakan siapa pun sebagai proyek tunggal, memaksa lahirnya definisi formal "algoritma" pada dekade berikutnya.

### Bab 5 — Gödel, Turing, Church: Tiga Jalan Menuju Definisi "Algoritma"
*Registry: NB-CON-xxx03 (Draft, Field) — Teori Komputabilitas · NB-CON-xxx04 (Draft, Technique) — Kalkulus Lambda · NB-CON-xxx05 (Draft, Theory) — Tesis Church-Turing · NB-PER-xxx02 (Draft) — Alan Turing · NB-PER-xxx03 (Draft) — Alonzo Church · Cross-reference NB-RES-0011, NB-RES-0012 (Confirmed, dari PR-002) — Teorema Ketaklengkapan Gödel · Cross-reference NB-PER-0011 (Confirmed) — Kurt Gödel*

Retakan pertama datang 1931, dari arah yang bahkan lebih jauh dari PR-10: Teorema Ketaklengkapan Kurt Gödel (sudah dibahas penuh di PR-2 — di sini cukup dicatat perannya sbg preseden psikologis, bukan diuraikan ulang) menunjukkan bahwa optimisme Program Hilbert punya batas struktural. Ini bukan jawaban atas Entscheidungsproblem atau PR-10 secara langsung, tapi ia menabur benih kecurigaan: kalau konsistensi aritmetika sendiri bisa gagal dibuktikan seperti yang diharapkan, mungkin permintaan-permintaan besar Hilbert lain juga menyimpan batas serupa.

Lima tahun kemudian, 1936, dua jawaban independen atas Entscheidungsproblem muncul nyaris bersamaan. Alan Turing, lewat mesin abstrak yang kelak menyandang namanya — sebuah model matematis presisi tentang "apa yang bisa dihitung mekanis, langkah demi langkah" — menunjukkan tak ada prosedur semacam itu untuk Entscheidungsproblem. Alonzo Church, lewat jalur sama sekali berbeda (kalkulus-λ, sistem formal untuk mendefinisikan dan memanipulasi fungsi), sampai pada kesimpulan yang setara.

Yang membuat 1936 begitu penting bukan cuma jawaban negatifnya, tapi definisi yang lahir sebagai efek sampingnya: untuk pertama kali, "algoritma" atau "prosedur efektif" — istilah yang dipakai Hilbert secara intuitif di rumusan PR-10 (Bab 2) — punya padanan matematis presisi. Turing, Church, dan (belakangan terbukti setara) fungsi rekursif Gödel/Kleene, ternyata mendefinisikan kelas fungsi yang persis sama meski dibangun dari arah berbeda total — kesetaraan yang dirangkum **Tesis Church-Turing**: apapun yang secara intuitif "bisa dihitung mekanis" persis sama dengan apa yang bisa dihitung mesin Turing (atau kalkulus-λ, atau fungsi rekursif).

Tanpa definisi presisi ini, PR-10 tak bisa dijawab ke arah manapun — bagaimana membuktikan "tak ada algoritma" kalau "algoritma" sendiri masih sekadar intuisi? Sejak 1936, pertanyaan Hilbert 1900 akhirnya punya kosakata yang cukup tajam untuk benar-benar diserang.

### Bab 6 — Konjektur Davis: Mengubah Pertanyaan Komputabilitas jadi Pertanyaan Aljabar
*Registry: NB-RES-xxx01 (Draft, Jenis tentatif: "Conjecture" — belum cocok vocab resmi §format-draft-mvc.md, lihat Lampiran) — Konjektur Davis · NB-PER-xxx04 (Draft) — Martin Davis*

Dengan "algoritma" akhirnya terdefinisi presisi, jalan menuju PR-10 masih butuh satu lompatan konseptual lagi. Pada 1953, Martin Davis mengajukan dugaan yang menjembatani dua dunia yang tadinya terasa jauh: himpunan yang bisa "dicacah" oleh sebuah algoritma (disebut himpunan *recursively enumerable*, RE — konsep langsung turunan dari mesin Turing Bab 5) ternyata, dugaannya, **persis sama** dengan himpunan yang bisa direpresentasikan sebagai himpunan solusi sebuah persamaan Diophantine.

Kalau dugaan ini benar, konsekuensinya luar biasa: pertanyaan komputabilitas (soal himpunan RE, ranah logika/teori komputasi) berubah jadi pertanyaan aljabar murni (soal representasi Diophantine, ranah teori bilangan) — dua ranah yang tadinya terasa sama sekali terpisah, ternyata bicara hal yang sama. Dan karena sudah diketahui ada himpunan RE yang tidak *decidable* (tak ada algoritma untuk memutuskan keanggotaannya — konsekuensi langsung hasil Turing 1936), kalau representasi Diophantine-nya juga berlaku, PR-10 otomatis punya jawaban: tak ada algoritma umum, karena kalau ada, ia bisa dipakai memutuskan himpunan RE yang sudah terbukti tak-decidable.

Konjektur Davis 1953 karena itu bukan cuma dugaan teknis — ia adalah peta jalan lengkap menuju jawaban PR-10, disusun 17 tahun sebelum jawabannya sendiri terbukti. Yang tersisa "cuma" satu hal: membuktikan setiap himpunan Diophantine eksponensial (bukan cuma polinomial biasa) benar-benar RE, dan sebaliknya.

### Bab 7 — Hipotesis Julia Robinson dan Fungsi Eksponensial Diophantine
*Registry: NB-RES-xxx02 (Draft, Jenis tentatif: "Conjecture" — sama spt Bab 6) — Hipotesis Julia Robinson · NB-CON-xxx06 (Draft, Object) — Persamaan Diophantine Eksponensial · NB-CON-xxx07 (Draft, Technique) — Persamaan Pell · NB-CON-xxx08 (Draft, Technique) — Barisan Fibonacci · NB-PER-xxx05 (Draft) — Julia Robinson · NB-PER-xxx06 (Draft) — Hilary Putnam*

"Setengah jalan" menuju Konjektur Davis sudah ditempuh bertahun-tahun sebelum konjektur itu sendiri dirumuskan. Julia Robinson, bekerja pada awal 1950-an, menunjukkan bahwa kalau **satu syarat teknis tunggal** bisa dipenuhi — yakni relasi pertumbuhan eksponensial (semacam "y = xᶻ") bisa direpresentasikan sebagai himpunan Diophantine — maka seluruh Konjektur Davis otomatis mengikuti. Syarat tunggal inilah yang dikenal sebagai **Hipotesis Julia Robinson**.

Persamaan Pell — kelas persamaan klasik berbentuk x² − Ny² = 1, sudah dikenal sejak matematikawan India dan diselidiki mendalam Fermat serta Lagrange (Bab 1) — menjadi alat kunci di sini: solusi persamaan Pell tumbuh secara eksponensial, sebuah fakta yang bisa "dipinjam" untuk menangkap pertumbuhan eksponensial murni di dalam kerangka Diophantine biasa. Martin Davis dan Hilary Putnam, bekerja bersama Robinson, mengasah pendekatan ini sepanjang 1950-an, mendapatkan hasil-hasil parsial yang terus mendekati — tapi tak pernah sepenuhnya menutup — celah eksponensial itu.

Butuh dua dekade lagi, dan satu alat teknis tak terduga — barisan Fibonacci, deret bilangan yang tampak jauh dari soal decidability — untuk akhirnya menutup celah itu.

### Bab 8 — 1970: Matiyasevich Menutup Celah Terakhir
*Registry: NB-RES-xxx03 (Draft, Theorem — bukan "Independence Result", lih. rekomendasi Fase 1.5 §B; MRDP adalah hasil recursion-theory, bukan hasil independensi-dari-aksioma) — Teorema MRDP · NB-CON-xxx09 (Draft, Technique) — Reduksi Davis-Putnam (bentuk normal 1961; catatan: "Teorema DPR" adalah nama alias hasil yang sama, lih. Keputusan Editorial Fase 1 §4) · NB-PER-xxx07 (Draft) — Yuri Matiyasevich*

Pada 1961, Davis, Putnam, dan Robinson menerbitkan hasil yang nyaris — tapi belum sepenuhnya — menuntaskan Hipotesis Julia Robinson: lewat sebuah reduksi bentuk normal, mereka menunjukkan hampir seluruh mekanisme yang dibutuhkan sudah bekerja, kecuali satu celah kecil di sekitar pertumbuhan eksponensial murni. Selama sembilan tahun, celah kecil itu bertahan — bukan karena diabaikan, tapi karena benar-benar sulit.

Yuri Matiyasevich, seorang matematikawan Soviet berusia 22 tahun, menutupnya pada 1970 — memakai barisan Fibonacci (Bab 7) untuk menangkap tepat pertumbuhan eksponensial yang dibutuhkan, murni dalam kerangka Diophantine polinomial biasa. Begitu celah itu tertutup, seluruh rantai sejak Bab 6 langsung tersambung: Hipotesis Julia Robinson terbukti, Konjektur Davis terbukti, dan — sebagai konsekuensi tak terelakkan — PR-10 punya jawaban.

Jawaban itu **negatif**. Himpunan Diophantine persis sama dengan himpunan RE (Teorema MRDP — akronim dari Martin **D**avis, Hilary **P**utnam, Julia **R**obinson, Yuri **M**atiyasevich). Nama ini sendiri punya sejarah kecil yang jarang diketahui: ada dua urutan akronim yang sama-sama beredar di literatur — "MRDP" dan "DPRM" — bukan karena salah satu alfabetis dan yang lain tidak (keduanya sama-sama bukan urutan alfabet), melainkan karena mencerminkan penekanan berbeda: Matiyasevich sendiri lebih suka "DPRM" (urutan kronologis, mendahulukan kontribusi para pendahulunya), sementara Davis lebih suka "MRDP" (mendahulukan nama penyelesai). Karena ada himpunan RE yang tak-decidable, dan setiap himpunan Diophantine adalah RE, maka **tak ada algoritma umum** yang bisa menentukan solvabilitas persamaan Diophantine sembarang dalam bilangan bulat. Kerja kolektif yang membentang dari Alexandria abad ke-3 sampai Leningrad 1970, melintasi Perang Dingin lewat kolaborasi tak-langsung matematikawan Amerika dan Soviet, berakhir dengan jawaban yang justru meniadakan objek yang dicari sejak awal.

### Bab 9 — Emil Post Sudah Menduganya Duluan
*Registry: NB-PER-xxx08 (Draft) — Emil Post*

Satu detail kecil layak diberi ruang tersendiri sebelum melangkah lebih jauh — bukan karena mengubah apa pun secara teknis, tapi karena ia menunjukkan sesuatu yang jarang terjadi dalam sejarah sains: antisipasi yang tepat, jauh sebelum buktinya tersedia.

Pada 1944 — sembilan tahun sebelum Konjektur Davis dirumuskan, dua puluh enam tahun sebelum Matiyasevich menutup celah terakhir — Emil Post, dalam sebuah makalah tentang himpunan rekursif, menulis dugaan bahwa masalah semacam PR-10 kemungkinan besar akan berakhir dengan pembuktian *unsolvability* (ketidakterselesaian), bukan penemuan algoritma. Post tidak punya kerangka Diophantine-eksponensial Robinson, tidak punya reduksi Davis-Putnam, tidak punya barisan Fibonacci Matiyasevich — ia cuma punya intuisi yang, retrospektif, ternyata tepat sasaran.

Kenapa ini layak dicatat: karena ia mengingatkan bahwa jalan menuju Bab 8 bukan proses linear yang jelas arahnya sejak awal. Di 1944, "PR-10 mungkin tak terpecahkan" masih terasa seperti spekulasi berani, bukan kesimpulan yang mendekati. Post melihat sesuatu yang benar sebelum alat untuk membuktikannya bahkan ada.

### Bab 10 — Undecidability sebagai Konsep, Bukan Cuma Hasil
*Registry: NB-CON-xxx10 (Draft, Field) — Undecidability*

Bab 4 sampai 9 membangun satu hasil spesifik: PR-10 tak terselesaikan. Tapi hasil itu adalah instansiasi dari sesuatu yang lebih besar — **undecidability** sebagai fenomena umum, kelas masalah yang secara struktural tak bisa diputuskan algoritma apapun, terlepas seberapa cerdik atau seberapa lama dicoba.

Entscheidungsproblem (Bab 4), Halting Problem (konsekuensi langsung konstruksi Turing di Bab 5), dan PR-10 (Bab 8) adalah tiga instansiasi konkret dari fenomena yang sama, ditemukan lewat tiga jalur teknis berbeda tapi berbagi mekanisme dasar yang berkerabat: representasi/pengkodean yang membuat sebuah sistem bisa "bicara tentang dirinya sendiri" atau "menyandikan" masalah lain yang sudah diketahui tak-decidable di dalam dirinya.

Inilah jawaban penuh atas pertanyaan yang dibuka Gerbang: janji "metode universal, jawaban pasti, waktu terbatas" itu bukan cuma belum ditemukan — untuk keluarga masalah tertentu, termasuk PR-10, janji semacam itu terbukti **tak bisa ditagih**, bukan karena kegagalan mencari, tapi karena struktur masalahnya sendiri menutup kemungkinan itu. Dengan pemahaman inilah narasi bisa melangkah maju: kalau ℤ sudah tertutup rapat, bagaimana dengan domain-domain lain?
## LAPISAN III — FRONTIER

### Bab 11 — Setelah 1970: Pertanyaan Berpindah ke ℚ
*Registry: NB-CON-xxx11 (Draft, Framework) — HTP atas ℚ (masih terbuka) · NB-RES-xxx04 (Draft, Theorem) — ℤ definabel *first-order* di ℚ (J. Robinson 1949, via teori Hasse-Minkowski utk bentuk kuadratik) · NB-RES-xxx05 (Draft, Jenis tentatif: "Conjecture" — lih. Lampiran) — Konjektur Mazur · NB-PER-xxx09 (Draft) — Barry Mazur · NB-PER-xxx10 (Draft) — Jochen Koenigsmann*

MRDP menutup pertanyaan untuk ℤ — tapi menutup satu pertanyaan sering membuka pertanyaan berikutnya yang bentuknya persis sama, cuma domainnya berpindah. Kalau tak ada algoritma umum untuk solvabilitas atas bilangan bulat, bagaimana dengan bilangan rasional (ℚ)? Ini **bukan** pertanyaan literal Hilbert 1900 (Bab 2 sudah menegaskan domain aslinya ℤ) — ini perluasan yang lahir belakangan, mewarisi semangat tapi bukan rumusan asli.

Yang menarik: benih jawabannya sudah ada bahkan sebelum pertanyaannya sendiri populer diajukan. Dalam disertasi PhD-nya di Berkeley tahun 1948 (setahun sebelum hipotesisnya sendiri di Bab 7), Julia Robinson menunjukkan, lewat teori Hasse-Minkowski untuk bentuk kuadratik, bahwa ℤ bisa didefinisikan secara *first-order* di dalam ℚ. Konsekuensinya: seluruh teori orde-pertama ℚ (bukan cuma pertanyaan solvabilitas Diophantine) juga tak-decidable — mewarisi ketakputusan ℤ lewat definisi itu.

Tapi ini belum cukup untuk HTP(ℚ) secara spesifik. Definisi *first-order* Robinson memakai kuantifikasi umum ("untuk semua", "ada") — sementara HTP secara ketat cuma butuh definisi **eksistensial murni** ("ada x sedemikian sehingga..."), jenis kuantifikasi yang persis cocok dengan bentuk persamaan Diophantine. Kalau definisi ℤ-di-dalam-ℚ Robinson bisa dipersempit dari first-order jadi eksistensial murni, HTP(ℚ) otomatis tereduksi ke HTP(ℤ) — sudah diketahui tak-decidable — dan pertanyaannya tertutup. Inilah tepatnya strategi yang dikejar dekade-dekade berikutnya: Jochen Koenigsmann pada 2016 mendekatkan celah ini lewat definisi *universal* (kuantifikasi "untuk semua" murni, tanpa "ada") — bukan eksistensial persis, tapi langkah signifikan menuju arah itu.

Menariknya, bukan semua matematikawan yakin strategi "persempit jadi eksistensial" ini akan berhasil. Barry Mazur, justru dengan nada yang ia sendiri sebut "contrarian" (1992), mengajukan konjektur yang **kalau benar justru menutup jalur ini**: closure topologis himpunan solusi rasional pada varietas apapun atas ℚ, dalam topologi Euclidean di ℝ, punya jumlah komponen terhubung berhingga. Kalau konjektur ini benar, konsekuensinya adalah ℤ **tidak bisa** didefinisikan secara Diophantine (eksistensial murni) di dalam ℚ sama sekali — artinya strategi "reduksi ke HTP(ℤ)" yang sedang dikejar sejak Robinson 1949 akan menemui jalan buntu struktural, bukan sekadar belum ditemukan buktinya. Konjektur Mazur karena itu bukan alat menuju jawaban PR-10(ℚ), melainkan pengingat bahwa arah jawabannya sendiri masih genuinely terbuka — bisa jadi undecidable lewat jalur lain, bisa jadi decidable, dua kemungkinan yang sama-sama belum tersingkirkan.

Sampai sumber paling akhir yang diverifikasi jendela ini (awal 2026), HTP(ℚ) **tetap terbuka** — bukan karena tak ada kemajuan, tapi karena celah antara "first-order" dan "eksistensial murni" itu masih belum genuinely tertutup.

### Bab 12 — Setengah Abad Perluasan: Ring dan Field Lain
*Registry: NB-CON-xxx12 (Draft, Method) — Generalisasi HTP ke ring/field lain · NB-PER-xxx11 (Draft) — Bjorn Poonen · NB-PER-xxx12 (Draft) — Jan Denef · NB-PER-xxx13 (Draft) — Alexandra Shlapentokh*

Sejalan dengan usaha menaklukkan ℚ, jalur riset lain sejak akhir 1970-an menempuh arah berbeda: alih-alih ℚ, bagaimana kalau ring atau field lain — ring bilangan bulat aljabar, ring fungsi, field p-adic? Jan Denef, Alexandra Shlapentokh, Thanases Pheidas, dan lainnya mengumpulkan hasil demi hasil parsial sepanjang 1980-2000an: sejumlah ring tertentu terbukti tak-decidable (mewarisi ketakputusan lewat definisi mirip strategi Bab 11), sementara ring lain masih menggantung.

Bjorn Poonen, sejak awal 2000-an, mempertajam alat teknisnya secara khusus: mengganti persamaan Pell (Bab 7, alat klasik utk menangkap pertumbuhan eksponensial) dengan kurva eliptik — objek yang jauh lebih kaya secara struktural, memungkinkan strategi *descent* (menurunkan pertanyaan definabilitas ke sifat-sifat aritmetika kurva itu sendiri) menjangkau kelas ring yang jauh lebih luas daripada yang bisa dicapai teknik Pell klasik.

Pola dari Bab 11-12 sudah mulai terlihat: setiap generalisasi butuh alat teknis yang lebih kaya dari generasi sebelumnya — Pell cukup untuk ℤ, kurva eliptik dibutuhkan untuk ring yang lebih umum. Pola inilah yang, dua dekade kemudian, akan meledak jadi terobosan yang menjawab bukan cuma satu ring tapi **seluruh kelas ring sekaligus**.

### Bab 13 — Terobosan 2024: Koymans dan Pagano
*Registry: NB-RES-xxx06 (Draft, Theorem) — Terobosan Koymans-Pagano (HTP tak-decidable utk semua ring finitely generated) · NB-CON-xxx13 (Draft, Technique) — Kombinatorika Aditif & Kurva Eliptik (tanpa pertumbuhan rank) · NB-PER-xxx14 (Draft) — Peter Koymans · NB-PER-xxx15 (Draft) — Carlo Pagano · NB-PER-xxx16 (Draft) — Wataru Kai*

Pada 2024, Peter Koymans dan Carlo Pagano mempublikasikan hasil yang menjawab bukan satu ring, bukan beberapa ring, tapi **seluruh kelas ring finitely generated sekaligus**: HTP tak-decidable untuk semua ring semacam itu. Ini lompatan skala yang jauh melampaui pola tambal-sulam Bab 12 — bukan menambah satu entri lagi ke daftar ring yang sudah terbukti, melainkan menutup seluruh kategori dengan satu argumen.

Mekanisme intinya menggabungkan dua bidang yang jarang bertemu: kombinatorika aditif (studi struktur himpunan bilangan lewat operasi penjumlahan) dan kurva eliptik yang secara khusus dipilih **tanpa pertumbuhan rank** — properti teknis yang memastikan konstruksi Diophantine yang dibutuhkan tetap terkendali di seluruh kelas ring target. Salah satu alat pendukung kunci berasal dari perluasan Teorema Green-Tao ke *number fields*, hasil yang dikerjakan Wataru Kai dan dikutip langsung dalam paper Koymans-Pagano.

Ini bukan cuma hasil matematis — ia juga jadi ukuran betapa jauh riset PR-10 sudah bergerak sejak 1970: dari satu domain tunggal (ℤ) yang butuh 17 tahun kerja kolektif untuk ditutup, ke seluruh kelas ring yang ditutup dalam satu paper.

### Bab 14 — Konfirmasi Independen: Alpöge-Bhargava-Ho-Shnidman
*Registry: NB-RES-xxx07 (Draft, Theorem) — Bukti independen kestabilan rank (2025) · NB-PER-xxx17 (Draft) — Levent Alpöge · NB-PER-xxx18 (Draft) — Manjul Bhargava · NB-PER-xxx19 (Draft) — Wei Ho · NB-PER-xxx20 (Draft) — Ari Shnidman*

Yang membuat konfirmasi berikutnya lebih meyakinkan lagi bukan cuma karena datang dari tim terpisah, tapi karena datang **secepat itu**: hanya sekitar dua bulan setelah preprint awal Koymans-Pagano dirilis (awal Desember 2024), tim terpisah — Levent Alpöge, Manjul Bhargava, Wei Ho, dan Ari Shnidman — mengunggah preprint mereka sendiri (30 Januari 2025) yang sampai pada hasil struktural sejalan, lewat metode independen yang juga bergantung pada kestabilan rank kurva eliptik, tapi dibangun dari jalur teknis berbeda (memakai hasil Wataru Kai yang sama sbg salah satu rujukan, tapi rute pembuktian yang tidak identik dengan Koymans-Pagano).

Nilai epistemik dari konfirmasi independen semacam ini melampaui sekadar "menambah satu bukti lagi": ketika dua tim, bekerja terpisah, memakai strategi teknis yang berbeda tapi sampai pada kesimpulan struktural yang sama, itu memperkuat kepercayaan terhadap hasil itu jauh melampaui apa yang bisa diberikan satu bukti tunggal — pola yang sama seperti kenapa konvergensi independen dihargai tinggi dalam proses verifikasi ilmiah manapun, termasuk proses penyusunan dokumen ini sendiri (lih. Aritmetika Presburger, Bab 16).

### Bab 15 — Kontras yang Sering Terlupakan: ℝ dan ℂ Justru *Decidable*
*Registry: Cross-reference NB-RES-0002 (Confirmed, dari PR-017) — Transfer Principle (Tarski, 1948), pemakaian ke-2 lintas-Problem · Cross-reference NB-PER-0004 (Confirmed) — Alfred Tarski*

Setelah empat bab yang seluruhnya berbicara soal *ketakputusan* — ℤ (Bab 8), kemungkinan besar ℚ (Bab 11), dan ring-ring lain (Bab 13-14) — satu kontras tajam layak ditegaskan sebelum melangkah ke refleksi penutup: pertanyaan analog PR-10 atas bilangan **real** (ℝ) atau **kompleks** (ℂ), alih-alih tak-decidable, justru terbukti **decidable** sepenuhnya.

Ini bukan kebetulan atau pengecualian kecil — ia konsekuensi langsung dari **Transfer Principle** Alfred Tarski (1948), hasil yang sudah dibahas mendalam di Jalur Eksplorasi PR-17 dalam konteks berbeda (representasi bentuk kuadratik sbg jumlah kuadrat). Tarski menunjukkan bahwa teori orde-pertama *real closed fields* (yang mencakup ℝ) punya prosedur eliminasi kuantifier yang lengkap — setiap pernyataan orde-pertama tentang ℝ, termasuk "apakah persamaan polinomial ini punya solusi", bisa diputuskan secara mekanis. Hasil paralel berlaku untuk ℂ lewat teori *algebraically closed fields*.

Kontras ini instruktif justru karena menunjukkan **di mana persis** garis antara decidable dan tak-decidable berada — bukan pada "persamaan polinomial" secara umum, melainkan spesifik pada domain solusi **bilangan bulat**. Begitu domainnya diperluas ke ℝ atau ℂ, struktur aljabar yang jauh lebih kaya (kepadatan, closure aljabar) justru membuat masalahnya lebih jinak, bukan lebih liar — kebalikan intuisi yang mungkin diharapkan siapa pun yang berpikir "domain lebih besar = lebih sulit diputuskan".

---

## LAPISAN IV — REFLEKSI

### Bab 16 — Status Modern
*Registry: NB-RES-xxx08 (Draft, Theorem) — Decidability Aritmetika Presburger (1929) · NB-PER-xxx21 (Draft) — Mojżesz Presburger · NB-CON-xxx14 (Draft, Method) — Formal Verification & Automated Reasoning · NB-PER-xxx22 (Draft) — Dominique Larchey-Wendling · NB-PER-xxx23 (Draft) — Yannick Forster*

Lebih dari lima dekade setelah 1970, riset di sekitar PR-10 tetap berjalan di beberapa jalur sekaligus, bukan menuju satu titik akhir tunggal. HTP(ℚ) tetap terbuka (Bab 11) — survei paling mutakhir yang diverifikasi jendela ini (makalah ekspositori Koymans-Pagano, awal 2026) merangkum status ini tanpa mengklaim penyelesaian. Terobosan ring finitely generated (Bab 13-14) tetap jadi hasil paling signifikan sejak MRDP itu sendiri.

Satu kontras layak ditambahkan di sini untuk menjawab pertanyaan yang sering muncul tanpa dijawab eksplisit: kenapa penjumlahan terasa "mudah" tapi perkalian membuka pintu ke ketakputusan? Mojżesz Presburger, pada 1929 — dua tahun sebelum Gödel, tujuh tahun sebelum Turing/Church — membuktikan bahwa aritmetika bilangan asli dengan **hanya penjumlahan** (tanpa perkalian) bersifat *decidable* sepenuhnya. Begitu perkalian ditambahkan — persis yang dibutuhkan untuk merumuskan persamaan Diophantine derajat tinggi — sistemnya berubah tak-decidable. Presburger memberi garis pemisah paling tajam dan paling awal untuk pertanyaan itu, jauh mendahului Gödel maupun MRDP.

Di sisi lain riset modern, bukti MRDP sendiri sudah diverifikasi ulang memakai *proof assistant* formal — Dominique Larchey-Wendling dan Yannick Forster memformalkan bukti lengkap "H10 dalam Coq", memastikan tak ada celah logis tersembunyi di jalur pembuktian aslinya, jenis verifikasi yang baru mungkin dilakukan berkat perkembangan alat pembuktian otomatis dekade-dekade terakhir. Riset di batas ini terus berjalan — sampai saat dokumen ini disusun, bahkan muncul hasil yang menghubungkan PR-10 dengan area logika lain (Rice's theorem) lewat bukti konstruktif terformalkan, diterbitkan begitu belakangan sehingga berada tepat di tepi jangkauan verifikasi jendela ini sendiri.

### Bab 17 — Jembatan ke Problem #2: Satu Krisis, Dua Wajah
*Registry: Cross-reference NB-CON-0025 (Confirmed, dari PR-002) — Program Hilbert, pemakaian ke-3 (PR-017 tidak memakainya, jadi ke-2 aktual: PR-002 → PR-010) · Cross-reference NB-RES-0011, NB-RES-0012 (Confirmed, dari PR-002) — Teorema Ketaklengkapan Gödel · Cross-reference NB-CON-xxx02 (internal, Bab 4 PR-10 ini sendiri) — Entscheidungsproblem · Cross-reference NB-PER-0001, NB-PER-0011 (Confirmed) — Hilbert, Gödel*

Jalur Eksplorasi PR-2 (Konsistensi Aritmetika) menutup Bab 19-nya dengan sebuah catatan terbuka: kandidat jembatan resmi ke PR-10, lewat Entscheidungsproblem dan Turing 1936, dicatat tapi belum dieksekusi — menunggu siklus PR-10 berjalan. Bab ini adalah eksekusi resminya, dari sisi PR-10.

Kedua Problem — PR-2 dan PR-10 — tampak sama sekali berbeda di permukaan. PR-2 bertanya apakah aritmetika bisa membuktikan konsistensinya sendiri; PR-10 bertanya apakah ada algoritma untuk solvabilitas Diophantine. Tapi keduanya jatuh lewat mekanisme yang berkerabat dekat, dan Entscheidungsproblem (Bab 4) adalah titik sambung historisnya yang literal: Teorema Ketaklengkapan Gödel (1931, jantung PR-2) memakai teknik pengkodean — mengubah pernyataan *tentang* sistem formal jadi pernyataan *di dalam* sistem formal itu sendiri — yang secara langsung menginspirasi pendekatan Turing menjawab Entscheidungsproblem lima tahun kemudian (1936). Dan jawaban Turing itulah yang, lewat definisi presisi "algoritma" yang dihasilkannya, menjadi prasyarat mutlak sebelum PR-10 bisa dijawab sama sekali (Bab 5).

Dengan kata lain: PR-2 tidak menjawab PR-10 secara langsung, tapi krisis yang dipicunya — dan alat teknis yang lahir dari krisis itu — adalah rantai kausal nyata menuju jawaban PR-10. Program Hilbert yang sama, diajukan dalam semangat optimisme yang sama (Bab 3), berakhir dengan dua kegagalan berkerabat di dua front berbeda: satu soal konsistensi pembuktian, satu soal keberadaan algoritma. Keduanya, pada akhirnya, adalah dua wajah dari satu krisis yang sama terhadap batas formalisme.

### Bab 18 — Dampak Filosofis

Kembali ke Gerbang: janji "metode universal, jawaban pasti, waktu terbatas" terbukti tak bisa ditagih — bukan cuma untuk PR-10, tapi (Bab 10) untuk seluruh kelas masalah yang berbagi struktur serupa. Ironi yang dibuka Bab 3 akhirnya terbayar penuh: "Wir müssen wissen, wir werden wissen" terwujud lewat jalan yang persis kebalikan dari yang diharapkan Hilbert — kita memang sampai *tahu*, tapi yang kita ketahui adalah ketidakmungkinan, bukan penemuan.

Status PR-10 juga layak dibedakan tegas dari problem Hilbert lain yang sering disandingkan keliru sbg "sama-sama tak terputuskan". Hipotesis Kontinum (PR-1) terbukti *independen dari ZFC* — pernyataan yang tak bisa dibuktikan maupun dibantah dari sistem aksioma tertentu, tapi ini soal batas satu sistem aksioma spesifik, bisa berbeda kalau aksioma diperluas. PR-10 tak-decidable dalam pengertian berbeda sama sekali: tak ada algoritma yang bisa menjawabnya, terlepas sistem aksioma manapun yang dipakai untuk membuktikan ketakputusan itu sendiri — dua jenis "tak terputuskan" yang gampang tertukar tapi secara teknis dari cabang matematika berbeda (teori model/proof theory vs teori komputabilitas).

Satu kontras populer terakhir layak diluruskan eksplisit, karena berpotensi mengaburkan makna PR-10 kalau dibiarkan implisit: **P vs NP** — pertanyaan besar lain abad ke-21 — sering disandingkan dengan PR-10 seolah keduanya soal yang sama. Bukan. PR-10 bertanya apakah algoritma untuk solvabilitas Diophantine **ada sama sekali**; P vs NP mengandaikan algoritma-algoritma tertentu memang **sudah ada**, dan bertanya soal **efisiensinya** — apakah masalah yang solusinya mudah diverifikasi juga mudah *ditemukan*. Keduanya soal batas komputasi, tapi di sumbu yang sama sekali berbeda: eksistensi versus efisiensi. Kekeliruan serupa juga layak diwaspadai untuk klaim populer bahwa komputasi kuantum "mengubah" status ketakputusan PR-10 — secara teknis, komputasi kuantum mengubah kelas kompleksitas (apa yang bisa dihitung *cepat*), bukan batas *decidability* (apa yang bisa dihitung sama sekali); tak ada mekanisme yang membuat kuantum relevan bagi hasil Bab 8. Batas yang ditunjukkan MRDP bersifat absolut terhadap model komputasi apapun yang setara Tesis Church-Turing — klasik maupun kuantum.

Dengan itu, Problem #10 Hilbert — diajukan sebagai permintaan satu prosedur — berkembang jadi sesuatu yang jauh melampaui jawaban ya/tidak yang dicari Hilbert sendiri: peta yang terus diperluas tentang persis di mana batas algoritmik berada, batas yang ternyata bukan kegagalan sementara pengetahuan manusia, melainkan struktur matematis yang bisa dipelajari, diperluas ke domain baru (Lapisan III), dan — seperti riset yang masih berjalan saat dokumen ini ditulis — belum selesai dipetakan sepenuhnya.

---

## Penutup

Draft Usulan MVC PR-10 selesai — Gerbang + 18 bab dalam 4 Lapisan, dari Diophantus abad ke-3 sampai riset yang masih berjalan di 2026. Seluruh 20 topik Keep:Primer dari Fase 1 tereksekusi jadi bab atau bagian substantif sebuah bab; topik Keep:Sekunder dianyam sbg materi pendukung (Persamaan Pell, Barisan Fibonacci, Kalkulus Lambda, Reduksi Davis-Putnam, dll. — semuanya muncul di bab yang relevan, bukan didaftar terpisah). Dua Named Bridge dieksekusi: PR-2↔PR-10 (Bab 17, sudah "dipesan" sejak PR-002 ditulis) dan PR-17↔PR-10 (Bab 15, ditemukan baru selama penyusunan draft ini — Transfer Principle Tarski dipakai dua kali di dua Problem berbeda).

**Status:** Draft — belum lulus Prosedur Audit Registry 5-Langkah, belum Seam Audit penuh (lihat Lampiran), belum disinkronkan ke Atlas Master. Siap lanjut ke audit registry formal atau Fase 3 (Verifikasi Mandiri), sesuai arahan.
## Lampiran — Registry (Draft, Placeholder)

*Seluruh ID `xxx` di bawah adalah placeholder internal dokumen ini — bukan nomor final. Penomoran definitif menunggu Prosedur Audit Registry 5-Langkah resmi (Atlas Master, Prinsip Proses).*

### Notebook Konsep (14 baru — semua Draft, Cluster B+F mengikuti Problem Registry PR-010)

| ID | Nama | Jenis | Muncul di |
|---|---|---|---|
| NB-CON-xxx01 | Persamaan Diophantine | Object | Bab 1 |
| NB-CON-xxx02 | Entscheidungsproblem | Framework | Bab 4, 17 |
| NB-CON-xxx03 | Teori Komputabilitas (Mesin Turing) | Field | Bab 5 |
| NB-CON-xxx04 | Kalkulus Lambda | Technique | Bab 5 |
| NB-CON-xxx05 | Tesis Church-Turing | Theory | Bab 5 |
| NB-CON-xxx06 | Persamaan Diophantine Eksponensial | Object | Bab 7 |
| NB-CON-xxx07 | Persamaan Pell | Technique | Bab 7 |
| NB-CON-xxx08 | Barisan Fibonacci (alat teknis MRDP) | Technique | Bab 7, 8 |
| NB-CON-xxx09 | Reduksi Davis-Putnam (bentuk normal 1961) | Technique | Bab 8 |
| NB-CON-xxx10 | Undecidability | Field | Bab 10, 17, 18 |
| NB-CON-xxx11 | HTP atas ℚ (masih terbuka) | Framework | Bab 11 |
| NB-CON-xxx12 | Generalisasi HTP ke ring/field lain | Method | Bab 12 |
| NB-CON-xxx13 | Kombinatorika Aditif & Kurva Eliptik (tanpa pertumbuhan rank) | Technique | Bab 13, 14 |
| NB-CON-xxx14 | Formal Verification & Automated Reasoning | Method | Bab 16 |

**Catatan Jenis "Object" ganda (xxx01, xxx06)**: dipertahankan terpisah, bukan digabung — persamaan Diophantine biasa (polinomial) dan persamaan Diophantine eksponensial adalah dua kelas objek matematis berbeda, bedanya justru krusial secara naratif (Bab 7 menjelaskan mengapa perluasan eksponensial dibutuhkan).

### Notebook Hasil Besar (8 baru)

| ID | Nama | Jenis | Tahun | Tokoh | Muncul di |
|---|---|---|---|---|---|
| NB-RES-xxx01 | Konjektur Davis | **tentatif "Conjecture"** ⚠ | 1953 | Martin Davis | Bab 6 |
| NB-RES-xxx02 | Hipotesis Julia Robinson | **tentatif "Conjecture"** ⚠ | ~1950-an | Julia Robinson | Bab 7 |
| NB-RES-xxx03 | Teorema MRDP | Theorem | 1970 | Davis, Putnam, Robinson, Matiyasevich | Bab 8 |
| NB-RES-xxx04 | ℤ definabel *first-order* di ℚ | Theorem | 1949 | Julia Robinson | Bab 11 |
| NB-RES-xxx05 | Konjektur Mazur | **tentatif "Conjecture"** ⚠ | ~1990-an | Barry Mazur | Bab 11 |
| NB-RES-xxx06 | Terobosan Koymans-Pagano | Theorem | 2024 | Koymans, Pagano | Bab 13 |
| NB-RES-xxx07 | Bukti independen kestabilan rank (ABHS) | Theorem | 2025 | Alpöge, Bhargava, Ho, Shnidman | Bab 14 |
| NB-RES-xxx08 | Decidability Aritmetika Presburger | Theorem | 1929 | Mojżesz Presburger | Bab 16 |

**⚠ Catatan vocab (3 entri, Bab 6/7/11)**: "Konjektur Davis", "Hipotesis Julia Robinson", dan "Konjektur Mazur" tak cocok bersih ke vocab resmi manapun (`Theorem · Lemma · Counterexample · Independence Result · Construction · Classification · Algorithm`) — ketiganya adalah **dugaan/hipotesis SEBELUM terbukti**, sebuah tahap historis berbeda dari hasil final (Konjektur Davis+Hipotesis J.R. digabung MENJADI Teorema MRDP begitu terbukti 1970; Konjektur Mazur belum/tidak terbukti). Vocab saat ini tak punya kategori utk tahap pra-bukti semacam ini. **Tidak dipaksakan** ke kategori terdekat — dicatat di sini sbg kandidat perluasan vocab Tier 2 (mis. Jenis baru "Conjecture"), persis preseden "Axiom" utk AC di PR-001 (ditunda sampai ada Problem lain yg mengonfirmasi kebutuhan yg sama).

**Catatan Jenis "Theorem" utk MRDP (xxx03)**: sengaja **bukan** "Independence Result" meski itu tag tentatif yang sempat dicatat Atlas §6 — lihat alasan lengkap di `PR-10_Analisis_Topik.md` Fase 1.5 §B (preseden Ketaklengkapan Gödel, NB-RES-0011/0012, diregistrasi Theorem biasa meski juga hasil "impossibility").

### Notebook Tokoh (23 baru)

| ID | Nama | Kontribusi | Tahun | Era | Muncul di |
|---|---|---|---|---|---|
| NB-PER-xxx01 | Diophantus | Kumpulan soal *Arithmetica*, asal-usul nama persamaan Diophantine | ~250 M | Classical | Bab 1 |
| NB-PER-xxx02 | Alan Turing | Mesin Turing, jawab negatif Entscheidungsproblem | 1936 | Modern | Bab 5 |
| NB-PER-xxx03 | Alonzo Church | Kalkulus-λ, formalisasi computability jalur independen | 1936 | Modern | Bab 5 |
| NB-PER-xxx04 | Martin Davis | Konjektur 1953; reduksi bersama Putnam-Robinson 1961 | 1953, 1961 | Modern → Contemporary | Bab 6, 7 |
| NB-PER-xxx05 | Julia Robinson | Hipotesis eksponensial; ℤ-di-ℚ 1949 | 1949, 1950-an | Modern | Bab 7, 11 |
| NB-PER-xxx06 | Hilary Putnam | Reduksi bentuk normal bersama Davis-Robinson | 1961 | Modern → Contemporary | Bab 7 |
| NB-PER-xxx07 | Yuri Matiyasevich | Menutup celah eksponensial via Fibonacci, bukti final MRDP | 1970 | Modern → Contemporary | Bab 8 |
| NB-PER-xxx08 | Emil Post | Antisipasi unsolvability PR-10 | 1944 | Modern | Bab 9 |
| NB-PER-xxx09 | Barry Mazur | Konjektur closure topologis solusi rasional | ~1990-an | Contemporary | Bab 11 |
| NB-PER-xxx10 | Jochen Koenigsmann | Definisi universal ℤ di ℚ | 2016 | Contemporary | Bab 11 |
| NB-PER-xxx11 | Bjorn Poonen | Teknik kurva eliptik/descent utk generalisasi HTP | sejak ~2000-an | Contemporary | Bab 12 |
| NB-PER-xxx12 | Jan Denef | Hasil parsial HTP ring/field lain | sejak akhir 1970-an | Modern → Contemporary | Bab 12 |
| NB-PER-xxx13 | Alexandra Shlapentokh | Hasil parsial HTP ring/field lain | 1990-2000an | Contemporary | Bab 12 |
| NB-PER-xxx14 | Peter Koymans | Terobosan HTP ring finitely generated | 2024 | Contemporary | Bab 13 |
| NB-PER-xxx15 | Carlo Pagano | Terobosan HTP ring finitely generated | 2024 | Contemporary | Bab 13 |
| NB-PER-xxx16 | Wataru Kai | Perluasan Teorema Green-Tao ke number fields, dipakai Koymans-Pagano & ABHS | 2023 | Contemporary | Bab 13 |
| NB-PER-xxx17 | Levent Alpöge | Bukti independen kestabilan rank | 2025 | Contemporary | Bab 14 |
| NB-PER-xxx18 | Manjul Bhargava | Bukti independen kestabilan rank | 2025 | Contemporary | Bab 14 |
| NB-PER-xxx19 | Wei Ho | Bukti independen kestabilan rank | 2025 | Contemporary | Bab 14 |
| NB-PER-xxx20 | Ari Shnidman | Bukti independen kestabilan rank | 2025 | Contemporary | Bab 14 |
| NB-PER-xxx21 | Mojżesz Presburger | Decidability aritmetika penjumlahan-saja | 1929 | Modern | Bab 16 |
| NB-PER-xxx22 | Dominique Larchey-Wendling | Formalisasi "H10 in Coq" | ~2019+ | Contemporary | Bab 16 |
| NB-PER-xxx23 | Yannick Forster | Formalisasi "H10 in Coq" | ~2019+ | Contemporary | Bab 16 |

### Cross-reference ke Problem Lain (Prinsip #1 & #3)

| Node existing | Dari Problem | Update `Terkait Problem` | Muncul di bab ini |
|---|---|---|---|
| NB-CON-0025 (Program Hilbert) | PR-002 | `PR-002, PR-010` | Bab 2, 17 |
| NB-PER-0001 (David Hilbert) | global | `+= PR-010` | Bab 2, 3, 17 |
| NB-RES-0011, NB-RES-0012 (Ketaklengkapan Gödel) | PR-002 | `PR-002, PR-010` | Bab 5, 17 (disebut, tak diderivasi ulang) |
| NB-PER-0011 (Kurt Gödel) | PR-001, PR-002 | `PR-001, PR-002, PR-010` | Bab 5, 17 |
| **NB-RES-0002 (Transfer Principle, Tarski 1948)** | **PR-017** | `PR-017, PR-010` | **Bab 15 — Named Bridge BARU, ditemukan selama penyusunan draft ini, bukan dipesan sebelumnya** |
| NB-PER-0004 (Alfred Tarski) | PR-017 | `PR-017, PR-010` | Bab 15 |

**Named Bridge #2↔#10 (Bab 17)**: eksekusi resmi dari kandidat yang sudah dicatat PR-002 Bab 19. Jalur teknis: Ketaklengkapan Gödel → teknik pengkodean yang menginspirasi Turing → Entscheidungsproblem terjawab negatif → definisi "algoritma" presisi → prasyarat PR-10 bisa dijawab.

**Named Bridge #17↔#10 (Bab 15) — temuan baru**: Transfer Principle Tarski dipakai PR-17 utk representasi bentuk kuadratik, dipakai PR-10 utk membuktikan kontras ℝ/ℂ decidable. Sah sbg Named Bridge (Prinsip #3) karena memakai teorema bernama yang sama secara teknis, bukan cuma kesamaan tokoh.

### Kandidat Belum Diregistrasi

| Nama/Topik | Kenapa ditahan |
|---|---|
| Emil du Bois-Reymond | Kontribusi nyata (frasa "ignorabimus", ~1872) tapi perannya di Bab 3 murni foil retoris satu-kalimat — tahan sampai ada Problem lain yg mengelaborasi lebih dalam |
| Jonathan Brossard | Paper 2026 terverifikasi asli (Fase 1 Bagian B) tp disebut cuma sekilas di Bab 16 — terlalu niche utk entri penuh di MVC awal; kandidat kuat kalau bab diperluas |
| Post's Correspondence Problem | Dianggap Optional di Fase 1 — disinggung Bab 9 hanya via nama Emil Post pribadi, PCP sbg konsep terpisah tak dimasukkan |
| Kurva eliptik sbg objek matematis umum | Disebut berulang (Bab 12-14) tp selalu dlm konteks teknik spesifik (descent, rank) — kandidat entri Object tersendiri kalau bab diperluas mendalam |

### Catatan Seleksi (28 topik Optional dari Fase 1 — sengaja tidak masuk draf)

Dikelompokkan per alasan, bukan didaftar 28 baris (demi kepadatan lampiran ini sendiri):

- **Analogi retoris tanpa mekanisme teknis** (Teorema Empat Warna, prinsip ketidakpastian Heisenberg) — ilustratif tp tak menambah argumen; Heisenberg khususnya berisiko konflasi kalau dielaborasi (sudah ditandai ⚠ sejak Fase 1).
- **Aplikasi tangensial modern** (RSA, Blockchain, Kriptografi Pasca-Kuantum, Kriptografi & Persamaan Diophantine aplikasi, SMT/SAT, Computer algebra, Zero-knowledge proofs, Komputasi Kuantum, PR-10 & AI modern) — relevansi+konsensus rendah; dua yg paling berisiko disalahpahami (Kuantum, AI) sengaja **tetap disinggung** di Bab 18 justru utk meluruskan miskonsepsi, bukan diabaikan total.
- **Perbandingan lintas-Problem yang tak memenuhi Prinsip #3** (Problem #6, #8, hubungan dgn #7) — kaitan tematik longgar, tak ada teorema/metode bernama yg dipakai ulang secara teknis, jadi tak dieksekusi sbg Named Bridge (beda dari #2 dan #17 yg memenuhi syarat).
- **Cabang matematika bertetangga tanpa dipakai mekanisme argumen** (Teori Bilangan Analitik/Transendental/Komputasional/Kategori/Automata, Word Problem for Groups, Tate-Shafarevich, Teorema Roth, abc conjecture, dll.) — nyata sbg cabang tp tak ada jalur teknis langsung ke narasi PR-10 yg dibangun draft ini.
- **Detail bibliografis/dekoratif** (judul asli "Mathematische Probleme", Teorema Fermat Kecil, Pendekatan Sistematis Grechuk) — presisi historis yg bagus tp tak menambah substansi argumen.
- **Label generik yg sudah dianggap alias/tumpang-tindih** (Teori Bilangan bidang umum, Aksioma Peano, Filsafat matematika: batas pengetahuan, Matiyasevich's theorem, Teorema DPR) — sudah diberi status alias eksplisit di Fase 1 Keputusan Editorial §4, tak perlu bab/entri terpisah.

*(Total 28 Optional Fase 1 tercakup lewat 6 kelompok alasan di atas — cross-check: 2+9+3+9+3+5=31, sedikit melebihi 28 krn beberapa item disebut di >1 kelompok, mis. abc conjecture juga bisa masuk "cabang bertetangga"; tidak dihitung ulang presisi di sini krn tujuannya transparansi alasan, bukan akuntansi baris.)*

### Catatan Audit Jahitan (Seam Audit)

**Tier A — audit penuh (transisi antar-Lapisan, wajib):**

| Seam | Penutup N | Pembuka N+1 | Pola |
|---|---|---|---|
| Bab 3→4 (Fondasi→Revolusi) | Deklaratif, menutup tema optimisme-terbalik | Menoleh balik eksplisit ke "optimisme Hilbert" | **B (Backward)** |
| Bab 10→11 (Revolusi→Frontier) | Bertanya eksplisit: "bagaimana dengan domain-domain lain?" | Menjawab langsung: "bagaimana dengan ℚ?" | **A (Forward)** |
| Bab 15→16 (Frontier→Refleksi) | Deklaratif, menutup kontras ℝ/ℂ | Mensintesis seluruh Lapisan III ("riset di sekitar PR-10 tetap berjalan di beberapa jalur"), bukan cuma mewarisi Bab 15 | **C (Synthesis)** |

Ketiga seam antar-lapisan lolos klasifikasi bersih — tak ada kandidat patch di titik ini.

**Tier B — sanity-check cepat (seam intra-Lapisan):** ditinjau sekilas seluruh 14 seam intra-Lapisan tersisa (Bab1→2, 2→3, 4→5, 5→6, 6→7, 7→8, 8→9, 9→10, 11→12, 12→13, 13→14, 14→15, 16→17, 17→18) — semuanya punya kalimat penutup/pembuka yang saling merujuk (pola A atau B), tak ditemukan seam yang netral di kedua sisi. Karena dokumen ini draft pertama (belum ada bab yg "disisipkan belakangan"), tak ada seam berisiko-tinggi tambahan di luar 3 titik Tier A.
