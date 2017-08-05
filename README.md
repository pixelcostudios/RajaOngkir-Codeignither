# RajaOngkir CodeIgniter
Merupakan library CodeIgniter untuk mengambil data dari API pada website [RajaOngkir](http://rajaongkir.com).
## Instalasi
Copy file sesuai dengan lokasinya masing-masing.
## Konfigurasi
Buka "**application/config/rajaongkir.php**" dan masukkan API key di sana.
## Support Akun
Ada macam akun yang tersedia starter, basic, pro
## Contoh Penggunaan
### Memuat library
```php
$this->load->library('rajaongkir');
```
### Melakukan request
```php
//Mendapatkan semua propinsi
$provinces = $this->rajaongkir->province();

//Mendapatkan semua kota
$cities = $this->rajaongkir->city();

//Mendapatkan data ongkos kirim
//$cost = $this->rajaongkir->cost($origin, $originType, $destination, $destinationType, $weight, $courier);
$cost = $this->rajaongkir->cost(501, 'city', 114, 'city', 1000, "jne");

//Mendapatkan daftar/nama kota yang mendukung pengiriman Internasional
$origin = $this->rajaongkir->internationalOrigin($province_id = NULL, $city_id = NULL);

//Mendapatkan daftar/nama negara tujuan pengiriman internasional
$destination = $this->rajaongkir->internationalDestination($country_id = NULL);

//Mendapatkan data ongkos kirim internasional (EMS)
$cost = $this->rajaongkir->internationalCost($origin, $destination, $weight, $courier);

//Untuk mendapatkan nilai kurs rupiah terhadap USD
$currency = $this->rajaongkir->currency();

//Untuk melacak paket/nomor resi
$resi = $this->rajaongkir->waybill($waybill_number, $courier);
```
### Response
Response yang dihasilkan berupa string JSON balasan dari RajaOngkir.
### Dokumentasi lebih lanjut
Silakan lihat code di dalam library, di dalamnya terdapat komentar yang dapat membantu Anda.
### Referensi
[Dokumentasi RajaOngkir](http://rajaongkir.com/dokumentasi)