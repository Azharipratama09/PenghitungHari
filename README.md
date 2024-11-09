## AplikasiPenghitungHari
 Latihan 4-Muhammad Azhari Nur Pratama-2210010326

## 1. Deskripsi Program
Aplikasi ini menghitung jumlah hari dalam bulan tertentu pada tahun tertentu yang dipilih oleh pengguna.
• Pengguna memilih bulan dari JComboBox dan memasukkan tahun menggunakan JSpinner
• Gunakan JCalendar untuk memilih bulan dan tahun
• Hasil jumlah hari ditampilkan setelah tombol ditekan
  
## 2. Komponen GUI: 
JFrame, JPanel, JLabel, JComboBox, JSpinner, JButton,JCalendar

## 3. Logika Program: 
Penggunaan API tanggal (LocalDate), Perhitungan hari dalam bulan, Perhitungan tahun kabisat

## 4. Events:
• ActionListener untuk tombol Hitung
```
    private void jButton1ActionPerformed(java.awt.event.ActionEvent evt) {                                         
       jButton1.addActionListener((ActionEvent e) -> {
        kalkulatorhari();
         });
    } 
```

• ChangeListener pada JSpinner untuk input tahun
```
    private void jSpinner1StateChanged(javax.swing.event.ChangeEvent evt) {                                       
      jSpinner1.addChangeListener((ChangeEvent e) -> {
        pembaruankalender();
    });
    }  
```

## 5. Variasi:
• Tampilkan informasi tambahan seperti hari pertama dan terakhir dalam bulan tersebut
```
// Mendapatkan hari pertama dan hari terakhir dalam bulan tersebut
        LocalDate firstDay = yearMonth.atDay(1);
        LocalDate lastDay = yearMonth.atEndOfMonth();
```

• Integrasikan fitur untuk menghitung selisih hari antara dua tanggal
```
    private void jButton4ActionPerformed(java.awt.event.ActionEvent evt) {                                         
        jButton4.addActionListener((ActionEvent e) -> {
            calculateDateDifference();
        });
    }                                        

```

# Hasil Gambar Project Ketika di Run
![Cuplikan layar 2024-11-07 220052](https://github.com/user-attachments/assets/147d07ae-e4d8-4317-bcdc-135710eabc52)


## Indikator Penilaian:
| No  | Komponen         |  Persentase  |
| :-: | --------------   |   :-----:    |
|  1  | Komponen GUI     |    10    |
|  2  | Logika Program   |    20    |
|  3  | Kesesuaian UI    |    20    |
|  4  | Constructor      |    20    |
|  5  | Memenuhi Variasi |    30    |
|     | TOTAL        | 100 |


## Pembuat
Nama  : Muhammad Azhari Nur Pratama
NPM   : 2210010326
