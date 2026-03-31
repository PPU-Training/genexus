# Folder Structure
---
Dalam praktik terbaik GeneXus, meskipun platform ini tidak mewajibkan struktur folder khusus untuk front-end atau back-end, penerapan standarisasi internal tetap penting untuk memudahkan kolaborasi tim, mencakup penamaan objek, pengelompokan modul, serta pengelolaan sumber daya, sehingga meminimalkan konflik kode, mempercepat pengembangan, dan mendukung pemeliharaan serta dokumentasi proyek secara konsisten.

Berikut adalah Struktur folder Frontend 

![image](https://hackmd.io/_uploads/rJFvdM-jee.png)
```
GenexusDocumentation =>App Name
└── Root Module
    ├── General
    │   ├── UI
    │   │   └── GlobalEvents
    │   ├── **GlobalDataProvider => Folder kumpulan data relasi**
    │   │   └── DP_UserRelation
    │   ├── **GlobalSDT => Folder kumpulan struktur**
    │   │   └── SDT_User
    │   ├── **Interfaces => Folder kumpulan screen**
    │   │   └── Home
    │   ├── **Services => Folder kumpulan logic interfacing**
    │   │   ├── Proc_Users
    │   │   └── Proc_UserById
    │   ├── **Styles => Folder kumpulan style css**
    │   │   ├── GlobalStyles
    │   │   └── Images
    │   └── **UserControl => Folder kumpulan custom widget / Javascript**
    │       └── UC_Toast
```

    
Berikut adalah Struktur folder Backend

![image](https://hackmd.io/_uploads/rykMSfbogg.png)
```
GeneXusDocumentation => App name
└── Root Module
    ├── General
    ├── KnowledgeBase1 => Module Global Styling dan CSS
    ├── Transaction => Folder kumpulan object Transaction
    ├── SDT => Folder kumpulan SDT (Structured Data Type)
    ├── DataProvider => Folder kumpulan object untuk mengambil dan menyusun data
    ├── Procedure => Folder kumpulan logika atau proses bisnis
    └── API => Folder kumpulan object untuk expose service (REST API)
```
