<img width="1920" height="920" alt="image" src="https://github.com/user-attachments/assets/89606f21-92e6-4bdc-a712-513828c5bf9f" /><div align="center">

# 🔐 Password Cracking Lab — JTR & NetworkWalks Tools

**Recovering a password-protected PDF's password using John the Ripper (Johnny GUI) and the NetworkWalks Hash Calculator / Password Cracker**
</div>

<p align="center">
  <img src="https://img.shields.io/badge/Skill-Cybersecurity-404040?style=flat-square&labelColor=C00000" />
  <img src="https://img.shields.io/badge/Week-03-0070C0?style=flat-square&labelColor=000000" />
  <img src="https://img.shields.io/badge/John%20the%20Ripper-1.9.0--jumbo-E87500?style=flat-square&labelColor=000000" />
  <img src="https://img.shields.io/badge/Skill-Password%20Cracking-404040?style=flat-square&labelColor=C00000" />
  <img src="https://img.shields.io/badge/Tool-Johnny%20GUI-238F89?style=flat-square&labelColor=000000" />
  <img src="https://img.shields.io/badge/Tool-NetworkWalks%20Hash%20Calculator-C00000?style=flat-square&labelColor=000000" />
  <img src="https://img.shields.io/badge/GitHub-404040?style=flat-square&labelColor=0070C0&logo=github&logoColor=white" />
  <img src="https://img.shields.io/badge/NetworkWalks-404040?style=flat-square&labelColor=C00000" />
</p>

---

## 📌 Project Overview

This project covers **Week 3's two essential project modules** of the NetworkWalks Cybersecurity & Ethical Hacking course:

- **PM1 — Password Cracking with JTR:** recovering a password-protected PDF's password using **John the Ripper (JTR)** via the **Johnny** GUI.
- **PM2 — Password Cracking with NetworkWalks Tools:** recovering a password-protected PDF's password using the **NetworkWalks Hash Calculator** and **Password Cracker** web tools.

Both modules use the same underlying idea: a locked PDF's password is stored as a hash, and that hash is extracted and then run through a wordlist-based cracking tool until a match is found.

⚠️ **Important:** These tools and techniques are for educational use only, on files you own or have explicit permission to test.

---

## 🎯 Objectives

- Extract a crackable password hash (`$pdf$...`) from a locked PDF file.
- Use **Johnny** (GUI for John the Ripper) to run a dictionary attack against the hash.
- Use the **NetworkWalks Hash Calculator** to extract the same type of hash from a locked PDF in-browser.
- Use the **NetworkWalks Password Cracker** to run a dictionary attack against that hash.
- Unlock the PDF files using the recovered passwords.
- Document the process, tools, and results.

---

## 🧰 Tools Used

| Tool | Purpose |
|---|---|
| **John the Ripper (JTR) 1.9.0-jumbo-1** | Password cracking engine |
| **Johnny** | GUI front-end for John the Ripper |
| **NetworkWalks Hash Calculator** | Extracts a crackable `$pdf$...` hash from a locked PDF in-browser |
| **NetworkWalks Password Cracker** | Runs a dictionary attack against a `$pdf$...` hash in-browser |

---

## 🪜 PM1 — Password Cracking with JTR

### Step 1. Set up Johnny

Johnny was configured to point to the John the Ripper executable (`john.exe`) so it could run attacks through the GUI.

<img width="1920" height="1030" alt="image" src="https://github.com/user-attachments/assets/7625f146-d006-485d-9695-98c22a6ffda9" />


### Step 2. Extract the hash and load it into Johnny

The locked PDF's hash was extracted (in `$pdf$...` format) and loaded into Johnny as a password file.

### Step 3. Run the attack

Johnny was used to start a new attack against the loaded hash using its built-in wordlist.

### Step 4. Password cracked

Johnny successfully cracked the password in a single attack run (`1/1 cracked`).

<img width="1522" height="550" alt="johnny1_output" src="https://github.com/user-attachments/assets/7f53d03e-8b2d-46c7-97f8-1d5966c23ce9" />


*(Password text has been masked above; the PDF was confirmed to open successfully with the recovered password.)*

---

## 🪜 PM2 — Password Cracking with NetworkWalks Tools

### Run 1 — My Locked PDF1.pdf

