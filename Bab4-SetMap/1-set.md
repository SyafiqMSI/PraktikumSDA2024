# 1 - Set

## Konsep Set

Set (atau **himpunan**) adalah suatu struktur data yang operasinya hanya digunakan untuk **mengecek keberadaan suatu data** tertentu. Konsep himpunan ini mirip dengan himpunan dengan matematika, akan tetapi dengan jumlah elemen yang terbatas (berbeda dengan himpunan di matematika yang mana jumlahnya bisa sampai tak terhingga, misal himpunan seluruh bilangan bulat).

Himpunan pada matematika juga memiliki operasi untuk mengecek suatu keanggotaan pada himpunan (misalkan, apakah angka 36 merupakan anggota himpunan bilangan bulat?). Begitu juga himpunan sebagai struktur data program komputer, ia dapat mengecek keanggotaan (keberadaan) suatu data dalam himpunan tersebut, dengan kompleksitas yang relatif singkat.

Pada umumnya, himpunan direpresentasikan dalam bentuk binary search tree supaya proses menambah, menghapus, dan mencari elemen bisa dilakukan seefisien mungkin (kompleksitas O(log N)).

Struktur data himpunan terdapat dalam header `<set>` pada C++.

## Deklarasi

Sebagai contoh:
```c++
std::set<int> fav_numbers;
```
Mendeklarasikan himpunan `fav_numbers` dengan tipe anggota elemen berupa `int`.

## Operasi

### Insertion

Memasukkan elemen angka `36` ke dalam himpunan `fav_numbers`:
```c++
fav_numbers.insert(36);
```

### Access

Mengecek apakah angka `36` ada dalam himpunan `fav_numbers`:
```c++
if (fav_numbers.count(36) == 1) {
    std::cout << "Angka 36 merupakan salah satu angka favorit saya" << std::endl;
}
```

atau menggunakan iterator:
```c++
std::set<int>::iterator it = fav_numbers.find(36);
if (it != fav_numbers.end()) {
    std::cout << "Angka 36 merupakan salah satu angka favorit saya" << std::endl;
}
```

### Removal

Menghapus keanggotaan angka `36` dari himpunan `fav_numbers`:
```c++
fav_numbers.erase(36);
```

atau menggunakan iterator:
```c++
std::set<int>::iterator it = fav_numbers.find(36); // temukan angka 36
fav_numbers.erase(it); // hapus angka 36 yang ditunjuk oleh `it`
```

### Iteration

Iterasi seluruh anggota elemen pada himpunan `fav_numbers`:
```c++
for (
    std::set<int>::iterator it = fav_numbers.begin();
    it != fav_numbers.end();
    ++it
) {
    std::cout << "Angka favorit: " << *it << std::endl;
}
```

## Selengkapnya

- [C++ Set](https://en.cppreference.com/w/cpp/container/set)
