# GeneXus 18 Requirements

Berikut adalah kebutuhan untuk menjalankan **GeneXus 18**.

---

## 🖥️ Sistem Operasi
- Hanya berjalan di **Windows**

---

## ⚙️ Hardware Minimum
- **Processor:** 1 GHz (disarankan multi-core)
- **RAM:** 4 GB (disarankan 8 GB, 16 GB untuk Android)
- **Storage:** 1.2 GB (butuh tambahan untuk project & build)

---

## 💻 Software
- .NET Framework 4.7.1 / 4.7.2 / 4.8
- SQL Server 2012+ atau LocalDB
- Internet Explorer (khusus Windows 10 ke bawah)
- Apache Maven 3.6.1+
- .NET SDK 8

### Catatan
- Windows 8.1+ untuk Live Editing
- LocalDB hanya untuk Knowledge Base
- .NET SDK 8 wajib untuk Query/Dashboard

---

## 🏗️ Kebutuhan Generate

| Generator | Kebutuhan |
|----------|----------|
| .NET Framework | ADO .NET Provider |
| .NET | .NET SDK 8 |
| Java | JDK 17+ |
| Mobile | Requirement Apple & Android |
| Angular | Requirement Angular |

**Tambahan:**
- Server: Tomcat / Spring Boot
- Disarankan JDK 17+

---

## ▶️ Kebutuhan Runtime

| Generator | Kebutuhan |
|----------|----------|
| .NET Framework | .NET 4.6.2+, IIS, URL Rewrite |
| .NET | ASP.NET Core Runtime 8 |
| Java | JRE 17+, Java EE Server |
| Mobile | Requirement Apple & Android |
| Angular | Requirement Angular |

---

## 🗄️ Database yang Didukung

- DB2
- Informix
- MySQL
- Oracle
- PostgreSQL
- SQL Server
- SAP Hana

**Mobile:**
- SQLite (bawaan Android/iOS)

---

## 🌐 Browser Support

| Browser | Minimum |
|--------|--------|
| Firefox | 97 |
| Chrome | 99 |
| Safari | 15.4 |
| Edge | 99 |

**Wajib:**
- Support CSS Cascade Layers
- Support ES6 Modules

---

## 🔧 Catatan Tambahan

### Aktifkan WebSocket (Windows)
1. Buka **Windows Features**
2. Masuk ke:
   - IIS → WWW Services → Application Development
3. Aktifkan **WebSocket Protocol**

---

## 🍎 Mac & Linux

- Tidak support langsung
- Gunakan:
  - Virtual Machine (Windows)
  - Alternatif: GeneXus Next

---

## 🔗 Referensi
- https://caniuse.com/css-cascade-layers  
- https://caniuse.com/es6-module  
- https://jquery.com/browser-support/
