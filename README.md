# Autoencoder untuk Pewarnaan Citra Dataset Rock-Paper-Scissors

## Deskripsi Dataset

Dataset yang digunakan adalah **Rock-Paper-Scissors Dataset** yang berisi gambar tangan membentuk gesture batu, kertas, dan gunting. Dataset ini terdiri dari:

- **Train:**
  - Paper: 840 gambar
  - Rock: 840 gambar
  - Scissors: 840 gambar

- **Test:**
  - Paper: 124 gambar
  - Rock: 124 gambar
  - Scissors: 124 gambar

- **Validation:**
  - Paper: 124 gambar
  - Rock: 124 gambar
  - Scissors: 124 gambar

Untuk mempercepat proses pelatihan, hanya **50 data** dari dataset training yang digunakan.

## Arsitektur Model Autoencoder

Autoencoder yang digunakan terdiri dari:

- **Encoder:**
  - 3 layer Conv2D berturut-turut dengan kernel size 3x3, stride 2, dan padding 1
  - Setiap layer diikuti oleh BatchNorm2d dan ReLU activation

- **Decoder:**
  - 3 layer ConvTranspose2D berturut-turut untuk mengembalikan resolusi gambar
  - Setiap layer diikuti oleh BatchNorm2d dan ReLU activation
  - Output layer menggunakan Tanh activation untuk menghasilkan citra dengan nilai antara -1 hingga 1

Ukuran input citra yang digunakan adalah **128x128 piksel**.

## Performa Model

Berikut hasil training selama 100 epoch:

| Epoch | Train Loss | Val Loss | Test Loss |
|------|------------|----------|-----------|
| 10   | 0.0246     | 0.0212   | 0.0217    |
| 20   | 0.0127     | 0.0105   | 0.0114    |
| 30   | 0.0089     | 0.0073   | 0.0093    |
| 40   | 0.0068     | 0.0057   | 0.0071    |
| 50   | 0.0060     | 0.0050   | 0.0066    |
| 60   | 0.0045     | 0.0046   | 0.0056    |
| 70   | 0.0047     | 0.0038   | 0.0057    |
| 80   | 0.0041     | 0.0042   | 0.0049    |
| 90   | 0.0033     | 0.0035   | 0.0046    |
| 100  | 0.0030     | 0.0028   | 0.0044    |

Dari tabel tersebut, terlihat bahwa model mengalami penurunan loss yang konsisten, menunjukkan bahwa model mampu belajar dengan baik.

## Contoh Hasil Input dan Output

Berikut contoh hasil pewarnaan citra menggunakan autoencoder:



## Kesimpulan

Dengan menggunakan Autoencoder sederhana dan hanya 50 data untuk training, model sudah mampu melakukan rekonstruksi warna citra dengan cukup baik. Performa yang terus meningkat pada training, validasi, dan testing menunjukkan bahwa pendekatan ini efektif untuk tugas pewarnaan gambar Rock-Paper-Scissors.

