# Usulan Patch — Skill `hilbert-sintesa`

**Status:** Usulan, belum diterapkan. Mengikuti semangat Prinsip Proses Atlas Master ("tidak ada perubahan arsitektur tanpa ditemukan kegagalan nyata saat implementasi") — tiap baris di bawah punya pemicu konkret dari siklus PR-10, bukan sekadar "kelihatannya lebih rapi". Kalau disetujui, cara paling wajar mengeksekusinya adalah lewat skill `skill-creator` yang sudah tersedia di environment — saya sengaja tidak mengedit langsung file skill di `/mnt/skills/plugins/hilbert-sintesa/`, karena ini aset bersama di luar satu siklus PR, konsisten dgn pola "usulkan dulu, jangan ubah sepihak" yang sudah dipegang proyek ini sendiri.

---

## Ringkasan (gaya tabel Pemicu, meniru Riwayat Versi Atlas Master)

| # | File Target | Perubahan | Pemicu Konkret dari Siklus PR-10 |
|---|---|---|---|
| P1 | `format-analisis-topik.md` | Rubrik eksplisit Relevansi + formula mekanis Rekomendasi | Dua jendela independen (W1-lama, W1-baru) menilai 98 topik identik, **44% Rekomendasi berbeda** — bukan krn beda fakta, krn tak ada rubrik bersama |
| P2 | `format-analisis-topik.md` | Pensiunkan "Evaluasi Ulang" jadi 4 tag overlay (bukan 1 kategori ke-4) | Kedua jendela sama-sama salah pakai label ini utk 3 makna berbeda (lemah-relevansi / risiko-konflasi / tumpang-tindih-granularitas / **ragu-akurasi** — makna asli skill sendiri) |
| P3 | `format-analisis-topik.md` | Wajib penunjukan primary/alias eksplisit utk pasangan duplikat kanonik | W1-lama biarkan pasangan Peano simetris "tunggu pemasangan"; W1-baru bikin keputusan sepihak — dua pendekatan berbeda tanpa arahan, menambah kerja rekonsiliasi yang tak perlu |
| P4 | `format-analisis-topik.md` | Cross-check terprogram kolom Konsensus **wajib sebelum finalisasi**, bukan opsional | Baris "Teorema Fermat Terakhir" (Konsensus tertukar 8/12↔3/12) lolos dari PENULISAN AWAL + REVISI EDITORIAL PUTARAN KEDUA — baru ketahuan lewat jendela audit eksternal terpisah (putaran ketiga) |
| P5 | `format-verifikasi-mandiri.md` | Ringkasan angka di kepala dokumen wajib dihitung ulang programatik, bukan ditulis dari ingatan saat mengetik intro | Ledger yang isinya soal verifikasi klaim ternyata menyimpan klaim ringkasannya SENDIRI yang salah hitung ("~55" vs aktual 48; "2" vs aktual 6) — ironi yang baru ketahuan lewat audit eksternal, bukan self-review |
| P6 | `format-verifikasi-mandiri.md` | Tandai eksplisit "klaim jahitan naratif" (transisi/framing/arah sebab-akibat) sbg kategori risiko tertinggi | Dari 4 klaim yg terbantahkan di Fase 3, **4/4 adalah detail yang ditambahkan sendiri demi kelancaran prosa** (bukan diwariskan data upstream) — pola 100%, bukan kebetulan |
| P7 | `format-draft-mvc.md` | Prompt eksplisit "pindai Named Bridge baru", bukan cuma eksekusi bridge yang sudah dipesan Problem lain | Jembatan PR-17↔PR-10 (Transfer Principle Tarski) ditemukan murni oportunistik saat menulis Bab 15 — skill saat ini cuma menuntun eksekusi bridge yang SUDAH diflag Problem lain, tak menuntun pencarian aktif bridge baru |
| P8 | `timing-atlas.md` | Panduan eksplisit: status "belum matang" sebuah Cluster taksonomi (mis. Cluster G) tak otomatis mengubah Rekomendasi topik-level | Ketegangan Cluster G (P vs NP/AI/Kuantum/Kripto "berakar tematik dari PR-10") vs Rekomendasi Optional saya berhasil diselesaikan dgn penalaran ad hoc — tapi tanpa panduan tertulis, jendela lain bisa menyimpulkan sebaliknya |
| P9 | `SKILL.md` | Dokumentasikan pola "audit lintas-jendela" sbg praktik dianjurkan (bukan wajib) + checklist ringan | 2 dari 3 lapis audit di siklus ini (perbandingan W1-lama, audit eksternal terpisah) menangkap error nyata yang lolos dari self-review berulang kali; pola ini terbukti bernilai tinggi tapi tak terdokumentasi sbg praktik resmi |

