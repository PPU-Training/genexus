# GeneXus 18 Requirements

The following is a list of the requirements to run **GeneXus 18**.

## GeneXus IDE
GeneXus IDE runs on the **Microsoft Windows Operating System**.

---

## Hardware Requirements
- Processor: minimum of 1 GHz (multi-core recommended)
- Memory: minimum of 4 GB RAM (8 GB recommended; 16 GB recommended for Android generation)
- Hard Disk: minimum 1.2 GB for installation  
  > Additional space required for knowledge bases and code generation

---

## Software Requirements
- Microsoft .NET Framework 4.7.1, 4.7.2, or 4.8 *(see note 1)*
- Microsoft SQL Server 2012+ (Express/Standard/others) or LocalDB *(see note 4)*
- Internet Explorer (Windows 10 or earlier), minimum 6.0 SP1 (11+ recommended) *(see note 2)*
- Apache Maven 3.6.1+ *(see note 3)*
- .NET SDK 8 *(see note 5)*

### Notes
1. Live Editing requires Windows 8.1+
2. Uses MSHTML libraries for HTML Editor
3. Required for installing/distributing modules
4. LocalDB only for Knowledge Base creation
5. Required if using Query or Dashboard objects

> **Note:** Admin rights are not required if SAC #39359 steps are followed.

---

## Generation Requirements

| Generator        | Requirements |
|------------------|-------------|
| .NET Framework   | ADO .NET provider for DBMS |
| .NET             | .NET SDK 8 |
| Java (1)         | Oracle JDK / OpenJDK 17+ (2) |
| Native Mobile    | Apple & Android requirements |
| Angular          | Angular requirements |

### Notes
1. Supported servers:
   - Apache Tomcat (7.0.67 – 11.x)
   - Spring Boot (JDK 17–21)
2. JDK 17+ improves compilation performance

---

## Execution Requirements

| Generator        | Requirements |
|------------------|-------------|
| .NET Framework   | .NET Framework 4.6.2+, IIS 6+, ADO .NET, URL Rewrite |
| .NET             | ASP.NET Core Runtime 8.x Hosting Bundle |
| Java             | JRE/OpenJDK 17+, Java EE/Jakarta EE Server, JDBC Driver |
| Native Mobile    | Apple & Android requirements |
| Angular          | Angular requirements |

### Notes
1. Use 4.7.2 if SameSite cookie is set
2. IIS 8 required for WebSocket
3. Servlet spec: 3.0 – 6.0
4. JDBC drivers obtained at build time
5. Hosting bundle required for IIS deployment

---

## Supported DBMS

### Main Generators (.NET, Java)

- DB2 Universal Database (7.1+)
- DB2 UDB for iSeries (V5R1+)
- Informix (7.31+)
- MySQL (4.x+)
- Oracle (8.1.5+)
- PostgreSQL (7.x+)
- SQL Server (2000+)
- SAP Hana DB (1.0+)

### Mobile
- SQLite (built-in Android/iOS)

### Notes
- DB2 iSeries requires IBM license
- Informix requires DRDA protocol
- MySQL ≥ 5.0.3 for GAM/GXflow
- Oracle ≥ 9 for GXflow
- SQL Server ≥ 2012 for GXflow

---

## Supported Browsers

### Minimum Versions

| Browser           | Min Version | Recommended |
|-------------------|------------|-------------|
| Firefox           | 97         | Latest / ESR |
| Chrome            | 99         | Latest |
| Safari            | 15.4       | Latest |
| Edge              | 99         | Latest |

### Notes
- Must support **CSS Cascade Layers**
- Must support **ES6 modules**
- jQuery 3.5.1 compatibility required

---

## Additional Notes

### WebSocket Enable (Windows)
1. Open **Windows Features**
2. Navigate to:
   - IIS → WWW Services → Application Development
3. Enable **WebSocket Protocol**

---

## Mac / Linux Support
GeneXus IDE requires Windows.

- Use Virtual Machine on Mac/Linux
- Alternative: **GeneXus Next**

---

## References
- CSS support: https://caniuse.com/css-cascade-layers  
- ES6 modules: https://caniuse.com/es6-module  
- jQuery support: https://jquery.com/browser-support/
