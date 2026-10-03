
<p align="center">
  <img src="https://github.com/user-attachments/assets/51fe122d-6993-4e35-b497-e9499fa78299" alt="IDA Pro Custom Logo" width="100%">
</p>

<p align="center">
  <img src="https://img.shields.io/badge/PYTHON-3776AB?style=for-the-badge&logo=python&logoColor=white" alt="Python">
  <img src="https://img.shields.io/badge/IDAPARSER-000000?style=for-the-badge&logo=codeforces&logoColor=white" alt="IDA Pro">
  <img src="https://img.shields.io/badge/CRYPTO-FF6F00?style=for-the-badge&logo=letsencrypt&logoColor=white" alt="RSA / Crypto">
  <img src="https://img.shields.io/badge/JSON-000000?style=for-the-badge&logo=json&logoColor=white" alt="JSON Serialization">
  <img src="https://img.shields.io/badge/HEX_EDITING-E24329?style=for-the-badge&logo=gnu-bash&logoColor=white" alt="Hex Patching">
  <img src="https://img.shields.io/badge/CROSS__PLATFORM-FCC624?style=for-the-badge&logo=linux&logoColor=black" alt="Multiplatform">
</p>

---

# IDA-Tools: Advanced Binary Patching and License Generation Suite

An advanced utility based on IDAPython and Python automation designed for static analysis binary manipulation, custom license structure management, and cross-platform RSA public modulus patching routines.

---

## Architecture and Technologies Involved

The development and implementation of this utility suite span multiple technical layers of reverse engineering and cryptography:

* **Python Core (`hashlib`, `json`, `os`):** Automation of workflows, alphabetical serialization of JSON dictionaries, and file processing on disk.
* **Asymmetric Cryptography (RSA):** Handling of large integers (bigints), byte transformations (little-endian / big-endian), modular exponentiation (`pow`), and SHA-256 secure hash digest functions for payload signing.
* **Binary Analysis and IDAPython:** Inspection of internal structures, Hex-Ray modules, and localization of public key signatures within compiled binaries.
* **Reverse Engineering and Hex Editing:** Identification of offsets, replacement of original byte sequences (`EDFD425CF978...`) with modified moduli (`EDFD42CBF978...`), and integrity validation.
* **Cross-Platform Support:** Adapted routines for 32-bit and 64-bit architectures across Windows, Linux, and macOS environments.

---

## Key Features

1. **Automated License Generation (`idapro.hexlic`):**
   * JSON structure featuring version metadata and configurable user details.
   * Massive injection of add-ons via the `add_every_addon()` function, mapping processor platforms (`HEXX86`, `HEXX64`, `HEXARM`, `HEXRV64`, etc.) with extended validity.
2. **Cryptographic Payload Signing (`sign_hexlic`):**
   * Strict alphabetical key ordering to ensure compatibility with the validator.
   * Generation of padding blocks and computation of secure hash digests signed using an integrated RSA private key.
3. **Automated Binary Patching (`generate_patched_dll`):**
   * Intelligent scanning of target binaries within the working directory.
   * Pre-execution status verification to prevent re-patching if the file has already been modified.
   * Automated generation of `.patched` copies ready to replace the originals.

---

## Supported Target Binaries

The script automatically scans and processes the following components depending on the operating system:

* **Windows:** `ida32.dll`, `ida.dll`
* **Linux:** `libida32.so`, `libida.so`
* **macOS:** `libida32.dylib`, `libida.dylib`

---

## Usage Instructions

Place the script alongside the IDA binaries or libraries you want to process in the same directory and run:

```bash
python IDA.py