---

## Detail per Patch

### P1 — Rubrik eksplisit Relevansi + formula Rekomendasi

**Tempel di `format-analisis-topik.md`, menggantikan/melengkapi definisi Relevansi & Rekomendasi yang sudah ada:**

> **Tes Relevansi** — tanyakan: *"Kalau topik ini dihapus total dari bab, apakah argumen inti Problem ini masih solid dan lengkap secara logis?"* Tidak → **Tinggi**. Bab tetap solid tapi kehilangan pengayaan signifikan → **Sedang**. Bab tak terasa kehilangan apa pun → **Rendah**.
>
> **Formula Rekomendasi** (mekanis, bukan judgment terpisah):
> ```
> Relevansi = Tinggi                      → Keep: Primer
> Relevansi = Sedang                      → Keep: Sekunder
> Relevansi = Rendah DAN Konsensus ≥ 4/N  → Keep: Sekunder
> Relevansi = Rendah DAN Konsensus < 4/N  → Optional
> ```
> (N = jumlah AI sumber Baseline Sintesa; ambang "4" default, boleh disesuaikan per siklus kalau N jauh beda dari 12 — dicatat eksplisit kalau diubah.)
>
> **Prinsip turunan:** hasil/definisi yang LANGSUNG menjadi bagian jawaban Problem dinilai Tinggi; MEKANISME TEKNIS di baliknya yang mendukung tapi bukan hasil itu sendiri dinilai Sedang. Ini disengaja — supaya Primer tetap ramping berisi hasil inti, bukan menggembung berisi seluruh alat pendukungnya.

**Kenapa ini penting:** tanpa rubrik ini, dua penilai yang sama-sama teliti bisa mendarat di kesimpulan berbeda utk >40% topik pada dataset yang identik — bukan krn salah satu ceroboh, tapi krn "Relevansi Sedang vs Rendah" adalah ambang subjektif tanpa tes yang bisa diulang.

### P2 — Rekomendasi: 3 level wajib + hingga 4 tag overlay opsional

**Ganti kategori "Evaluasi Ulang" (kategori ke-4) dengan definisi berikut:**

> Rekomendasi SELALU salah satu dari 3 level: `Keep: Primer` / `Keep: Sekunder` / `Optional`. Level ini BOLEH ditempeli 0–2 tag overlay (independen dari level, tidak menggantikannya):
> - **`⚠ Cek Akurasi`** — makna ASLI "Evaluasi Ulang": sumber tunggal mencurigakan atau premis tampak keliru, akurasi perlu dicek sebelum dianggap settled.
> - **`⚠ Risiko Konflasi`** — topik valid disebut tapi gampang disalahpahami/di-overclaim tanpa penjelasan hati-hati (mis. istilah populer yang mirip tapi beda level teknis).
> - **`⚠ Cek Granularitas`** — kemungkinan alias/tumpang-tindih kanonik dgn topik lain di tabel yang sama.

**Kenapa ini penting:** ditemukan langsung di siklus ini — dua jendela independen sama-sama salah pakai "Evaluasi Ulang" untuk makna yang BUKAN definisi aslinya (dipakai utk "topik lemah" bukan "akurasi meragukan"), krn satu label dipaksa menampung 3-4 kebutuhan berbeda yang sebenarnya orthogonal satu sama lain.

### P3 — Pasangan duplikat kanonik wajib diberi penunjukan eksplisit

