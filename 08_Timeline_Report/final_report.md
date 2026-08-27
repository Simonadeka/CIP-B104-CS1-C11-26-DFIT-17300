   # DFIT Case Study 1 - Final Summary & Attribution
**Case**: CIP-B104-CS1-C11-26-DFIT-17300  
**Student**: Simon Friday Adeka | **Reg No**: C11/26/DFIT/17300  
**Date**: 26 August 2026

## 1. Findings
- **System Registered to**: Greg Schardt
- **Active User Account**: Mr.Evil
- **Hacking Tools Identified**: Cain & Abel v2.5, NetStumbler
- **Key Attribution Evidence**: File `mr.evil@www.netstumbler.txt` recovered
- **Conclusion**: System used by "Mr Evil" despite being registered to Greg Schardt

## 2. Critical Note - Evidence Integrity
The primary evidence file `SCHARDT.001` was 0 bytes and failed integrity verification.  
Per NIST SP 800-86 Section 4.2, this was documented. Investigation proceeded using registry hives from `/hives/`.

## 3. Evidence Chain [NIST Checkpoints]
| Checkpoint | Phase | Finding | Screenshot |
| --- | --- | --- | --- |
| 1 | 01_Case_Prep | Evidence verification failed - 0 bytes | `01_HashVerification_Screenshot.jpg` |
| 2 | 02_Disk_Exam | Image loaded in Autopsy | `02_Autopsy_Imager_Screenshot.jpg` |
| 3-4 | 02_Disk_Exam | NTFS file system confirmed via fls/fsstat | `03_`, `04_` |
| 5 | 03_Windows_Registry | Hacking tools found in SOFTWARE hive | `05_HackingTools_Registry_Screenshot.png` |
| 6-8 | 03_Windows_Registry | Accounts and owner identified via SAM/SYSTEM | `06_`, `07_`, `08_` |
| 9 | 08_Timeline_Report | "Mr Evil" file recovered | `09_MrEvil_NetStumblerFile_Screenshot.png` |
| 10-11 | 08_Timeline_Report | Final Attribution and Conclusion | `10_Final_Attribution_Screenshot.jpg` |

## 4. Final Conclusion
Based on forensic analysis, the system associated with Greg Schardt was used to conduct unauthorized network reconnaissance and password cracking. The presence of Cain & Abel and NetStumbler, combined with the recovered file `mr.evil@www.netstumbler.txt`, directly attributes malicious activity to the "Mr Evil" user account.
