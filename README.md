# Loan Portfolio Risk Analysis

## Project Background

Pemberian pinjaman merupakan salah satu aktivitas utama dalam industri keuangan. Keputusan yang kurang tepat dalam menilai kelayakan peminjam dapat meningkatkan risiko gagal bayar (*default*) dan berdampak pada kerugian perusahaan.

Proyek ini bertujuan untuk menganalisis profil borrower guna mengidentifikasi karakteristik peminjam yang memiliki risiko gagal bayar paling tinggi. Hasil analisis diharapkan dapat membantu lembaga keuangan memahami faktor-faktor yang memengaruhi risiko pinjaman sehingga proses evaluasi kredit dapat dilakukan secara lebih efektif.

---

## Business Problem

**Which borrower profiles have the highest probability of default?**

Untuk menjawab pertanyaan tersebut, analisis difokuskan pada hubungan antara kondisi finansial borrower dengan status pembayaran pinjaman.

---

## Project Objectives

Analisis dilakukan untuk:

- Mengidentifikasi profil borrower dengan risiko default tertinggi.
- Menentukan faktor yang paling berpengaruh terhadap risiko pinjaman.
- Menemukan kombinasi karakteristik borrower yang paling berisiko untuk diberikan pinjaman.

---

## Dataset Overview

Dataset berisi informasi mengenai borrower beserta karakteristik keuangan dan status pinjamannya. Setiap baris pada dataset merepresentasikan **satu borrower**.

### Kolom yang digunakan

| Kolom | Deskripsi |
|-------|-----------|
| **annual_income** | Pendapatan tahunan borrower untuk menganalisis hubungan income terhadap risiko default. |
| **debt_to_income (DTI)** | Rasio utang terhadap pendapatan yang menggambarkan beban finansial borrower. |
| **grade** | Kelas risiko kredit (A–G), di mana Grade A merupakan kualitas kredit terbaik dan Grade G paling berisiko. |
| **loan_status** | Status pinjaman yang digunakan untuk mengelompokkan pinjaman menjadi kategori Good dan Risky. |
| **loan_amount** | Jumlah pinjaman yang digunakan untuk melihat hubungan besar pinjaman dengan risiko default. |

### Feature Engineering

Untuk mendukung analisis, dibuat beberapa kolom baru:

- **loan_risk**
  - Good
  - Risky

- **income_segment**
  - Low Income
  - Middle Income
  - High Income

- **dti_segment**
  - Low DTI
  - Medium DTI
  - High DTI

- **loan_amount_segment**
  - Small Loan
  - Medium Loan
  - Large Loan

---

## Data Cleaning

Sebelum dilakukan analisis, dilakukan proses pembersihan data untuk meningkatkan kualitas dataset.

| Kolom | Permasalahan | Jumlah Data | Magnitude | Solvable | Penanganan |
|-------|--------------|------------:|----------:|:--------:|------------|
| annual_income | Nilai income 0 atau 1 | 24 | 0.24% | Ya | Removed |
| debt_to_income | Nilai NULL | 24 | 0.24% | Ya | Removed |
| Seluruh kolom | Data duplikat | 28 | 0.28% | Ya | Removed |
| Seluruh kolom | Baris kosong | 5 | 0.05% | Ya | Removed |

Seluruh permasalahan data memiliki proporsi kurang dari 1% sehingga penghapusan data tidak memberikan pengaruh yang signifikan terhadap hasil analisis.

---

## Tools

- Microsoft Excel
- Pivot Table
- Conditional Formatting
- Data Visualization

---

## Business Questions

Analisis dilakukan untuk menjawab beberapa pertanyaan berikut.

1. Apakah borrower dengan income rendah lebih sering mengalami default?
2. Apakah Debt-to-Income (DTI) yang tinggi meningkatkan risiko default?
3. Grade kredit mana yang memiliki tingkat default tertinggi?
4. Apakah jumlah pinjaman yang lebih besar memiliki risiko lebih tinggi?

---

## Expected Insights

Melalui analisis ini diharapkan dapat diperoleh insight mengenai:

- Profil borrower dengan risiko default tertinggi.
- Faktor yang paling memengaruhi risiko default.
- Kombinasi karakteristik borrower yang paling berbahaya untuk diberikan pinjaman.

---

## Analysis Preview

![Loan Portfolio Risk Analysis](analysis-preview.png)

---

## Analysis Results

### 1. Overall Loan Risk Distribution

Sebagian besar pinjaman berada pada kategori **Good**.

- Good Loan : **9.794**
- Risky Loan : **177**

Hanya sekitar **1,78%** dari seluruh pinjaman yang tergolong berisiko.

