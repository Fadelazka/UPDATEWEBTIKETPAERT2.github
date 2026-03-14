PENJELASAN KODE HTML PAGE LOGIN :
Container Utama
<form id="authForm" onsubmit="handleAuth(event)">
•	- id="page-auth" → Digunakan oleh JavaScript untuk menampilkan/menyembunyikan halaman ini (melalui fungsi navigateTo).
•	class="page-view" → Secara default menyembunyikan halaman (CSS: .page-view { display: none; }). Kelas active akan ditambahkan saat halaman ditampilkan.
•	min-h-screen → Tinggi minimum setinggi layar penuh.
•	bg-cover dan bg-center → Mengatur gambar latar agar menutupi area dan berada di tengah.
•	style="background-image: url(...)" → Gambar latar dari Unsplash (pantai).
Overlay Gelap dan Kontainer Form
<div class="min-h-screen bg-black/50 flex items-center justify-center p-4">
•	bg-black/50 → Overlay hitam dengan opasitas 50% agar teks dan form lebih terbaca di atas gambar.
•	flex items-center justify-center → Memusatkan konten secara vertikal dan horizontal.
•	p-4 → Padding 1rem (16px) di semua sisi untuk jarak pada layar kecil.
Kartu Putih (Form Container)
<div class="bg-white rounded-2xl shadow-2xl w-full max-w-md overflow-hidden relative">
•	bg-white → Latar belakang putih.
•	rounded-2xl → Sudut sangat melengkung (border-radius besar).
•	shadow-2xl → Bayangan besar untuk efek kedalaman.
•	w-full max-w-md → Lebar penuh dengan maksimum 448px (agar tidak terlalu lebar di layar besar).
•	overflow-hidden → Memastikan konten tidak keluar dari batas sudut melengkung.
•	relative → Posisi relatif untuk menempatkan tombol kembali secara absolut di dalamnya.
Tombol Kembali
<button onclick="navigateBack()" class="absolute top-4 left-4 text-gray-500 hover:text-gray-800 transition">
  <i class="fas fa-arrow-left text-xl"></i>
</button>
•	onclick="navigateBack()" → Memanggil fungsi JavaScript untuk kembali ke halaman sebelumnya (biasanya beranda).
•	absolute top-4 left-4 → Diposisikan di pojok kiri atas kartu.
•	text-gray-500 hover:text-gray-800 → Warna ikon abu-abu, berubah lebih gelap saat di-hover.
•	transition → Efek transisi halus saat hover.
•	Ikon panah kiri dari Font Awesome.
Konten Utama (Padding dan Judul)
<div class="p-8 pt-12">
p-8 → Padding 2rem (32px) di semua sisi.
pt-12 → Padding top khusus 3rem (48px) untuk memberi ruang lebih karena tombol kembali di atas.

<div class="text-center mb-8">
  <h2 class="text-3xl font-bold text-[#1e3c5c]" id="authTitle">Selamat Datang</h2>
  <p class="text-gray-500 mt-2" id="authSubtitle">Masuk untuk melanjutkan pemesanan tiket Anda.</p>