**Step 1. Extract the hash with the Hash Calculator**

The locked PDF was uploaded to the NetworkWalks Hash Calculator, which parsed it locally in the browser and returned a `$pdf$...` hash (pdf2john / hashcat compatible format).

<img width="1920" height="915" alt="image" src="https://github.com/user-attachments/assets/439eaf7c-6777-458f-8e5c-a7e11ef2427c" />


**Step 2. Paste the hash into the Password Cracker**

The extracted hash was pasted into the NetworkWalks Password Cracker, using the built-in 100-password wordlist.

<img width="1920" height="915" alt="image" src="https://github.com/user-attachments/assets/644b9844-259b-45dd-a2bd-cf21bf8cf12a" />


**Step 3. Password cracked**

The dictionary attack tried different candidate passwords and found a match at 91% progress.

<img width="1920" height="905" alt="image" src="https://github.com/user-attachments/assets/d50d1aa9-5a92-4099-afe0-6a18946a26fc" />

*(Password text has been masked above.)*

### Run 2 — My Locked PDF2.pdf

**Step 1. Extract the hash with the Hash Calculator**

The second locked PDF was uploaded to the Hash Calculator to extract its `$pdf$...` hash.

<img width="1920" height="920" alt="image" src="https://github.com/user-attachments/assets/d4d1d512-5292-4c0f-beb1-b30da108da31" />


**Step 2. Paste the hash into the Password Cracker**

The hash was pasted into the Password Cracker and the attack was started.

<img width="1920" height="920" alt="image" src="https://github.com/user-attachments/assets/ef8b2917-295d-4c8e-a5f8-ca0aaf418514" />



**Step 3. Password cracked**

The tool found a match at 35% progress through the wordlist.

<img width="1920" height="905" alt="image" src="https://github.com/user-attachments/assets/a52a2ed1-20b4-4c4c-be3d-651dc740e0f7" />


*(Password text has been masked above.)*

---

## 🔎 Results Summary

| Module | Tool | Hash Source | Result |
|---|---|---|---|
| PM1 | Johnny / John the Ripper | Locked PDF (JTR flow) | ✅ Password cracked, PDF unlocked |
| PM2 — Run 1 | NetworkWalks Hash Calculator + Password Cracker | My Locked PDF1.pdf | ✅ Password cracked successfully |
| PM2 — Run 2 | NetworkWalks Hash Calculator + Password Cracker | My Locked PDF2.pdf | ✅ Password cracked successfully |
| PM2 — Run 2 | NetworkWalks Hash Calculator + Password Cracker | My Locked PDF3.pdf | ✅ Password cracked successfully |

---
## 🚩 Flags Captured

- **PM1 Flag (JTR):** [PM1_Flag.pdf](./PM1_Flag.pdf)
- **PM2 Flag 1:** [PM2_Flag_1.pdf](./PM2_Flag_1.pdf)
- **PM2 Flag 2:** [PM2_Flag_2.pdf](./PM2_Flag_2.pdf)
- **PM2 Flag 3 (Persistence):** [PM2_Flag_Persistence.pdf](./PM2_Flag_Persistence.pdf)

---
## 💡 What I Learned

- How a password-protected PDF stores its password as a hash (`$pdf$...` format), and how that hash is extracted using a `pdf2john`/hashcat-compatible approach.
- How a dictionary attack works: trying candidate passwords from a wordlist against a hash until a match is found.
- The difference between a desktop GUI tool (Johnny/JTR) and browser-based tools (NetworkWalks Hash Calculator & Password Cracker) for doing the same type of attack.
- Why short, common passwords (like the ones used in this lab) can be cracked almost instantly, which highlights the importance of using long, complex, unique passwords.
- The importance of masking cracked credentials before sharing screenshots or documentation publicly.

---

## 🔐 Security & Ethical Use

This lab was performed strictly for educational purposes on sample files provided by NetworkWalks for this course. The techniques shown here must only be used on systems/files you own or have explicit permission to test.

---

## 👤 Author

**Sreejith Nair** — B084
Cybersecurity Student, NetworkWalks

---

## 📌 Project Information

**Program Name:** Cybersecurity at NetworkWalks | **Week:** 03 | **Project:** Password Cracking with JTR (PM1) & NetworkWalks Tools (PM2) | **Repository:** GitHub
