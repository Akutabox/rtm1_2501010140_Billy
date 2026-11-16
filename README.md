
# Tugas 1 - Akuisisi dan Manajemen Data

## Cuaca per Jam di Enam Destinasi Wisata Bali

### 1. Sumber Data

- Nama: Open-Meteo Forecast API
- URL: https://api.open-meteo.com/v1/forecast
- Penerbit: Open-Meteo
- Lisensi: Mengacu pada ketentuan penggunaan Open-Meteo.
- Atribusi: Weather data by Open-Meteo.com

### 2. Tanggal dan Jam Akses

- Waktu akses: 2026-11-16 18:50:44
- Zona waktu: WITA (Asia/Makassar)

### 3. Metode Akuisisi

Menggunakan API resmi Open-Meteo dengan Python Requests.

Endpoint:
https://api.open-meteo.com/v1/forecast

Parameter:
- latitude dan longitude: koordinat enam destinasi
- hourly: temperature_2m, precipitation, cloud_cover, wind_speed_10m
- timezone: Asia/Makassar
- forecast_days: 7
- wind_speed_unit: kmh

Pengambilan data menggunakan timeout 15 detik,
User-Agent, pemeriksaan status code, serta retry
dengan exponential backoff apabila terjadi gangguan.

### 4. Batasan Etika

- Sumber data menggunakan Open-Meteo API.
- Ketentuan penggunaan dan atribusi mengikuti aturan Open-Meteo.
- Atribusi sumber dicantumkan.
- Tidak mengambil data pribadi.
- Pengambilan dilakukan dalam satu request batch.
- Penggunaan API mengikuti prinsip fair use.
- Tidak menggunakan API key karena tidak diperlukan
  untuk penggunaan non-komersial pada endpoint ini.

### 5. Penjelasan Kolom Dataset

| Kolom | Keterangan |
|---|---|
| lokasi | Nama destinasi wisata |
| waktu_wita | Waktu perkiraan cuaca |
| suhu_c | Suhu udara dalam Celsius |
| curah_hujan_mm | Curah hujan dalam milimeter |
| tutupan_awan_persen | Persentase tutupan awan |
| kecepatan_angin_kmh | Kecepatan angin km/jam |

Jumlah lokasi: 6
Jumlah record: 1008
Jumlah kolom: 6

Data mencakup perkiraan cuaca per jam selama tujuh hari.
Data merupakan hasil perkiraan model cuaca, bukan
pengukuran langsung dari stasiun cuaca.

### 6. Cara Menjalankan Ulang

1. Instal library:
   pip install pandas requests

2. Buka notebooks/Akusisi_OpenMateo.ipynb

3. Isi nama, NIM, dan email kampus.

4. Jalankan seluruh cell dari awal.

5. Hasil akuisisi tersimpan pada data/raw/
   dan dokumentasi tersimpan pada docs/.

## Referensi

Open-Meteo: https://open-meteo.com/
Lisensi: https://creativecommons.org/licenses/by/4.0/

Weather data by Open-Meteo.com