</div>
text-center → Teks rata tengah.
mb-8 → Margin bawah 2rem.
#authTitle dan #authSubtitle → Elemen dengan ID ini akan diubah teksnya oleh JavaScript saat mode login/register berubah.
text-[#1e3c5c] → Warna biru tua khusus (kode warna).
text-gray-500 → Teks abu-abu untuk subtitle.

 Formulir
<form id="authForm" onsubmit="handleAuth(event)">
id="authForm" → Memudahkan referensi di JavaScript.
onsubmit="handleAuth(event)" → Mencegah pengiriman default dan menangani login/register.
  
a. Field Nama (Register)
<div id="registerFields" class="hidden mb-4">
  <label class="tw-label">Nama Lengkap</label>
  <input type="text" id="authName" class="tw-input" placeholder="Masukkan nama Anda" />
</div>
id="registerFields" → Div ini disembunyikan secara default (hidden). JavaScript akan menampilkannya saat mode register aktif.
tw-label → Class kustom untuk label (font tebal, margin bawah, warna).
id="authName" → Input nama, hanya digunakan saat register.
tw-input → Class kustom untuk input (border, padding, radius, efek focus).

b. Field Email
<div class="mb-4">
  <label class="tw-label">Alamat Email</label>
  <input type="email" id="authEmail" required class="tw-input" placeholder="email@contoh.com" />
</div>
type="email" → Memastikan format email valid.
required → HTML5 validation, field tidak boleh kosong.
id="authEmail" → Digunakan JavaScript untuk mengambil nilai email.

c. Field Password
<div class="mb-6">
  <label class="tw-label">Kata Sandi</label>
  <input type="password" id="authPassword" required class="tw-input" placeholder="••••••••" />
</div>
type="password" → Karakter tersembunyi.
id="authPassword" → Untuk mengambil nilai password (meskipun tidak divalidasi di kode saat ini).

d. Tombol Submit
<button type="submit" class="w-full bg-[#f39c12] hover:bg-[#e67e22] text-white font-bold py-3 rounded-xl transition shadow-lg text-lg">
  <span id="authBtnText">Masuk Sekarang</span>
</button>
type="submit" → Memicu event submit pada form.
w-full → Lebar penuh.
bg-[#f39c12] → Warna oranye.
hover:bg-[#e67e22] → Warna lebih gelap saat hover.
py-3 → Padding vertikal 0.75rem.
rounded-xl → Sudut melengkung.
shadow-lg → Bayangan.
text-lg → Ukuran font besar.
#authBtnText → Teks tombol berubah sesuai mode (Login/Register).

Toggle Mode (Login/Register)
<div class="mt-6 text-center border-t border-gray-200 pt-6">
  <p class="text-gray-600" id="authToggleText">
    Belum punya akun? 
    <button onclick="toggleAuthMode()" class="text-[#2b6c94] font-bold hover:underline">Daftar di sini</button>
  </p>
</div>
border-t border-gray-200 pt-6 → Garis pembatas atas dengan padding.
#authToggleText → Paragraf ini akan diubah seluruh HTML-nya oleh JavaScript saat mode berganti.
onclick="toggleAuthMode()" → Memanggil fungsi untuk beralih antara login dan register.
text-[#2b6c94] → Warna biru untuk tautan.
font-bold hover:underline → Tebal dan garis bawah saat hover.

Hubungan dengan JavaScript
id pada elemen-elemen kunci (seperti authTitle, authSubtitle, registerFields, authName, authEmail, authPassword, authBtnText, authToggleText, authForm) digunakan langsung oleh fungsi toggleAuthMode() dan handleAuth().
onclick pada tombol kembali dan tombol toggle memanggil fungsi global.
onsubmit pada form memanggil handleAuth(event).

CSS yang Terkait
Class .tw-input dan .tw-label didefinisikan di <style> global.
Utility Tailwind seperti bg-black/50, rounded-2xl, shadow-2xl, dll. berasal dari pustaka Tailwind yang diimpor.
Aturan .page-view dan .active mengontrol tampilan halaman.

PENJELASKAN KODE" HTML PAGE DI BAGIAN DESTINASI :
 Container Utama Halaman
<div id="page-destinasi" class="page-view bg-gray-50 min-h-screen pb-12">
id="page-destinasi" → Digunakan oleh JavaScript untuk menampilkan/menyembunyikan halaman ini (fungsi navigateTo).
class="page-view" → Secara default halaman tersembunyi (CSS: .page-view { display: none; }). Kelas active akan ditambahkan saat halaman ditampilkan.
bg-gray-50 → Latar belakang abu-abu sangat muda.
min-h-screen → Tinggi minimum setinggi layar.
pb-12 → Padding bawah 3rem (48px) untuk memberi ruang.
  
Navigasi Sticky (Header)
<div class="bg-white shadow-sm p-4 sticky top-0 z-20">
  <div class="max-w-6xl mx-auto flex items-center">
    <button onclick="navigateTo('page-home')" class="text-[#2b6c94] font-bold hover:text-[#1e3c5c]">
      <i class="fas fa-arrow-left mr-2"></i> Kembali ke Beranda
    </button>
  </div>
</div>
sticky top-0 z-20 → Header tetap di atas saat halaman di-scroll, dengan z-index tinggi agar tidak tertutup elemen lain.
bg-white shadow-sm → Latar putih dengan bayangan kecil.
max-w-6xl mx-auto → Lebar maksimum 1152px dan rata tengah.
Tombol kembali → Menggunakan onclick="navigateTo('page-home')" untuk kembali ke beranda. Ikon panah kiri dari Font Awesome.
text-[#2b6c94] → Warna biru khas.

 Konten Utama (Grid 2 Kolom)
<div class="max-w-6xl mx-auto px-4 mt-8 grid grid-cols-1 lg:grid-cols-3 gap-8">
max-w-6xl mx-auto px-4 mt-8 → Kontainer pusat dengan lebar maksimum, padding horizontal, dan margin atas.
grid grid-cols-1 lg:grid-cols-3 gap-8 → Grid 1 kolom di mobile, 3 kolom di layar besar (lg). Jarak antar kolom 2rem (gap-8).

Kolom Kiri (2/3 Lebar)
<div class="lg:col-span-2 space-y-6">
lg:col-span-2 → Di layar besar, kolom ini menempati 2 dari 3 bagian grid.
space-y-6 → Jarak vertikal antar elemen di dalamnya 1.5rem.

a. Kartu Informasi Destinasi
<div class="bg-white rounded-2xl shadow-sm overflow-hidden">
  <div id="destHeroImg" class="h-80 bg-gradient-to-r from-blue-500 to-teal-400 bg-cover bg-center"></div>
  <div class="p-8">
    <div class="flex justify-between items-start mb-4">
      <div>
        <h1 id="destTitle" class="text-4xl font-bold text-[#1e3c5c] mb-2">Nama Destinasi</h1>
        <p id="destLocation" class="text-gray-500 text-lg"><i class="fas fa-map-marker-alt text-[#f39c12]"></i> Lokasi</p>
      </div>
      <div class="bg-yellow-100 text-yellow-800 px-4 py-2 rounded-full font-bold flex items-center">
        <i class="fas fa-star text-yellow-500 mr-2"></i> <span id="destRating">5.0</span>
      </div>
    </div>
    <hr class="my-6 border-gray-200" />
    <h3 class="text-xl font-bold mb-3">Deskripsi Lengkap</h3>
    <p id="destDesc" class="text-gray-600 leading-relaxed text-lg">Deskripsi panjang destinasi akan muncul di sini.</p>
  </div>
</div>
#destHeroImg → Div ini akan diisi background image destinasi oleh JavaScript (style.backgroundImage). Tinggi 20rem (h-80), dengan gradien fallback.
#destTitle, #destLocation, #destRating, #destDesc → Elemen dengan ID ini akan diisi data dari objek destinasi yang dipilih.
Ikon lokasi dari Font Awesome dengan warna oranye (text-[#f39c12]).
Rating ditampilkan dalam badge kuning bulat.
hr sebagai pembatas.

Kolom Kanan (1/3 Lebar) - Form Pemesanan
<div class="space-y-6">
  <div class="bg-white rounded-2xl shadow-lg p-6 border-t-4 border-[#2b6c94]">
    <h3 class="text-2xl font-bold text-[#1e3c5c] mb-6"><i class="fas fa-ticket-alt text-[#f39c12]"></i> Pesan Tiket</h3>
    
    <div class="space-y-4">
Kartu putih dengan border atas biru tebal.
space-y-4 → Jarak antar elemen form 1rem.

a. Tanggal Kunjungan
<div>
  <label class="tw-label">Tanggal Kunjungan</label>
  <input type="date" id="bookDate" class="tw-input" />
</div>
type="date" → Input tanggal dengan kalender.
id="bookDate" → Untuk diakses JavaScript (misal mengatur min attribute).
tw-label dan tw-input → Class kustom untuk styling konsisten.

b. Jumlah Tiket
<div>
  <label class="tw-label">Jumlah Tiket</label>
  <input type="number" id="bookQty" min="1" value="1" class="tw-input" onchange="calculateDestTotal()" />
</div>
id="bookQty" → Menyimpan jumlah tiket.
min="1" → Minimal 1.
onchange="calculateDestTotal()" → Memanggil fungsi JavaScript setiap kali nilai berubah untuk menghitung ulang total.

c. Opsi Tambahan (Checkbox)
<div class="bg-gray-50 p-4 rounded-xl border border-gray-100 space-y-3">
  <label class="flex items-center space-x-3 cursor-pointer">
    <input type="checkbox" id="bookGuide" class="w-5 h-5 text-blue-600 rounded" onchange="calculateDestTotal()">
    <span class="text-gray-700">Pemandu Wisata (+Rp 75.000)</span>
  </label>
  <label class="flex items-center space-x-3 cursor-pointer">
    <input type="checkbox" id="bookMeal" class="w-5 h-5 text-blue-600 rounded" onchange="calculateDestTotal()">
    <span class="text-gray-700">Makan Siang (+Rp 50.000)</span>
  </label>
</div>
Checkbox dengan ID #bookGuide dan #bookMeal, masing-masing memicu calculateDestTotal() saat berubah.
flex items-center space-x-3 → Ikon dan teks sejajar.

d. Metode Pembayaran
<div class="pt-4 border-t border-gray-200">
  <label class="tw-label">Metode Pembayaran</label>
  <select id="destPaymentMethod" class="tw-input bg-gray-50">
    <option value="transfer">Transfer Bank (BCA/Mandiri/BNI)</option>
    <option value="ewallet">E-Wallet (GoPay/OVO/Dana)</option>
    <option value="qris">QRIS</option>
  </select>
</div>
id="destPaymentMethod" → Menyimpan pilihan metode (meski belum diproses di JavaScript simulasi).
tw-input dengan latar abu-abu.

e. Ringkasan Harga
<div class="bg-[#f6fafd] p-4 rounded-xl border border-blue-100 mt-4">
  <div class="flex justify-between items-center mb-2 text-gray-600">
    <span>Harga Tiket</span>
    <span id="bookPricePer">Rp 0</span>
  </div>
  <div class="flex justify-between items-center text-xl font-bold text-[#1e3c5c] border-t border-gray-200 pt-3 mt-2">
    <span>Total Tagihan</span>
    <span id="bookTotal">Rp 0</span>
  </div>
</div>
#bookPricePer → Menampilkan harga per tiket (diisi JavaScript).
#bookTotal → Menampilkan total tagihan setelah kalkulasi (diisi JavaScript).

f. Tombol Bayar
<button onclick="processPayment('destinasi')" class="w-full bg-[#2b6c94] hover:bg-[#1e4f6e] text-white font-bold py-4 rounded-xl shadow-lg transition flex justify-center items-center text-lg mt-4">
  <i class="fas fa-lock mr-2"></i> Bayar & Booking Sekarang
</button>
onclick="processPayment('destinasi')" → Memanggil fungsi pembayaran dengan parameter 'destinasi'.
Styling: tombol biru dengan ikon gembok.

Hubungan dengan JavaScript dan CSS
JavaScript
#destHeroImg, #destTitle, #destLocation, #destRating, #destDesc, #bookPricePer → Diisi oleh fungsi openDestinasiPage(dest).
#bookDate → Di-set min dan value di fungsi yang sama.
#bookQty, #bookGuide, #bookMeal → Memicu calculateDestTotal().
#bookTotal → Diperbarui oleh calculateDestTotal().
Tombol bayar → Memicu processPayment('destinasi').

CSS
Class .tw-input dan .tw-label didefinisikan di <style> global, memberikan tampilan konsisten pada input dan label.
Utility Tailwind lainnya (seperti bg-white, rounded-2xl, shadow-lg, dll.) langsung dari Tailwind CDN.
Aturan .page-view.active memastikan halaman ini tampil saat diperlukan.

PENJELASAN KODE HTML PAGE PAKET :
Container Utama Halaman
<div id="page-paket" class="page-view bg-gray-50 min-h-screen pb-12">
id="page-paket" → Digunakan oleh JavaScript untuk menampilkan/menyembunyikan halaman ini (fungsi navigateTo).
class="page-view" → Secara default halaman tersembunyi (CSS: .page-view { display: none; }). Kelas active akan ditambahkan saat halaman ditampilkan.
bg-gray-50 → Latar belakang abu-abu sangat muda.
min-h-screen → Tinggi minimum setinggi layar.
pb-12 → Padding bawah 3rem (48px) untuk memberi ruang.
  
Navigasi Sticky (Header)
<div class="bg-white shadow-sm p-4 sticky top-0 z-20">
  <div class="max-w-6xl mx-auto flex items-center">
    <button onclick="navigateTo('page-home')" class="text-[#2b6c94] font-bold hover:text-[#1e3c5c]">
      <i class="fas fa-arrow-left mr-2"></i> Kembali ke Beranda
    </button>
  </div>
</div>
sticky top-0 z-20 → Header tetap di atas saat halaman di-scroll, dengan z-index tinggi agar tidak tertutup elemen lain.
bg-white shadow-sm → Latar putih dengan bayangan kecil.
max-w-6xl mx-auto → Lebar maksimum 1152px dan rata tengah.
Tombol kembali → Menggunakan onclick="navigateTo('page-home')" untuk kembali ke beranda. Ikon panah kiri dari Font Awesome.
text-[#2b6c94] → Warna biru khas.

Konten Utama (Flex Layout)
<div class="max-w-6xl mx-auto px-4 mt-8">
  <div class="bg-white rounded-3xl shadow-lg overflow-hidden flex flex-col md:flex-row">
max-w-6xl mx-auto px-4 mt-8 → Kontainer pusat dengan lebar maksimum, padding horizontal, dan margin atas.
bg-white rounded-3xl shadow-lg overflow-hidden → Kartu putih dengan sudut sangat melengkung (border-radius besar), bayangan besar, dan konten tidak keluar dari batas.
flex flex-col md:flex-row → Layout fleksibel dengan arah kolom di mobile, berubah menjadi baris di layar medium ke atas.

Bagian Kiri (Informasi Paket)
<div class="w-full md:w-3/5 p-8 lg:p-12 bg-[#1e3c5c] text-white relative bg-cover bg-center" style="background-image: linear-gradient(rgba(30, 60, 92, 0.9), rgba(30, 60, 92, 0.9)), url('https://images.unsplash.com/...');">
w-full md:w-3/5 → Lebar penuh di mobile, 60% di layar medium ke atas.
p-8 lg:p-12 → Padding responsif.
bg-[#1e3c5c] → Warna biru tua sebagai fallback.
relative → Posisi relatif untuk menempatkan ikon latar secara absolut.
bg-cover bg-center → Gambar latar menutupi area dan terpusat.
style="background-image: ..." → Gambar dari Unsplash dengan overlay gelap menggunakan gradien RGBA.

a. Ikon Latar Besar (Dekoratif)
<div class="absolute top-0 right-0 opacity-10 text-9xl mt-10 mr-10" id="pkgIconBg">
  <i class="fas fa-users"></i>
</div>
absolute top-0 right-0 → Diposisikan di pojok kanan atas.
opacity-10 → Sangat transparan (hanya efek bayangan).
text-9xl → Ukuran font sangat besar.
id="pkgIconBg" → Akan diisi oleh JavaScript dengan ikon yang sesuai dengan paket (misal fa-heart, fa-people-group).

b. Label dan Judul
<div class="relative z-10">
  <div class="inline-block bg-[#f39c12] text-white px-4 py-1 rounded-full text-sm font-bold tracking-wider mb-6">PAKET SPESIAL</div>
  <h1 id="pkgTitle" class="text-4xl lg:text-5xl font-bold mb-4">Nama Paket</h1>
  <p id="pkgFitur" class="text-xl text-blue-200 mb-8"><i class="fas fa-check-circle mr-2"></i>Fitur utama paket</p>
relative z-10 → Memastikan konten di atas ikon latar.
Label "PAKET SPESIAL" → Tombol kecil berwarna oranye dengan teks putih, huruf kapital, dan tracking lebar.
#pkgTitle → Tempat judul paket (diisi JavaScript).
#pkgFitur → Tempat fitur utama paket, dengan ikon centang hijau.
  
c. Deskripsi Paket
<div class="bg-white/10 p-6 rounded-2xl backdrop-blur-sm mb-6">
  <h3 class="text-xl font-bold mb-3 flex items-center"><i class="fas fa-info-circle text-[#f39c12] mr-3"></i> Deskripsi Paket</h3>
  <p id="pkgDesc" class="text-gray-200 leading-relaxed">Deskripsi detail mengenai paket wisata ini.</p>
</div>
bg-white/10 → Latar putih dengan opasitas 10%.
backdrop-blur-sm → Efek blur pada latar belakang di belakang elemen.
#pkgDesc → Akan diisi deskripsi panjang paket.

d. Tips & Rekomendasi
<div class="bg-yellow-500/20 p-6 rounded-2xl border border-yellow-500/30 backdrop-blur-sm">
  <h3 class="text-xl font-bold mb-3 text-yellow-300 flex items-center"><i class="fas fa-lightbulb mr-3"></i> Tips & Rekomendasi</h3>
  <p id="pkgSaran" class="text-gray-200 leading-relaxed">Saran persiapan untuk memaksimalkan liburan Anda.</p>
</div>
bg-yellow-500/20 → Latar kuning dengan opasitas 20%.
border-yellow-500/30 → Border kuning transparan.
#pkgSaran → Akan diisi tips oleh JavaScript.

Bagian Kanan (Form Reservasi)
<div class="w-full md:w-2/5 p-8 lg:p-12 bg-white flex flex-col justify-center">
  <h2 class="text-2xl font-bold text-[#1e3c5c] mb-6">Detail Reservasi Paket</h2>
  
  <div class="space-y-5">
w-full md:w-2/5 → Lebar penuh di mobile, 40% di layar medium ke atas.
bg-white → Latar putih.
flex flex-col justify-center → Menyusun konten secara vertikal dan memusatkannya di tengah.

a. Tanggal Keberangkatan
<div>
  <label class="tw-label">Pilih Tanggal Keberangkatan</label>
  <input type="date" id="pkgDate" class="tw-input bg-gray-50" />
</div>
type="date" → Input tanggal dengan kalender.
id="pkgDate" → Untuk diakses JavaScript (mengatur min dan value).
tw-label dan tw-input → Class kustom untuk styling konsisten (didefinisikan di CSS global).
bg-gray-50 → Latar abu-abu muda.

b. Informasi Kontak Pemesan
<div>
  <label class="tw-label">Informasi Kontak Pemesan</label>
  <input type="text" placeholder="Nama Lengkap" class="tw-input mb-3" />
  <input type="text" placeholder="Nomor WhatsApp" class="tw-input" />
</div>
Dua input tanpa ID khusus (tidak diproses oleh JavaScript dalam kode ini, hanya sebagai placeholder). Jika diperlukan, bisa ditambahkan ID nantinya.
mb-3 → Margin bawah untuk input pertama.

c. Metode Pembayaran
<div class="pt-4 border-t border-gray-200">
  <label class="tw-label">Metode Pembayaran</label>
  <select id="pkgPaymentMethod" class="tw-input bg-gray-50">
    <option value="transfer">Transfer Bank (BCA/Mandiri/BNI)</option>
    <option value="cc">Kartu Kredit / Debit</option>
    <option value="qris">QRIS (Scan Langsung)</option>
  </select>
</div>
id="pkgPaymentMethod" → Menyimpan pilihan metode pembayaran.
border-t border-gray-200 pt-4 → Garis pembatas di atas.
tw-input → Styling sama dengan input.

d. Total Biaya
<div class="bg-blue-50 p-5 rounded-2xl border border-blue-100 mt-6">
  <p class="text-gray-500 text-sm mb-1">Total Biaya Paket</p>
  <p id="pkgPrice" class="text-3xl font-bold text-[#2b6c94]">Rp 0</p>
</div>
bg-blue-50 → Latar biru sangat muda.
#pkgPrice → Akan diisi harga paket oleh JavaScript.

e. Tombol Konfirmasi & Bayar
<button onclick="processPayment('paket')" class="w-full bg-[#f39c12] hover:bg-[#e67e22] text-white font-bold py-4 rounded-xl shadow-lg transition text-lg mt-4 flex justify-center items-center">
  <i class="fas fa-shield-alt mr-2"></i> Konfirmasi & Bayar
</button>
onclick="processPayment('paket')" → Memanggil fungsi pembayaran dengan parameter 'paket'.
Styling: tombol oranye dengan ikon perisai.

Hubungan dengan JavaScript dan CSS
JavaScript
#pkgTitle, #pkgFitur, #pkgDesc, #pkgSaran, #pkgIconBg, #pkgPrice → Diisi oleh fungsi openPaketPage(paket) saat pengguna memilih paket.
#pkgDate → Di-set min dan value di fungsi yang sama.
#pkgPaymentMethod → Menyimpan pilihan metode (meskipun tidak diproses dalam simulasi saat ini).
Tombol bayar → Memicu processPayment('paket').

CSS
Class .tw-input dan .tw-label didefinisikan di <style> global, memberikan tampilan konsisten pada input, select, dan label.
Utility Tailwind lainnya (seperti bg-white, rounded-3xl, shadow-lg, backdrop-blur-sm, dll.) langsung dari Tailwind CDN.
Aturan .page-view.active memastikan halaman ini tampil saat diperlukan.

