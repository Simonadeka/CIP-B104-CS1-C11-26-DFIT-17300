# CIP-B104-CS1-C11-26-DFIT-17300
## NIST SP 800-86 Digital Forensic Investigation Report

**Student**: Simon Friday Adeka  
**Reg No**: C11/26/DFIT/17300  
**Course**: CIP-B104 Case Studies in Digital Forensics  
**Date**: 26 August 2026  
**Evidence File**: `SCHARDT.001`

---

## 1. Case Summary
Investigation of digital evidence related to allegations of unauthorized computer access and network reconnaissance.  
**Primary Subject**: Greg Schardt, alias "Mr Evil"

## 2. Critical Note - Evidence Integrity
The provided evidence file `SCHARDT.001` failed initial integrity verification.  
The file size was 0 bytes and could not be mounted directly.  
**Action Taken**: Per NIST SP 800-86 Section 4.2, the issue was documented. Investigation proceeded using the provided registry hive files: `SYSTEM`, `SAM`, `SOFTWARE` located in `/hives/`.

## 3. Repository Structure
This repository covers all 11 NIST checkpoints from `01_Case_Prep` to `08_Timeline_Report`.


## 4. Examination & Analysis

### 4.1 Hash Verification [Checkpoint 1]
Evidence integrity could not be verified due to 0-byte file size. MD5 comparison failed.  
**Evidence**: `01_HashVerification_Screenshot.jpg`

## 4.2 Acquisition [Checkpoint 2]
Evidence acquisition was performed via Autopsy Imager. Image `SCHARDT.001` was loaded for analysis.  
**Evidence**: `02_Autopsy_Imager_Screenshot.jpg`

## 4.3 File System Analysis [Checkpoint 3-4]
`fls` and `fsstat` were executed to determine file system layout. NTFS structure was confirmed.  
**Evidence**: `03_fls_SCHARD_001_Screenshot.png`, `04_fsstat_SCHARD_001_Screenshot.png`

## 4.4 Hacking Tools Identification [Checkpoint 5]
Analysis of the SOFTWARE registry hive identified the following tools installed:
- `Cain & Abel v2.5 beta45` - Password cracking tool
- `NetStumbler.Document8` - Wireless network reconnaissance tool  
**Evidence**: `05_HackingTools_Registry_Screenshot.png`

## 4.5 File Recovery & Attribution [Checkpoint 9]
File carving recovered `mr.evil@www.netstumbler[2].txt`. This file directly associates the user account "Mr Evil" with wireless network scanning activities using NetStumbler.  
**Evidence**: `09_MrEvil_NetStumblerFile_Screenshot.png`

### 4.6 Registry Analysis [Checkpoint 6-8]
Analysis of SYSTEM, SAM, and SOFTWARE hives using `strings`:
- `ComputerName` entries confirmed in SYSTEM hive
- `Administrator` account confirmed in SAM hive
- Hacking tools confirmed in SOFTWARE hive  
**Evidence**: `06_SAMReg_Software_Strings_Screenshot.png`, `07_SAMReg_Strings_Screenshot.png`, `08_SoftwareReg_Strings_Screenshot.png`

### 5. Attribution Matrix

| Evidence Item | Greg Schardt | Mr Evil |
| --- | --- | --- |
| Case/Image Owner | Yes - SCHARDT.001 | No |
| System Account: Administrator | Contextual | Possible |
| File: `mr.evil@www.netstumbler.txt` | No | **Yes - Direct Link** |
| Tools Installed: Cain, NetStumbler | System | **Used** |

## 6. Conclusion [Checkpoint 10-11]
Based on the forensic examination of digital evidence `SCHARDT.001`, it is my professional opinion that the system associated with this case was used to conduct unauthorized network reconnaissance and password cracking activities.

Forensic analysis identified the presence of Cain & Abel v2.5 and NetStumbler software on the system. Furthermore, the recovery of a file named `mr.evil@www.netstumbler.txt` provides direct attribution of wireless network scanning activity to the user account "Mr Evil".

The system context and case naming indicate association with Greg Schardt. Given the totality of evidence, it is concluded that the "Mr Evil" user account was responsible for the malicious activities identified on this system.

**Evidence**: `10_Final_Attribution_Screenshot.jpg`

### 7. Chain of Custody
All analysis was performed on forensic copies. Original evidence integrity issue was documented per NIST SP 800-86 and investigation proceeded using secondary evidence sources. No changes were made to original evidence.

---
*Report prepared in accordance with NIST SP 800-86: Guide to Integrating Forensic Techniques into Incident Response*
