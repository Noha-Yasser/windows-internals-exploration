1. Objectives
- Explore Windows authentication mechanisms.
- Extract and analyze SAM & SYSTEM hive files.
- Crack password hashes using common tools.

2. SAM & SYSTEM Extraction

- *Tool Used:* `reg save` (built-in)  
  
  reg save HKLM\SAM sam.save
  reg save HKLM\SYSTEM system.save
  
- Method: Files extracted from live system with Administrator privileges.

- Notes: SYSTEM hive needed to decrypt the hashes in the SAM file.


3. Hash Extraction

- Tool Used: `mimikatz`  
  - Module: `lsadump::sam`
  - Output: NTLM hashes for local users
  - Example:
    ```
    Administrator:500:aad3b435b51404eeaad3b435b51404ee:<NTLM_HASH>:::
    ```

- Alternative:`pwdump` or `samdump2` with Linux tools.

---

4. Hash Cracking

- *Tools Used:*  
  - `hashcat` (mode 1000 for NTLM)  
  - `John the Ripper` with `rockyou.txt`

- Command Used:
  ```
  hashcat -m 1000 hashes.txt rockyou.txt
  ```

- Result: See `hash_crack_results.txt` for cracked passwords.


5. Key Learnings
- NTLM hashes are vulnerable to dictionary and brute-force attacks.
- SYSTEM hive is essential to decrypt SAM contents.
