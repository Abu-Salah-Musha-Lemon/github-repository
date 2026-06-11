# Digital Forensics & Investigation (DFI) Laboratory Reports

This repository contains a comprehensive set of academic laboratory reports and practical guides covering various fields of digital forensics, security auditing, and evidentiary preservation. Each experiment contains structural walkthroughs, command references, and methodologies aligned with standard forensic practices.

---

## 📋 Table of Contents

1. [Experiment 01: File Hiding and Signature Analysis Using WinHex](#experiment-01-file-hiding-and-signature-analysis-using-winhex)
2. [Experiment 02: Cryptographic Password Recovery via AOPR](#experiment-02-cryptographic-password-recovery-via-aopr)
3. [Experiment 03: Folder Lock and Unlock Using Command Prompt](#experiment-03-folder-lock-and-unlock-using-command-prompt)
4. [Experiment 04: Advanced Steganography via Binary Stream Concatenation](#experiment-04-advanced-steganography-via-binary-stream-concatenation)
5. [Experiment 05: Live Volatile Memory (RAM) Acquisition](#experiment-05-live-volatile-memory-ram-acquisition)
6. [Experiment 06: Expert Witness Format (E01) Image Container Generation](#experiment-06-expert-witness-format-e01-image-container-generation)

---

## 🔬 Experiment Summaries & Technical Specs

### Experiment 01: File Hiding and Signature Analysis Using WinHex
* **Objective:** Manipulate binary-level headers to bypass operating system file-type validation.
* **Core Concepts:** File signatures (magic numbers), hex editing, file identification layer validation.
* **Key Targets:** Modifying JPEG header signature structures (`FF D8 FF E0` / `FF D8 FF E1`) to securely disrupt standard photo application workflows without corrupting the underlying payload blocks.

### Experiment 02: Cryptographic Password Recovery via AOPR
* **Objective:** Audit and decrypt document protection schemas using targeted algorithmic arrays.
* **Software Tool:** Advanced Office Password Recovery (AOPR) v7.20.
* **Attack Metrics Covered:** Brute-Force, Dictionary Lookup, Mask Restriction, and Hybrid-Combination architectures.
* **Recovered Core Metric:** Successfully decrypted a protected Word Document password layer to surface target plaintext credentials (`six`).

### Experiment 03: Folder Lock and Unlock Using Command Prompt
* **Objective:** Use file system attribute modification switches via the command line interpreter to conceal entire local storage assets.
* **Commands Applied:** * Lock: `attrib +h +s "FolderName"`
  * Unlock: `attrib -h -s "FolderName"`
* **Forensic Significance:** Demonstrates how OS-level security descriptors can mask elements from visual rendering lists, shielding them even when basic hidden files are displayed.

### Experiment 04: Advanced Steganography via Binary Stream Concatenation
* **Objective:** Build multi-format hybrid containers holding hidden compressed data payloads beneath standard graphics wrappers.
* **Execution Pattern:** `copy /b host_image.jpg + hidden_payload.zip output_composite.jpg`
* **Mechanics:** Exploits the JPEG End-of-Image (EOI) termination boundary block (`FF D9`) to preserve native image layout functionality while allowing bottom-up zip archive carvers (like 7-Zip) to extract internal archives.

### Experiment 05: Live Volatile Memory (RAM) Acquisition
* **Objective:** Capture volatile runtime system state metadata before execution memory updates decay due to reboots or shutdowns.
* **Tooling Infrastructure:** Exterro FTK Imager application framework layer.
* **Triage Logging Array:** Outlines system commands (`systeminfo`, `tasklist`, `ipconfig /all`, `netstat`, `net user`, `arp -a`, `driverquery`) necessary to capture network connections, driver configurations, and memory layout spaces prior to running physical memory image burns.

### Experiment 06: Expert Witness Format (E01) Image Container Generation
* **Objective:** Securely encapsulate raw unstructured data dumps into verified, authenticated forensic images.
* **Output Format:** E01 (Expert Witness Format) using structural middle-tier compression parameters.
* **Mathematical Verification Metrics:**
  * **MD5 Checksum:** `50f98918fb45f4136a8b067018a2da2d` (Verified Match Status)
  * **SHA1 Checksum:** `e8cca43e83bb9e94487a6402f10991b5777d7c1d` (Verified Match Status)
  * **Bad Blocks Count:** Exactly `0` — mathematically validating pristine duplication profiles.

---

## 🛠️ Requirements & Environment Setup
* **Operating System:** Windows 11 (Build 10.0.26100) running with elevated Administrator command shell parameters.
* **Forensic Software Toolsets:** * WinHex Editor Suite
  * ElcomSoft Advanced Office Password Recovery (AOPR)
  * Exterro FTK Imager Desktop GUI
  * 7-Zip Archival Suite

---

## 🖋️ Verification & Chain of Custody
All experiments documented within these outputs have been formally validated against mathematical hash matches to confirm data integrity. 
* **Verification Date:** June 11, 2026
