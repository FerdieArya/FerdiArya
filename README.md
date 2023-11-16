# UTS Metode Numerik
Nama : ferdie arya jantanu <br>
NIM : 23422057

# Soal:
1. Persamaan non Linear<br>
   x + x^3 - x = 4
2. Persamaan Linier<br>
   2x - 4 = 8

# Jawaban:
1. **Penyederhanaan Persamaan Non Linear:**<br>
    3 + x^3 - x = 4 <br> 3 + x^3 - x - 4 = 0 <br> x^3 - x + 3 - 4 = 0 <br> x^3 - x - 1 = 0 atau x^3 - x = 1 <br><br>
   **Solusi:**<br>
   Untuk menemukan solusi dari persamaan non-linier tersebut, Saya memanfaatkan pendekatan iteratif, seperti metode Newton-Raphson untuk persamaan non-linier, dan metode            eliminasi untuk persamaan linier. Di bawah ini adalah contoh program sederhana yang menggunakan metode-metode tersebut.<br>

```
def fungsi(x):
    return x**3 - x - 1

def turunan_fungsi(x):
    return 3*x**2 - 1

def newton_raphson(p0, toleransi, maks_iter):
    i = 1
    while i <= maks_iter:
        p = p0 - fungsi(p0) / turunan_fungsi(p0)
        print(f'Iterasi {i}: x = {p:.6f}')
        if abs(p - p0) < toleransi:
            return p, i
        i += 1
        p0 = p

    return None, i

p0_awal = 1.0  # Tebakan awal
toleransi = 1e-6
maks_iter = 1000

akar, iterasi = newton_raphson(p0_awal, toleransi, maks_iter)

if akar is not None:
    print('\nMetode konvergen.')
    print(f'Akar persamaan: {akar}')
    print(f'Jumlah iterasi: {iterasi}')
else:
    print('Metode Newton-Raphson tidak konvergen.')


Output:
Iterasi 1: x = 1.500000
Iterasi 2: x = 1.347826
Iterasi 3: x = 1.325200
Iterasi 4: x = 1.324718
Iterasi 5: x = 1.324718

Metode konvergen.
Akar persamaan: 1.3247179572447898
Jumlah iterasi: 5

```

2. **Penyederhanaan Persamaan linear:**<br>
  2x - 4 = 8<br>
  2x = 8 + 4<br>
  2x = 12 x = 6<br><br>
  **Solusi**<br>
   Persamaan linier dapat diselesaikan secara langsung tanpa perlu mengandalkan metode iteratif karena sifatnya yang sederhana. Berikut adalah contoh implementasinya menggunakan bahasa pemrograman Python:<br>

```
def fungsi(x):
    return 2*x - 4 - 8

def turunan_fungsi(x):
    return 2

def newton_raphson(tebakan_awal, epsilon=1e-6, iterasi_maks=100):
    x = tebakan_awal
    iterasi = 0

    while abs(fungsi(x)) > epsilon and iterasi < iterasi_maks:
        x = x - (fungsi(x) / turunan_fungsi(x))
        iterasi += 1

    if abs(fungsi(x)) <= epsilon:
        return x
    else:
        raise ValueError("Metode Newton-Raphson tidak konvergen")

# Menentukan tebakan awal
tebakan_awal = 0.0

# Memanggil fungsi Newton-Raphson
hasil = newton_raphson(tebakan_awal)

# Menampilkan hasil
print("Solusi persamaan: x =", hasil)

Output:
Solusi persamaan: x = 6.0
```
