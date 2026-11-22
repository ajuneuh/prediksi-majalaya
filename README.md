# Prakiraan Banjir Majalaya (Citarum Hulu)

Repositori ini hanya berisi **hasil** prakiraan otomatis debit Sungai Citarum di pos AWLR Majalaya dan perkiraan genangan di sekitarnya. Berkas diperbarui otomatis: setiap 3 jam saat kondisi normal, dan lebih rapat (sampai tiap 10 menit) saat hujan, debit naik, atau status tidak Normal.

> **Bukan peringatan resmi.** Prakiraan dihitung otomatis dari data telemetri BBWS Citarum. Ikuti informasi resmi BBWS Citarum dan BPBD.

## Berkas

| Berkas | Isi |
|---|---|
| `Status_Peringatan.json` | status terkini (NORMAL / WASPADA / SIAGA / AWAS), pesan singkat, debit & tinggi air terukur, perkiraan 3 dan 24 jam ke depan, perkiraan genangan |
| `Prediksi_Debit_24Jam.csv` | prakiraan debit tiap jam 24 jam ke depan: paling mungkin (P50) dan rentang P10-P90 |
| `Data_Debit_7Hari.csv`, `Data_Hujan_7Hari.csv` | debit dan hujan terukur 7 hari terakhir |
| `Plot_PrediksiH+1_Hist7Hari.png`, `Plot_PrediksiH+1_Hist1Hari.png` | grafik debit terukur dan prakiraan |
| `Prediksi_Rendaman.tif`, `Plot_Rendaman.png` | perkiraan kedalaman genangan maksimum (paling mungkin) |
| `Prediksi_Rendaman_P90.tif`, `Plot_Rendaman_P90.png` | perkiraan genangan jika air lebih tinggi (P90) |

GeoTIFF: float32, EPSG:32748 (UTM 48S), resolusi 6 m, NODATA -9999, hanya kedalaman >= 0,10 m di luar alur sungai.
Waktu dalam WIB. Ambang status mengikuti batas peringatan pos AWLR Majalaya: Peringatan 1 (TMA 3,81 m, 62,9 m3/s), Peringatan 2 (4,11 m, 69,4 m3/s), Kritis (4,51 m, 78,4 m3/s).

## Akses langsung

```
https://raw.githubusercontent.com/ajuneuh/prediksi-majalaya/main/Status_Peringatan.json
https://raw.githubusercontent.com/ajuneuh/prediksi-majalaya/main/Plot_PrediksiH+1_Hist1Hari.png
```

Riwayat commit repositori ini dipadatkan secara berkala; yang tersedia hanya hasil terbaru.
