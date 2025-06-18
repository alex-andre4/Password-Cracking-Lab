# 🔐 Password Cracking Lab – Hashcat & John the Ripper

This project showcases practical password cracking techniques using two widely-used tools: **Hashcat** and **John the Ripper**. It was completed as part of a cybersecurity lab assignment focused on identifying hash types, configuring attacks, and recovering plaintext passwords from various hash algorithms.

---

## 🧪 Lab Overview

- 🔍 **Hash Identification** using [hashes.com](https://hashes.com/en/tools/hash_identifier)
- 🧾 **Cracking Techniques** with dictionary attacks (`rockyou.txt`)
- 🧰 **Tools Used**: Hashcat, John the Ripper, Linux (Kali), rockyou wordlist
- 🧠 **Objectives**: Analyze, identify, and crack 10 different hashes using both tools

---

## 💥 Cracked Hash Samples

| Label | Hash Type | Mode | Password |
|-------|-----------|------|----------|
| a     | MD5       | `-m 0` | `HELLO` |
| b     | MD5       | `-m 0` | `easy` |
| c     | SHA1      | `-m 100` | `password123` |
| d     | SHA256    | `-m 1400` | `letmein` |
| e     | bcrypt    | `-m 3200` | `bleh` |
| f     | MD4       | `-m 900` | `Eternity22` |
| g     | SHA256    | `-m 1400` | `paule` |
| h     | NTLM      | `-m 1000` | `n63umy8lkf4i` |
| i     | SHA512crypt | `-m 1800` | `waka99` |
| j     | SHA1      | `-m 100` | ❌ Uncracked |

---

## 🧰 Example Commands

### 🔧 Hashcat

```bash
# General format
hashcat -m <mode> -a 0 user.hash rockyou.txt

# Example: SHA1
hashcat -m 100 -a 0 hashes/sha1.hash rockyou.txt

🔧 John the Ripper

# General format
john --format=<format> --wordlist=rockyou.txt user.hash

# Example: MD5
john --format=raw-md5 --wordlist=rockyou.txt hashes/md5.hash

For a full list of formats, run:

john --list=formats

📸 Screenshots

Cracked password evidence with visible system username is located in /screenshots. Each image is labeled clearly for cross-reference with the hash challenges.
🧠 Observations & Comparison

    Hashcat: Better for detailed control, mode reference, and verbose output. Easier to learn.

    John the Ripper: Faster execution, simpler output, great for batch cracking.

    Conclusion: Prefer Hashcat for precision and clarity, John for speed in bulk operations.

✅ Ethical Use Cases

    Penetration Testing: Simulate real-world attacks to expose weak passwords before attackers do.

    Account Recovery: Lawful recovery of critical accounts or access to important documents/data.

🔗 References

    Hash Identifier – Hashes.com

    Hashcat Wiki

    rockyou.txt wordlist (not included in repo)

📄 License

This project is licensed under the MIT License. Intended for educational and ethical cybersecurity training only.
