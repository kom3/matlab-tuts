# Tutorial Matlab
Karena kita manusia, sering lupa kan, makanya saya dokumentasikan beberapa snippet kode yang mungkin bisa digunakan dilain waktu. Jika ingin berkontribusi, silahkan lakukan **Pull Request**.
## Metode Numerik
Kumpulan dari kode matlab yang digunakan untuk menyelesaikan beberapa masalah numerik yang biasanya digunakan pada mata kuliah **Metode Numerik**.
### Differential Equation
Kadang kalian bingung kan, gimana cara menyelesaikan persamaan differensial. Nah mari kita coba untuk membahasnya menggunakan program.

Misalkan saya mempunyai sebuah persamaan differensial berikut

`dy/dx = y' = -2x - y`

Definsikan symbolic function untuk **y(x)**

`>> syms y(x)`

Ubahkan persamaan differensial yang awal tadi menjadi notasi di MATLAB dan simpan pada suatu variabel, misalnya **fungsi**.

`>> fungsi = diff(y,x)==-2*x-y`

Mungkin kamu akan mendapatkan hasil sebagai berikut

```
fungsi(x) =
 
diff(y(x), x) == - 2*x - y(x)
```

Sekarang cari penyelesaian dari persamaan tersebut menggunakan fungsi **dsolve**

`>> ySol(x) = dsolve(fungsi)`

Berikut adalah outputnya

```
ySol(x) =
 
C1*exp(-x) - 2*x + 2
```

Pada output masih terdapat sebuah konstanta **C1**, nah untuk mencari nilai konstanta ini, kita harus memasukkan nilai awalan, misalkan kita mempunya awalan bahwa

`y(0) = 0`

Masukkan pada matlab, misalkan

`>> awalan = y(0)==0`

Gunakan fungsi **dsolve** kembali untuk menyelesaikan persamaan yang tadi, namun dengan parameter tambahan

`>> ySol(x) = dsolve(fungsi, awalan)`

Keluaran dari program adalah sebagai berikut

```
ySol(x) =
 
2 - 2*exp(-x) - 2*x
```

Sekarang anda telah menyelesaikan persamaan diferensial biasa, dan telah mendapatkan hasilnya.