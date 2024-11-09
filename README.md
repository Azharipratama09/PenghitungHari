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
 private void kalkulatorhari() {
        //Mengambil nilai bulan dari JComboBox
        int month = jComboBox1.getSelectedIndex() + 1; // ComboBox menggunakan indeks dari 0, jadi ditambah 1
        // Mengambil nilai tahun dari JSpinner
        int year = (int) jSpinner1.getValue();

        // Juga mengatur tanggal JCalendar sesuai dengan bulan dan tahun yang dipilih
        Calendar selectedDate = jCalendar1.getCalendar();
        selectedDate.set(Calendar.MONTH, month - 1); // Calendar.MONTH menggunakan indeks dari 0
        selectedDate.set(Calendar.YEAR, year);
        jCalendar1.setCalendar(selectedDate); // Menampilkan bulan dan tahun yang dipilih di JCalendar

        // Membuat objek YearMonth berdasarkan bulan dan tahun yang dipilih
        YearMonth yearMonth = YearMonth.of(year, month);

        // Menghitung jumlah hari dalam bulan tersebut
        int daysInMonth = yearMonth.lengthOfMonth();

        // Mendapatkan hari pertama dan hari terakhir dalam bulan tersebut
        LocalDate firstDay = yearMonth.atDay(1);
        LocalDate lastDay = yearMonth.atEndOfMonth();

        // Menampilkan hasil jumlah hari, hari pertama, dan hari terakhir pada JLabel
        jLabel10.setText(String.format(
            "Jumlah hari: %d, Hari pertama: %s, Hari terakhir: %s", 
            daysInMonth, firstDay.getDayOfWeek(), lastDay.getDayOfWeek()
        ));
     
    }

```

• ChangeListener pada JSpinner untuk input tahun
```
    private void jSpinner1StateChanged(javax.swing.event.ChangeEvent evt) {                                       
      jSpinner1.addChangeListener((ChangeEvent e) -> {
        pembaruankalender();
    });
    }
private void pembaruankalender() {
        int month = jComboBox1.getSelectedIndex(); // Indeks bulan ComboBox mulai dari 0
        int year = (int) jSpinner1.getValue();

        // Mengatur JCalendar untuk bulan dan tahun yang dipilih
        Calendar selectedDate = Calendar.getInstance();
        selectedDate.set(Calendar.YEAR, year);
        selectedDate.set(Calendar.MONTH, month); // Calendar.MONTH juga mulai dari 0
        selectedDate.set(Calendar.DAY_OF_MONTH, 1);
        jCalendar1.setCalendar(selectedDate); // Memperbarui tampilan JCalendar
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
  private void calculateDateDifference() {
        // Mendapatkan tanggal awal dan akhir dari JCalendar
        Calendar startCal = jCalendar2.getCalendar();
        Calendar endCal = jCalendar3.getCalendar();

        // Konversi Calendar ke LocalDate
        LocalDate startDate = startCal.toInstant().atZone(ZoneId.systemDefault()).toLocalDate();
        LocalDate endDate = endCal.toInstant().atZone(ZoneId.systemDefault()).toLocalDate();

        // Menghitung selisih hari menggunakan ChronoUnit.DAYS
        long daysBetween = ChronoUnit.DAYS.between(startDate, endDate);

        // Menampilkan hasil selisih hari pada JLabel
        jLabel8.setText("Selisih hari antara dua tanggal: " + daysBetween + " hari");
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
