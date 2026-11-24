# 🦉 OBiopsy

<p align="center">
  <img src="https://img.shields.io/badge/Platform-Linux-0a0c10?style=flat-square"/>
  <img src="https://img.shields.io/badge/Category-OForensics-blue?style=flat-square"/>
  <img src="https://img.shields.io/badge/License-Proprietary-orange?style=flat-square"/>
  <img src="https://img.shields.io/badge/Part%20of-OwlSec%20Toolkit-7b5ea7?style=flat-square"/>
  <img src="https://img.shields.io/badge/Version-2.1.0-cyan?style=flat-square"/>
</p>

> **OBiopsy** — Advanced Digital Forensics & Intelligence Suite

---

> ⚠️ **AUTHORISED USE ONLY** — Use only on systems you own or have explicit written permission to test. Unauthorised use is illegal.

---

## 📌 Overview

OBiopsy is a digital forensics and intelligence suite for triaging files and artifacts with no external dependencies. It computes hashes, identifies file types by magic bytes, measures entropy, extracts strings and network artifacts, and compares hashes against IOCs or IOC lists. A subcommand interface makes each capability scriptable, and findings can be exported as a full JSON report.

---

## ✨ Features

- File hashing (MD5/SHA1/SHA256, optional SHA512/BLAKE2b)
- Magic-byte file-type identification and Shannon entropy
- Printable-string extraction with length filter and grep
- IOC hash comparison against a single hash or a hash list
- YARA-style pattern scanning and network-artifact extraction
- Directory batch scanning (JSON lines) and full JSON report export

---

## ⚙️ Requirements

- **Linux**
- **No Python installation needed** — runs as a standalone executable

---

## 🚀 Usage

```bash
./OBiopsy hash suspicious.bin --extra
./OBiopsy strings malware.exe -n 10 --grep http
./OBiopsy batch ./evidence/ --max 500
./OBiopsy --help
```

---

## 📦 Part of OwlSec Toolkit

This tool is part of the **OwlSec** suite — a collection of 275+ security and privacy tools.

🔗 [owlsec.org](https://owlsec.org)

---

## ©️ License

Proprietary — © 2026 Owlsec LLC. All rights reserved.

*Tools are distributed as pre-built executables. Source code is proprietary.*

---

## 🔍 Verification & Transparency

This tool is closed-source. These files let you see exactly what is inside it,
without the source:

- [`SBOM.cdx.json`](SBOM.cdx.json) — CycloneDX inventory: SHA-256 of this
  binary, bundled CPython version, and every bundled library with its exact
  version and license. Feed it to Grype, Trivy or Dependency-Track to audit
  our dependencies for CVEs yourself.
- [`THIRD-PARTY-NOTICES.md`](THIRD-PARTY-NOTICES.md) — the full license text
  of every third-party component, extracted from this binary.

**No telemetry, no analytics, no licence check-in.** This tool does not phone
home. Verify that claim yourself:

```bash
sudo strace -f -e trace=network ./OBiopsy --help   # watch every network call
firejail --net=none ./OBiopsy --help               # deny the network entirely
```

Release signing, GPL compliance and vulnerability reporting:
[**TRUST.md**](https://github.com/owlsecx/owl-os/blob/main/TRUST.md)
