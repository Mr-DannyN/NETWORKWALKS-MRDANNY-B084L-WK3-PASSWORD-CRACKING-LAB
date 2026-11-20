# NetworkWalks — Week 3: Password Cracking Lab

This repo documents two lab exercises from Week 3 of the NetworkWalks Cybersecurity & Ethical Hacking program, both focused on recovering the password of an encrypted PDF file using different tools.

> **Disclaimer:** Performed on sample files provided for training purposes in an authorized lab environment. Password cracking should only ever be done on files/systems you own or have explicit permission to test.

## Background

Password-protected PDFs store their password as a **hash**; a one-way, scrambled representation of the password. Cracking tools extract that hash and test candidate passwords against it until one produces a matching hash. Weak or common passwords can be cracked quickly, which is exactly what this lab demonstrates.

## Module 1 — Password Cracking with John the Ripper (JTR)
`Week3/JTR Cracking/`

**Tools:** John the Ripper (JTR) + Johnny (GUI)

**Steps performed:**
1. Extracted each locked PDF's crackable hash (`hash1.txt`, `hash2.txt`, `hash3.txt`) using an online PDF-hash extractor.
2. Loaded the hash into Johnny and ran an attack.
3. Johnny cracked the password.
4. Used the recovered password to unlock the original PDF.

**Locked PDF password prompt**
![Locked PDF prompt](Week3/JTR%20Cracking/Locked_pdf1.png)

**Hash extracted from locked PDF**
![Hash extracted](Week3/JTR%20Cracking/01-extract-hash.png)

**Johnny GUI — password cracked**
![Johnny cracked](Week3/JTR%20Cracking/02-passwordcracked.png)

**Final cracked result**
![Cracked result](Week3/JTR%20Cracking/03-cracked-result.png)

**Source files:** `My Locked PDF1.pdf`, `My Locked PDF2.pdf`, `My Locked PDF3.pdf`
**Extracted hashes:** `hash1.txt`, `hash2.txt`, `hash3.txt`

## Module 2 — Password Cracking with NetworkWalks Online Tools
`Week3/NW Cracking/`

**Tools:** NetworkWalks Hash Calculator + Password Cracker (browser-based)

**Steps performed:**
1. Uploaded the locked PDF to the Hash Calculator, which extracted the hash locally.
2. Copied the hash into the Password Cracker tool.
3. The tool iterated through a wordlist and found a match.
4. Used the recovered password to open the PDF.

**Hash extracted via Hash Calculator**
![NW hash extracted](Week3/NW%20Cracking/NW_HashCrack.png)

**Password Cracker — match found**
![NW password cracked](Week3/NW%20Cracking/Cracked_Password.png)

**Source file:** `My Locked PDF1.pdf`

## Key Takeaways

- Two different approaches — an offline tool (JTR/Johnny) and a browser-based tool (NetworkWalks) — reached the same result, showing there's more than one valid path to the same security-testing outcome.
- The passwords cracked quickly because they were short/common — a practical demonstration of why weak passwords are a serious security risk.
- This reinforces the basics of password hashing, hash extraction, and dictionary/wordlist attacks.

##
