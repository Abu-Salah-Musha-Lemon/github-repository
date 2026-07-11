# Digital Forensics & Investigation — Exam Solutions

Fully worked solutions to **six past final-exam question papers** (2022–2025 sessions) for the *Digital Forensics and Investigation* course (CSE-5210 / CSE-520), M.Sc. in CSE (Professional), Jagannath University — solved strictly from the course lecture sheet.

**Source material:** *Guide to Computer Forensics and Investigations*, 4th Edition (16-chapter lecture sheet — acquisition, validation, extraction, reconstruction, reporting, file systems, e-mail/mobile/network forensics, etc.)

## 📚 Papers covered

1. Winter 2025 (17th batch) — Full Marks 60
2. Summer 2024 (16th batch) — full Marks 60
3. Winter 2023 (15th batch) — full Marks 60
4. Winter 2023 (14th batch) — Full Marks 50
5. Winter 2023 (13th batch) — Full Marks 50
6. Winter 2022 (11th batch) — Full Marks 50

## ✅ Methodology

- Every question is numbered exactly as it appears in its original paper.
- Answers use **only** the terminology, definitions, and examples found in the lecture sheet — no outside sources.
- Each answer follows: **Solution steps → Calculations (where applicable) → Final Answer.**
- Where the lecture sheet genuinely doesn't cover a topic, this is flagged explicitly as **Insufficient Information**, with a note on what's missing, rather than guessed or fabricated. Flagged topics include: Resilient File System (ReFS), Mini-WinFE Boot CD/DVD/USB, machine learning/AI in modern forensics tools, the bit-level mechanics of "Substitution" steganography, email encryption/digital signatures as a dedicated topic, and the password-compromise scenario question (partial, lecture-grounded reasoning only).

## ⚠️ Disclaimer

These are **study aid materials**, prepared to help with exam revision by mapping each question back to its source in the lecture notes. They are not official answer keys. Please verify against your course syllabus and consult your instructor for grading-specific expectations.

---

# Full Solutions

# Jagannath University — CSE-5210, Digital Forensics and Investigation
## Paper 1: M.Sc. 3rd Semester Final Examination 2025 (Session: Winter 2025, 17th batch)

---

## Question 1

### (a) Do computer forensics and data recovery refer to the same activities? Justify your answer. — 4 marks

**Solution**

- Step 1: Identify how the lecture sheet defines each discipline separately under "Computer Forensics Versus Other Related Disciplines."
- Step 2: Compare their goals and working assumptions.
- Step 3: Justify whether they are the same or different.

**Calculations**

Not applicable — this is a conceptual/comparative question, no numerical computation is required.

**Final Answer**

No, computer forensics and data recovery are **not** the same activity, although they are closely related.

- **Computer forensics** investigates data that can be retrieved from a computer's hard disk or other storage media, with the specific task of recovering data that users have hidden or deleted and using it as **evidence** — the evidence can be inculpatory ("incriminating") or exculpatory.
- **Data recovery** is a related discipline that involves recovering information that was deleted by mistake, or lost during a power surge or server crash. Typically, in data recovery, you already know what you are looking for.

Justification: The key difference lies in the *purpose and known-target* of the recovery. In data recovery, the technician usually knows what data is missing and works only to restore it for the owner's use. In computer forensics, the investigator does not necessarily know in advance what will be found; the recovered data must additionally be handled under a chain of custody and prepared as legally admissible evidence for a civil, criminal, or administrative case. Therefore, computer forensics **uses** data-recovery techniques but adds an evidentiary and legal dimension that plain data recovery does not have.

---

### (b) List three common types of digital crime. — 4 marks

**Solution**

- Step 1: Refer to the lecture sheet's list of corporate computer crimes under "Understanding Corporate Investigations."
- Step 2: Select any three types from the list.

**Calculations**

Not applicable — descriptive/listing question.

**Final Answer**

According to the lecture sheet, corporate computer crimes can involve:

1. **E-mail harassment**
2. **Falsification of data**
3. **Embezzlement**

(Other types listed in the same source include gender and age discrimination, sabotage, and industrial espionage.)

---

### (c) What are some ways to determine the resources needed for an investigation? — 4 marks

**Solution**

- Step 1: Refer to "Taking a Systematic Approach" in the lecture sheet, which lists the steps for problem solving in an investigation.
- Step 2: Extract the specific step relating to resource determination and its surrounding context (assessing the case).
- Step 3: Present the resource-determination process.

**Calculations**

Not applicable — conceptual/procedural question.

**Final Answer**

The lecture sheet places "Determine the resources you need" as one of the steps for problem solving in a systematic approach to an investigation, coming after making an initial assessment of the case type, determining a preliminary design/approach, and creating a detailed checklist.

To determine the resources needed, an investigator should:
- **Assess the case** systematically by outlining: the situation, nature of the case, specifics of the case, type of evidence, operating system, known disk format, and location of evidence.
- From these case details, **determine the case requirements**, i.e., the type of evidence, the computer forensics tools needed, and any special operating systems required.
- Only after this assessment can the investigator obtain and copy an evidence disk drive and proceed to analyze and recover the digital evidence.

---

## Question 2

### (a) What do you mean by remote acquisition? Explain the remote acquisition with ProDiscover Basic or EnCase Enterprise. — 6 marks

**Solution**

- Step 1: Define remote acquisition from the lecture sheet's "Using Remote Network Acquisition Tools" section.
- Step 2: List the drawbacks mentioned in the lecture sheet.
- Step 3: Explain remote acquisition using ProDiscover (or EnCase Enterprise) with its specific features, exactly as listed in the lecture sheet.

**Calculations**

Not applicable — descriptive question.

**Final Answer**

**Remote acquisition** means that you can remotely connect to a suspect computer via a network connection and copy data from it, instead of physically removing the drive. Remote acquisition tools vary in configurations and capabilities. Drawbacks include: the LAN's data transfer speeds and routing table conflicts could cause problems; gaining the permissions needed to access more secure subnets can be difficult; and heavy traffic could cause delays and errors.

**Remote Acquisition with ProDiscover:**
With ProDiscover Investigator you can:
- Preview a suspect's drive remotely while it's in use
- Perform a live acquisition
- Encrypt the connection
- Copy the suspect computer's RAM
- Use the optional stealth mode

ProDiscover Incident Response adds further functions: capture volatile system state information, analyze current running processes, locate unseen files and processes, remotely view and listen to IP ports, run hash comparisons, and create a hash inventory of all files remotely.

The **PDServer remote agent** is ProDiscover's utility for remote access; it needs to be loaded on the suspect machine, and can be installed via a Trusted CD, preinstallation, or by pushing it out and running it remotely. PDServer can run in **stealth mode**, changing its process name to appear as an OS function. Remote connection security features include Password Protection, Encryption, Secure Communication Protocol, Write Protected Trusted Binaries, and Digital Signatures.

