# Reconnaissance & Enumeration Report

## 📌 Target Information

| Item | Detail |
|------|--------|
| Program Platform | (Bugcrowd / HackerOne / YesWeHack) |
| Target Name | |
| Target Domain | |
| Scope Type | (Domain / Wildcard / API / etc) |
| Engagement Rules Followed | Yes |

---

# 1️⃣ Reconnaissance Phase

## 1.1 Web Stack Identification

### Objective
Mengidentifikasi teknologi yang digunakan oleh target.

### Methodology
- Wappalyzer
- BuiltWith
- HTTP Header Inspection
- WhatWeb
- Manual inspection

### Findings

| Component | Technology |
|------------|------------|
| Web Server | |
| Backend Language | |
| Framework | |
| CDN | |
| WAF | |
| Other | |

### Evidence

```
[Masukkan hasil scan yang relevan]
```

---

## 1.2 Domain Registration Information

### Objective
Mengetahui informasi registrar dan metadata domain.

### Tools Used
- whois
- online WHOIS lookup

### Findings

| Item | Result |
|------|--------|
| Registrar | |
| Creation Date | |
| Expiration Date | |
| Name Server | |
| Privacy Protection | Yes / No |

### Analysis
Jelaskan apakah domain menggunakan privacy guard dan apa implikasinya.

---

# 2️⃣ DNS Enumeration

## 2.1 DNS Record Enumeration

### Tools Used
- dig
- nslookup
- dnsrecon

### Record Types Checked
- A
- AAAA
- MX
- TXT
- NS
- CNAME

### Findings

| Record Type | Result |
|-------------|--------|
| A | |
| MX | |
| TXT | |
| etc | |

### Analysis
Apakah ditemukan:
- SPF record?
- DMARC?
- Subdomain via certificate transparency?
- Misconfiguration?

Jika DNS enumeration gagal:
Jelaskan penyebabnya (WAF, DNSSEC, rate limiting, dll)

---

# 3️⃣ Subdomain Enumeration

## 3.1 Methodology

- Subfinder
- Amass
- Assetfinder
- crt.sh
- Certificate Transparency logs
- Passive enumeration

## 3.2 Findings

Total subdomain ditemukan: **X**

```
sub1.target.com
sub2.target.com
api.target.com
dev.target.com
...
```

## 3.3 Categorization

| Subdomain | Purpose |
|------------|---------|
| api | API service |
| dev | Development |
| mail | Mail server |
| cdn | CDN |

---

# 4️⃣ Directory Enumeration / Fuzzing

## 4.1 Tools Used
- ffuf
- gobuster
- dirsearch

## 4.2 Wordlist Used
- SecLists common.txt
- directory-list-2.3-medium.txt

## 4.3 Findings

```
/admin
/login
/dashboard
/api/v1/
/backup.zip
```

## 4.4 Analysis
Apakah ditemukan:
- Endpoint sensitif?
- Backup file?
- Misconfigured directory?
- Dev endpoint exposed?

---

# 5️⃣ Wayback Machine Enumeration

## 5.1 Objective
Mengidentifikasi endpoint lama atau tidak terdokumentasi.

## 5.2 Tools
- waybackurls
- gau

## 5.3 Findings

Total historical URL: **X**

Contoh:

```
/old-admin/
/beta/
/v1/api/
/test.php
```

## 5.4 Analysis
Apakah ditemukan:
- Deprecated endpoint?
- Hardcoded parameter?
- API lama yang masih aktif?

---

# 6️⃣ Google Dorking

## 6.1 Dorks Used

```
site:target.com
site:target.com filetype:sql
site:target.com inurl:admin
site:target.com ext:env
```

## 6.2 Findings

| Dork | Result |
|------|--------|
| filetype:sql | Not Found |
| inurl:admin | Login page found |
| ext:env | None |

---

# 7️⃣ Overall Attack Surface Summary

| Category | Count |
|-----------|--------|
| Subdomains | |
| Live Subdomains | |
| Sensitive Endpoints | |
| Historical URLs | |

---

# 8️⃣ Observations & Potential Risk Areas

- Development subdomain exposed
- API endpoint publicly accessible
- Outdated framework detected
- Possible information disclosure via headers

> Note: No exploitation performed. Only passive & safe reconnaissance conducted.

---

# 9️⃣ Conclusion

Reconnaissance berhasil dilakukan sesuai scope program.  
Beberapa area berpotensi untuk diuji lebih lanjut pada tahap vulnerability assessment.
