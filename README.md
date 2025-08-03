# windows-internals-exploration
A practical exploration of Windows authentication mechanisms, focusing on registry file extraction and password hash cracking techniques
# Windows Security Internals Exploration

## Overview
A hands-on exploration of Windows authentication internals, focusing on how credentials are stored and how attackers might extract and crack password hashes from the registry.


## Topics Covered
Extraction of SAM & SYSTEM registry files  
- Understanding the Windows logon process and hash storage  
- Cracking NTLM hashes using common tools

## Tools Used
- Mimikatz– for dumping hashes from memory  
- John the Ripper / Hashcat – for offline hash cracking  
- FTK Imager / reg save – for safe extraction of registry hives

## Outcome
Built foundational understanding of credential storage in Windows environments. Practiced identifying and mitigating risks related to credential exposure, in a controlled lab setup.