> Kalau ditemukan 2+ baris di superset yang diduga merujuk hal yang sama (varian nama/istilah), Fase 1 **wajib** menunjuk satu sbg kanonik-primer dan sisanya sbg alias (tag `⚠ Cek Granularitas`) — **jangan** membiarkan status keduanya setara "menunggu pemasangan". Penunjukan ini boleh dikoreksi lagi saat pemasangan lintas-jendela kalau jendela lain tak setuju — tapi harus ada keputusan eksplisit dulu, bukan dibiarkan menggantung.

**Kenapa ini penting:** membiarkan status setara terasa "aman" (tidak mendahului keputusan), tapi sebenarnya cuma memindahkan keputusan yang sama ke tahap pemasangan yang justru lebih ramai variabelnya (banyak jendela sekaligus) — lebih murah diputuskan (dan dikoreksi kalau perlu) satu-jendela-satu-waktu.

### P4 — Cross-check terprogram Konsensus, wajib sebelum baris dianggap final

> Sebelum Bagian B Fase 1 dianggap selesai (dan sebelum revisi editorial apa pun berdasarkan angka Konsensus tertentu), jalankan pencocokan terprogram: untuk setiap baris, bandingkan nama kanonik + angka Konsensus yang ditulis di tabel terhadap Sheet "Konsensus 12 AI" mentah — bukan mengandalkan baca-manual saat menyalin 90+ baris. Kesalahan lirik-baris-tetangga (nama Tokoh vs nama Topik yang mirip/berdekatan) adalah pola galat yang realistis pada tabel sebesar ini.

**Kenapa ini penting:** ini persis kegagalan W1-T1 — lolos dari penulisan awal DAN dari revisi editorial (yang bahkan secara eksplisit MENGUTIP angka Konsensus itu sbg justifikasi keputusan), baru ketahuan di audit independen ketiga. Satu skrip pencocokan 10 baris kode akan menangkap ini seketika, di titik termurah utk memperbaikinya.

### P5 — Ringkasan angka Verifikasi Mandiri wajib dihitung ulang programatik

> Kalimat ringkasan hasil di kepala `*_Verifikasi_Mandiri.md` (jumlah klaim, jumlah per status) **wajib** dihasilkan dari penghitungan terprogram terhadap ledger yang sudah ditulis — ditulis TERAKHIR, setelah ledger lengkap, bukan diperkirakan sambil mengetik pembuka dokumen.

**Kenapa ini penting:** siklus ini menghasilkan ironi yang layak jadi pelajaran eksplisit — dokumen yang seluruh isinya tentang mendisiplinkan verifikasi klaim, gagal menerapkan disiplin yang sama ke klaim ringkasannya sendiri, dan itu lolos dari review penulis sendiri.

### P6 — Tandai "klaim jahitan naratif" sbg kategori risiko tertinggi

**Tambahkan ke bagian metodologi `format-verifikasi-mandiri.md`:**

> Saat menyisir klaim faktual, beri prioritas lebih tinggi pada **klaim yang berfungsi sbg jahitan naratif** — kalimat yang menghubungkan dua fakta lewat klaim arah/sebab-akibat/perbandingan ("X mencerminkan Y", "disusun sesuai Z", "terjadi setahun setelah W", "mendukung dugaan bahwa...") — dibanding klaim atomik (satu tanggal, satu nama, disalin langsung dari tabel sumber). Klaim jahitan naratif secara empiris (siklus PR-10: 4 dari 4 klaim terbantahkan adalah jenis ini) lebih berisiko krn ditulis untuk membuat prosa mengalir, bukan disalin dari data yang sudah diverifikasi upstream — penulis (termasuk model bahasa) cenderung mengisi kesenjangan naratif dgn sesuatu yang *terasa* logis tanpa sadar sedang membuat klaim faktual baru.

**Kenapa ini penting:** ini temuan paling bernilai dari seluruh Fase 3 siklus ini — pola 100% (4/4), bukan anekdot tunggal. Kalau berulang di siklus PR lain, ini pantas dianggap prinsip umum, bukan kebetulan satu siklus.

### P7 — Prompt eksplisit pemindaian Named Bridge baru

**Tambahkan ke `format-draft-mvc.md`, di bagian penyusunan tiap bab:**

