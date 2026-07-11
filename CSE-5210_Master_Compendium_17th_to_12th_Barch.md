# Digital Forensics & Investigation — Exam Answers

Exam-ready answers to **six past final-exam papers** for *Digital Forensics and Investigation* (CSE-5210 / CSE-520), M.Sc. in CSE (Professional), Jagannath University — sourced strictly from the course lecture sheet (*Guide to Computer Forensics and Investigations*, 4th Edition, 16 chapters).

Repeated questions across papers are answered once and referenced consistently; where the lecture sheet doesn't cover a topic, this is marked **Insufficient Information**.

---

## 📑 Table of Contents

- [Paper 1 — Winter 2025 (17th batch), Full Marks 60](#paper-1--winter-2025-17th-batch-full-marks-60)
  - [Question 1](#p1--question-1)
    - [(a) Do computer forensics and data recovery refer to the same activities? Justify your answer.](#p1-q1a)
    - [(b) List three common types of digital crime.](#p1-q1b)
    - [(c) What are some ways to determine the resources needed for an investigation?](#p1-q1c)
  - [Question 2](#p1--question-2)
    - [(a) What do you mean by remote acquisition? Explain the remote acquisition with ProDiscover Basic or EnCase Enterprise.](#p1-q2a)
    - [(b) Describe certification and training requirements for digital forensics labs.](#p1-q2b)
    - [(c) Explain the purpose of a virtual machine for computer forensics and investigation.](#p1-q2c)
  - [Question 3](#p1--question-3)
    - [(a) How do inodes keep track of a file's name and data?](#p1-q3a)
    - [(b) Discuss the importance of digital hash in forensic investigation.](#p1-q3b)
    - [(c) What are the five required functions for computer forensics tools? Briefly explain.](#p1-q3c)
  - [Question 4](#p1--question-4)
    - [(a) How can 'Hiding Partitions' and 'Marking Bad Clusters' techniques be used to hide data?](#p1-q4a)
    - [(b) What is carving or salvaging? How does one repair a damaged file header?](#p1-q4b)
    - [(c) Write down the steps for reconstructing file fragments.](#p1-q4c)
  - [Question 5](#p1--question-5)
    - [(a) What do you mean by validating forensics data? Explain validating with hexadecimal editors.](#p1-q5a)
    - [(b) What is drive slack? Explain it according to the purposes of digital forensics.](#p1-q5b)
    - [(c) Explain different types of digital evidence storage formats.](#p1-q5c)
  - [Question 6](#p1--question-6)
    - [(a) What is the necessity of live acquisition? Explain standard procedure for live acquisition.](#p1-q6a)
    - [(b) Explain internet abuse and e-mail abuse investigation.](#p1-q6b)
    - [(c) Explain bit stream copy and bit stream image with examples.](#p1-q6c)
  - [Question 7](#p1--question-7)
    - [(a) Explain the acquisition procedures for cell phones and mobile devices.](#p1-q7a)
    - [(b) Describe tasks in investigation of e-mail crime and violations.](#p1-q7b)
    - [(c) Analyze the function of e-mail forensics tools.](#p1-q7c)
- [Paper 2 — Summer 2024 (16th batch)](#paper-2--summer-2024-16th-batch)
  - [Question 1](#p2--question-1)
    - [(a) What do you mean by remote acquisition? Explain the remote acquisition with ProDiscover Basic or EnCase Enterprise.](#p2-q1a)
    - [(b) What is carving or salvaging? How does one repair a damaged file header?](#p2-q1b)
    - [(c) State the procedure of reconstructing a File Fragment.](#p2-q1c)
  - [Question 2](#p2--question-2)
    - [(a) Explain and state hardware and software forensics tools.](#p2-q2a)
    - [(b) Describe tasks performed by computer forensics tools.](#p2-q2b)
    - [(c) Explain the Resilient file system in brief.](#p2-q2c)
  - [Question 3](#p2--question-3)
    - [(a) Explain the key certification requirements and guidelines set by ASCLD for a computer-forensics lab.](#p2-q3a)
    - [(b) Compare and contrast the three digital-evidence storage formats — raw, proprietary, and AFF — including advantages/disadvantages.](#p2-q3b)
    - [(c) Describe the challenges and methods for acquiring data from RAID systems.](#p2-q3c)
  - [Question 4](#p2--question-4)
    - [(a) Explain common data hiding techniques in brief.](#p2-q4a)
    - [(b) What is write blocker? Explain software-write blocker and hardware-write blocker in brief.](#p2-q4b)
    - [(c) Explain the contingency planning for image acquisition.](#p2-q4c)
  - [Question 5](#p2--question-5)
    - [(a) An employee suspects his password has been compromised (changed 2 days ago, still used). What might be going on?](#p2-q5a)
    - [(b) What is drive slack? Explain it according to the purposes of digital forensics.](#p2-q5b)
    - [(c) Explain different types of digital evidence storage formats.](#p2-q5c)
  - [Question 6](#p2--question-6)
    - [(a) Define 'order of volatility' and explain how it guides your actions during a live acquisition.](#p2-q6a)
    - [(b) List and explain three common e-mail fraud techniques.](#p2-q6b)
    - [(c) Outline the standard procedure for a live RAM acquisition on a compromised system.](#p2-q6c)
  - [Question 7](#p2--question-7)
    - [(a) What is the necessity of live acquisition? Explain standard procedure for live acquisition.](#p2-q7a)
    - [(b) What is validation protocol? Explain digital forensics examination protocol.](#p2-q7b)
    - [(c) Describe certification and training requirements for digital forensics labs.](#p2-q7c)
- [Paper 3 — Winter 2023 (15th batch)](#paper-3--winter-2023-15th-batch)
  - [Question 1](#p3--question-1)
    - [(a) Define computer forensics and explain bit stream copy & bit stream image.](#p3-q1a)
    - [(b) What is computer crime? Why do you need Mini-WinFE Boot CD/DVD or USB drive?](#p3-q1b)
    - [(c) Explain the ways to determine the best acquisition method.](#p3-q1c)
  - [Question 2](#p3--question-2)
    - [(a) What do you mean by remote acquisition? Explain the remote acquisition with ProDiscover Basic or EnCase Enterprise.](#p3-q2a)
    - [(b) What is carving or salvaging? How does repair damaged file header?](#p3-q2b)
    - [(c) Explain the purpose of a virtual machine for computer forensics and investigation.](#p3-q2c)
  - [Question 3](#p3--question-3)
    - [(a) Explain the roles of Windows Registry for computer forensics and investigation.](#p3-q3a)
    - [(b) Describe tasks perform by computer forensics tools.](#p3-q3b)
    - [(c) Explain Resilient file system in brief.](#p3-q3c)
  - [Question 4](#p3--question-4)
    - [(a) Explain common data hiding techniques in brief.](#p3-q4a)
    - [(b) What is write blocker? Explain software-write blocker and hardware-write blocker in brief.](#p3-q4b)
    - [(c) Write down the steps for reconstructing file fragments.](#p3-q4c)
  - [Question 5](#p3--question-5)
    - [(a) An employee suspects his password has been compromised (changed 2 days ago, still used). What might be going on?](#p3-q5a)
    - [(b) What is drive slack? Explain it according to the purposes of digital forensics.](#p3-q5b)
    - [(c) Explain different types of digital evidence storage formats.](#p3-q5c)
  - [Question 6](#p3--question-6)
    - [(a) What is the necessity of live acquisition? Explain standard procedure for live acquisition.](#p3-q6a)
    - [(b) What is validation protocol? Explain digital forensics examination protocol.](#p3-q6b)
    - [(c) Describe certification and training requirements for digital forensics labs.](#p3-q6c)
  - [Question 7](#p3--question-7)
    - [(a) What procedural steps should a digital forensic investigator follow when analyzing emails?](#p3-q7a)
    - [(b) What are the critical factors to consider when conducting an email investigation?](#p3-q7b)
    - [(c) How can forensic investigators handle the obstacles from encrypted emails and signed messages?](#p3-q7c)
- [Paper 4 — Winter 2023 (14th batch), Full Marks 50](#paper-4--winter-2023-14th-batch-full-marks-50)
  - [Question 1](#p4--question-1)
    - [(a) Define computer forensics, network forensics and data recovery.](#p4-q1a)
    - [(b) What is digital evidence? Assess general tasks investigators perform with digital evidence.](#p4-q1b)
    - [(c) Explain the ways to determine the best acquisition method.](#p4-q1c)
  - [Question 2](#p4--question-2)
    - [(a) What do you mean by remote acquisition? Explain with ProDiscover Basic or EnCase Enterprise.](#p4-q2a)
    - [(b) What do you understand by EFS and BitLocker? Explain whole disk encryption.](#p4-q2b)
    - [(c) Explain the purpose of a virtual machine for computer forensics and investigation.](#p4-q2c)
  - [Question 3](#p4--question-3)
    - [(a) Explain bit stream copy and bit stream image with examples.](#p4-q3a)
    - [(b) Describe tasks perform by computer forensics tools.](#p4-q3b)
    - [(c) Explain the roles of Windows Registry for computer forensics and investigation.](#p4-q3c)
  - [Question 4](#p4--question-4)
    - [(a) Explain common data hiding techniques in brief.](#p4-q4a)
    - [(b) What is carving or salvaging? How does repair damaged file header?](#p4-q4b)
    - [(c) Write down the steps for reconstructing file fragments.](#p4-q4c)
  - [Question 5](#p4--question-5)
    - [(a) What do you mean by validating forensics data? Explain validating with hexadecimal editors.](#p4-q5a)
    - [(b) What is drive slack? Explain it according to the purposes of digital forensics.](#p4-q5b)
    - [(c) Explain different types of digital evidence storage formats.](#p4-q5c)
  - [Question 6](#p4--question-6)
    - [(a) Explain the concept of hashing in digital forensics and its role in verifying integrity.](#p4-q6a)
    - [(b) Describe the role of machine learning and AI in modern computer forensics tools.](#p4-q6b)
  - [Question 7](#p4--question-7)
    - [(a) Describe the steps involved in conducting an email investigation. Outline key considerations at each stage.](#p4-q7a)
    - [(b) Evaluate the role of email encryption and digital signatures in email investigations.](#p4-q7b)
- [Paper 5 — Winter 2023 (13th batch), Full Marks 50](#paper-5--winter-2023-13th-batch-full-marks-50)
  - [Question 1](#p5--question-1)
    - [(a) Explain digital forensics and investigations in brief.](#p5-q1a)
    - [(b) What is digital evidence? Assess general tasks investigators perform with digital evidence.](#p5-q1b)
    - [(c) Explain the ways to determine the best acquisition method.](#p5-q1c)
  - [Question 2](#p5--question-2)
    - [(a(i–ii)) Discuss the need for Extraction in computer forensics; list any two sub-functions of Extraction.](#p5-q2aiii)
    - [(b) Illustrate in detail how Substitution works in Steganography. Give a clear example.](#p5-q2b)
  - [Question 3](#p5--question-3)
    - [(a) Explain bit stream copy and bit stream image with examples.](#p5-q3a)
    - [(b) Describe tasks perform by computer forensics tools.](#p5-q3b)
    - [(c) Explain developing standard procedure for network forensics.](#p5-q3c)
  - [Question 4](#p5--question-4)
    - [(a) Explain common data hiding techniques in brief.](#p5-q4a)
    - [(b) What is carving or salvaging? How does repair damaged file header?](#p5-q4b)
    - [(c) Write down the steps for reconstructing file fragments.](#p5-q4c)
  - [Question 5](#p5--question-5)
    - [(a) What do you mean by validating forensics data? Explain validating with hexadecimal editors.](#p5-q5a)
    - [(b) What is drive slack? Explain it according to the purposes of digital forensics.](#p5-q5b)
    - [(c) Explain different types of digital evidence storage formats.](#p5-q5c)
  - [Question 6](#p5--question-6)
    - [(a) Compare and contrast RAID 0 and RAID 1.](#p5-q6a)
    - [(b) Describe the RAID acquisition methods.](#p5-q6b)
  - [Question 7](#p5--question-7)
    - [(a) Explain the acquisition procedures for cell phones and mobile devices.](#p5-q7a)
    - [(b) Explain some mobile forensics tools in brief.](#p5-q7b)
    - [(c) Describe tasks in investigation of e-mail crime and violations.](#p5-q7c)
    - [(d) Analyze the function of e-mail forensics tools.](#p5-q7d)
- [Paper 6 — Winter 2022 (11th batch)](#paper-6--winter-2022-11th-batch)
  - [Question 1](#p6--question-1)
    - [(a) What is digital evidence? Assess general tasks investigators perform with digital evidence.](#p6-q1a)
    - [(b) State guidelines for processing an incident or crime scene.](#p6-q1b)
    - [(c) What do you mean by remote acquisition? Explain with ProDiscover or EnCase Enterprise.](#p6-q1c)
  - [Question 2](#p6--question-2)
    - [(a) Explain how to find criminal activities on an NTFS disk.](#p6-q2a)
    - [(b) What are EFS and BitLocker? Explain whole disk encryption.](#p6-q2b)
    - [(c) Explain the roles of Windows Registry for computer forensics investigations.](#p6-q2c)
  - [Question 3](#p6--question-3)
    - [(a) Describe the activities performed by computer forensics tools.](#p6-q3a)
    - [(b) Define bit stream copy and bit stream image.](#p6-q3b)
  - [Question 4](#p6--question-4)
    - [(a) Explain how to locate and recover graphics files on the suspect's drive.](#p6-q4a)
    - [(b) Explain identifying graphics file fragments and reconstruction of file fragments.](#p6-q4b)
    - [(c) What is metafile graphics? Explain graphics file formats.](#p6-q4c)
  - [Question 5](#p6--question-5)
    - [(a) Define digital forensics and investigations.](#p6-q5a)
    - [(b) What do you mean by validating forensics data? Explain validating with hex editors and computer forensics programs.](#p6-q5b)
    - [(c) Explain common data hiding techniques in brief.](#p6-q5c)
  - [Question 6](#p6--question-6)
    - [(a) Explain standard procedures for performing a live acquisition.](#p6-q6a)
    - [(b) Describe standard procedures for network forensics.](#p6-q6b)
  - [Question 7](#p6--question-7)
    - [(a) Explain the acquisition procedures for cell phones/mobile devices and state some mobile forensics tools.](#p6-q7a)
    - [(b) Describe tasks in investigation of e-mail crime and violations and analyze the function of e-mail forensics tools.](#p6-q7b)

---
## Paper 1 — Winter 2025 (17th batch), Full Marks 60

### P1 – Question 1

<a id="p1-q1a"></a>
**(a) Do computer forensics and data recovery refer to the same activities? Justify your answer.** — *4 marks*

No — computer forensics and data recovery are related but **not the same**.
- **Computer forensics** investigates data retrievable from a computer's hard disk or other storage media, specifically recovering data that users have hidden or deleted and using it as **evidence** (inculpatory or exculpatory) in a case.
- **Data recovery** involves recovering information lost by mistake, a power surge, or a server crash — the technician already knows what is being looked for.

The key difference is purpose: data recovery restores known-missing data for the owner's use; computer forensics uncovers unknown data and must preserve it under chain of custody as legally admissible evidence. So forensics *uses* data-recovery techniques but adds an evidentiary/legal dimension.

<a id="p1-q1b"></a>
**(b) List three common types of digital crime.** — *4 marks*

Corporate computer crimes can involve:
1. **E-mail harassment**
2. **Falsification of data**
3. **Embezzlement**

(Also valid: gender/age discrimination, sabotage, industrial espionage.)

<a id="p1-q1c"></a>
**(c) What are some ways to determine the resources needed for an investigation?** — *4 marks*

Determine the resources needed as part of the systematic approach to an investigation:
- **Assess the case**: situation, nature of the case, specifics, type of evidence, operating system, known disk format, and location of the evidence.
- From this assessment, **determine the case requirements**: type of evidence, computer forensics tools needed, and any special operating systems required.
- Only then obtain and copy the evidence disk drive and proceed to analyze/recover the evidence.

### P1 – Question 2

<a id="p1-q2a"></a>
**(a) What do you mean by remote acquisition? Explain the remote acquisition with ProDiscover Basic or EnCase Enterprise.** — *6 marks*

**Remote acquisition** = connecting to a suspect computer over a network to copy its data, instead of physically removing the drive. Drawbacks: LAN speed/routing-table conflicts, difficulty gaining access to secure subnets, heavy traffic causing delays/errors.

**With ProDiscover Investigator:** preview the drive remotely while in use, perform live acquisition, encrypt the connection, copy the suspect's RAM, use stealth mode. ProDiscover Incident Response adds: capture volatile system state, analyze running processes, locate unseen files/processes, remotely view/listen to IP ports, run hash comparisons, create a remote hash inventory. The **PDServer remote agent** is loaded on the suspect machine (Trusted CD / preinstalled / pushed remotely) and can run in stealth mode. Security features: Password Protection, Encryption, Secure Communication Protocol, Write Protected Trusted Binaries, Digital Signatures.

**With EnCase Enterprise:** remote acquisition of media/RAM data, IDS tool integration, imaging one or more systems, system preview, wide file-system format support, RAID support (hardware and software).

<a id="p1-q2b"></a>
**(b) Describe certification and training requirements for digital forensics labs.** — *3 marks*

The **American Society of Crime Laboratory Directors (ASCLD)** offers guidelines for managing a lab, acquiring official certification, and auditing lab functions/procedures.

Certifications/bodies: **IACIS** (CEECS, CFCE), **HTCN** (Certified Computer Crime Investigator – Basic/Advanced; Certified Computer Forensic Technician – Basic/Advanced), **EnCE** (EnCase Certified Examiner), **ACE** (AccessData Certified Examiner), plus HTCIA, SANS Institute, CTIN, NTI, Southeast Cybercrime Institute, FLETC, NW3C.

Staff must maintain training in hardware/software, OS and file types, deductive reasoning, technical training, and investigative skills, with work reviewed regularly by the lab manager.

<a id="p1-q2c"></a>
**(c) Explain the purpose of a virtual machine for computer forensics and investigation.** — *4 marks*

Investigators must: **detect** a VM installed on a host, **acquire an image** of a VM, and **use VMs to examine malware** safely (common software: VirtualBox, Virtual PC, Parallels, VMware). Check whether VMs are loaded on a host and check the Registry for install/uninstall clues, since a suspect may use a VM to hide activity.

### P1 – Question 3

<a id="p1-q3a"></a>
**(a) How do inodes keep track of a file's name and data?** — *4 marks*

In UNIX/Linux (Ext2fs/Ext3fs), **inodes** hold information about each file/directory and point to other inodes or data blocks; an internal link count of 0 marks a deleted inode.

The first inode has **13 pointers**: pointers 1–10 are **direct pointers** to data blocks, pointer 11 is an **indirect pointer**, pointer 12 a **double-indirect pointer**, pointer 13 a **triple-indirect pointer**.

The **superblock** stores disk geometry, available space, and the location of the first inode. **Inode blocks** follow the superblock and are assigned to every file allocation unit. **Data blocks** are where files/directories are actually stored, linked directly from the inodes. A **continuation inode** carries further file info (mode, type, link count, status flag).

<a id="p1-q3b"></a>
**(b) Discuss the importance of digital hash in forensic investigation.** — *4 marks*

Validating data integrity via hashing is essential for court-admissible evidence.
- **CRC (Cyclic Redundancy Check)** — detects if a file's contents changed; CRC-32 is the latest version but is **not** a forensic hashing algorithm.
- **MD5 (Message Digest 5)** — converts a file into a hexadecimal hash value; any bit/byte change alters the hash.
- **SHA-1** — newer algorithm developed by NIST.

**Three rules for forensic hashes:** (1) you can't predict a file/device's hash value; (2) no two hash values can be the same; (3) any change to the file/device changes the hash value.

**Importance:** hashing the original evidence and comparing it to the hash of the image proves the copy is unaltered; any later tampering changes the hash immediately, making hashing central to validating both acquisition and analysis before court.

<a id="p1-q3c"></a>
**(c) What are the five required functions for computer forensics tools? Briefly explain.** — *4 marks*

Five major categories of tasks performed by computer forensics tools:
1. **Acquisition** — copying the original drive (physical/logical copy, various formats, command-line/GUI/remote acquisition, verification).
2. **Validation and discrimination** — validation ensures data integrity; discrimination sorts/searches data (hashing with CRC-32/MD5/SHA, filtering by hash sets, file-header analysis).
3. **Extraction** — the recovery task, hardest to master (data viewing, keyword searching, decompressing, carving, decrypting, bookmarking).
4. **Reconstruction** — recreating a suspect drive (disk-to-disk, image-to-disk, partition-to-partition, image-to-partition copy).
5. **Reporting** — producing the examination report (log reports, report generator).

### P1 – Question 4

<a id="p1-q4a"></a>
**(a) How can 'Hiding Partitions' and 'Marking Bad Clusters' techniques be used to hide data?** — *4 marks*

**Hiding Partitions:** a suspect deletes references to a partition using a disk editor and re-creates the links later — the partition becomes invisible while its data still exists (tools: GDisk, PartitionMagic, System Commander, LILO). Investigators must account for all disk space; unaccounted-for space signals a hidden partition.

**Marking Bad Clusters:** common on FAT systems — sensitive data is placed on free space, then a disk editor marks that space as a "bad" cluster (e.g., typing **B** in Norton Disk Edit) so the OS won't write over it. Forensic tools can still read marked-bad clusters directly, revealing the hidden data.

<a id="p1-q4b"></a>
**(b) What is carving or salvaging? How does one repair a damaged file header?** — *3 marks*

**Carving/salvaging** = recovering all file fragments (typically from slack space and free/unallocated space) so forensic tools can help reassemble them.

**Repairing a damaged header:** each file type has a unique header (e.g., JPEG = FF D8 FF E0 00 10, often with a JFIF string). Steps: try opening the file; if unreadable, recover more file pieces if needed → compare the header to a good sample → manually insert the correct hexadecimal values → test the corrected file.

<a id="p1-q4c"></a>
**(c) Write down the steps for reconstructing file fragments.** — *4 marks*

1. Locate and export all clusters of the fragmented file.
2. Determine the starting and ending cluster numbers for each fragmented group of clusters.
3. Copy each fragmented group, in proper sequence, to a recovery file.
4. Rebuild the corrupted file's header so it opens correctly in the appropriate viewer/application.

### P1 – Question 5

<a id="p1-q5a"></a>
**(a) What do you mean by validating forensics data? Explain validating with hexadecimal editors.** — *5 marks*

Validating forensic data means ensuring data integrity for court presentation — critical since standard tools have hashing limitations.

**Hex editors:** e.g., **Hex Workshop** provides hashing algorithms (MD5, SHA-1) and can hash specific files or sectors within a file.
**Discriminating with hash values:** AccessData's **Known File Filter (KFF)** compares known file hash values (e.g., MSWord.exe) against files on the evidence drive/image to filter out known, irrelevant files; the KFF database is periodically updated.

<a id="p1-q5b"></a>
**(b) What is drive slack? Explain it according to the purposes of digital forensics.** — *3 marks*

Microsoft OSs allocate disk space in **clusters**, producing **drive slack** — unused space in a cluster between the end of an active file and the end of the cluster. Drive slack = **RAM slack + file slack** (NTFS produces much less file slack than FAT).

Forensically, this unused space can still hold remnants of previously deleted/overwritten files (or old memory contents), so investigators examine it for hidden evidence the OS no longer shows.

<a id="p1-q5c"></a>
**(c) Explain different types of digital evidence storage formats.** — *4 marks*

1. **Raw format** — bit-stream data written directly to a file. *Pros:* fast transfers, ignores minor read errors, readable by most tools. *Cons:* needs as much storage as the original, may miss bad sectors.
2. **Proprietary formats** — vendor-specific. *Pros:* optional compression, image can be split into segments, metadata can be embedded. *Cons:* can't be shared across different tools, segment file-size limits.
3. **Advanced Forensics Format (AFF)** — open-source (Dr. Simson L. Garfinkel, Basis Technology). Compressed or uncompressed images, no size restriction, space for metadata, simple/extensible design, multi-platform. File extensions: **.afd** (segmented image) and **.afm** (AFF metadata).

### P1 – Question 6

<a id="p1-q6a"></a>
**(a) What is the necessity of live acquisition? Explain standard procedure for live acquisition.** — *4 marks*

**Necessity:** live acquisitions are vital for active network intrusions/attacks, and are increasingly performed *before* taking a system offline, since attack evidence may exist only in running processes/RAM (governed by **Order of Volatility** — how long data lasts on a system). Live acquisitions don't follow typical static forensic procedures.

**Standard procedure:**
1. Create/download a bootable forensic CD (e.g., Helix, DEFT).
2. Log all actions taken.
3. Send collected information to a network drive if possible.
4. Copy the physical memory (RAM) first.
5. Continue with incident-specific next steps.
6. Obtain a forensic hash of all recovered files.

Tools: Mantech Memory DD, Win32dd, winen.exe, BackTrack 4.

<a id="p1-q6b"></a>
**(b) Explain internet abuse and e-mail abuse investigation.** — *4 marks*

**Internet abuse investigation** needs: the organization's proxy server logs, the suspect's IP address, the suspect's disk drive, and a forensic analysis tool. Steps: use standard forensic techniques → extract all URL information → request the proxy server log from the firewall administrator → compare recovered data with the log → continue analyzing the disk drive.

**E-mail abuse investigation** needs: an electronic copy of the offending e-mail (with header data), e-mail server logs (if available), access to the central mail server (if used), access to the suspect's computer, and a forensic tool. Steps: use standard forensic techniques → obtain the suspect's/victim's e-mail data → for Web-based mail use tools like FTK's Internet Keyword Search → examine header data of all relevant messages.

<a id="p1-q6c"></a>
**(c) Explain bit stream copy and bit stream image with examples.** — *4 marks*

- **Bit-stream disk-to-image file** — most common method; multiple bit-for-bit copies can be made into an image file (tools: ProDiscover, EnCase, FTK, SMART, Sleuth Kit, X-Ways, iLook).
- **Bit-stream disk-to-disk** — used when imaging isn't possible; requires matching the target disk's geometry (tools: EnCase, SafeBack, SnapCopy).

Both are exact sector-by-sector duplicates (not simple file copies); they differ only in destination — an image file vs. a physical disk.

### P1 – Question 7

<a id="p1-q7a"></a>
**(a) Explain the acquisition procedures for cell phones and mobile devices.** — *5 marks*

Main concerns: **loss of power** and **PC synchronization** (mobile devices have volatile memory). Disconnect the device from any cable/cradle immediately. Isolate it from incoming signals using a paint can, the Paraben Wireless StrongHold Bag, or eight layers of antistatic bags (trade-off: this triggers roaming mode, draining the battery faster).

In the lab, check: internal memory, SIM card, removable/external memory cards, and system server (needs a warrant/subpoena). Acquisition = synchronizing with the device like a PC (to download data) + reading the SIM card (service data, call data, messages, location info) — noting that PINs/access codes may be needed if power was lost.

<a id="p1-q7b"></a>
**(b) Describe tasks in investigation of e-mail crime and violations.** — *4 marks*

Goals: find who is behind the crime, collect evidence, present findings, build a case (consult an attorney, since handling varies by jurisdiction, e.g., for spam). Crimes involving e-mail: narcotics trafficking, extortion, sexual harassment, child abduction/pornography.

Tasks: access the victim's computer/e-mail client to find and copy evidence, access protected/encrypted material, print e-mails, guide the victim by phone to open/copy e-mail (including headers), and recover deleted e-mails (servers can often recover them, similar to deleted-file recovery).

<a id="p1-q7c"></a>
**(c) Analyze the function of e-mail forensics tools.** — *3 marks*

Specialized tools (FTK, ProDiscover Basic, FINALeMAIL, Sawmill-GroupWise, DBXtract, Aid4Mail/MailBag Assistant, Paraben E-Mail Examiner, Ontrack EmailRepair, R-Tools R-Mail) let investigators find e-mail database files, personal e-mail files, offline storage files, and log files — without needing deep knowledge of the underlying server/client architecture. E.g., **FINALeMAIL** scans e-mail databases, recovers deleted e-mails, and finds associated files; **FTK** indexes an entire disk/image (via dtSearch) for fast retrieval of Outlook/Outlook Express e-mail.

---

## Paper 2 — Summer 2024 (16th batch)

### P2 – Question 1

<a id="p2-q1a"></a>
**(a) What do you mean by remote acquisition? Explain the remote acquisition with ProDiscover Basic or EnCase Enterprise.** — *5 marks*

**Remote acquisition** = connecting to a suspect computer over a network to copy its data, instead of physically removing the drive. Drawbacks: LAN speed/routing-table conflicts, difficulty gaining access to secure subnets, heavy traffic causing delays/errors.

**With ProDiscover Investigator:** preview the drive remotely while in use, perform live acquisition, encrypt the connection, copy the suspect's RAM, use stealth mode. ProDiscover Incident Response adds: capture volatile system state, analyze running processes, locate unseen files/processes, remotely view/listen to IP ports, run hash comparisons, create a remote hash inventory. The **PDServer remote agent** is loaded on the suspect machine (Trusted CD / preinstalled / pushed remotely) and can run in stealth mode. Security features: Password Protection, Encryption, Secure Communication Protocol, Write Protected Trusted Binaries, Digital Signatures.

**With EnCase Enterprise:** remote acquisition of media/RAM data, IDS tool integration, imaging one or more systems, system preview, wide file-system format support, RAID support (hardware and software).

<a id="p2-q1b"></a>
**(b) What is carving or salvaging? How does one repair a damaged file header?** — *4 marks*

**Carving/salvaging** = recovering all file fragments (typically from slack space and free/unallocated space) so forensic tools can help reassemble them.

**Repairing a damaged header:** each file type has a unique header (e.g., JPEG = FF D8 FF E0 00 10, often with a JFIF string). Steps: try opening the file; if unreadable, recover more file pieces if needed → compare the header to a good sample → manually insert the correct hexadecimal values → test the corrected file.

<a id="p2-q1c"></a>
**(c) State the procedure of reconstructing a File Fragment.** — *3 marks*

1. Locate and export all clusters of the fragmented file.
2. Determine the starting and ending cluster numbers for each fragmented group of clusters.
3. Copy each fragmented group, in proper sequence, to a recovery file.
4. Rebuild the corrupted file's header so it opens correctly in the appropriate viewer/application.

### P2 – Question 2

<a id="p2-q2a"></a>
**(a) Explain and state hardware and software forensics tools.** — *4 marks*

- **Hardware forensic tools** — range from single-purpose components to complete computer systems/servers.
- **Software forensic tools** — command-line applications and GUI applications, commonly used to copy data from a suspect's disk to an image file.

Both types perform the five task categories: acquisition, validation and discrimination, extraction, reconstruction, and reporting.

<a id="p2-q2b"></a>
**(b) Describe tasks performed by computer forensics tools.** — *5 marks*

Five major categories of tasks performed by computer forensics tools:
1. **Acquisition** — copying the original drive (physical/logical copy, various formats, command-line/GUI/remote acquisition, verification).
2. **Validation and discrimination** — validation ensures data integrity; discrimination sorts/searches data (hashing with CRC-32/MD5/SHA, filtering by hash sets, file-header analysis).
3. **Extraction** — the recovery task, hardest to master (data viewing, keyword searching, decompressing, carving, decrypting, bookmarking).
4. **Reconstruction** — recreating a suspect drive (disk-to-disk, image-to-disk, partition-to-partition, image-to-partition copy).
5. **Reporting** — producing the examination report (log reports, report generator).

<a id="p2-q2c"></a>
**(c) Explain the Resilient file system in brief.** — *3 marks*

**Insufficient Information** — the lecture sheet covers FAT, NTFS, EFS/BitLocker, HFS, and Ext2fs/Ext3fs in detail, but contains **no section on the Resilient File System (ReFS)** anywhere in its 16 chapters. No definition, features, or NTFS-comparison is available to answer this from the lecture sheet alone.

### P2 – Question 3

<a id="p2-q3a"></a>
**(a) Explain the key certification requirements and guidelines set by ASCLD for a computer-forensics lab.** — *5 marks*

The **American Society of Crime Laboratory Directors (ASCLD)** offers guidelines for managing a lab, acquiring official certification, and auditing lab functions/procedures.

Certifications/bodies: **IACIS** (CEECS, CFCE), **HTCN** (Certified Computer Crime Investigator – Basic/Advanced; Certified Computer Forensic Technician – Basic/Advanced), **EnCE** (EnCase Certified Examiner), **ACE** (AccessData Certified Examiner), plus HTCIA, SANS Institute, CTIN, NTI, Southeast Cybercrime Institute, FLETC, NW3C.

Staff must maintain training in hardware/software, OS and file types, deductive reasoning, technical training, and investigative skills, with work reviewed regularly by the lab manager.

<a id="p2-q3b"></a>
**(b) Compare and contrast the three digital-evidence storage formats — raw, proprietary, and AFF — including advantages/disadvantages.** — *4 marks*

1. **Raw format** — bit-stream data written directly to a file. *Pros:* fast transfers, ignores minor read errors, readable by most tools. *Cons:* needs as much storage as the original, may miss bad sectors.
2. **Proprietary formats** — vendor-specific. *Pros:* optional compression, image can be split into segments, metadata can be embedded. *Cons:* can't be shared across different tools, segment file-size limits.
3. **Advanced Forensics Format (AFF)** — open-source (Dr. Simson L. Garfinkel, Basis Technology). Compressed or uncompressed images, no size restriction, space for metadata, simple/extensible design, multi-platform. File extensions: **.afd** (segmented image) and **.afm** (AFF metadata).

<a id="p2-q3c"></a>
**(c) Describe the challenges and methods for acquiring data from RAID systems.** — *3 marks*

**Concerns:** how much storage is needed, what RAID type is used, whether the tool can read a forensically copied RAID image or split RAID-disk data, and challenges from older hardware-firmware RAID systems (size is the biggest concern — RAID systems often hold terabytes).

**Vendors/methods:** Technologies Pathways ProDiscover, Guidance Software EnCase, X-Ways Forensics, Runtime Software, R-Tools Technologies. When a RAID is too large for static acquisition, use the **sparse or logical acquisition method** to retrieve only relevant data.

### P2 – Question 4

<a id="p2-q4a"></a>
**(a) Explain common data hiding techniques in brief.** — *4 marks*

1. **File manipulation** — hiding via filenames/extensions or the hidden-file property.
2. **Disk manipulation** — hidden partitions (deleted partition references, re-linked later) and bad clusters (marking free space holding hidden data as "bad," common on FAT).
3. **Encryption** — bit shifting (altering byte values so files resemble binary executable code, via tools like Hex Workshop) and steganography (hiding small amounts of data inside image/text files; tools: S-Tools, DPEnvelope, jpgx, tte).

<a id="p2-q4b"></a>
**(b) What is write blocker? Explain software-write blocker and hardware-write blocker in brief.** — *4 marks*

A **write blocker** prevents any data being written to the evidence drive during acquisition.
- **Hardware write-blocker** — a physical device connected between the evidence disk and the workstation (e.g., "connect evidence disk to write-blocker → connect target disk to write-blocker → start FTK Imager → create disk image").
- **Software write-blocker** — a utility/registry-based method, e.g., the Windows XP USB write-protection feature (backup Registry → modify it to enable write-protection → toggle via desktop icons); forensic Linux boot CDs similarly mount drives read-only, eliminating the need for a hardware write-blocker.

<a id="p2-q4c"></a>
**(c) Explain the contingency planning for image acquisition.** — *4 marks*

- Create a duplicate copy of the evidence image file.
- Make **at least two images**, using **different tools or techniques** for each.
- Copy the **host protected area** of the drive too (consider a BIOS-level hardware acquisition tool).
- Be prepared for **encrypted drives**, such as Windows Vista Ultimate/Enterprise's whole-disk encryption.

### P2 – Question 5

<a id="p2-q5a"></a>
**(a) An employee suspects his password has been compromised (changed 2 days ago, still used). What might be going on?** — *4 marks*

**Insufficient Information** — the lecture sheet has no scenario-specific coverage of password reuse/compromise. Using the closest related content (password-recovery techniques: dictionary attack, brute-force attack, profile-based password guessing, via tools like AccessData PRTK or John the Ripper), a lecture-grounded partial explanation is: the new password may be similarly weak/predictable and vulnerable to the same cracking techniques that compromised the original password.

<a id="p2-q5b"></a>
**(b) What is drive slack? Explain it according to the purposes of digital forensics.** — *4 marks*

Microsoft OSs allocate disk space in **clusters**, producing **drive slack** — unused space in a cluster between the end of an active file and the end of the cluster. Drive slack = **RAM slack + file slack** (NTFS produces much less file slack than FAT).

Forensically, this unused space can still hold remnants of previously deleted/overwritten files (or old memory contents), so investigators examine it for hidden evidence the OS no longer shows.

<a id="p2-q5c"></a>
**(c) Explain different types of digital evidence storage formats.** — *4 marks*

1. **Raw format** — bit-stream data written directly to a file. *Pros:* fast transfers, ignores minor read errors, readable by most tools. *Cons:* needs as much storage as the original, may miss bad sectors.
2. **Proprietary formats** — vendor-specific. *Pros:* optional compression, image can be split into segments, metadata can be embedded. *Cons:* can't be shared across different tools, segment file-size limits.
3. **Advanced Forensics Format (AFF)** — open-source (Dr. Simson L. Garfinkel, Basis Technology). Compressed or uncompressed images, no size restriction, space for metadata, simple/extensible design, multi-platform. File extensions: **.afd** (segmented image) and **.afm** (AFF metadata).

### P2 – Question 6

<a id="p2-q6a"></a>
**(a) Define 'order of volatility' and explain how it guides your actions during a live acquisition.** — *5 marks*

**Order of volatility (OOV)** = how long a piece of information lasts on a system. Because RAM/running-process data is the most volatile (lost immediately at power-down), live-acquisition procedure prioritizes capturing it first — copy physical memory (RAM) early, before proceeding to incident-specific next steps, since delay risks permanently losing that evidence.

<a id="p2-q6b"></a>
**(b) List and explain three common e-mail fraud techniques.** — *3 marks*

1. **Phishing** — HTML-format e-mails used to create deceptive links to fake Web pages.
2. **Spoofing** — falsifying the sender/source of an e-mail to commit fraud.
3. **The "419" / Nigerian Scam** — a noteworthy advance-fee fraud scheme.

<a id="p2-q6c"></a>
**(c) Outline the standard procedure for a live RAM acquisition on a compromised system.** — *4 marks*

1. Create/download a bootable forensic CD (Helix, DEFT).
2. Log all actions taken.
3. Send collected data to a network drive if possible.
4. **Copy the physical memory (RAM).**
5. Continue with incident-specific next steps.
6. Obtain a forensic hash of all recovered files.

Tools: Mantech Memory DD, Win32dd, winen.exe, BackTrack 4.

### P2 – Question 7

<a id="p2-q7a"></a>
**(a) What is the necessity of live acquisition? Explain standard procedure for live acquisition.** — *4 marks*

**Necessity:** live acquisitions are vital for active network intrusions/attacks, and are increasingly performed *before* taking a system offline, since attack evidence may exist only in running processes/RAM (governed by **Order of Volatility** — how long data lasts on a system). Live acquisitions don't follow typical static forensic procedures.

**Standard procedure:**
1. Create/download a bootable forensic CD (e.g., Helix, DEFT).
2. Log all actions taken.
3. Send collected information to a network drive if possible.
4. Copy the physical memory (RAM) first.
5. Continue with incident-specific next steps.
6. Obtain a forensic hash of all recovered files.

Tools: Mantech Memory DD, Win32dd, winen.exe, BackTrack 4.

<a id="p2-q7b"></a>
**(b) What is validation protocol? Explain digital forensics examination protocol.** — *4 marks*

Always verify results using **at least two tools** — one for retrieval/examination, one for verification — and understand how each tool works; cross-check with a disk editor (Hex Workshop, WinHex).

**Computer Forensics Examination Protocol:**
1. Perform the investigation with a GUI tool.
2. Verify results with a disk editor.
3. Compare the hash values from both tools.

<a id="p2-q7c"></a>
**(c) Describe certification and training requirements for digital forensics labs.** — *4 marks*

The **American Society of Crime Laboratory Directors (ASCLD)** offers guidelines for managing a lab, acquiring official certification, and auditing lab functions/procedures.

Certifications/bodies: **IACIS** (CEECS, CFCE), **HTCN** (Certified Computer Crime Investigator – Basic/Advanced; Certified Computer Forensic Technician – Basic/Advanced), **EnCE** (EnCase Certified Examiner), **ACE** (AccessData Certified Examiner), plus HTCIA, SANS Institute, CTIN, NTI, Southeast Cybercrime Institute, FLETC, NW3C.

Staff must maintain training in hardware/software, OS and file types, deductive reasoning, technical training, and investigative skills, with work reviewed regularly by the lab manager.

---

## Paper 3 — Winter 2023 (15th batch)

### P3 – Question 1

<a id="p3-q1a"></a>
**(a) Define computer forensics and explain bit stream copy & bit stream image.** — *3 marks*

- **Bit-stream disk-to-image file** — most common method; multiple bit-for-bit copies can be made into an image file (tools: ProDiscover, EnCase, FTK, SMART, Sleuth Kit, X-Ways, iLook).
- **Bit-stream disk-to-disk** — used when imaging isn't possible; requires matching the target disk's geometry (tools: EnCase, SafeBack, SnapCopy).

Both are exact sector-by-sector duplicates (not simple file copies); they differ only in destination — an image file vs. a physical disk.

<a id="p3-q1b"></a>
**(b) What is computer crime? Why do you need Mini-WinFE Boot CD/DVD or USB drive?** — *4 marks*

**Computer crime** — computers can contain information showing the chain of events leading to a crime and evidence for conviction; law enforcement must follow proper procedure, since digital evidence can be easily altered by an overeager investigator.

**Insufficient Information (Mini-WinFE)** — the lecture sheet does not mention Mini-WinFE Boot CD/DVD/USB anywhere in its 16 chapters (it covers Helix, DEFT, Knoppix-STD, and other Linux Live CDs instead).

<a id="p3-q1c"></a>
**(c) Explain the ways to determine the best acquisition method.** — *5 marks*

Types: **static acquisitions** and **live acquisitions**. Four methods:
1. Bit-stream disk-to-image file (most common; multiple bit-for-bit copies).
2. Bit-stream disk-to-disk (when imaging isn't possible; consider disk geometry).
3. Logical disk-to-disk or disk-to-disk data (limited time; specific files only).
4. Sparse data copy of a file/folder (also collects unallocated/deleted fragments; useful for large disks, PST/OST files, RAID servers).

Considerations: source-disk size (compression, digital signatures), tape backup for very large drives, and whether the disk can be retained.

### P3 – Question 2

<a id="p3-q2a"></a>
**(a) What do you mean by remote acquisition? Explain the remote acquisition with ProDiscover Basic or EnCase Enterprise.** — *4 marks*

**Remote acquisition** = connecting to a suspect computer over a network to copy its data, instead of physically removing the drive. Drawbacks: LAN speed/routing-table conflicts, difficulty gaining access to secure subnets, heavy traffic causing delays/errors.

**With ProDiscover Investigator:** preview the drive remotely while in use, perform live acquisition, encrypt the connection, copy the suspect's RAM, use stealth mode. ProDiscover Incident Response adds: capture volatile system state, analyze running processes, locate unseen files/processes, remotely view/listen to IP ports, run hash comparisons, create a remote hash inventory. The **PDServer remote agent** is loaded on the suspect machine (Trusted CD / preinstalled / pushed remotely) and can run in stealth mode. Security features: Password Protection, Encryption, Secure Communication Protocol, Write Protected Trusted Binaries, Digital Signatures.

**With EnCase Enterprise:** remote acquisition of media/RAM data, IDS tool integration, imaging one or more systems, system preview, wide file-system format support, RAID support (hardware and software).

<a id="p3-q2b"></a>
**(b) What is carving or salvaging? How does repair damaged file header?** — *4 marks*

**Carving/salvaging** = recovering all file fragments (typically from slack space and free/unallocated space) so forensic tools can help reassemble them.

**Repairing a damaged header:** each file type has a unique header (e.g., JPEG = FF D8 FF E0 00 10, often with a JFIF string). Steps: try opening the file; if unreadable, recover more file pieces if needed → compare the header to a good sample → manually insert the correct hexadecimal values → test the corrected file.

<a id="p3-q2c"></a>
**(c) Explain the purpose of a virtual machine for computer forensics and investigation.** — *3 marks*

Investigators must: **detect** a VM installed on a host, **acquire an image** of a VM, and **use VMs to examine malware** safely (common software: VirtualBox, Virtual PC, Parallels, VMware). Check whether VMs are loaded on a host and check the Registry for install/uninstall clues, since a suspect may use a VM to hide activity.

### P3 – Question 3

<a id="p3-q3a"></a>
**(a) Explain the roles of Windows Registry for computer forensics and investigation.** — *4 marks*

The **Registry** is a database storing hardware/software configuration, network connections, user preferences, and setup information — it can hold valuable evidence. View via Regedit (Win 9x) or Regedt32 (Win 2000/XP); ProDiscover Basic can extract System.dat/User.dat from an image.

Per the summary: the Registry **keeps a record of attached hardware, user preferences, network connections, and installed software** — directly useful for reconstructing device/software/network history on a suspect machine, and for detecting VM install/uninstall activity.

<a id="p3-q3b"></a>
**(b) Describe tasks perform by computer forensics tools.** — *5 marks*

Five major categories of tasks performed by computer forensics tools:
1. **Acquisition** — copying the original drive (physical/logical copy, various formats, command-line/GUI/remote acquisition, verification).
2. **Validation and discrimination** — validation ensures data integrity; discrimination sorts/searches data (hashing with CRC-32/MD5/SHA, filtering by hash sets, file-header analysis).
3. **Extraction** — the recovery task, hardest to master (data viewing, keyword searching, decompressing, carving, decrypting, bookmarking).
4. **Reconstruction** — recreating a suspect drive (disk-to-disk, image-to-disk, partition-to-partition, image-to-partition copy).
5. **Reporting** — producing the examination report (log reports, report generator).

<a id="p3-q3c"></a>
**(c) Explain Resilient file system in brief.** — *3 marks*

**Insufficient Information** — the lecture sheet covers FAT, NTFS, EFS/BitLocker, HFS, and Ext2fs/Ext3fs in detail, but contains **no section on the Resilient File System (ReFS)** anywhere in its 16 chapters. No definition, features, or NTFS-comparison is available to answer this from the lecture sheet alone.

### P3 – Question 4

<a id="p3-q4a"></a>
**(a) Explain common data hiding techniques in brief.** — *4 marks*

1. **File manipulation** — hiding via filenames/extensions or the hidden-file property.
2. **Disk manipulation** — hidden partitions (deleted partition references, re-linked later) and bad clusters (marking free space holding hidden data as "bad," common on FAT).
3. **Encryption** — bit shifting (altering byte values so files resemble binary executable code, via tools like Hex Workshop) and steganography (hiding small amounts of data inside image/text files; tools: S-Tools, DPEnvelope, jpgx, tte).

<a id="p3-q4b"></a>
**(b) What is write blocker? Explain software-write blocker and hardware-write blocker in brief.** — *4 marks*

A **write blocker** prevents any data being written to the evidence drive during acquisition.
- **Hardware write-blocker** — a physical device connected between the evidence disk and the workstation (e.g., "connect evidence disk to write-blocker → connect target disk to write-blocker → start FTK Imager → create disk image").
- **Software write-blocker** — a utility/registry-based method, e.g., the Windows XP USB write-protection feature (backup Registry → modify it to enable write-protection → toggle via desktop icons); forensic Linux boot CDs similarly mount drives read-only, eliminating the need for a hardware write-blocker.

<a id="p3-q4c"></a>
**(c) Write down the steps for reconstructing file fragments.** — *4 marks*

1. Locate and export all clusters of the fragmented file.
2. Determine the starting and ending cluster numbers for each fragmented group of clusters.
3. Copy each fragmented group, in proper sequence, to a recovery file.
4. Rebuild the corrupted file's header so it opens correctly in the appropriate viewer/application.

### P3 – Question 5

<a id="p3-q5a"></a>
**(a) An employee suspects his password has been compromised (changed 2 days ago, still used). What might be going on?** — *4 marks*

**Insufficient Information** — the lecture sheet has no scenario-specific coverage of password reuse/compromise. Using the closest related content (password-recovery techniques: dictionary attack, brute-force attack, profile-based password guessing, via tools like AccessData PRTK or John the Ripper), a lecture-grounded partial explanation is: the new password may be similarly weak/predictable and vulnerable to the same cracking techniques that compromised the original password.

<a id="p3-q5b"></a>
**(b) What is drive slack? Explain it according to the purposes of digital forensics.** — *4 marks*

Microsoft OSs allocate disk space in **clusters**, producing **drive slack** — unused space in a cluster between the end of an active file and the end of the cluster. Drive slack = **RAM slack + file slack** (NTFS produces much less file slack than FAT).

Forensically, this unused space can still hold remnants of previously deleted/overwritten files (or old memory contents), so investigators examine it for hidden evidence the OS no longer shows.

<a id="p3-q5c"></a>
**(c) Explain different types of digital evidence storage formats.** — *4 marks*

1. **Raw format** — bit-stream data written directly to a file. *Pros:* fast transfers, ignores minor read errors, readable by most tools. *Cons:* needs as much storage as the original, may miss bad sectors.
2. **Proprietary formats** — vendor-specific. *Pros:* optional compression, image can be split into segments, metadata can be embedded. *Cons:* can't be shared across different tools, segment file-size limits.
3. **Advanced Forensics Format (AFF)** — open-source (Dr. Simson L. Garfinkel, Basis Technology). Compressed or uncompressed images, no size restriction, space for metadata, simple/extensible design, multi-platform. File extensions: **.afd** (segmented image) and **.afm** (AFF metadata).

### P3 – Question 6

<a id="p3-q6a"></a>
**(a) What is the necessity of live acquisition? Explain standard procedure for live acquisition.** — *4 marks*

**Necessity:** live acquisitions are vital for active network intrusions/attacks, and are increasingly performed *before* taking a system offline, since attack evidence may exist only in running processes/RAM (governed by **Order of Volatility** — how long data lasts on a system). Live acquisitions don't follow typical static forensic procedures.

**Standard procedure:**
1. Create/download a bootable forensic CD (e.g., Helix, DEFT).
2. Log all actions taken.
3. Send collected information to a network drive if possible.
4. Copy the physical memory (RAM) first.
5. Continue with incident-specific next steps.
6. Obtain a forensic hash of all recovered files.

Tools: Mantech Memory DD, Win32dd, winen.exe, BackTrack 4.

<a id="p3-q6b"></a>
**(b) What is validation protocol? Explain digital forensics examination protocol.** — *4 marks*

Always verify results using **at least two tools** — one for retrieval/examination, one for verification — and understand how each tool works; cross-check with a disk editor (Hex Workshop, WinHex).

**Computer Forensics Examination Protocol:**
1. Perform the investigation with a GUI tool.
2. Verify results with a disk editor.
3. Compare the hash values from both tools.

<a id="p3-q6c"></a>
**(c) Describe certification and training requirements for digital forensics labs.** — *4 marks*

The **American Society of Crime Laboratory Directors (ASCLD)** offers guidelines for managing a lab, acquiring official certification, and auditing lab functions/procedures.

Certifications/bodies: **IACIS** (CEECS, CFCE), **HTCN** (Certified Computer Crime Investigator – Basic/Advanced; Certified Computer Forensic Technician – Basic/Advanced), **EnCE** (EnCase Certified Examiner), **ACE** (AccessData Certified Examiner), plus HTCIA, SANS Institute, CTIN, NTI, Southeast Cybercrime Institute, FLETC, NW3C.

Staff must maintain training in hardware/software, OS and file types, deductive reasoning, technical training, and investigative skills, with work reviewed regularly by the lab manager.

### P3 – Question 7

<a id="p3-q7a"></a>
**(a) What procedural steps should a digital forensic investigator follow when analyzing emails?** — *4 marks*

1. **Access/preserve evidence** — access the victim's computer (or guide them by phone) to recover the e-mail, headers included.
2. **Copy and print the e-mail** before starting the investigation (may also forward as an attachment; drag-to-storage-medium in most GUI clients).
3. **View/extract the e-mail header** — method varies by client (Outlook: Message Options → copy headers; Outlook Express: Properties → Message Source; Novell Evolution: View → All Message Headers; Hotmail: Options → Mail Display Settings → Advanced; Yahoo: Mail Options → Show All headers) — then paste into a text editor.
4. **Examine the header** for: return path, recipient's address, sending service type, sending server IP, e-mail server name, unique message number, date/time sent, attachment info.
5. **Examine additional e-mail files** (Outlook .pst/.ost, address books, saved Web pages for Web-mail).
6. **Check server logs** if available (UNIX: sendmail.cf, syslog.conf, /var/log/maillog; Exchange: .edb/.stm files, transaction logs, tracking.log).

<a id="p3-q7b"></a>
**(b) What are the critical factors to consider when conducting an email investigation?** — *4 marks*

- Return path, recipient's address, and sending server IP — to trace the message's true origin.
- Sending service type and e-mail server name — client/server architecture affects traceability.
- Unique message number and date/time sent — for building a timeline.
- Attachment file information — attachments may themselves hold evidence.
- Legal/jurisdictional factors — consult an attorney, since handling (e.g., of spam) varies by location.
- Whether messages were deleted — servers can often still recover them.

<a id="p3-q7c"></a>
**(c) How can forensic investigators handle the obstacles from encrypted emails and signed messages?** — *4 marks*

**Insufficient Information** — the lecture sheet does not cover encrypted e-mail or digital signatures specifically. The closest related content is general encrypted-file recovery: **key escrow** (recovers data if a passphrase is forgotten/key corrupted), **cracking the password** (expert techniques/powerful computers), or **persuading the suspect to reveal the password** — using dictionary attacks, brute-force attacks, or profile-based guessing (tools: AccessData PRTK, John the Ripper). This can be applied by extension to e-mail, but the lecture sheet gives no e-mail-specific technique.

---

## Paper 4 — Winter 2023 (14th batch), Full Marks 50

### P4 – Question 1

<a id="p4-q1a"></a>
**(a) Define computer forensics, network forensics and data recovery.** — *3 marks*

- **Computer forensics** — obtaining and analyzing digital information as evidence in civil, criminal, or administrative cases; recovers data hidden/deleted from storage media, used as evidence (inculpatory or exculpatory).
- **Network forensics** — yields information about how a perpetrator/attacker gained access to a network.
- **Data recovery** — recovering information lost by mistake, power surge, or server crash; the target data is already known.

<a id="p4-q1b"></a>
**(b) What is digital evidence? Assess general tasks investigators perform with digital evidence.** — *3 marks*

**Digital evidence** = any information stored or transmitted in digital form; U.S. courts accept it as physical/tangible evidence (some require it printed for court).

General investigator tasks: identify digital information/artifacts as evidence → collect, preserve, and document evidence → analyze, identify, and organize evidence → rebuild evidence or repeat a situation to verify reproducible results. Collecting computers and processing a scene must be done systematically.

<a id="p4-q1c"></a>
**(c) Explain the ways to determine the best acquisition method.**

Types: **static acquisitions** and **live acquisitions**. Four methods:
1. Bit-stream disk-to-image file (most common; multiple bit-for-bit copies).
2. Bit-stream disk-to-disk (when imaging isn't possible; consider disk geometry).
3. Logical disk-to-disk or disk-to-disk data (limited time; specific files only).
4. Sparse data copy of a file/folder (also collects unallocated/deleted fragments; useful for large disks, PST/OST files, RAID servers).

Considerations: source-disk size (compression, digital signatures), tape backup for very large drives, and whether the disk can be retained.

### P4 – Question 2

<a id="p4-q2a"></a>
**(a) What do you mean by remote acquisition? Explain with ProDiscover Basic or EnCase Enterprise.** — *4 marks*

**Remote acquisition** = connecting to a suspect computer over a network to copy its data, instead of physically removing the drive. Drawbacks: LAN speed/routing-table conflicts, difficulty gaining access to secure subnets, heavy traffic causing delays/errors.

**With ProDiscover Investigator:** preview the drive remotely while in use, perform live acquisition, encrypt the connection, copy the suspect's RAM, use stealth mode. ProDiscover Incident Response adds: capture volatile system state, analyze running processes, locate unseen files/processes, remotely view/listen to IP ports, run hash comparisons, create a remote hash inventory. The **PDServer remote agent** is loaded on the suspect machine (Trusted CD / preinstalled / pushed remotely) and can run in stealth mode. Security features: Password Protection, Encryption, Secure Communication Protocol, Write Protected Trusted Binaries, Digital Signatures.

**With EnCase Enterprise:** remote acquisition of media/RAM data, IDS tool integration, imaging one or more systems, system preview, wide file-system format support, RAID support (hardware and software).

<a id="p4-q2b"></a>
**(b) What do you understand by EFS and BitLocker? Explain whole disk encryption.** — *4 marks*

- **EFS (Encrypting File System)** — introduced in Windows 2000; public/private-key encryption of files, folders, or volumes. A recovery certificate is issued to the local admin account (Vista Business+/XP Pro/2000); recoverable via Cipher, Copy, or Efsrecvr commands.
- **BitLocker** — Vista Enterprise/Ultimate only; requires a TPM chip (v1.2+), a TCG-compliant BIOS, two NTFS partitions, and BIOS set to boot the hard drive first.
- **Whole disk encryption** — protects against loss of laptops/handhelds. Features: preboot authentication, full/partial disk encryption with secure hibernation, advanced encryption algorithms, key management, TPM-based key generation/login authentication. Each sector (often including the boot sector) is encrypted separately; must be decrypted with a vendor tool before examination. Tools: PGP Whole Disk Encryption, Voltage SecureDisk, Utimaco SafeGuard Easy, Jetico BestCrypt, SoftWinter Sentry 2020; open-source: TrueCrypt, CrossCrypt, FreeOTFE.

<a id="p4-q2c"></a>
**(c) Explain the purpose of a virtual machine for computer forensics and investigation.** — *2 marks*

Investigators must: **detect** a VM installed on a host, **acquire an image** of a VM, and **use VMs to examine malware** safely (common software: VirtualBox, Virtual PC, Parallels, VMware). Check whether VMs are loaded on a host and check the Registry for install/uninstall clues, since a suspect may use a VM to hide activity.

### P4 – Question 3

<a id="p4-q3a"></a>
**(a) Explain bit stream copy and bit stream image with examples.** — *3 marks*

- **Bit-stream disk-to-image file** — most common method; multiple bit-for-bit copies can be made into an image file (tools: ProDiscover, EnCase, FTK, SMART, Sleuth Kit, X-Ways, iLook).
- **Bit-stream disk-to-disk** — used when imaging isn't possible; requires matching the target disk's geometry (tools: EnCase, SafeBack, SnapCopy).

Both are exact sector-by-sector duplicates (not simple file copies); they differ only in destination — an image file vs. a physical disk.

<a id="p4-q3b"></a>
**(b) Describe tasks perform by computer forensics tools.** — *4 marks*

Five major categories of tasks performed by computer forensics tools:
1. **Acquisition** — copying the original drive (physical/logical copy, various formats, command-line/GUI/remote acquisition, verification).
2. **Validation and discrimination** — validation ensures data integrity; discrimination sorts/searches data (hashing with CRC-32/MD5/SHA, filtering by hash sets, file-header analysis).
3. **Extraction** — the recovery task, hardest to master (data viewing, keyword searching, decompressing, carving, decrypting, bookmarking).
4. **Reconstruction** — recreating a suspect drive (disk-to-disk, image-to-disk, partition-to-partition, image-to-partition copy).
5. **Reporting** — producing the examination report (log reports, report generator).

<a id="p4-q3c"></a>
**(c) Explain the roles of Windows Registry for computer forensics and investigation.** — *3 marks*

The **Registry** is a database storing hardware/software configuration, network connections, user preferences, and setup information — it can hold valuable evidence. View via Regedit (Win 9x) or Regedt32 (Win 2000/XP); ProDiscover Basic can extract System.dat/User.dat from an image.

Per the summary: the Registry **keeps a record of attached hardware, user preferences, network connections, and installed software** — directly useful for reconstructing device/software/network history on a suspect machine, and for detecting VM install/uninstall activity.

### P4 – Question 4

<a id="p4-q4a"></a>
**(a) Explain common data hiding techniques in brief.** — *4 marks*

1. **File manipulation** — hiding via filenames/extensions or the hidden-file property.
2. **Disk manipulation** — hidden partitions (deleted partition references, re-linked later) and bad clusters (marking free space holding hidden data as "bad," common on FAT).
3. **Encryption** — bit shifting (altering byte values so files resemble binary executable code, via tools like Hex Workshop) and steganography (hiding small amounts of data inside image/text files; tools: S-Tools, DPEnvelope, jpgx, tte).

<a id="p4-q4b"></a>
**(b) What is carving or salvaging? How does repair damaged file header?** — *3 marks*

**Carving/salvaging** = recovering all file fragments (typically from slack space and free/unallocated space) so forensic tools can help reassemble them.

**Repairing a damaged header:** each file type has a unique header (e.g., JPEG = FF D8 FF E0 00 10, often with a JFIF string). Steps: try opening the file; if unreadable, recover more file pieces if needed → compare the header to a good sample → manually insert the correct hexadecimal values → test the corrected file.

<a id="p4-q4c"></a>
**(c) Write down the steps for reconstructing file fragments.** — *3 marks*

1. Locate and export all clusters of the fragmented file.
2. Determine the starting and ending cluster numbers for each fragmented group of clusters.
3. Copy each fragmented group, in proper sequence, to a recovery file.
4. Rebuild the corrupted file's header so it opens correctly in the appropriate viewer/application.

### P4 – Question 5

<a id="p4-q5a"></a>
**(a) What do you mean by validating forensics data? Explain validating with hexadecimal editors.** — *4 marks*

Validating forensic data means ensuring data integrity for court presentation — critical since standard tools have hashing limitations.

**Hex editors:** e.g., **Hex Workshop** provides hashing algorithms (MD5, SHA-1) and can hash specific files or sectors within a file.
**Discriminating with hash values:** AccessData's **Known File Filter (KFF)** compares known file hash values (e.g., MSWord.exe) against files on the evidence drive/image to filter out known, irrelevant files; the KFF database is periodically updated.

<a id="p4-q5b"></a>
**(b) What is drive slack? Explain it according to the purposes of digital forensics.** — *3 marks*

Microsoft OSs allocate disk space in **clusters**, producing **drive slack** — unused space in a cluster between the end of an active file and the end of the cluster. Drive slack = **RAM slack + file slack** (NTFS produces much less file slack than FAT).

Forensically, this unused space can still hold remnants of previously deleted/overwritten files (or old memory contents), so investigators examine it for hidden evidence the OS no longer shows.

<a id="p4-q5c"></a>
**(c) Explain different types of digital evidence storage formats.** — *3 marks*

1. **Raw format** — bit-stream data written directly to a file. *Pros:* fast transfers, ignores minor read errors, readable by most tools. *Cons:* needs as much storage as the original, may miss bad sectors.
2. **Proprietary formats** — vendor-specific. *Pros:* optional compression, image can be split into segments, metadata can be embedded. *Cons:* can't be shared across different tools, segment file-size limits.
3. **Advanced Forensics Format (AFF)** — open-source (Dr. Simson L. Garfinkel, Basis Technology). Compressed or uncompressed images, no size restriction, space for metadata, simple/extensible design, multi-platform. File extensions: **.afd** (segmented image) and **.afm** (AFF metadata).

### P4 – Question 6

<a id="p4-q6a"></a>
**(a) Explain the concept of hashing in digital forensics and its role in verifying integrity.** — *5 marks*

Hashing converts a file/disk/sector into a fixed hexadecimal **hash value** — critical for court-admissible evidence.
- **CRC-32** — detects content changes; not a forensic algorithm.
- **MD5** — hex hash value; any bit/byte change alters it.
- **SHA-1** — newer NIST algorithm.

**Three rules:** can't predict a hash value; no two hash values match; any change alters the hash.

**Role:** hash the original at acquisition, compare to the image's hash — a match proves the copy is unaltered; any later change is instantly detectable. This underlies validation/discrimination tool tasks (hashing + filtering, e.g., against NSRL/KFF) and the Examination Protocol (GUI tool → disk-editor verification → hash comparison).

<a id="p4-q6b"></a>
**(b) Describe the role of machine learning and AI in modern computer forensics tools.** — *5 marks*

**Insufficient Information** — the lecture sheet (based on the 4th-edition textbook covering ProDiscover, EnCase, FTK, Hex Workshop, and OS/file-system analysis) contains **no discussion of machine learning or artificial intelligence** anywhere in its 16 chapters. No ML/AI tool features, benefits, or challenges can be answered from this source.

### P4 – Question 7

<a id="p4-q7a"></a>
**(a) Describe the steps involved in conducting an email investigation. Outline key considerations at each stage.** — *6 marks*

1. **Access/preserve evidence** — access the victim's computer (or guide them by phone) to recover the e-mail, headers included.
2. **Copy and print the e-mail** before starting the investigation (may also forward as an attachment; drag-to-storage-medium in most GUI clients).
3. **View/extract the e-mail header** — method varies by client (Outlook: Message Options → copy headers; Outlook Express: Properties → Message Source; Novell Evolution: View → All Message Headers; Hotmail: Options → Mail Display Settings → Advanced; Yahoo: Mail Options → Show All headers) — then paste into a text editor.
4. **Examine the header** for: return path, recipient's address, sending service type, sending server IP, e-mail server name, unique message number, date/time sent, attachment info.
5. **Examine additional e-mail files** (Outlook .pst/.ost, address books, saved Web pages for Web-mail).
6. **Check server logs** if available (UNIX: sendmail.cf, syslog.conf, /var/log/maillog; Exchange: .edb/.stm files, transaction logs, tracking.log).

<a id="p4-q7b"></a>
**(b) Evaluate the role of email encryption and digital signatures in email investigations.** — *4 marks*

**Insufficient Information** — the lecture sheet does not cover encrypted e-mail or digital signatures specifically. The closest related content is general encrypted-file recovery: **key escrow** (recovers data if a passphrase is forgotten/key corrupted), **cracking the password** (expert techniques/powerful computers), or **persuading the suspect to reveal the password** — using dictionary attacks, brute-force attacks, or profile-based guessing (tools: AccessData PRTK, John the Ripper). This can be applied by extension to e-mail, but the lecture sheet gives no e-mail-specific technique.

---

## Paper 5 — Winter 2023 (13th batch), Full Marks 50

### P5 – Question 1

<a id="p5-q1a"></a>
**(a) Explain digital forensics and investigations in brief.** — *3 marks*

- **Computer forensics** — obtaining and analyzing digital information as evidence in civil, criminal, or administrative cases; recovers data hidden/deleted from storage media, used as evidence (inculpatory or exculpatory).
- **Network forensics** — yields information about how a perpetrator/attacker gained access to a network.
- **Data recovery** — recovering information lost by mistake, power surge, or server crash; the target data is already known.

<a id="p5-q1b"></a>
**(b) What is digital evidence? Assess general tasks investigators perform with digital evidence.** — *3 marks*

**Digital evidence** = any information stored or transmitted in digital form; U.S. courts accept it as physical/tangible evidence (some require it printed for court).

General investigator tasks: identify digital information/artifacts as evidence → collect, preserve, and document evidence → analyze, identify, and organize evidence → rebuild evidence or repeat a situation to verify reproducible results. Collecting computers and processing a scene must be done systematically.

<a id="p5-q1c"></a>
**(c) Explain the ways to determine the best acquisition method.** — *4 marks*

Types: **static acquisitions** and **live acquisitions**. Four methods:
1. Bit-stream disk-to-image file (most common; multiple bit-for-bit copies).
2. Bit-stream disk-to-disk (when imaging isn't possible; consider disk geometry).
3. Logical disk-to-disk or disk-to-disk data (limited time; specific files only).
4. Sparse data copy of a file/folder (also collects unallocated/deleted fragments; useful for large disks, PST/OST files, RAID servers).

Considerations: source-disk size (compression, digital signatures), tape backup for very large drives, and whether the disk can be retained.

### P5 – Question 2

<a id="p5-q2aiii"></a>
**(a(i–ii)) Discuss the need for Extraction in computer forensics; list any two sub-functions of Extraction.** — *5 marks*

**Need:** Extraction is the recovery task in an investigation — the **most demanding task to master**, since recovering data is the essential first step before any analysis, reconstruction, or reporting can happen. It must also deal with encrypted files/systems (password-recovery tools build dictionary-attack lists; brute-force attacks follow if that fails).

**Two sub-functions (of six):** **Data viewing** and **Keyword searching** (others: decompressing, carving, decrypting, bookmarking).

<a id="p5-q2b"></a>
**(b) Illustrate in detail how Substitution works in Steganography. Give a clear example.** — *5 marks*

**Insufficient Information (partial)** — the lecture sheet defines steganography only generally: Greek for "hidden writing," originally used for digital watermarks to protect copyrighted material; small amounts of data are hidden inside image/text files, very hard to detect without prior knowledge (tools: S-Tools, DPEnvelope, jpgx, tte). It does **not** describe a specific "Substitution" (e.g., least-significant-bit) mechanism or give a worked bitwise example — that detail is missing from the lecture sheet.

### P5 – Question 3

<a id="p5-q3a"></a>
**(a) Explain bit stream copy and bit stream image with examples.** — *3 marks*

- **Bit-stream disk-to-image file** — most common method; multiple bit-for-bit copies can be made into an image file (tools: ProDiscover, EnCase, FTK, SMART, Sleuth Kit, X-Ways, iLook).
- **Bit-stream disk-to-disk** — used when imaging isn't possible; requires matching the target disk's geometry (tools: EnCase, SafeBack, SnapCopy).

Both are exact sector-by-sector duplicates (not simple file copies); they differ only in destination — an image file vs. a physical disk.

<a id="p5-q3b"></a>
**(b) Describe tasks perform by computer forensics tools.** — *4 marks*

Five major categories of tasks performed by computer forensics tools:
1. **Acquisition** — copying the original drive (physical/logical copy, various formats, command-line/GUI/remote acquisition, verification).
2. **Validation and discrimination** — validation ensures data integrity; discrimination sorts/searches data (hashing with CRC-32/MD5/SHA, filtering by hash sets, file-header analysis).
3. **Extraction** — the recovery task, hardest to master (data viewing, keyword searching, decompressing, carving, decrypting, bookmarking).
4. **Reconstruction** — recreating a suspect drive (disk-to-disk, image-to-disk, partition-to-partition, image-to-partition copy).
5. **Reporting** — producing the examination report (log reports, report generator).

<a id="p5-q3c"></a>
**(c) Explain developing standard procedure for network forensics.** — *3 marks*

Network forensics is long and tedious. Standard procedure: use a standard installation image for network systems → close the way in after an attack → retrieve all volatile data → acquire all compromised drives → compare forensic image files to the original installation image. Work from the image to find what changed; restore drives to understand the attack; work on an isolated system; load the image as a VM for analysis if needed.

### P5 – Question 4

<a id="p5-q4a"></a>
**(a) Explain common data hiding techniques in brief.** — *4 marks*

1. **File manipulation** — hiding via filenames/extensions or the hidden-file property.
2. **Disk manipulation** — hidden partitions (deleted partition references, re-linked later) and bad clusters (marking free space holding hidden data as "bad," common on FAT).
3. **Encryption** — bit shifting (altering byte values so files resemble binary executable code, via tools like Hex Workshop) and steganography (hiding small amounts of data inside image/text files; tools: S-Tools, DPEnvelope, jpgx, tte).

<a id="p5-q4b"></a>
**(b) What is carving or salvaging? How does repair damaged file header?** — *3 marks*

**Carving/salvaging** = recovering all file fragments (typically from slack space and free/unallocated space) so forensic tools can help reassemble them.

**Repairing a damaged header:** each file type has a unique header (e.g., JPEG = FF D8 FF E0 00 10, often with a JFIF string). Steps: try opening the file; if unreadable, recover more file pieces if needed → compare the header to a good sample → manually insert the correct hexadecimal values → test the corrected file.

<a id="p5-q4c"></a>
**(c) Write down the steps for reconstructing file fragments.** — *3 marks*

1. Locate and export all clusters of the fragmented file.
2. Determine the starting and ending cluster numbers for each fragmented group of clusters.
3. Copy each fragmented group, in proper sequence, to a recovery file.
4. Rebuild the corrupted file's header so it opens correctly in the appropriate viewer/application.

### P5 – Question 5

<a id="p5-q5a"></a>
**(a) What do you mean by validating forensics data? Explain validating with hexadecimal editors.** — *4 marks*

Validating forensic data means ensuring data integrity for court presentation — critical since standard tools have hashing limitations.

**Hex editors:** e.g., **Hex Workshop** provides hashing algorithms (MD5, SHA-1) and can hash specific files or sectors within a file.
**Discriminating with hash values:** AccessData's **Known File Filter (KFF)** compares known file hash values (e.g., MSWord.exe) against files on the evidence drive/image to filter out known, irrelevant files; the KFF database is periodically updated.

<a id="p5-q5b"></a>
**(b) What is drive slack? Explain it according to the purposes of digital forensics.** — *3 marks*

Microsoft OSs allocate disk space in **clusters**, producing **drive slack** — unused space in a cluster between the end of an active file and the end of the cluster. Drive slack = **RAM slack + file slack** (NTFS produces much less file slack than FAT).

Forensically, this unused space can still hold remnants of previously deleted/overwritten files (or old memory contents), so investigators examine it for hidden evidence the OS no longer shows.

<a id="p5-q5c"></a>
**(c) Explain different types of digital evidence storage formats.** — *3 marks*

1. **Raw format** — bit-stream data written directly to a file. *Pros:* fast transfers, ignores minor read errors, readable by most tools. *Cons:* needs as much storage as the original, may miss bad sectors.
2. **Proprietary formats** — vendor-specific. *Pros:* optional compression, image can be split into segments, metadata can be embedded. *Cons:* can't be shared across different tools, segment file-size limits.
3. **Advanced Forensics Format (AFF)** — open-source (Dr. Simson L. Garfinkel, Basis Technology). Compressed or uncompressed images, no size restriction, space for metadata, simple/extensible design, multi-platform. File extensions: **.afd** (segmented image) and **.afm** (AFF metadata).

### P5 – Question 6

<a id="p5-q6a"></a>
**(a) Compare and contrast RAID 0 and RAID 1.** — *7 marks*

| Aspect | RAID 0 | RAID 1 |
|---|---|---|
| Purpose | Rapid access + increased storage | Data recovery |
| Redundancy | None | Yes (mirroring) |
| Cost | Lower | Higher |
| Data safety | Lower (no redundancy) | Higher |

RAID = Redundant Array of Independent (originally "Inexpensive") Disks — two or more disks configured together, originally for data redundancy. RAID 0 trades redundancy for speed/capacity; RAID 1 trades cost for recoverability.

<a id="p5-q6b"></a>
**(b) Describe the RAID acquisition methods.** — *3 marks*

**Concerns:** how much storage is needed, what RAID type is used, whether the tool can read a forensically copied RAID image or split RAID-disk data, and challenges from older hardware-firmware RAID systems (size is the biggest concern — RAID systems often hold terabytes).

**Vendors/methods:** Technologies Pathways ProDiscover, Guidance Software EnCase, X-Ways Forensics, Runtime Software, R-Tools Technologies. When a RAID is too large for static acquisition, use the **sparse or logical acquisition method** to retrieve only relevant data.

### P5 – Question 7

<a id="p5-q7a"></a>
**(a) Explain the acquisition procedures for cell phones and mobile devices.** — *3 marks*

Main concerns: **loss of power** and **PC synchronization** (mobile devices have volatile memory). Disconnect the device from any cable/cradle immediately. Isolate it from incoming signals using a paint can, the Paraben Wireless StrongHold Bag, or eight layers of antistatic bags (trade-off: this triggers roaming mode, draining the battery faster).

In the lab, check: internal memory, SIM card, removable/external memory cards, and system server (needs a warrant/subpoena). Acquisition = synchronizing with the device like a PC (to download data) + reading the SIM card (service data, call data, messages, location info) — noting that PINs/access codes may be needed if power was lost.

<a id="p5-q7b"></a>
**(b) Explain some mobile forensics tools in brief.** — *2 marks*

- **Paraben Software Device Seizure Toolbox** — cables, SIM card readers, etc.
- **Data Pilot** — similar toolbox.
- **BitPim** — views phone data, but not intended for forensics.
- **MOBILedit!** — has a built-in write-blocker.
- **SIMCon** — reads SIM files, recovers deleted texts, hashes with MD5/SHA-1.

<a id="p5-q7c"></a>
**(c) Describe tasks in investigation of e-mail crime and violations.** — *3 marks*

Goals: find who is behind the crime, collect evidence, present findings, build a case (consult an attorney, since handling varies by jurisdiction, e.g., for spam). Crimes involving e-mail: narcotics trafficking, extortion, sexual harassment, child abduction/pornography.

Tasks: access the victim's computer/e-mail client to find and copy evidence, access protected/encrypted material, print e-mails, guide the victim by phone to open/copy e-mail (including headers), and recover deleted e-mails (servers can often recover them, similar to deleted-file recovery).

<a id="p5-q7d"></a>
**(d) Analyze the function of e-mail forensics tools.** — *2 marks*

Specialized tools (FTK, ProDiscover Basic, FINALeMAIL, Sawmill-GroupWise, DBXtract, Aid4Mail/MailBag Assistant, Paraben E-Mail Examiner, Ontrack EmailRepair, R-Tools R-Mail) let investigators find e-mail database files, personal e-mail files, offline storage files, and log files — without needing deep knowledge of the underlying server/client architecture. E.g., **FINALeMAIL** scans e-mail databases, recovers deleted e-mails, and finds associated files; **FTK** indexes an entire disk/image (via dtSearch) for fast retrieval of Outlook/Outlook Express e-mail.

---

## Paper 6 — Winter 2022 (11th batch)

### P6 – Question 1

<a id="p6-q1a"></a>
**(a) What is digital evidence? Assess general tasks investigators perform with digital evidence.** — *4 marks*

**Digital evidence** = any information stored or transmitted in digital form; U.S. courts accept it as physical/tangible evidence (some require it printed for court).

General investigator tasks: identify digital information/artifacts as evidence → collect, preserve, and document evidence → analyze, identify, and organize evidence → rebuild evidence or repeat a situation to verify reproducible results. Collecting computers and processing a scene must be done systematically.

<a id="p6-q1b"></a>
**(b) State guidelines for processing an incident or crime scene.** — *2 marks*

- Keep a journal documenting all activities.
- Secure the scene (be professional; remove non-investigation personnel).
- Take video/photos of the area around the computer; sketch the scene.
- Check computers as soon as possible; don't cut power unless it's an old Windows 9x/MS-DOS system.
- Save data from running applications safely; record active windows/sessions; note everything done while copying data live.
- Close applications and shut down the computer.
- Bag and tag evidence: one person collects/logs everything; tag with date/time, serial number/unique features, make/model, collector's name; maintain two logs; keep constant control of evidence and scene.
- Look for and collect related information/documentation (passwords, PINs, bank accounts, etc.).

<a id="p6-q1c"></a>
**(c) What do you mean by remote acquisition? Explain with ProDiscover or EnCase Enterprise.** — *4 marks*

**Remote acquisition** = connecting to a suspect computer over a network to copy its data, instead of physically removing the drive. Drawbacks: LAN speed/routing-table conflicts, difficulty gaining access to secure subnets, heavy traffic causing delays/errors.

**With ProDiscover Investigator:** preview the drive remotely while in use, perform live acquisition, encrypt the connection, copy the suspect's RAM, use stealth mode. ProDiscover Incident Response adds: capture volatile system state, analyze running processes, locate unseen files/processes, remotely view/listen to IP ports, run hash comparisons, create a remote hash inventory. The **PDServer remote agent** is loaded on the suspect machine (Trusted CD / preinstalled / pushed remotely) and can run in stealth mode. Security features: Password Protection, Encryption, Secure Communication Protocol, Write Protected Trusted Binaries, Digital Signatures.

**With EnCase Enterprise:** remote acquisition of media/RAM data, IDS tool integration, imaging one or more systems, system preview, wide file-system format support, RAID support (hardware and software).

### P6 – Question 2

<a id="p6-q2a"></a>
**(a) Explain how to find criminal activities on an NTFS disk.** — *2 marks*

In NTFS, **data streams** let data be appended to existing files and can **obscure evidentiary data**, intentionally or not — a data stream is an extra file attribute. **The only way to tell a file has a data stream is by examining its MFT entry.** Investigators should therefore inspect MFT entries for hidden streams, check for **EFS/BitLocker** encryption, and check the **Windows Registry** (records attached hardware, preferences, network connections, installed software) for signs of suspicious activity.

<a id="p6-q2b"></a>
**(b) What are EFS and BitLocker? Explain whole disk encryption.** — *4 marks*

- **EFS (Encrypting File System)** — introduced in Windows 2000; public/private-key encryption of files, folders, or volumes. A recovery certificate is issued to the local admin account (Vista Business+/XP Pro/2000); recoverable via Cipher, Copy, or Efsrecvr commands.
- **BitLocker** — Vista Enterprise/Ultimate only; requires a TPM chip (v1.2+), a TCG-compliant BIOS, two NTFS partitions, and BIOS set to boot the hard drive first.
- **Whole disk encryption** — protects against loss of laptops/handhelds. Features: preboot authentication, full/partial disk encryption with secure hibernation, advanced encryption algorithms, key management, TPM-based key generation/login authentication. Each sector (often including the boot sector) is encrypted separately; must be decrypted with a vendor tool before examination. Tools: PGP Whole Disk Encryption, Voltage SecureDisk, Utimaco SafeGuard Easy, Jetico BestCrypt, SoftWinter Sentry 2020; open-source: TrueCrypt, CrossCrypt, FreeOTFE.

<a id="p6-q2c"></a>
**(c) Explain the roles of Windows Registry for computer forensics investigations.** — *4 marks*

The **Registry** is a database storing hardware/software configuration, network connections, user preferences, and setup information — it can hold valuable evidence. View via Regedit (Win 9x) or Regedt32 (Win 2000/XP); ProDiscover Basic can extract System.dat/User.dat from an image.

Per the summary: the Registry **keeps a record of attached hardware, user preferences, network connections, and installed software** — directly useful for reconstructing device/software/network history on a suspect machine, and for detecting VM install/uninstall activity.

### P6 – Question 3

<a id="p6-q3a"></a>
**(a) Describe the activities performed by computer forensics tools.** — *7 marks*

1. **Acquisition** — copying the original drive: physical/logical data copy, various acquisition formats, command-line/GUI/remote acquisition, and verification (comparing original vs. image). Raw image files can be viewed with any hex editor; vendor tools often segment images into smaller files.
2. **Validation and discrimination** — validation checks copied-data integrity; discrimination sorts/searches data. Subfunctions: hashing (CRC-32, MD5, SHA), filtering (e.g., via the NSRL hash-value database), and file-header analysis (detects incorrect extensions, discriminates by file type).
3. **Extraction** — the recovery task, hardest to master. Subfunctions: data viewing, keyword searching, decompressing, carving, decrypting (dictionary/brute-force attacks on protected files), bookmarking.
4. **Reconstruction** — recreating a suspect drive to show what happened: disk-to-disk, image-to-disk, partition-to-partition, image-to-partition copy (tools: SafeBack, SnapBack, EnCase, FTK Imager, ProDiscover).
5. **Reporting** — completing the analysis/examination report: log reports, report generator.

<a id="p6-q3b"></a>
**(b) Define bit stream copy and bit stream image.** — *3 marks*

- **Bit-stream disk-to-image file** — most common method; multiple bit-for-bit copies can be made into an image file (tools: ProDiscover, EnCase, FTK, SMART, Sleuth Kit, X-Ways, iLook).
- **Bit-stream disk-to-disk** — used when imaging isn't possible; requires matching the target disk's geometry (tools: EnCase, SafeBack, SnapCopy).

Both are exact sector-by-sector duplicates (not simple file copies); they differ only in destination — an image file vs. a physical disk.

### P6 – Question 4

<a id="p6-q4a"></a>
**(a) Explain how to locate and recover graphics files on the suspect's drive.** — *4 marks*

- Plain OS tools are slow and results are hard to verify.
- Prefer **forensic tools**: examine image **headers** (compare to good samples for baseline analysis), **reconstruct fragmented files** by identifying data patterns/modified headers, **carve/salvage** fragments from slack and free space, and use tools (e.g., ProDiscover) to search unallocated space for graphics evidence — being alert to false positives.

<a id="p6-q4b"></a>
**(b) Explain identifying graphics file fragments and reconstruction of file fragments.** — *3 marks*

**Identifying fragments (carving/salvaging):** recovering all file fragments — typically carved from slack and free space — using forensic tools to identify and help reassemble image file fragments.

**Reconstructing fragments:** locate/export all clusters of the fragmented file → determine starting/ending cluster numbers for each fragment group → copy fragments, in proper sequence, to a recovery file → rebuild the corrupted header so it opens in a graphics viewer.

<a id="p6-q4c"></a>
**(c) What is metafile graphics? Explain graphics file formats.** — *3 marks*

Three graphics types: **bitmap** (pixel grid), **vector** (mathematical drawing instructions — smaller, scales without quality loss), and **metafile graphics** — a **combination of bitmap and vector** (e.g., a scanned photo + text), inheriting both types' pros/cons (bitmap portion loses quality on enlargement, vector portion doesn't).

**Formats:** Bitmap — GIF (.gif), JPEG (.jpeg/.jpg), TIFF (.tiff/.tif), Windows Bitmap (.bmp). Vector — HPGL (.hpgl), AutoCAD (.dxf). Nonstandard — Targa (.tga), RTL (.rtl), Photoshop (.psd)/Illustrator (.ai), Freehand (.fh9), SVG (.svg), Paintbrush (.pcx).

### P6 – Question 5

<a id="p6-q5a"></a>
**(a) Define digital forensics and investigations.** — *2 marks*

- **Computer forensics** — obtaining and analyzing digital information as evidence in civil, criminal, or administrative cases; recovers data hidden/deleted from storage media, used as evidence (inculpatory or exculpatory).
- **Network forensics** — yields information about how a perpetrator/attacker gained access to a network.
- **Data recovery** — recovering information lost by mistake, power surge, or server crash; the target data is already known.

<a id="p6-q5b"></a>
**(b) What do you mean by validating forensics data? Explain validating with hex editors and computer forensics programs.** — *4 marks*

**Validating forensic data** ensures data integrity for court presentation — a critical aspect of computer forensics.

**With hex editors:** e.g., Hex Workshop hashes specific files/sectors (MD5, SHA-1); AccessData's KFF database filters known files by comparing hash values.

**With computer forensics programs:** built-in validation features vary by tool — ProDiscover's **.eve** files embed metadata including the hash value (automatic validation), while raw **.dd** images have no metadata and need manual validation. In FTK Imager, choosing Expert Witness (.e01) or SMART (.s01) format shows extra validation options; the validation report lists MD5 and SHA-1 hash values.

<a id="p6-q5c"></a>
**(c) Explain common data hiding techniques in brief.** — *4 marks*

1. **File manipulation** — hiding via filenames/extensions or the hidden-file property.
2. **Disk manipulation** — hidden partitions (deleted partition references, re-linked later) and bad clusters (marking free space holding hidden data as "bad," common on FAT).
3. **Encryption** — bit shifting (altering byte values so files resemble binary executable code, via tools like Hex Workshop) and steganography (hiding small amounts of data inside image/text files; tools: S-Tools, DPEnvelope, jpgx, tte).

### P6 – Question 6

<a id="p6-q6a"></a>
**(a) Explain standard procedures for performing a live acquisition.** — *5 marks*

**Necessity:** live acquisitions are vital for active network intrusions/attacks, and are increasingly performed *before* taking a system offline, since attack evidence may exist only in running processes/RAM (governed by **Order of Volatility** — how long data lasts on a system). Live acquisitions don't follow typical static forensic procedures.

**Standard procedure:**
1. Create/download a bootable forensic CD (e.g., Helix, DEFT).
2. Log all actions taken.
3. Send collected information to a network drive if possible.
4. Copy the physical memory (RAM) first.
5. Continue with incident-specific next steps.
6. Obtain a forensic hash of all recovered files.

Tools: Mantech Memory DD, Win32dd, winen.exe, BackTrack 4.

<a id="p6-q6b"></a>
**(b) Describe standard procedures for network forensics.** — *5 marks*

- Always use a standard installation image for network systems.
- Close the way in after an attack.
- Attempt to retrieve all volatile data.
- Acquire all compromised drives.
- Compare the forensic image's files to the original installation image.

Work from the image to see what changed and restore drives to understand the attack; work on an isolated system to avoid spreading malware; there's an opportunity to load the image as a VM for analysis.

### P6 – Question 7

<a id="p6-q7a"></a>
**(a) Explain the acquisition procedures for cell phones/mobile devices and state some mobile forensics tools.** — *5 marks*

Main concerns: **loss of power** and **PC synchronization** (mobile devices have volatile memory). Disconnect the device from any cable/cradle immediately. Isolate it from incoming signals using a paint can, the Paraben Wireless StrongHold Bag, or eight layers of antistatic bags (trade-off: this triggers roaming mode, draining the battery faster).

In the lab, check: internal memory, SIM card, removable/external memory cards, and system server (needs a warrant/subpoena). Acquisition = synchronizing with the device like a PC (to download data) + reading the SIM card (service data, call data, messages, location info) — noting that PINs/access codes may be needed if power was lost.

<a id="p6-q7b"></a>
**(b) Describe tasks in investigation of e-mail crime and violations and analyze the function of e-mail forensics tools.** — *5 marks*

Goals: find who is behind the crime, collect evidence, present findings, build a case (consult an attorney, since handling varies by jurisdiction, e.g., for spam). Crimes involving e-mail: narcotics trafficking, extortion, sexual harassment, child abduction/pornography.

Tasks: access the victim's computer/e-mail client to find and copy evidence, access protected/encrypted material, print e-mails, guide the victim by phone to open/copy e-mail (including headers), and recover deleted e-mails (servers can often recover them, similar to deleted-file recovery).

---