---

### 2. Loan Risk by Income Segment

| Income Segment | Risk Rate |
|---------------|----------:|
| Low Income | **2.15%** |
| High Income | **1.81%** |
| Middle Income | **1.66%** |

Borrower dengan pendapatan rendah menunjukkan tingkat risiko tertinggi dibandingkan kelompok income lainnya.

---

### 3. Loan Risk by Debt-to-Income (DTI)

| DTI Segment | Risk Rate |
|------------|----------:|
| Low DTI | **1.92%** |
| Medium DTI | **1.61%** |
| High DTI | **1.92%** |

Hasil analisis menunjukkan bahwa hubungan antara DTI dan risiko default tidak menunjukkan pola yang konsisten.

---

### 4. Loan Risk by Credit Grade

| Credit Grade | Risk Rate |
|-------------|----------:|
| A | 0.77% |
| B | 1.09% |
| C | 1.96% |
| D | 3.41% |
| E | 5.09% |
| F | **10.53%** |
| G | 8.33% |

Semakin rendah kualitas grade kredit, semakin tinggi tingkat risiko default.

---

### 5. Loan Risk by Loan Size

| Loan Size | Risk Rate |
|-----------|----------:|
| Small Loan | 1.46% |
| Medium Loan | 1.61% |
| Large Loan | **2.35%** |

Borrower dengan jumlah pinjaman yang lebih besar cenderung memiliki tingkat risiko yang lebih tinggi.

---

### 6. Borrower Risk Combination Analysis

Analisis kombinasi menggunakan heatmap berdasarkan **Credit Grade** dan **Income Segment** menunjukkan bahwa:

- Grade F + Low Income memiliki tingkat risiko tertinggi (**12.50%**).
- Grade F + Middle Income memiliki tingkat risiko sebesar (**10.81%**).
- Borrower dengan grade kredit rendah tetap memiliki risiko tinggi meskipun berada pada kelompok income yang lebih tinggi.

Hal ini menunjukkan bahwa **Credit Grade merupakan faktor yang paling dominan dalam memengaruhi risiko default**.

---

## Key Findings

Berdasarkan hasil analisis, diperoleh beberapa temuan utama:

- Portofolio pinjaman didominasi oleh pinjaman dengan status **Good**, sementara pinjaman berisiko hanya sekitar **1.78%**.
- Borrower dengan **income rendah** memiliki kecenderungan risiko lebih tinggi dibandingkan kelompok income lainnya.
- **Credit Grade** merupakan faktor yang paling berpengaruh terhadap risiko default.
- Borrower dengan **jumlah pinjaman besar** menunjukkan tingkat risiko yang lebih tinggi.
- Hubungan antara **Debt-to-Income (DTI)** dan risiko default tidak menunjukkan pola yang konsisten.
- Kombinasi **Grade F dan Low Income** merupakan kelompok borrower dengan tingkat risiko tertinggi.

---

## Recommendations

Berdasarkan hasil analisis, beberapa rekomendasi yang dapat dipertimbangkan adalah:

- Memperketat proses evaluasi kredit untuk borrower dengan **Credit Grade** rendah, terutama Grade E, F, dan G.
- Memberikan evaluasi tambahan pada pengajuan pinjaman dengan nominal besar.
- Menjadikan **Credit Grade** sebagai indikator utama dalam proses penilaian risiko kredit.
- Melakukan penilaian lebih mendalam terhadap borrower dengan pendapatan rendah sebelum pinjaman disetujui.
- Mengembangkan model credit scoring yang mengombinasikan Credit Grade, Income, dan Loan Amount agar proses penilaian risiko menjadi lebih akurat.

---

## Business Relevance

Analisis ini relevan untuk berbagai institusi keuangan, seperti:

- Bank
- Pegadaian
- Perusahaan Pembiayaan (Multifinance)
- Fintech Lending
- Koperasi Simpan Pinjam

Hasil analisis dapat digunakan sebagai dasar untuk meningkatkan kualitas proses penilaian kredit, mengurangi risiko gagal bayar, serta membantu pengambilan keputusan dalam pemberian pinjaman.

---

## Limitations

- Klasifikasi risiko disederhanakan menjadi dua kategori, yaitu **Good** dan **Risky**, berdasarkan status pinjaman.
- Segmentasi Income, DTI, dan Loan Amount dibuat berdasarkan distribusi data pada dataset, bukan berdasarkan kebijakan resmi suatu institusi keuangan.
- Analisis ini bersifat **Exploratory Data Analysis (EDA)** sehingga menunjukkan hubungan antarvariabel dan bukan hubungan sebab-akibat.