*(Alternatively, with EnCase Enterprise, remote acquisition features include: remote data acquisition of a computer's media and RAM data, integration with intrusion detection system (IDS) tools, options to create an image of data from one or more systems, preview of systems, support for a wide range of file system formats, and RAID support for both hardware and software.)*

---

### (b) Describe certification and training requirements for digital forensics labs. — 3 marks

**Solution**

- Step 1: Identify the certifying body named in the lecture sheet.
- Step 2: List the certifications/organizations mentioned.

**Calculations**

Not applicable.

**Final Answer**

The **American Society of Crime Laboratory Directors (ASCLD)** offers guidelines for managing a lab, acquiring an official certification, and auditing lab functions and procedures.

Certification/training bodies and credentials listed in the lecture sheet include:
- **International Association of Computer Investigative Specialists (IACIS)** — offers Certified Electronic Evidence Collection Specialist (CEECS) and Certified Forensic Computer Examiners (CFCEs)
- **High-Tech Crime Network (HTCN)** — Certified Computer Crime Investigator (Basic/Advanced), Certified Computer Forensic Technician (Basic/Advanced)
- **EnCase Certified Examiner (EnCE) Certification**
- **AccessData Certified Examiner (ACE) Certification**
- Other bodies: High Technology Crime Investigation Association (HTCIA), SANS Institute, Computer Technology Investigators Network (CTIN), New Technologies Inc. (NTI), Southeast Cybercrime Institute, Federal Law Enforcement Training Center (FLETC), National White Collar Crime Center (NW3C)

Staff must also maintain knowledge and training in hardware and software, OS and file types, deductive reasoning, technical training, and investigative skills, with work reviewed regularly by the lab manager.

---

### (c) Explain the purpose of a virtual machine for computer forensics and investigation. — 4 marks

**Solution**

- Step 1: Refer to "Virtual Machines Overview" in the lecture sheet.
- Step 2: State why VMs matter to investigators.

**Calculations**

Not applicable.

**Final Answer**

Virtual machines are important in today's networks, and investigators must know how to:
- **Detect** a virtual machine installed on a host,
- **Acquire an image** of a virtual machine, and
- **Use virtual machines to examine malware.**

Common VM software includes VirtualBox, Virtual PC, Parallels, and VMware. As part of an investigation, the examiner should check whether virtual machines are loaded on a host computer and check the Registry for clues that virtual machines have been installed or uninstalled — since a suspect may use a VM to hide activity or to run/isolate malware safely for analysis (the lecture sheet also notes there is an "opportunity to load [a compromised] image as a VM for analysis" in network forensics work).

---

## Question 3

### (a) How do inodes keep track of a file's name and data? — 4 marks

**Solution**

- Step 1: Refer to "Understanding Inodes" (Linux/UNIX file systems, ch. 8 of the lecture sheet).
- Step 2: Explain the inode's pointer structure.

**Calculations**

Not applicable.

**Final Answer**

In UNIX/Linux file systems (Ext2fs/Ext3fs), **inodes contain information about each file or directory** and hold a pointer to other inodes or blocks. Each inode keeps an internal link count; deleted inodes have a count value of 0.

Link data itself is stored in data blocks. The **first inode has 13 pointers**:
- Pointers 1 to 10 are **direct pointers** to data storage blocks
- Pointer 11 is an **indirect pointer**
- Pointer 12 is a **double-indirect pointer**
- Pointer 13 is a **triple-indirect pointer**

The **superblock** indicates disk geometry, available space, and the location of the first inode, and manages the file system. **Inode blocks** are the first data after the superblock and are assigned to every file allocation unit. **Data blocks** are where directories and files are actually stored, and this location is linked directly to the inodes. A **continuation inode** provides further information about a file or directory, such as its mode and file type, the quantity of links, and the file/directory status flag. This chain of pointers is how an inode tracks both the identity (via directory/link entries) and the physical data location of a file.

---

### (b) Discuss the importance of digital hash in forensic investigation. — 4 marks

**Solution**

- Step 1: Refer to "Obtaining a Digital Hash" in the lecture sheet.
- Step 2: Explain each hashing algorithm mentioned.
- Step 3: State the three rules for forensic hashes and why hashing matters.

**Calculations**

Not applicable (no numeric hash computation is provided in the lecture sheet to work through).

**Final Answer**

A digital hash is critical because ensuring the integrity of data collected is essential for presenting evidence in court — validating forensic data is one of the most critical aspects of computer forensics.

- **Cyclic Redundancy Check (CRC)** — a mathematical algorithm that determines whether a file's contents have changed; the most recent version is CRC-32, though it is **not** considered a forensic hashing algorithm.
- **Message Digest 5 (MD5)** — a mathematical formula that translates a file into a hexadecimal code value (a hash value); if a single bit or byte in the file changes, the digital hash changes.
- **Secure Hash Algorithm version 1 (SHA-1)** — a newer hashing algorithm developed by NIST.

**Three rules for forensic hashes:**
1. You can't predict the hash value of a file or device.
2. No two hash values can be the same.
3. If anything changes in the file or device, the hash value must change.

Because of these properties, a hash value acts as a unique "digital fingerprint" of evidence: investigators hash the original media at acquisition time and compare it to the hash of the working copy/image at every later stage, proving that the evidence has not been altered — this is central to validating both the acquisition and any subsequent analysis before a court.

---

### (c) What are the five required functions for computer forensics tools? Briefly explain. — 4 marks

**Solution**

- Step 1: Refer to "Tasks Performed by Computer Forensics Tools" in the lecture sheet.
- Step 2: List the five major categories.
- Step 3: Briefly explain each with its subfunctions.

**Calculations**

Not applicable.

**Final Answer**

The lecture sheet lists **five major categories** of tasks performed by computer forensics tools:

1. **Acquisition** — making a copy of the original drive. Subfunctions: physical data copy, logical data copy, data acquisition format, command-line acquisition, GUI acquisition, remote acquisition, and verification.
2. **Validation and discrimination** — validation ensures the integrity of data being copied; discrimination involves sorting and searching through all investigation data. Subfunctions: hashing (CRC-32, MD5, SHA), filtering (based on hash value sets), and analyzing file headers (to discriminate files by type).
3. **Extraction** — the recovery task in an investigation, considered the most demanding task to master. Subfunctions: data viewing, keyword searching, decompressing, carving, decrypting, and bookmarking.
4. **Reconstruction** — re-creating a suspect drive to show what happened during a crime/incident. Subfunctions: disk-to-disk copy, image-to-disk copy, partition-to-partition copy, and image-to-partition copy.
5. **Reporting** — producing a report to complete a forensics disk analysis and examination. Subfunctions: log reports and report generator.

---

## Question 4

### (a) How can "Hiding Partitions" and "Marking Bad Clusters" techniques be used to hide data? — 4 marks

**Solution**

- Step 1: Refer to "Addressing Data-hiding Techniques" → "Hiding Partitions" and "Marking Bad Clusters."
- Step 2: Explain each technique as described in the lecture sheet.

**Calculations**

Not applicable.

**Final Answer**

Both are **disk manipulation** data-hiding techniques listed under "Addressing Data-hiding Techniques":

- **Hiding Partitions:** A suspect can delete references to a partition using a disk editor, then re-create the links later to access it again — effectively making the partition invisible to normal inspection while the data on it still exists. Disk-partitioning utilities such as GDisk, PartitionMagic, System Commander, and LILO can be used for this purpose. Because of this, an investigator must account for **all disk space** when analyzing a disk, so unaccounted-for space is a red flag for a hidden partition.
- **Marking Bad Clusters:** This is common with FAT systems. The suspect places sensitive information on free space and then uses a disk editor to mark that space as a "bad" cluster, so the operating system will not write over it or normally access it (e.g., in Norton Disk Edit, typing **B** in the FAT entry corresponding to that cluster marks it as bad). Because forensic tools can still read marked-bad clusters directly, an investigator can recover the hidden data by examining these clusters instead of trusting the OS's "bad" flag.

---

### (b) What is carving or salvaging? How does one repair a damaged file header? — 3 marks

**Solution**

- Step 1: Define carving/salvaging from "Identifying Graphics File Fragments."
- Step 2: Describe the header-repair procedure from "Repairing Damaged File Headers" / "Rebuilding File Headers."

**Calculations**

Not applicable.

**Final Answer**

**Carving or salvaging** means recovering all file fragments (e.g., of a graphics file) that remain on a disk, typically from slack space and free/unallocated space, so that computer forensics tools can help identify image file fragments and put them back together.

**Repairing a damaged file header:**
- Use **good header samples** for comparison — each image file type has a unique file header (e.g., a JPEG header is FF D8 FF E0 00 10, and most JPEG files also include a JFIF string).
- Try to open the file first; if its content cannot be seen, follow these steps:
  - Recover more pieces of the file if needed.
  - Examine the file header and compare it with a good header sample.
  - Manually insert the correct hexadecimal values into the damaged header.
  - Test the corrected file to confirm it opens properly.

---

### (c) Write down the steps for reconstructing file fragments. — 4 marks

**Solution**

- Step 1: Refer directly to "Reconstructing File Fragments" in the lecture sheet.
- Step 2: List the steps in order.

**Calculations**

Not applicable.

**Final Answer**

According to the lecture sheet, to reconstruct file fragments you must **locate the starting and ending clusters for each fragmented group of clusters** in the file, following these steps:

1. Locate and export all clusters of the fragmented file.
2. Determine the starting and ending cluster numbers for each fragmented group of clusters.
3. Copy each fragmented group of clusters, in their proper sequence, to a recovery file.
4. Rebuild the corrupted file's header to make it readable in a graphics viewer (or appropriate application).

---

## Question 5

### (a) What do you mean by validating forensics data? Explain validating with hexadecimal editors. — 5 marks

**Solution**

- Step 1: Define validating forensic data from "Validating Forensic Data."
- Step 2: Explain the hexadecimal-editor validation method and its uses.

**Calculations**

Not applicable.

**Final Answer**

**Validating forensic data** means ensuring the integrity of the data you collect, which is essential for presenting the evidence in court — it is one of the most critical aspects of computer forensics. Most computer forensic tools provide automated hashing of image files, but these tools have limitations in performing hashing, so learning how to use advanced hexadecimal editors is necessary to ensure data integrity.

**Validating with Hexadecimal Editors:**
- Advanced hexadecimal editors offer features not available in standard computer forensics tools, such as hashing specific files or sectors.
- **Hex Workshop** provides several hashing algorithms (such as MD5 and SHA-1) and can generate the hash value of selected data sets within a file or sector.
- **Using hash values to discriminate data:** AccessData maintains a separate database called the **Known File Filter (KFF)**, which filters known program files (e.g., MSWord.exe) from view by comparing known file hash values to files on the evidence drive or image files. AccessData periodically updates these known file hash values and posts an updated KFF.

This lets an investigator both verify that an acquired image is unaltered and separate "known" files (already identified/irrelevant) from files that require closer analysis.

---

### (b) What is drive slack? Explain it according to the purposes of digital forensics. — 3 marks

**Solution**

- Step 1: Define drive slack from "Examining FAT Disks."
- Step 2: Explain its forensic significance.

**Calculations**

Not applicable.

**Final Answer**

Microsoft operating systems allocate disk space for files by **clusters**. This results in **drive slack** — the unused space in a cluster between the end of an active file and the end of the cluster. Drive slack includes **RAM slack and file slack**. NTFS results in much less file slack space than FAT.

**Forensic purpose:** Because a cluster is allocated as a whole unit even when a file doesn't fully use it, leftover data from a previously deleted or overwritten file (or old memory contents in the case of RAM slack) can remain in this unused space. Investigators examine drive slack because it may still contain fragments of deleted files, passwords, or other evidentiary data that the operating system no longer displays through its normal file listing.

---

### (c) Explain different types of digital evidence storage formats. — 4 marks

**Solution**

- Step 1: Refer to "Understanding Storage Formats for Digital Evidence."
- Step 2: Explain each of the three formats with their advantages/disadvantages.

**Calculations**

Not applicable.

**Final Answer**

The lecture sheet lists **three** storage formats for digital evidence:

1. **Raw format** — makes it possible to write bit-stream data to files.
   - Advantages: fast data transfers; can ignore minor data read errors on the source drive; most computer forensics tools can read raw format.
   - Disadvantages: requires as much storage as the original disk/data; tools might not collect marginal (bad) sectors.
2. **Proprietary formats** — offered by most forensic tool vendors.
   - Features: option to compress or not compress image files; can split an image into smaller segmented files; can integrate metadata into the image file.
   - Disadvantages: inability to share an image between different tools; file-size limitation for each segmented volume.
3. **Advanced Forensics Format (AFF)** — developed by Dr. Simson L. Garfinkel of Basis Technology Corporation.
   - Design goals: provide compressed or uncompressed image files; no size restriction for disk-to-image files; provide space in the image file (or segmented files) for metadata; simple, extensible design; open source for multiple platforms/OSs.
   - File extensions: **.afd** for segmented image files, **.afm** for AFF metadata.

---

## Question 6

### (a) What is the necessity of live acquisition? Explain standard procedure for live acquisition. — 4 marks

**Solution**

- Step 1: Refer to "Performing Live Acquisitions."
- Step 2: Explain why live acquisition is necessary.
- Step 3: List the standard steps.

**Calculations**

Not applicable.

**Final Answer**

**Necessity:** Live acquisitions are especially useful when dealing with active network intrusions or attacks. Live acquisitions performed *before* taking a system offline are becoming a necessity because attacks might leave footprints only in running processes or RAM, which are lost once the system is powered down. Note that live acquisitions don't follow typical (static) forensics procedures. The concept of **Order of Volatility (OOV)** — how long a piece of information lasts on a system — underlies why live data must be captured quickly.

**Standard procedure (steps):**
1. Create or download a bootable forensic CD (e.g., Helix, DEFT).
2. Keep a log of all your actions.
3. Send collected information to a network drive if possible.
4. Copy the physical memory (RAM) first.
5. The next step varies depending on the incident being investigated.
6. Get a forensic hash value of all files you recover during the live acquisition.

Tools for capturing RAM mentioned in the lecture sheet include Mantech Memory DD, Win32dd, winen.exe (Guidance Software), and BackTrack 4.

---

### (b) Explain internet abuse and e-mail abuse investigation. — 4 marks

**Solution**

- Step 1: Refer to "Employee Termination Cases" in the lecture sheet.
- Step 2: Explain internet abuse investigation requirements/steps.
- Step 3: Explain email abuse investigation requirements/steps.

**Calculations**

Not applicable.

**Final Answer**

**Internet abuse investigations** — to conduct one you need: the organization's Internet proxy server logs, the suspect computer's IP address, the suspect computer's disk drive, and your preferred computer forensics analysis tool. Recommended steps: use standard forensic analysis techniques and procedures; use appropriate tools to extract all Web page URL information; contact the network firewall administrator to request a proxy server log; compare the data recovered from forensic analysis to the proxy server log; and continue analyzing the computer's disk drive data.

**E-mail abuse investigations** — to conduct one you need: an electronic copy of the offending e-mail containing message header data; e-mail server log records (if available); for e-mail systems that store users' messages on a central server, access to that server; access to the computer to perform forensic analysis on it; and your preferred computer forensics analysis tool. Recommended steps: use standard forensic analysis techniques; obtain an electronic copy of the suspect's and victim's e-mail folder or data; for Web-based e-mail, use tools such as FTK's Internet Keyword Search option to extract all related e-mail address information; and examine header data of all messages of interest to the investigation.

---

### (c) Explain bit stream copy and bit stream image with examples. — 4 marks

**Solution**

- Step 1: Refer to "Determining the Best Acquisition Method."
- Step 2: Distinguish bit-stream disk-to-image from bit-stream disk-to-disk, with tool examples.

**Calculations**

Not applicable.

**Final Answer**

The lecture sheet lists **bit-stream disk-to-image file** and **bit-stream disk-to-disk** as two of the four acquisition methods (the other two being logical disk-to-disk/data and sparse data copy).

- **Bit-stream disk-to-image file:** The most common acquisition method; you can make more than one copy, and each copy is a bit-for-bit replication of the original drive. Example tools: ProDiscover, EnCase, FTK, SMART, Sleuth Kit, X-Ways, iLook.
- **Bit-stream disk-to-disk:** Used when a disk-to-image copy is not possible; the investigator must consider the target disk's geometry configuration. Example tools: EnCase, SafeBack, SnapCopy.

Both methods produce a **bit-stream copy** — an exact, sector-by-sector duplicate of the source media (as opposed to a simple logical file copy) — but the destination differs: an image file in the first case, and a physical disk in the second.

---

## Question 7

### (a) Explain the acquisition procedures for cell phones and mobile devices. — 5 marks

**Solution**

- Step 1: Refer to "Understanding Acquisition Procedures for Cell Phones and Mobile Devices."
- Step 2: List the main concerns and steps.

**Calculations**

Not applicable.

**Final Answer**

Main concerns: loss of power and synchronization with PCs. All mobile devices have volatile memory, so making sure they don't lose power before RAM data can be retrieved is critical. A device attached to a PC via a cable or cradle/docking station should be disconnected from the PC immediately. Depending on the warrant or subpoena, the time of seizure might be relevant.

Because messages might still be received on the device after seizure, the device should be **isolated from incoming signals** using one of:
- A paint can
- The Paraben Wireless StrongHold Bag
- Eight layers of antistatic bags

(Drawback: isolating the device puts it into roaming mode, which accelerates battery drainage.)

In the lab, check: internal memory, SIM card, removable/external memory cards, and system server (the last requires a search warrant or subpoena). Acquisition generally involves two tasks: acting as though you are a PC synchronizing with the device (to download data), and reading the SIM card. Information retrievable from the SIM includes service-related data (SIM/subscriber identifiers), call data, message information, and location information — though if power has been lost, PINs or other access codes may be required to view files.

---

### (b) Describe tasks in investigation of E-mail crime and violations. — 4 marks

**Solution**

- Step 1: Refer to "Investigating E-mail Crimes and Violations."
- Step 2: List the goals and process.

**Calculations**

Not applicable.

**Final Answer**

E-mail investigations are similar to other kinds of investigations, with the goals of: finding who is behind the crime, collecting the evidence, presenting the findings, and building a case. Handling depends on the city, state, or country (e.g., for spam), so investigators should always consult with an attorney. Examples of crimes involving e-mail include narcotics trafficking, extortion, sexual harassment, and child abduction/pornography.

Tasks include: accessing the victim's computer to recover evidence; using the victim's e-mail client to find and copy evidence, access protected or encrypted material, and print e-mails; guiding the victim by phone to open and copy e-mail including headers; and handling deleted e-mails, since servers can often recover deleted e-mails similarly to the deletion of files on a hard drive.

---

### (c) Analyze the function of E-mail forensics tools. — 3 marks

**Solution**

- Step 1: Refer to "Using Specialized E-mail Forensics Tools."
- Step 2: Explain their function and list examples.

**Calculations**

Not applicable.

**Final Answer**

Specialized e-mail forensics tools (e.g., AccessData's Forensic Toolkit (FTK), ProDiscover Basic, FINALeMAIL, Sawmill-GroupWise, DBXtract, Fookes Aid4Mail and MailBag Assistant, Paraben E-Mail Examiner, Ontrack Easy Recovery EmailRepair, R-Tools R-Mail) allow an investigator to find: e-mail database files, personal e-mail files, offline storage files, and log files. Their key advantage is that the investigator does **not** need to know in detail how the underlying e-mail servers and clients work internally. For example, **FINALeMAIL** scans e-mail database files, recovers deleted e-mails, and searches the computer for other files associated with e-mail. **AccessData FTK** can index data on a disk image or entire drive for faster retrieval and integrates dtSearch (which builds a b-tree index of all text data) to recover e-mail from Outlook/Outlook Express.
# Jagannath University — CSE-5210, Digital Forensics and Investigation
## Paper 2: M.Sc. 2nd Semester Final Examination 2025 (Session: Summer 2024, Professional 16th batch)

---

## Question 1

### (a) What do you mean by remote acquisition? Explain the remote acquisition with ProDiscover Basic or EnCase Enterprise. — 5 marks

**Solution / Calculations / Final Answer**

*(Same underlying lecture-sheet content as Paper 1, Q2(a).)*

**Remote acquisition** means connecting remotely to a suspect computer via a network connection and copying data from it, rather than physically removing the drive. Drawbacks: LAN data-transfer speed and routing-table conflicts, difficulty gaining permission to access secure subnets, and heavy traffic causing delays/errors.

With **ProDiscover Investigator**, you can preview a suspect's drive remotely while it's in use, perform a live acquisition, encrypt the connection, copy the suspect's RAM, and use stealth mode. ProDiscover Incident Response adds: capturing volatile system state information, analyzing running processes, locating unseen files/processes, remotely viewing/listening to IP ports, running hash comparisons, and creating a remote hash inventory. The **PDServer remote agent** must be loaded on the suspect machine (via Trusted CD, preinstallation, or pushing it out remotely) and can run in stealth mode. Security features: Password Protection, Encryption, Secure Communication Protocol, Write Protected Trusted Binaries, Digital Signatures.

*(With EnCase Enterprise: remote data acquisition of media/RAM, IDS tool integration, imaging one or more systems, system preview, wide file-system format support, and RAID support for hardware and software.)*

**Final Answer:** As above — remote acquisition allows evidence collection over a network without physically seizing the drive, using tools like ProDiscover (PDServer agent) or EnCase Enterprise.

---

### (b) What is carving or salvaging? How does one repair a damaged file header? — 4 marks

*(Same content as Paper 1, Q4(b).)*

**Final Answer:** Carving/salvaging is recovering all file fragments (from slack/free space) so forensic tools can help reassemble them. To repair a damaged header: use good header samples (each file type has a unique header, e.g., JPEG = FF D8 FF E0 00 10, often with a JFIF string), try opening the file, then recover more pieces if needed, compare the header with a good sample, manually insert the correct hexadecimal values, and test the corrected file.

---

### (c) State the procedure of reconstructing a File Fragment. — 3 marks

*(Same content as Paper 1, Q4(c).)*

**Final Answer:** Locate and export all clusters of the fragmented file → determine the starting and ending cluster numbers for each fragmented group → copy each fragmented group of clusters, in proper sequence, to a recovery file → rebuild the corrupted file's header to make it readable.

---

## Question 2

### (a) Explain and state hardware and software forensics tools. — 4 marks

**Solution**

- Step 1: Refer to "Types of Computer Forensics Tools" (opening of the tools chapter).
- Step 2: Distinguish hardware vs software tools.

**Calculations**

Not applicable.

**Final Answer**

- **Hardware forensic tools** range from single-purpose components to complete computer systems and servers.
- **Software forensic tools** are of two types: command-line applications and GUI applications. They are commonly used to copy data from a suspect's disk drive to an image file.

Both categories perform the five major task categories described elsewhere in the lecture sheet: acquisition, validation and discrimination, extraction, reconstruction, and reporting.

---

### (b) Describe tasks performed by computer forensics tools. — 5 marks

*(Same content as Paper 1, Q3(c).)*

**Final Answer:** Five major categories — **Acquisition** (physical/logical copy, various formats, verification), **Validation and discrimination** (hashing with CRC-32/MD5/SHA, filtering, header analysis), **Extraction** (data viewing, keyword searching, decompressing, carving, decrypting, bookmarking), **Reconstruction** (disk-to-disk, image-to-disk, partition-to-partition, image-to-partition copy), and **Reporting** (log reports, report generator).

---

### (c) Explain the Resilient file system in brief. — 3 marks

**Solution**

- Step 1: Search the entire lecture sheet (all 16 chapters, including the Windows/DOS file systems chapter) for "Resilient File System" / "ReFS."
- Step 2: Report findings.

**Insufficient Information**

The lecture sheet does not provide sufficient information to answer this question. It covers FAT, NTFS, EFS/BitLocker, HFS (Macintosh), and Ext2fs/Ext3fs (Linux) in detail, but it does **not** contain any section on the Resilient File System (ReFS). No definition, features, or comparison to NTFS for ReFS is present anywhere in the 16-chapter lecture sheet, so a complete answer cannot be constructed strictly from this material.

---

## Question 3

### (a) Explain the key certification requirements and guidelines set by the American Society of Crime Laboratory Directors (ASCLD) for a computer-forensics lab. — 5 marks

*(Same content as Paper 1, Q2(b), focused on ASCLD.)*

**Final Answer:** The **ASCLD** offers guidelines for managing a lab, acquiring an official certification, and auditing lab functions and procedures. Under this framework, the lab manager's duties include setting up case-management processes, promoting group consensus, maintaining fiscal responsibility, enforcing ethical standards among staff, planning lab updates, establishing quality-assurance processes, setting production schedules, and estimating caseloads and result timelines. Staff members must maintain knowledge/training in hardware and software, OS and file types, deductive reasoning, technical training, and investigative skills, with work reviewed regularly by the lab manager. The lecture sheet directs labs to check the ASCLD Web site for its online manual and further certification information.

---

### (b) Compare and contrast the three digital-evidence storage formats — raw, proprietary, and Advanced Forensics Format (AFF) — including their advantages and disadvantages. — 4 marks

*(Same content as Paper 1, Q5(c), reframed as a comparison.)*

**Final Answer**

| Format | Advantages | Disadvantages |
|---|---|---|
| **Raw format** | Fast data transfers; can ignore minor data read errors on the source drive; most computer forensics tools can read raw format | Requires as much storage as the original disk/data; tools might not collect marginal (bad) sectors |
| **Proprietary formats** | Option to compress or not; can split image into smaller segmented files; can integrate metadata into the image file | Cannot share an image between different tools; file-size limitation for each segmented volume |
| **Advanced Forensics Format (AFF)** | Provides compressed or uncompressed image files; no size restriction for disk-to-image files; provides space for metadata; simple, extensible design; open source, multi-platform | (Not specified as a disadvantage in the lecture sheet beyond design trade-offs of an open, extensible format) |

AFF (developed by Dr. Simson L. Garfinkel of Basis Technology Corporation) uses **.afd** for segmented image files and **.afm** for AFF metadata.

---

### (c) Describe the challenges and methods for acquiring data from RAID systems. — 3 marks

**Solution**

- Step 1: Refer to "Acquiring RAID Disks."
- Step 2: List concerns and vendor methods.

**Calculations**

Not applicable.

**Final Answer**

**Concerns/challenges:**
- How much data storage is needed?
- What type of RAID is used?
- Do you have the right acquisition tool?
- Can the tool read a forensically copied RAID image?
- Can the tool read split data saves of each RAID disk?
- Older hardware-firmware RAID systems can be a challenge when making an image, and size is the biggest concern since many RAID systems have terabytes of data.

**Methods/vendors:** Technologies Pathways ProDiscover, Guidance Software EnCase, X-Ways Forensics, Runtime Software, R-Tools Technologies. Occasionally a RAID system is too large for a static acquisition, so investigators retrieve only the data relevant to the case using the **sparse or logical acquisition method**.

---

## Question 4

### (a) Explain common data hiding techniques in brief. — 4 marks

**Solution**

- Step 1: Refer to "Addressing Data-hiding Techniques."
- Step 2: List and briefly describe each category.

**Calculations**

Not applicable.

**Final Answer**

The lecture sheet groups data-hiding techniques into three categories:

1. **File manipulation** — hiding via filenames and extensions, or using the hidden file property.
2. **Disk manipulation** — hidden partitions (deleting partition references via a disk editor, then re-creating the links later) and bad clusters (marking free space holding hidden data as a "bad" cluster, common on FAT systems).
3. **Encryption** — bit shifting (shifting bit patterns to alter byte values, making files look like binary executable code, using tools like Hex Workshop) and steganography (Greek for "hidden writing"; hiding small amounts of data inside image or text files, very hard to detect without prior knowledge; tools include S-Tools, DPEnvelope, jpgx, and tte).

---

### (b) What is write blocker? Explain Software-write blocker and hardware-write blocker in brief. — 4 marks

**Solution**

- Step 1: Refer to "Using Acquisition Tools" and related sections on write-blocking.
- Step 2: Distinguish hardware vs. software approaches as described in the lecture sheet.

**Calculations**

Not applicable.

**Final Answer**

A **write blocker** is a device or utility used during acquisition to prevent any data from being written to the suspect's (evidence) drive, so the original media is never altered.

- **Hardware write-blocker:** A physical device connected between the evidence disk and the forensic workstation. The lecture sheet states that acquired data must be protected with a well-tested write-blocking hardware device, and gives an example acquisition procedure: "Connect evidence disk to a write-blocker → Connect target disk to write-blocker → Start FTK Imager → Create Disk Image."
- **Software write-blocker:** Implemented as a utility/feature rather than a physical device — for example, the **Windows XP USB write-protection feature**, which blocks any writing to USB devices by modifying the Windows Registry (back up the Registry, modify it to enable the write-protection feature, and create desktop icons to toggle it). Similarly, forensic Linux boot CDs are configured not to mount, or to mount as read-only, any connected storage media, which "eliminates the need for a [hardware] write-blocker."

---

### (c) Explain the contingency planning for image acquisition. — 4 marks

*(Same content basis as "Contingency Planning for Image Acquisitions.")*

**Final Answer**

Contingency planning for image acquisition means preparing for possible acquisition failures or complications:

- Create a duplicate copy of the evidence image file.
- Make **at least two images** of the digital evidence, using **different tools or techniques** for each.
- Copy the **host protected area** of the disk drive as well — consider a hardware acquisition tool that can access the drive at the BIOS level.
- Be prepared to deal with **encrypted drives**, such as those using the whole-disk-encryption feature available in Windows Vista Ultimate and Enterprise editions.

---

## Question 5

### (a) An employee suspects that his password has been compromised. He changed it two days ago, yet it seems someone has used it again. What might be going on? — 4 marks

**Solution**

- Step 1: Search the lecture sheet for content addressing password compromise/reuse scenarios directly.
- Step 2: Apply the closest relevant lecture-sheet concepts (password recovery/cracking techniques) to reason about the scenario, since no scenario-specific answer exists verbatim in the notes.

**Insufficient Information**

The lecture sheet does not provide a direct, scenario-specific explanation for this situation. It does not discuss password caching, keyloggers, or session-hijacking as causes of repeated password compromise. What is missing is any section explicitly analyzing "why a changed password can still be exploited."

However, using the **closest related concepts actually present** in the lecture sheet (under "Recovering Passwords" / "Examining Encrypted Files"), a partial, lecture-grounded explanation can be offered: the lecture sheet describes password-cracking techniques an attacker could still use even after a password change — **dictionary attack**, **brute-force attack**, and **password guessing based on the suspect's/victim's profile** (using tools such as AccessData PRTK, Advanced Password Recovery Software Toolkit, or John the Ripper, which can build custom dictionaries or profile-based password lists). If the new password is similarly weak or predictable (e.g., based on personal information), the same recovery/cracking techniques that compromised the old password could just as easily compromise the new one — meaning the new password may not have been meaningfully different or complex enough to resist attack.

*For a fully complete answer (e.g., addressing malware/keyloggers or credential caching), material beyond this lecture sheet would be required.*

---

### (b) What is drive slack? Explain it according to the purposes of digital forensics. — 4 marks

*(Same content as Paper 1, Q5(b).)*

**Final Answer:** Drive slack is the unused space in a cluster between the end of an active file and the end of the cluster, arising because Microsoft OSs allocate space by clusters. It includes RAM slack and file slack (NTFS has much less file slack than FAT). Forensically, this leftover space may retain fragments of previously deleted or overwritten data, so investigators examine it for hidden evidence.

---

### (c) Explain different types of digital evidence storage formats. — 4 marks

*(Same content as Paper 1, Q5(c) / this paper Q3(b).)*

**Final Answer:** Raw format, proprietary formats, and Advanced Forensics Format (AFF) — as detailed above in Question 3(b) of this paper.

---

## Question 6

### (a) Define "order of volatility" and explain how it guides your actions during a live acquisition. — 5 marks

**Solution**

- Step 1: Refer to "Performing Live Acquisitions."
- Step 2: Define OOV and connect it to live-acquisition sequencing.

**Calculations**

Not applicable.

**Final Answer**

**Order of volatility (OOV)** is defined in the lecture sheet as **how long a piece of information lasts on a system**. Live acquisitions are especially useful for active network intrusions/attacks, and are increasingly necessary *before* taking a system offline, because attacks might leave footprints only in running processes or RAM — the most volatile data. Live acquisitions do not follow typical (static) forensic procedures.

**How it guides live-acquisition actions:** because RAM and running-process data are the most volatile (lost immediately on power-down), the standard procedure prioritizes capturing them first: create/boot a forensic CD, log all actions, and **copy the physical memory (RAM)** early in the process, before proceeding to the next steps (which vary by incident) and getting a forensic hash of everything recovered. In short, OOV means the investigator must collect the most fragile/short-lived data (RAM, running processes) before anything less volatile (like the hard disk), since delay risks permanently losing that evidence.

---

### (b) List and explain three common e-mail fraud techniques. — 3 marks

**Solution**

- Step 1: Refer to "Exploring the Role of E-mail in Investigations" and the chapter summary.
- Step 2: List the fraud techniques named in the lecture sheet.

**Calculations**

Not applicable.

**Final Answer**

The lecture sheet identifies e-mail fraudsters as using the following techniques:

1. **Phishing** — e-mails typically sent in HTML format, which allows the creation of links to text on a Web page (to deceive users, e.g., into visiting fake sites).
2. **Spoofing** — falsifying the sender/source of an e-mail; spoofing e-mail can be used to commit fraud.
3. **The "419" or Nigerian Scam** — cited in the lecture sheet as one of the most noteworthy e-mail scams, an advance-fee style fraud scheme.

---

### (c) Outline the standard procedure you would follow to perform a live RAM acquisition on a compromised system. — 4 marks

**Solution**

- Step 1: Refer to "Performing a Live Acquisition in Windows."
- Step 2: List the RAM-specific steps and tools.

**Calculations**

Not applicable.

**Final Answer**

Steps (from "Performing Live Acquisitions"):
1. Create or download a bootable forensic CD (e.g., Helix, DEFT).
2. Keep a log of all actions taken.
3. Send collected information to a network drive if possible.
4. **Copy the physical memory (RAM).**
5. Continue with steps that vary depending on the incident being investigated.
6. Obtain a forensic hash value of all files recovered during the live acquisition.

Tools available to capture RAM: **Mantech Memory DD, Win32dd, winen.exe** (from Guidance Software), and **BackTrack 4**.

---

## Question 7

### (a) What is the necessity of live acquisition? Explain standard procedure for live acquisition. — 4 marks

*(Same content as Paper 1, Q6(a).)*

**Final Answer:** Necessary because attacks may leave evidence only in running processes/RAM, which is lost once the system is shut down, and live acquisitions don't follow typical static forensic procedures. Standard procedure: create/download a bootable forensic CD → log all actions → send data to a network drive → copy physical memory (RAM) → proceed with incident-specific next steps → hash all recovered files.

---

### (b) What is validation protocol? Explain digital forensics examination protocol. — 4 marks

**Solution**

- Step 1: Refer to "Using Validation Protocols."
- Step 2: Explain the Computer Forensics Examination Protocol described there.

**Calculations**

Not applicable.

**Final Answer**

A **validation protocol** means you must always verify your results. The lecture sheet's guidance: use at least **two tools** for retrieving/examining and for verification; understand how the tools work; one way to compare results and verify a new tool is by using a disk editor such as Hex Workshop or WinHex, since disk editors, although lacking a flashy interface, are reliable and can access raw data.

**Computer Forensics Examination Protocol:**
1. Perform the investigation with a GUI tool.
2. Verify your results with a disk editor.
3. Compare the hash values obtained with both tools.

---

### (c) Describe certification and training requirements for digital forensics labs. — 4 marks

*(Same content as Paper 1, Q2(b).)*

**Final Answer:** As detailed in Question 2(b) of Paper 1 — ASCLD guidelines, IACIS (CEECS, CFCE), HTCN (Certified Computer Crime Investigator, Certified Computer Forensic Technician), EnCE, ACE, and additional bodies (HTCIA, SANS, CTIN, NTI, Southeast Cybercrime Institute, FLETC, NW3C).
# Jagannath University — CSE-5210, Digital Forensics and Investigation
## Paper 3: M.Sc. 2nd Semester Final Examination 2024 (Session: Winter 2023, Professional 15th batch)

---

## Question 1

### (a) Define computer forensics and explain bit stream copy & bit stream image. — 3 marks

**Solution / Final Answer**

**Computer forensics** involves obtaining and analyzing digital information for use as evidence in civil, criminal, or administrative cases; it investigates data that can be retrieved from a computer's hard disk or other storage media, including data that users have hidden or deleted.

**Bit stream copy and bit stream image** (from "Determining the Best Acquisition Method"):
- **Bit-stream disk-to-image file** — the most common method; you can make more than one copy, and each copy is a bit-for-bit replication of the original drive (tools: ProDiscover, EnCase, FTK, SMART, Sleuth Kit, X-Ways, iLook).
- **Bit-stream disk-to-disk** — used when a disk-to-image copy isn't possible; requires considering the target disk's geometry configuration (tools: EnCase, SafeBack, SnapCopy).

**Calculations:** Not applicable — descriptive/definitional question.

---

### (b) What is computer crime? Why do you need Mini-WinFE Boot CD/DVD or USB drive, explain it in brief. — 4 marks

**Solution**

- Step 1: Search the lecture sheet for "computer crime" and "Mini-WinFE."
- Step 2: Report what is and is not present.

**Final Answer (partial) / Insufficient Information**

The lecture sheet references "An Overview of a Computer Crime," noting that computers can contain information that helps law enforcement determine the chain of events leading to a crime and evidence that can lead to a conviction, and that law enforcement officers should follow proper procedure when acquiring such evidence because digital evidence can be easily altered by an overeager investigator.

However, **the lecture sheet does not provide sufficient information to answer the Mini-WinFE Boot CD/DVD/USB portion of this question.** It discusses other bootable forensic tools (Helix, DEFT, Knoppix-STD, The Auditor) and Linux Live CDs in the context of write-blocking/live acquisition, but Mini-WinFE specifically is not mentioned anywhere in the 16 chapters provided. What is missing: any definition, purpose, or usage procedure for Mini-WinFE.

---

### (c) Explain the ways to determine the best acquisition method. — 5 marks

**Solution**

- Step 1: Refer to "Determining the Best Acquisition Method."
- Step 2: List types and the four methods, plus factors to consider.

**Final Answer**

Types of acquisitions: **static acquisitions** and **live acquisitions**. Four methods:
1. Bit-stream disk-to-image file (most common; multiple copies possible; bit-for-bit replication)
2. Bit-stream disk-to-disk (when disk-to-image isn't possible; consider disk geometry)
3. Logical disk-to-disk or disk-to-disk data (when time is limited; captures only specific files of interest)
4. Sparse data copy of a file or folder (also collects fragments of unallocated/deleted data; useful for large disks, PST/OST mail files, RAID servers)

When choosing a method, consider: the **size of the source disk** (lossless compression may help; use digital signatures for verification), whether an alternative such as **tape backup** is needed for very large drives, and **whether you can retain the disk**.

**Calculations:** Not applicable.

---

## Question 2

### (a) What do you mean by remote acquisition? Explain the remote acquisition with ProDiscover Basic or EnCase Enterprise. — 4 marks

*(Same content as Paper 1, Q2(a).)*

**Final Answer:** Remote acquisition = connecting to a suspect computer over a network to copy data without physically seizing the drive. With ProDiscover Investigator: preview drive remotely, live acquisition, encrypted connection, RAM copy, stealth mode, plus PDServer remote agent features (as detailed in Paper 1 Q2(a)). With EnCase Enterprise: remote media/RAM acquisition, IDS integration, multi-system imaging/preview, wide file-format and RAID support.

---

### (b) What is curving or salvaging? How does repair damaged file header? — 4 marks

*(Same content as Paper 1, Q4(b).)*

**Final Answer:** Carving/salvaging recovers all file fragments from slack/free space so forensic tools can reassemble them. Header repair: use good header samples, try opening the file, recover more pieces if needed, compare header with a good sample, manually insert correct hex values, then test.

---

### (c) Explain the purpose of a virtual machine for computer forensics and investigation. — 3 marks

*(Same content as Paper 1, Q2(c).)*

**Final Answer:** Investigators must detect VMs installed on a host, acquire an image of a VM, and use VMs to examine malware (VirtualBox, Virtual PC, Parallels, VMware). Check whether VMs are loaded on a host and check the Registry for install/uninstall clues.

---

## Question 3

### (a) Explain the roles of Windows Registry for computer forensics and investigation. — 4 marks

**Solution**

- Step 1: Refer to "Understanding the Windows Registry" and the ch06 summary.
- Step 2: Explain its investigative value.

**Final Answer**

The **Registry** is a database that stores hardware and software configuration information, network connections, user preferences, and setup information. For investigative purposes, **the Registry can contain valuable evidence**. To view it, investigators can use Regedit (Windows 9x) or Regedt32 (Windows 2000/XP); ProDiscover Basic can also be used to extract System.dat and User.dat from an image file.

Per the chapter summary, the **Windows Registry keeps a record of attached hardware, user preferences, network connections, and installed software** — this is directly useful to an investigator trying to establish what devices were connected, what software was installed/used, and what network activity occurred on a suspect machine. It is also useful for detecting whether virtual machine software has been installed or uninstalled.

**Calculations:** Not applicable.

---

### (b) Describe tasks perform by computer forensics tools. — 5 marks

*(Same content as Paper 1, Q3(c) / Paper 2, Q2(b).)*

**Final Answer:** Five categories — Acquisition, Validation and discrimination, Extraction, Reconstruction, Reporting (with subfunctions as detailed previously).

---

### (c) Explain Resilient file system in brief. — 3 marks

*(Same as Paper 2, Q2(c).)*

**Insufficient Information:** The lecture sheet does not cover the Resilient File System (ReFS) anywhere in its 16 chapters; only FAT, NTFS, HFS, and Ext2fs/Ext3fs are discussed.

---

## Question 4

### (a) Explain common data hiding techniques in brief. — 4 marks

*(Same content as Paper 2, Q4(a).)*

**Final Answer:** File manipulation (filenames/extensions, hidden property), disk manipulation (hidden partitions, bad clusters), and encryption (bit shifting, steganography) — as detailed in Paper 2 Question 4(a).

---

### (b) What is write blocker? Explain Software-write blocker and hardware-write blocker in brief. — 4 marks

*(Same content as Paper 2, Q4(b).)*

**Final Answer:** A write blocker prevents writes to the evidence drive during acquisition. Hardware write-blocker = a physical device connected between evidence disk and workstation. Software write-blocker = a utility/registry-based method (e.g., Windows XP USB write-protection feature, or forensic Linux Live CDs mounting drives read-only).

---

### (c) Write down the steps for reconstructing file fragments. — 4 marks

*(Same content as Paper 1, Q4(c).)*

**Final Answer:** Locate and export all clusters of the fragmented file → determine starting/ending cluster numbers for each fragment group → copy fragments in proper sequence to a recovery file → rebuild the corrupted file's header.

---

## Question 5

### (a) An employee suspects that his password has been compromised. He changed it two days ago, yet it seems someone has used it again. What might be going on? — 4 marks

*(Same content/insufficiency note as Paper 2, Q5(a).)*

**Insufficient Information (partial answer provided):** The lecture sheet has no scenario-specific coverage, but using its password-recovery content (dictionary attack, brute-force attack, profile-based password guessing, tools like PRTK/John the Ripper), a plausible explanation grounded in the lecture sheet is that the new password may be similarly weak/predictable and vulnerable to the same cracking techniques that compromised the original password.

---

### (b) What is drive slack? Explain it according to the purposes of digital forensics. — 4 marks

*(Same content as Paper 1, Q5(b).)*

**Final Answer:** Drive slack = unused space in a cluster between the end of an active file and the end of the cluster (includes RAM slack and file slack; NTFS has much less than FAT). Forensically significant because it may retain remnants of previously deleted/overwritten data.

---

### (c) Explain different types of digital evidence storage formats. — 4 marks

*(Same content as Paper 1, Q5(c).)*

**Final Answer:** Raw format, Proprietary formats, and Advanced Forensics Format (AFF) — with their respective advantages/disadvantages as detailed earlier.

---

## Question 6

### (a) What is the necessity of live acquisition? Explain standard procedure for live acquisition. — 4 marks

*(Same content as Paper 1, Q6(a).)*

**Final Answer:** Necessary because attack evidence may exist only in RAM/running processes, lost on shutdown. Steps: create/download bootable forensic CD → log actions → send data to network drive → copy RAM → continue with incident-specific steps → hash all recovered files.

---

### (b) What is validation protocol? Explain digital forensics examination protocol. — 4 marks

*(Same content as Paper 2, Q7(b).)*

**Final Answer:** Validation protocol = always verify results using at least two tools (one for retrieval/examination, one for verification), understanding how each tool works, and cross-checking with a disk editor (Hex Workshop/WinHex). Computer Forensics Examination Protocol: perform investigation with a GUI tool → verify results with a disk editor → compare hash values from both tools.

---

### (c) Describe certification and training requirements for digital forensics labs. — 4 marks

*(Same content as Paper 1, Q2(b).)*

**Final Answer:** As detailed earlier — ASCLD guidelines; IACIS (CEECS, CFCE); HTCN certifications; EnCE; ACE; plus HTCIA, SANS, CTIN, NTI, Southeast Cybercrime Institute, FLETC, NW3C.

---

## Question 7

### (a) What procedural steps should a digital forensic investigator follow when analyzing emails? — 4 marks

**Solution**

- Step 1: Refer to "Examining E-mail Messages" and "Viewing/Examining E-mail Headers."
- Step 2: List the procedural steps in order.

**Final Answer**

1. **Access the victim's computer** to recover evidence (or guide the victim on the phone to open and copy the e-mail, including headers).
2. **Copy and print the e-mail** involved in the crime or policy violation before starting the investigation; the message may also be forwarded as an attachment to another address. In many GUI e-mail programs, this can be done by dragging the e-mail to a storage medium or saving it elsewhere.
3. **Learn how to find and view the e-mail header** for the specific client type (GUI, command-line, or Web-based), then copy and paste the header into a text document so it can be read with a text editor. (The lecture sheet gives client-specific steps, e.g., Outlook: Message Options dialog → copy headers; Outlook Express: Properties → Message Source; Novell Evolution: View → All Message Headers; Hotmail: Options → Mail Display Settings → Advanced; Yahoo: Mail Options → General Preferences → Show All headers.)
4. **Examine the e-mail header** to gather supporting evidence and track the suspect — return path, recipient's e-mail address, type of sending e-mail service, IP address of the sending server, name of the e-mail server, unique message number, date/time sent, and attachment file information.
5. **Examine additional e-mail files** (e.g., Outlook's .pst/.ost files, an electronic address book, or saved Web pages for Web-based e-mail).
6. If necessary, contact the network e-mail administrator and check **server logs** (UNIX: /etc/sendmail.cf, /etc/syslog.conf, /var/log/maillog; Microsoft Exchange: .edb/.stm database files, transaction logs, tracking.log).

**Calculations:** Not applicable.

---

### (b) What are the critical factors to consider when conducting an email investigation in digital forensics? — 4 marks

**Final Answer**

Based on "Examining E-mail Headers" and "Investigating E-mail Crimes and Violations," the critical factors are:

- **Return path, recipient's e-mail address, and sending server's IP address** — needed to trace the true origin of the message.
- **Type of sending e-mail service and name of the e-mail server** — since client/server architecture and naming conventions (corporate vs. public accounts) affect how easily an e-mail can be traced.
- **Unique message number and date/time sent** — for establishing a timeline of events.
- **Attachment file information** — attachments may themselves contain evidence.
- **Legal/jurisdictional factors** — because handling depends on the city, state, or country (e.g., for spam), an attorney should always be consulted.
- **Whether messages have been deleted** — since e-mail servers can often recover deleted e-mails similarly to file deletion on a hard drive.

**Calculations:** Not applicable.

---

### (c) How can forensic investigators handle the obstacles presented by encrypted emails and signed messages in email investigations? — 4 marks

**Solution**

- Step 1: Search the lecture sheet specifically for "encrypted e-mail" or "signed message" handling.
- Step 2: Report findings and connect to the closest related lecture-sheet material.

**Insufficient Information**

The lecture sheet does not provide sufficient information to answer this question in full. The e-mail investigations chapter does not discuss encrypted or digitally signed e-mail messages, or techniques specific to overcoming e-mail encryption/signatures.

What is available in the lecture sheet is the **general** treatment of encrypted files under "Examining Encrypted Files" and "Recovering Passwords" (in the data-hiding/analysis chapter): recovering encrypted data without a password can rely on **key escrow** (designed to recover encrypted data if a user forgets a passphrase or the user key is corrupted), **cracking the password** using expert techniques and powerful computers, or **persuading the suspect to reveal the password**. Password-recovery techniques listed include dictionary attacks, brute-force attacks, and profile-based password guessing, using tools such as AccessData PRTK and John the Ripper.

These general techniques could, by extension, be applied to an encrypted e-mail attachment or message body, but the lecture sheet does not specifically address e-mail encryption/digital signatures, so a complete, targeted answer cannot be given from this source alone.
# Jagannath University — CSE-5210, Digital Forensics and Investigation
## Paper 4: M.Sc.(Professional) 2nd Semester Final Examination 2024 (Admission Session: Winter 2023, 14th batch) — Full Marks 50

---

## Question 1

### (a) Define computer forensics, network forensics and data recovery. — 3 marks

**Solution / Final Answer**

From "Computer Forensics Versus Other Related Disciplines":

- **Computer forensics** — involves obtaining and analyzing digital information as evidence in civil, criminal, or administrative cases; it investigates data that can be retrieved from a computer's hard disk or other storage media, including the task of recovering data that users have hidden or deleted and using it as evidence (inculpatory or exculpatory).
- **Network forensics** — yields information about how a perpetrator or an attacker gained access to a network.
- **Data recovery** — recovering information that was deleted by mistake or lost during a power surge or server crash; typically, you already know what you're looking for.

**Calculations:** Not applicable.

---

### (b) What is digital evidence? Assess general tasks that investigator performances with digital evidences. — 3 marks

**Solution / Final Answer**

From "Identifying Digital Evidence": **Digital evidence** can be any information stored or transmitted in digital form; U.S. courts accept digital evidence as physical evidence since digital data is a tangible object (some courts require it to be printed out for presentation).

**General tasks investigators perform when working with digital evidence:**
- Identify digital information or artifacts that can be used as evidence.
- Collect, preserve, and document the evidence.
- Analyze, identify, and organize the evidence.
- Rebuild the evidence, or repeat a situation, to verify that results can be reproduced reliably.

Collecting computers and processing a criminal or incident scene must be done systematically.

**Calculations:** Not applicable.

---

### (c) Explain the ways to determine the best acquisition method.

*(Same content as Paper 3, Q1(c).)*

**Final Answer:** Types: static and live acquisitions. Four methods: bit-stream disk-to-image, bit-stream disk-to-disk, logical/sparse disk-to-disk, sparse data copy of a file/folder. Considerations: source disk size (compression, digital signatures), tape backup for large drives, and whether the disk can be retained.

---

## Question 2

### (a) What do you mean by remote acquisition? Explain the remote acquisition with Prodiscover basic or Encase Enterprise. — 4 marks

*(Same content as Paper 1, Q2(a).)*

**Final Answer:** As detailed in Paper 1, Question 2(a) — remote network connection to copy suspect data, ProDiscover Investigator features and PDServer agent, or EnCase Enterprise's remote acquisition features.

---

### (b) What do you understand by EFS and bit-locker? Explain whole disk encryption. — 4 marks

**Solution**

- Step 1: Refer to "NTFS Encrypting File System (EFS)" and "Understanding Whole Disk Encryption" / "Examining Microsoft BitLocker."
- Step 2: Explain each term and whole-disk encryption in detail.

**Final Answer**

- **EFS (Encrypting File System)** — introduced with Windows 2000; implements a public-key/private-key method of encrypting files, folders, or disk volumes. When used in Windows Vista Business Edition or higher, XP Professional, or 2000, a recovery certificate is generated and sent to the local Windows administrator account. Users can apply EFS to files on local workstations or a remote server. Windows administrators can recover a key through Windows or via MS-DOS commands (Cipher, Copy, Efsrecvr — used to decrypt EFS files).
- **BitLocker** — available only with Vista Enterprise and Ultimate editions. Requirements: a computer capable of running Windows Vista, a TPM microchip (v1.2 or newer), a BIOS compliant with the Trusted Computing Group (TCG), two NTFS partitions, and the BIOS configured to boot the hard drive first before other bootable peripherals.
- **Whole disk encryption:** Motivated by concern over loss of personal identity information (PII) and trade secrets from stolen laptops/handheld devices, software vendors provide whole disk encryption. Features: preboot authentication, full or partial disk encryption with secure hibernation, advanced encryption algorithms, key management functions, and a Trusted Platform Module (TPM) microchip to generate encryption keys and authenticate logins. Whole disk encryption tools encrypt each sector of a drive separately, often including the boot sector (to prevent bypassing the secured partition). To examine an encrypted drive, it must first be decrypted using a vendor-specific program. Third-party whole disk encryption tools mentioned: PGP Whole Disk Encryption, Voltage SecureDisk, Utimaco SafeGuard Easy, Jetico BestCrypt Volume Encryption, SoftWinter Sentry 2020; open-source tools: TrueCrypt, CrossCrypt, FreeOTFE.

**Calculations:** Not applicable.

---

### (c) Explain the purpose of a virtual machine for computer forensics and investigation. — 2 marks

*(Same content as Paper 1, Q2(c).)*

**Final Answer:** Detect installed VMs on a host, acquire a VM image, and use VMs to examine malware; check the Registry for VM install/uninstall evidence.

---

## Question 3

### (a) Explain bit stream copy and bit stream image with examples. — 3 marks

*(Same content as Paper 3, Q1(a) bitstream portion.)*

**Final Answer:** Bit-stream disk-to-image file (most common; bit-for-bit copy into an image file; e.g., ProDiscover, EnCase, FTK) and bit-stream disk-to-disk (used when imaging isn't possible; e.g., EnCase, SafeBack, SnapCopy).

---

### (b) Describe tasks perform by computer forensics tools. — 4 marks

*(Same content as Paper 1, Q3(c).)*

**Final Answer:** Acquisition, Validation and discrimination, Extraction, Reconstruction, Reporting — with subfunctions as detailed in Paper 1, Question 3(c).

---

### (c) Explain the roles of Windows Registry for computer forensics and investigation. — 3 marks

*(Same content as Paper 3, Q3(a).)*

**Final Answer:** The Registry stores hardware/software configuration, network connections, user preferences, and setup information, and can contain valuable evidence; it keeps a record of attached hardware, user preferences, network connections, and installed software, and is used (via Regedit/Regedt32 or ProDiscover Basic to extract System.dat/User.dat) to detect VM installation and reconstruct system usage history.

---

## Question 4

### (a) Explain common data hiding techniques in brief. — 4 marks

*(Same content as Paper 2, Q4(a).)*

**Final Answer:** File manipulation, disk manipulation (hidden partitions, bad clusters), and encryption (bit shifting, steganography) — as detailed previously.

---

### (b) What is curving or salvaging? How does repair damaged file header? — 3 marks

*(Same content as Paper 1, Q4(b).)*

**Final Answer:** Carving/salvaging recovers file fragments from slack/free space; header repair uses good header samples, comparing and manually correcting hex values, then testing the file.

---

### (c) Write down the steps for reconstructing file fragments. — 3 marks

*(Same content as Paper 1, Q4(c).)*

**Final Answer:** Locate/export all fragment clusters → determine start/end cluster numbers → copy fragments in sequence to a recovery file → rebuild the file header.

---

## Question 5

### (a) What do you mean by validating forensics data? Explain validating with hexadecimal editors. — 4 marks

*(Same content as Paper 1, Q5(a).)*

**Final Answer:** Validating forensic data means ensuring data integrity for court presentation. Hex editors (e.g., Hex Workshop) can hash specific files/sectors with MD5/SHA-1; AccessData's KFF database filters known files by comparing hash values.

---

### (b) What is drive slack? Explain it according to the purposes of digital forensics. — 3 marks

*(Same content as Paper 1, Q5(b).)*

**Final Answer:** Unused space in a cluster between the end of an active file and the end of the cluster (RAM slack + file slack); forensically significant as it may retain remnants of previously stored data.

---

### (c) Explain different types of digital evidence storage formats. — 3 marks

*(Same content as Paper 1, Q5(c).)*

**Final Answer:** Raw format, proprietary formats, Advanced Forensics Format (AFF) — with their respective features/advantages/disadvantages.

---

## Question 6

### (a) Explain the concept of hashing in digital forensics. How are hash values used to verify the integrity of acquired data, and what role do they play in the forensic examination process? — 5 marks

**Solution**

- Step 1: Refer to "Obtaining a Digital Hash" and "Validating Data Acquisitions."
- Step 2: Explain hashing concept, algorithms, the three forensic-hash rules, and their role in the examination process.

**Final Answer**

Hashing is a mathematical process that converts a file (or disk/sector) into a fixed hexadecimal code value called a **hash value** or digital hash — validating forensic data via hashing is one of the most critical aspects of computer forensics, since it is essential for presenting evidence in court.

Algorithms covered in the lecture sheet:
- **CRC-32 (Cyclic Redundancy Check)** — determines whether a file's contents have changed, but is not considered a forensic hashing algorithm.
- **MD5 (Message Digest 5)** — translates a file into a hexadecimal hash value; if even a single bit/byte changes, the hash changes.
- **SHA-1 (Secure Hash Algorithm v1)** — a newer algorithm developed by NIST.

**Three rules for forensic hashes:** (1) you can't predict the hash value of a file/device; (2) no two hash values can be the same; (3) if anything changes in the file/device, the hash value must change.

**Role in verifying integrity:** At acquisition, the original evidence is hashed, and the resulting hash value is compared against the hash of the forensic image/copy. If the two hash values match, the copy is proven to be an unaltered, bit-for-bit duplicate. Any later change to the file or device would change the hash value, immediately revealing tampering. In the **validation** stage of tools' tasks (validation and discrimination), hashing (CRC-32, MD5, SHA) and filtering (e.g., against the National Software Reference Library, NSRL, or AccessData's Known File Filter, KFF) rely on hash comparisons to both prove data integrity and to sort/discriminate known files from files that require analysis. This is why hashing underlies the **Computer Forensics Examination Protocol** (perform investigation with a GUI tool → verify with a disk editor → compare hash values from both tools) used to validate results throughout an investigation.

**Calculations:** Not applicable — no numeric hash is provided in the lecture sheet to compute step by step; the answer is conceptual, based on the properties of hash functions described above.

---

### (b) Describe the role of machine learning and artificial intelligence in modern computer forensics tools. How do these technologies enhance digital investigations, and what challenges do they present? — 5 marks

**Solution**

- Step 1: Search the entire lecture sheet for "machine learning" and "artificial intelligence."
- Step 2: Report findings.

**Insufficient Information**

The lecture sheet does not provide sufficient information to answer this question. It is based on the "Guide to Computer Forensics and Investigations" (4th Edition), which covers acquisition, validation, extraction, reconstruction, and reporting tools such as ProDiscover, EnCase, FTK, Hex Workshop, and various OS/file-system analysis techniques — but it does not discuss machine learning or artificial intelligence anywhere in its 16 chapters. What is missing: any description of ML/AI-based tool features, their benefits for digital investigations, or the associated challenges (e.g., explainability, chain-of-custody concerns, false positives), which would need to be sourced from more recent material outside this lecture sheet.

---

## Question 7

### (a) Describe the steps involved in conducting an email investigation in digital forensics. Outline the key considerations at each stage. — 6 marks

*(Same content basis as Paper 3, Q7(a) and Q7(b), combined and expanded.)*

**Final Answer**

**Step 1 — Access and preserve the evidence:** Access the victim's computer (or guide the victim by phone) to recover the e-mail evidence. *Key consideration:* legal authority/consent to access the account, and preserving message headers along with the body.

**Step 2 — Copy and print the e-mail:** Copy and print the e-mail involved in the crime/policy violation before starting the investigation; it may also be forwarded as an attachment. *Key consideration:* maintain an unaltered copy alongside the working copy.

**Step 3 — View and extract the e-mail header:** Learn the client-specific method to expose full headers (GUI, command-line, or Web-based clients each differ — e.g., Outlook's Message Options dialog, Outlook Express's Message Source, Yahoo's "Show All headers"), then copy/paste into a text editor. *Key consideration:* headers contain unique identifying numbers, the sending server's IP address, and the sending time.

**Step 4 — Examine the header for tracing information:** Extract the return path, recipient's address, sending service type, sending server IP, e-mail server name, unique message number, date/time sent, and attachment information. *Key consideration:* this is the primary way to trace the true origin of a spoofed or anonymous message.

**Step 5 — Examine additional e-mail files:** Check client-side files (e.g., Outlook's .pst/.ost), address books, or saved Web pages for Web-based mail. *Key consideration:* deleted e-mails can often still be recovered similarly to deleted files on a disk.

**Step 6 — Check e-mail server logs, if available:** For UNIX (sendmail.cf, syslog.conf, /var/log/maillog) or Microsoft Exchange (.edb/.stm database files, transaction logs, tracking.log). *Key consideration:* contact the network e-mail administrator as soon as possible, since servers can recover deleted e-mail.

**Step 7 — Use specialized e-mail forensics tools:** FTK, ProDiscover Basic, FINALeMAIL, etc., to find e-mail database files, personal e-mail files, offline storage files, and logs without needing to know the underlying server/client architecture in detail.

**Calculations:** Not applicable.

---

### (b) Evaluate the role of email encryption and digital signatures in email investigations. How do these security measures impact the forensic analysis of email communications, and what techniques can be used to overcome encryption barriers? — 4 marks

**Solution**

- Step 1: Search the lecture sheet for "e-mail encryption" and "digital signature" as investigation topics.
- Step 2: Report findings and connect to the closest general lecture-sheet material on encryption.

**Insufficient Information**

The lecture sheet's e-mail investigations chapter does not discuss e-mail encryption or digital signatures, or their specific impact on forensic analysis of e-mail. This is missing from the material provided.

The closest related content is the **general** treatment of encrypted files (in the data-hiding/analysis chapter, "Examining Encrypted Files" and "Recovering Passwords"), which could be applied by extension: recovering encrypted data without the password can use **key escrow** (recovering encrypted data if a passphrase is forgotten or the user key is corrupted), **cracking the password** (using expert techniques/powerful computers), or **persuading the suspect to reveal the password**; password-recovery techniques include dictionary attacks, brute-force attacks, and profile-based password guessing (tools: AccessData PRTK, John the Ripper). Because the lecture sheet does not specifically discuss e-mail encryption/digital signatures, a fully targeted answer cannot be constructed from this source alone.
# Jagannath University — CSE-5210, Digital Forensics and Investigation
## Paper 5: M.Sc.(Professional) 2nd Semester Final Examination 2023 (Session: Winter 2023, 13th batch) — Full Marks 50

---

## Question 1

### (a) Explain digital forensics and investigations in brief. — 3 marks

**Final Answer**

**Computer/digital forensics** involves obtaining and analyzing digital information as evidence in civil, criminal, or administrative cases. It investigates data retrievable from a computer's hard disk or other storage media, including data that users have hidden or deleted, using it as evidence that can be inculpatory or exculpatory. A **computer investigation** follows a systematic approach: assessing the case, planning the investigation, securing evidence, analyzing/recovering digital evidence, and completing/critiquing the case report — always maintaining a chain of custody for the evidence.

**Calculations:** Not applicable.

---

### (b) What is digital evidence? Assess general tasks that investigator performances with digital evidences. — 3 marks

*(Same content as Paper 4, Q1(b).)*

**Final Answer:** Digital evidence is any information stored or transmitted in digital form, accepted by U.S. courts as physical evidence. General investigator tasks: identify digital information/artifacts as evidence; collect, preserve, and document evidence; analyze, identify, and organize evidence; rebuild evidence or repeat a situation to verify reproducibility of results.

---

### (c) Explain the ways to determine the best acquisition method. — 4 marks

*(Same content as Paper 3, Q1(c).)*

**Final Answer:** Static vs. live acquisitions; four methods (bit-stream disk-to-image, bit-stream disk-to-disk, logical/sparse disk-to-disk, sparse data copy); considerations of source-disk size, tape backup for large drives, and disk retainability.

---

## Question 2

### (a) You are presenting in a Digital Forensics conference a session titled: "Essential Features in Forensics Tools." Part of your presentation involves Extraction. — 5 marks
#### i. Discuss the need for Extraction in computer forensics
#### ii. List any two sub-functions of Extraction.

**Solution**

- Step 1: Refer to "Tasks Performed by Computer Forensics Tools" → Extraction.
- Step 2: Explain the need, then list two subfunctions.

**Final Answer**

**i. Need for Extraction:** Extraction is the **recovery task** in a computing investigation. It is considered the **most demanding of all tasks to master**, because recovering data is the very first step in analyzing an investigation's data — without successful extraction, no later analysis, reconstruction, or reporting is possible. Extraction also has to deal with encrypted files and systems, which the lecture sheet identifies as a problem from an investigation perspective; many password-recovery tools generate potential password lists for a dictionary attack, and if that fails a brute-force attack can be run.

**ii. Two sub-functions of Extraction** (any two from the list of six): **Data viewing** and **Keyword searching** (others listed: decompressing, carving, decrypting, bookmarking). Keyword searching in particular speeds up analysis for investigators.

**Calculations:** Not applicable.

---

### (b) Illustrate in detail how Substitution works in Steganography. Give a clear example. — 5 marks

**Solution**

- Step 1: Search the lecture sheet for "Steganography" and any mention of a "Substitution" technique.
- Step 2: Report what general steganography content exists, and flag the missing detail.

**Insufficient Information**

The lecture sheet does not provide sufficient information to answer this question in full. It defines steganography only in general terms, under "Using Steganography to Hide Data": Steganography is Greek for "hidden writing." Steganography tools were originally created to protect copyrighted material by inserting digital watermarks into a file. A suspect can hide information inside image or text document files; most steganography programs can insert only small amounts of data into a file, and it is very hard to spot without prior knowledge. Tools mentioned: S-Tools, DPEnvelope, jpgx, and tte.

However, **the lecture sheet does not describe a specific "Substitution" technique or method** (such as least-significant-bit substitution) or walk through a worked numeric/bitwise example of how data bits replace image data bits. What is missing: the mechanism of how substitution steganography selects and replaces bits (e.g., in the least significant bits of pixel data) and a concrete illustrative example, which would need to be sourced from material beyond this lecture sheet.

---

## Question 3

### (a) Explain bit stream copy and bit stream image with examples. — 3 marks

*(Same content as Paper 3, Q1(a).)*

**Final Answer:** Bit-stream disk-to-image file (ProDiscover, EnCase, FTK, SMART, Sleuth Kit, X-Ways, iLook) and bit-stream disk-to-disk (EnCase, SafeBack, SnapCopy) — both are bit-for-bit replications, differing only in destination (image file vs. physical disk).

---

### (b) Describe tasks perform by computer forensics tools. — 4 marks

*(Same content as Paper 1, Q3(c).)*

**Final Answer:** Acquisition, Validation and discrimination, Extraction, Reconstruction, Reporting.

---

### (c) Explain developing standard procedure for network forensics. — 3 marks

**Solution**

- Step 1: Refer to "Developing Standard Procedures for Network Forensics."
- Step 2: List the steps.

**Final Answer**

Network forensics is a long, tedious process. Standard procedure:
- Always use a standard installation image for systems on a network.
- Close any way in after an attack.
- Attempt to retrieve all volatile data.
- Acquire all compromised drives.
- Compare files on the forensic image to the original installation image.

Additionally: work from the image to find what has changed (computer forensics) and restore drives to understand the attack (network forensics); work on an isolated system to prevent malware from affecting other systems; and there is an opportunity to load the image as a VM for analysis.

**Calculations:** Not applicable.

---

## Question 4

### (a) Explain common data hiding techniques in brief. — 4 marks

*(Same content as Paper 2, Q4(a).)*

**Final Answer:** File manipulation, disk manipulation (hidden partitions, bad clusters), encryption (bit shifting, steganography).

---

### (b) What is curving or salvaging? How does repair damaged file header? — 3 marks

*(Same content as Paper 1, Q4(b).)*

**Final Answer:** Carving/salvaging recovers file fragments from slack/free space; header repair uses good header samples and manual hex correction, then testing.

---

### (c) Write down the steps for reconstructing file fragments. — 3 marks

*(Same content as Paper 1, Q4(c).)*

**Final Answer:** Locate/export fragments → determine start/end cluster numbers → copy in sequence to a recovery file → rebuild the header.

---

## Question 5

### (a) What do you mean by validating forensics data? Explain validating with hexadecimal editors. — 4 marks

*(Same content as Paper 1, Q5(a).)*

**Final Answer:** Validating forensic data ensures data integrity for court presentation. Hexadecimal editors like Hex Workshop hash specific files/sectors (MD5, SHA-1); AccessData's KFF filters known files via hash comparison.

---

### (b) What is drive slack? Explain it according to the purposes of digital forensics. — 3 marks

*(Same content as Paper 1, Q5(b).)*

**Final Answer:** Drive slack = unused space in a cluster between an active file's end and the cluster's end (RAM slack + file slack); forensically significant since it can retain remnants of previously stored data.

---

### (c) Explain different types of digital evidence storage formats. — 3 marks

*(Same content as Paper 1, Q5(c).)*

**Final Answer:** Raw format, proprietary formats, and Advanced Forensics Format (AFF), with their respective advantages/disadvantages as detailed earlier.

---

## Question 6

### (a) Organizations may use RAID disks to store data. Compare and contrast RAID 0 and RAID 1. — 7 marks

**Solution**

- Step 1: Refer to "Understanding RAID."
- Step 2: Compare and contrast RAID 0 and RAID 1 directly.

**Final Answer**

| Aspect | RAID 0 | RAID 1 |
|---|---|---|
| Purpose | Provides rapid access and increased storage | Designed for data recovery |
| Redundancy | Lacks redundancy | Provides redundancy (mirroring) |
| Cost | Less expensive | More expensive than RAID 0 |
| Data safety | Lower — no redundancy means a single disk failure can lose data | Higher — designed specifically for data recovery |

Both are part of the general RAID definition: a **Redundant Array of Independent (formerly "Inexpensive") Disks** — a computer configuration involving two or more disks, originally developed as a data-redundancy measure. RAID 0 sacrifices redundancy for speed and capacity, while RAID 1 sacrifices cost efficiency for redundancy/recoverability.

**Calculations:** Not applicable — this is a conceptual comparison; the lecture sheet gives no numeric formulas for RAID capacity or performance to compute.

---

### (b) Describe the RAID acquisition methods. — 3 marks

*(Same content as Paper 2, Q3(c).)*

**Final Answer:** Concerns: data storage size needed, RAID type used, whether the tool can read a forensically copied RAID image or split RAID disk data, and challenges with older hardware-firmware RAID systems. Vendors offering RAID acquisition: Technologies Pathways ProDiscover, Guidance Software EnCase, X-Ways Forensics, Runtime Software, R-Tools Technologies. When a RAID system is too large for static acquisition, use the **sparse or logical acquisition method** to retrieve only relevant data.

---

## Question 7

### (a) Explain the acquisition procedures for cell phones and mobile devices. — 3 marks

*(Same content as Paper 1, Q7(a), condensed.)*

**Final Answer:** Main concerns: loss of power and PC synchronization (all mobile devices have volatile memory). Disconnect the device from any cable/cradle immediately; isolate it from incoming signals (paint can, Paraben Wireless StrongHold Bag, or eight layers of antistatic bags — noting this accelerates battery drain via roaming mode). Check internal memory, SIM card, removable memory, and system servers (last requires a warrant). Acquisition = synchronizing with the device to download data, plus reading the SIM card.

---

### (b) Explain some mobile forensics tools in brief. — 2 marks

**Solution**

- Step 1: Refer to "Mobile Forensics Tools."
- Step 2: List and briefly describe tools.

**Final Answer**

- **Paraben Software Device Seizure Toolbox** — contains cables, SIM card readers, and more.
- **Data Pilot** — similar to Paraben's toolbox.
- **BitPim** — can view data on many phones, but is not intended for forensics use.
- **MOBILedit!** — has a built-in write-blocker.
- **SIMCon** — reads files on SIM cards, recovers deleted text messages, and archives files with MD5 and SHA-1 hashes.

**Calculations:** Not applicable.

---

### (c) Describe tasks in investigation of E-mail crime and violations. — 3 marks

*(Same content as Paper 1, Q7(b).)*

**Final Answer:** Goals — find who is behind the crime, collect the evidence, present findings, build a case. Tasks — access the victim's computer, use the e-mail client to find/copy evidence and access protected/encrypted material, print e-mails, guide victims by phone, and recover deleted e-mails (servers can often recover them, similar to file deletion recovery).

---

### (d) Analyze the function of E-mail forensics tools. — 2 marks

*(Same content as Paper 1, Q7(c).)*

**Final Answer:** Specialized tools (FTK, ProDiscover Basic, FINALeMAIL, Sawmill-GroupWise, DBXtract, Aid4Mail/MailBag Assistant, Paraben E-Mail Examiner, Ontrack EmailRepair, R-Tools R-Mail) let investigators find e-mail database files, personal e-mail files, offline storage files, and logs, without needing detailed knowledge of the underlying servers/clients. FINALeMAIL, for example, scans e-mail databases, recovers deleted e-mails, and finds associated files.
# Jagannath University — CSE-520, Digital Forensics and Investigation
## Paper 6: M.Sc. in CSE (Professional Program), 2nd Semester Final Examination 2022 (Session: Winter 2022, 11th batch)

---

## Question 1

### (a) What is digital evidence? Assess general tasks investigators performance with digital evidence. — 4 marks

*(Same content as Paper 4, Q1(b).)*

**Final Answer:** Digital evidence is any information stored or transmitted in digital form, treated by U.S. courts as physical evidence. General tasks: identify digital information/artifacts as evidence; collect, preserve, and document evidence; analyze, identify, and organize evidence; rebuild evidence or repeat a situation to verify reproducibility of results.

---

### (b) State guidelines for processing an incident or crime scene. — 2 marks

**Solution**

- Step 1: Refer to "Processing an Incident or Crime Scene."
- Step 2: List the key guidelines.

**Final Answer**

- Keep a journal to document your activities.
- Secure the scene: be professional, and remove people not part of the investigation.
- Take video and still recordings of the area around the computer, paying attention to detail.
- Sketch the incident or crime scene.
- Check computers as soon as possible.
- Don't cut electrical power to a running system unless it's an older Windows 9x or MS-DOS system.
- Save data from current applications as safely as possible; record all active windows or shell sessions; make notes of everything done when copying data from a live suspect computer.
- Close applications and shut down the computer.
- Bag and tag the evidence: assign one person to collect/log all evidence; tag each item with date/time, serial numbers or unique features, make/model, and the collector's name; maintain two separate logs; maintain constant control of the evidence and the scene.
- Look for information related to the investigation (e.g., passwords, passphrases, PINs, bank accounts) and collect related documentation/media.

**Calculations:** Not applicable.

---

### (c) What do you mean by remote acquisition? Explain the remote acquisition with Pro Discover or Encase Enterprise tools. — 4 marks

*(Same content as Paper 1, Q2(a).)*

**Final Answer:** As detailed in Paper 1, Question 2(a).

---

## Question 2

### (a) Explain, how to find criminal activities on an NTFS disc? — 2 marks

**Solution**

- Step 1: Refer to "NTFS Data Streams" and related NTFS content.
- Step 2: Explain how hidden/obscured data can be found.

**Final Answer**

The lecture sheet explains that in NTFS, **data streams** are a way data can be appended to existing files, and can **obscure valuable evidentiary data**, intentionally or by coincidence — a data stream becomes an additional file attribute allowing a file to be associated with different applications. Critically, **you can only tell whether a file has a data stream attached by examining that file's MFT (Master File Table) entry.** To find criminal activity on an NTFS disk, an investigator should therefore examine MFT entries for files (since "everything written to the disk is considered a file" in NTFS, and the Partition Boot Sector plus the MFT are the first data sets on the disk) to reveal hidden data streams; investigators should also check whether files/volumes have been encrypted with **EFS or BitLocker**, since NTFS can encrypt data this way, and check the **Windows Registry**, which keeps a record of attached hardware, user preferences, network connections, and installed software that may indicate suspicious activity.

**Calculations:** Not applicable.

---

### (b) What are EFS and Bit-Locker? Explain the whole disc encryption? — 4 marks

*(Same content as Paper 4, Q2(b).)*

**Final Answer:** As detailed in Paper 4, Question 2(b) — EFS (public/private key encryption introduced in Windows 2000, recoverable via administrator recovery certificate and Efsrecvr), BitLocker (Vista Enterprise/Ultimate, requiring TPM 1.2+, TCG-compliant BIOS, two NTFS partitions), and whole disk encryption (preboot authentication, full/partial encryption with secure hibernation, TPM-based key management; must be decrypted with a vendor-specific program before examination).

---

### (c) Explain the roles of Windows Registry for computer forensics investigations. — 4 marks

*(Same content as Paper 3, Q3(a).)*

**Final Answer:** The Registry is a database of hardware/software configuration, network connections, user preferences, and setup information, and can hold valuable evidence — it records attached hardware, user preferences, network connections, and installed software, viewable via Regedit/Regedt32 or extractable (System.dat/User.dat) with ProDiscover Basic; it is also checked to detect installed/uninstalled virtual machines.

---

## Question 3

### (a) Describe the activities performed by computer forensics tools. — 7 marks

*(Same content as Paper 1, Q3(c), presented in full detail.)*

**Final Answer**

Five major categories of tasks performed by computer forensics tools:

1. **Acquisition** — making a copy of the original drive. Subfunctions: physical data copy, logical data copy, data acquisition format, command-line acquisition, GUI acquisition, remote acquisition, and verification (comparing the original drive with the image). Two data-copying methods: physical copying of the entire drive, and logical copying of a disk partition; formats vary from raw data to vendor-specific proprietary compressed data (raw image files can be viewed with any hexadecimal editor); creating smaller segmented files is a typical vendor-tool feature.
2. **Validation and discrimination** — validation ensures the integrity of copied data; discrimination sorts and searches through investigation data. Subfunctions: hashing (CRC-32, MD5, Secure Hash Algorithms), filtering (based on hash value sets, e.g., using the National Software Reference Library, NSRL), and analyzing file headers (to discriminate files by type and detect incorrect extensions).
3. **Extraction** — the recovery task in an investigation, and the most demanding task to master, since recovering data is the first step in analysis. Subfunctions: data viewing, keyword searching (speeds up analysis), decompressing, carving, decrypting (dealing with password-protected/encrypted files via dictionary or brute-force attacks), and bookmarking.
4. **Reconstruction** — re-creating a suspect drive to show what happened during a crime/incident. Subfunctions: disk-to-disk copy, image-to-disk copy, partition-to-partition copy, image-to-partition copy (tools: SafeBack, SnapBack, EnCase, FTK Imager, ProDiscover).
5. **Reporting** — producing a report to complete the forensic disk analysis/examination. Subfunctions: log reports and report generator.

**Calculations:** Not applicable.

---

### (b) Define bit stream copy and bit stream image. — 3 marks

*(Same content as Paper 3, Q1(a).)*

**Final Answer:** Bit-stream disk-to-image file (most common; multiple bit-for-bit copies to an image file; e.g., ProDiscover, EnCase, FTK) and bit-stream disk-to-disk (used when imaging isn't possible; considers disk geometry; e.g., EnCase, SafeBack, SnapCopy).

---

## Question 4

### (a) Explain how to locate and recover graphics files on the suspect's drive. — 4 marks

**Solution**

- Step 1: Refer to "Locating and Recovering Graphics Files."
- Step 2: Explain the OS-tool vs. forensic-tool approaches.

**Final Answer**

- Using plain **operating system tools** is time-consuming and the results are difficult to verify.
- Using **computer forensics tools** is preferred:
  - Examine **image headers**, comparing them with good header samples and using header information to create a baseline analysis.
  - **Reconstruct fragmented image files** by identifying data patterns and modified headers.
  - **Carve/salvage** from slack space and free space to recover all file fragments, then use the tool's capability to help identify image file fragments and put them back together.
  - Use tools such as ProDiscover to search unallocated space and extract/recover possible JPEG (or other graphics) evidence — being aware that false hits (false positives) can occur.

**Calculations:** Not applicable.

---

### (b) Explain identifying graphics file fragments and reconstruction file fragments. — 3 marks

*(Same content basis as Paper 1, Q4(c) plus the graphics-specific identification step.)*

**Final Answer:** **Identifying fragments (carving/salvaging):** recovering all file fragments, typically carved from slack and free space, using forensic tools to help identify image file fragments and reassemble them. **Reconstructing fragments:** locate and export all clusters of the fragmented file → determine the starting and ending cluster numbers for each fragmented group of clusters → copy each fragmented group, in proper sequence, to a recovery file → rebuild the corrupted file's header to make it readable in a graphics viewer.

---

### (c) What is metafiles graphics? Explain graphics file formats. — 3 marks

**Solution**

- Step 1: Refer to "Understanding Metafile Graphics" and "Understanding Graphics File Formats."
- Step 2: Define metafile graphics and list the format types.

**Final Answer**

A graphics file may be one of three types: **bitmap images** (a grid of individual pixels), **vector graphics** (based on mathematical instructions, storing only calculations for drawing lines/shapes — smaller size, preserving quality when enlarged), and **metafile graphics** — a **combination of bitmap and vector graphics** (e.g., a scanned photo, which is bitmap, combined with text, which is vector). Metafile graphics share the advantages and disadvantages of both types; e.g., when enlarged, the bitmap part loses quality while the vector part does not.

**Graphics file formats:**
- Standard bitmap formats: GIF (.gif), JPEG (.jpeg/.jpg), TIFF (.tiff/.tif), Windows Bitmap (.bmp)
- Standard vector formats: Hewlett Packard Graphics Language (.hpgl), AutoCAD (.dxf)
- Nonstandard formats: Targa (.tga), Raster Transfer Language (.rtl), Adobe Photoshop (.psd) and Illustrator (.ai), Freehand (.fh9), Scalable Vector Graphics (.svg), Paintbrush (.pcx)

**Calculations:** Not applicable.

---

## Question 5

### (a) Define digital forensics and investigations? — 2 marks

*(Same content as Paper 5, Q1(a), condensed.)*

**Final Answer:** Computer/digital forensics involves obtaining and analyzing digital information as evidence in civil, criminal, or administrative cases, recovering data that has been hidden or deleted from storage media and using it as evidence (inculpatory or exculpatory). A computer investigation is the systematic process of assessing, planning, securing, analyzing, and reporting on such evidence.

---

### (b) What do you mean by validating forensics data? Explain validating with hexadecimal editors and computer forensics programs. — 4 marks

*(Same content as Paper 1, Q5(a), plus the "computer forensics programs" section.)*

**Final Answer**

**Validating forensic data** means ensuring the integrity of collected data, essential for presenting it in court; this is one of the most critical aspects of computer forensics.

**With hexadecimal editors:** advanced hex editors (e.g., Hex Workshop) offer hashing of specific files/sectors (MD5, SHA-1) beyond what forensic tools alone provide; AccessData's Known File Filter (KFF) database compares known file hash values to files on the evidence drive/image to filter out known files.

**With computer forensics programs:** commercial forensics programs have built-in validation features — e.g., ProDiscover's **.eve** files contain metadata that includes the hash value, so validation happens automatically, whereas **raw format (.dd)** image files don't contain metadata and must be validated manually. In AccessData FTK Imager, selecting the Expert Witness (.e01) or SMART (.s01) format displays additional validation options, and the validation report lists MD5 and SHA-1 hash values.

**Calculations:** Not applicable.

---

### (c) Explain common data hiding techniques in brief. — 4 marks

*(Same content as Paper 2, Q4(a).)*

**Final Answer:** File manipulation (filenames/extensions, hidden property), disk manipulation (hidden partitions, bad clusters), and encryption (bit shifting, steganography).

---

## Question 6

### (a) Explain standard procedures for performing a live acquisition. — 5 marks

*(Same content as Paper 1, Q6(a).)*

**Final Answer:** Live acquisition is necessary because attacks may leave footprints only in running processes/RAM (Order of Volatility governs data fragility). Standard steps: create/download a bootable forensic CD (Helix, DEFT) → log all actions → send data to a network drive → copy physical memory (RAM) first → continue with incident-specific steps → obtain a forensic hash of all recovered files. Tools: Mantech Memory DD, Win32dd, winen.exe, BackTrack 4.

---

### (b) Describe standard procedures for network forensics. — 5 marks

*(Same content as Paper 5, Q3(c).)*

**Final Answer:** Network forensics is a long, tedious process. Standard procedure: always use a standard installation image for network systems → close the way in after an attack → attempt to retrieve all volatile data → acquire all compromised drives → compare the forensic image's files to the original installation image. Work from the image to find what has changed (computer forensics side) and restore drives to understand the attack (network forensics side); work on an isolated system to prevent malware spreading; there's an opportunity to load the image as a VM for analysis. Also review network logs (servers, routers, firewalls — e.g., using tcpdump) and use dedicated network tools (Sysinternals suite: RegMon, Process Explorer, Handle, Filemon; PsTools: PsExec, PsGetSid, PsKill, PsList, PsLoggedOn, PsPasswd, PsService, PsShutdown, PsSuspend; Knoppix-STD: dcfldd, memfetch, photorec, snort, oinkmaster, john, chntpw, tcpdump/ethereal).

---

## Question 7

### (a) Explain the acquisition procedures for cell phones and mobile device and state some mobile forensics tools. — 5 marks

*(Same content as Paper 1, Q7(a) and Paper 5, Q7(b), combined.)*

**Final Answer:** Main concerns are loss of power and PC synchronization (mobile devices have volatile memory). Disconnect the device from any PC connection immediately; isolate it from incoming signals (paint can, Paraben Wireless StrongHold Bag, or eight layers of antistatic bags — accepting the roaming-mode battery-drain trade-off). Check internal memory, SIM card, removable memory, and system servers (the last needs a warrant/subpoena). Acquisition is performed by synchronizing with the device (to download data) and by reading the SIM card via a SIM card reader (remove back panel → remove battery → remove SIM → insert into reader).

**Mobile forensics tools:** Paraben Software Device Seizure Toolbox, Data Pilot, BitPim (not intended for forensics), MOBILedit! (has a write-blocker), SIMCon (reads SIM files, recovers deleted texts, hashes with MD5/SHA-1); for iPhones specifically: MacLockPick II (uses backup files, can't recover deleted files) and MDBackUp Extract (analyzes the iTunes mobile sync backup directory).

---

### (b) Describe tasks in investigation of E-mail crime and violations and analyze the function of E-mail forensics tools. — 5 marks

*(Same content as Paper 1, Q7(b) and Q7(c), combined.)*

**Final Answer:** **Tasks:** goals are finding who is behind the crime, collecting evidence, presenting findings, and building a case (handling depends on jurisdiction, e.g., for spam, so consult an attorney); crimes involving e-mail include narcotics trafficking, extortion, sexual harassment, and child abduction/pornography. Tasks: access the victim's computer/e-mail client to find and copy evidence, access protected/encrypted material, print e-mails, guide the victim by phone to open/copy e-mail including headers, and recover deleted e-mails (servers can often recover them similarly to deleted files).

**Function of e-mail forensics tools:** tools such as AccessData FTK, ProDiscover Basic, FINALeMAIL, Sawmill-GroupWise, DBXtract, Fookes Aid4Mail/MailBag Assistant, Paraben E-Mail Examiner, Ontrack EmailRepair, and R-Tools R-Mail let investigators find e-mail database files, personal e-mail files, offline storage files, and log files — without needing to know in depth how the e-mail servers/clients work internally. FINALeMAIL specifically scans e-mail database files, recovers deleted e-mails, and searches for associated files; FTK indexes an entire disk/image for fast retrieval and integrates dtSearch to recover Outlook/Outlook Express e-mail.