> Sebelum menetapkan sebuah Konsep/Hasil di bab sbg entri BARU, cek registry Atlas: adakah Problem lain yang SUDAH punya entri Confirmed dgn nama teorema/teknik/objek yang sama persis (bukan cuma mirip tema)? Ini pemindaian aktif, terpisah dari eksekusi bridge yang sudah diflag eksplisit di Catatan Terbuka Problem lain — bridge baru sering ditemukan justru saat menulis, bukan direncanakan sebelumnya.

**Kenapa ini penting:** Named Bridge PR-17↔PR-10 (Transfer Principle Tarski) di siklus ini murni ditemukan oportunistik saat menulis Bab 15 — bukan hasil proses yang dituntun skill. Kalau prosesnya jadi eksplisit, kemungkinan menemukan bridge semacam ini di siklus-siklus mendatang naik, bukan tergantung kebetulan penulis ingat.

### P8 — Panduan status Cluster taksonomi vs Rekomendasi topik

**Tambahkan ke `timing-atlas.md`:**

> Kalau sebuah Cluster taksonomi tingkat-proyek (mis. Cluster G) menyebut topik X "berakar tematik" dari Problem yang sedang dikerjakan, TAPI cluster itu sendiri belum py entri Notebook Konsep terdaftar ("ekstrapolasi", belum matang) — status itu **tidak otomatis** menaikkan Rekomendasi X di Bagian B Fase 1. Cluster taksonomi menjawab "topik ini ada tempatnya di suatu tempat dalam proyek"; Rekomendasi Fase 1 menjawab "topik ini penting di BAB Problem ini". Dua pertanyaan berbeda — dokumentasikan tensinya kalau ada, tapi jangan biarkan satu diam-diam menggantikan yang lain.

**Kenapa ini penting:** ketegangan ini nyata muncul (Cluster G vs rating Optional topik-topik CS populer) dan terselesaikan lewat penalaran ad hoc jendela ini — tanpa panduan tertulis, jendela lain bisa menyimpulkan sebaliknya (menaikkan Rekomendasi krn "kan sudah disebut Atlas"), menghasilkan inkonsistensi lintas-siklus PR yang justru dijaga arsitektur Atlas.

### P9 — Dokumentasikan pola audit lintas-jendela sbg praktik dianjurkan

**Tambahkan ke `SKILL.md`, bagian penutup atau catatan proses:**

> **Praktik dianjurkan (opsional, tergantung ketersediaan jendela lain):** kalau ada output Fase 1 independen dari sesi/jendela lain utk Problem yang sama, ATAU tersedia jendela terpisah khusus audit, jalankan perbandingan/audit terstruktur sebelum lanjut fase berikutnya — bukan cuma mengandalkan self-review. Checklist minimal: (a) cocokkan nama+angka tiap baris tabel besar ke sheet mentah scr terprogram, (b) hitung ulang tally/ringkasan angka scr terprogram, (c) cek konsistensi arah logis klaim sebab-akibat/perbandingan yg dipakai sbg justifikasi keputusan. Di siklus PR-10, langkah semacam ini (dijalankan 2×, oleh 2 jendela berbeda) menangkap error nyata yang lolos berulang kali dari self-review penulis sendiri.

**Kenapa ini penting:** bukan buat wajib (tak semua siklus akan punya jendela lain tersedia), tapi kalau tersedia, siklus ini menunjukkan nilainya konkret dan terukur — layak didokumentasikan sbg pola resmi, bukan kebetulan yang terlupakan begitu siklus ini selesai.

---

## Catatan Penutup

Sembilan usulan di atas semuanya berakar pada kejadian nyata siklus ini (bukan spekulasi "akan lebih baik kalau..."), mengikuti standar yang sama dipegang Atlas Master sendiri utk Riwayat Versi-nya. Kalau ingin diterapkan, skill `skill-creator` yang sudah ada di environment ini adalah alat yang tepat — saya bisa bantu menjalankannya kalau diarahkan, termasuk menulis draf konkret perubahan `SKILL.md`/`references/*.md` siap-tempel berdasarkan poin-poin di atas.
