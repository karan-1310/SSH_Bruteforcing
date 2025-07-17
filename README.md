
# 🔐 SSH Brute Force Attack Simulation

This project demonstrates how to simulate an **SSH brute force attack** on a **local machine** using a Python script (`ssh_bruteforce.py`) and a password wordlist (`wordlist.txt`). The purpose is purely **educational** — to understand how brute-force attacks work, assess password strength, and promote better security practices.

---

## 📌 Objective

- Understand the **mechanism** of brute force attacks on SSH.
- Demonstrate how attackers might exploit weak credentials.
- Encourage the implementation of **strong authentication methods** and protective mechanisms like fail2ban, SSH key authentication, or rate-limiting.

---

## ⚠️ Legal & Ethical Disclaimer

> **This project is intended for educational use only.**  
> Do **not** use this code or approach on any system you do not own or have explicit permission to test. Unauthorized access is illegal and unethical.

---

## 🛠️ Tools & Technologies

- **Language:** Python 3
- **Libraries:**
  - `paramiko` – for SSH protocol handling
  - `argparse` – for command-line arguments
  - `time` – to measure execution
- **Target:** SSH server running locally (e.g., `localhost` or `127.0.0.1`)
- **Environment:** Linux/Mac (or Windows with OpenSSH enabled)

---

## 📂 Project Structure

```

ssh-brute-force/
├── ssh\_bruteforce.py     # Python script to perform brute force
├── wordlist.txt          # Wordlist containing possible passwords
└── README.md             # Project documentation

````

---

## 🧠 How It Works

1. The script takes in:
   - **Target IP/hostname**
   - **SSH username**
   - **Path to wordlist file**

2. For each password in the wordlist:
   - It attempts to establish an SSH connection using `paramiko`.
   - If the authentication fails, it tries the next password.
   - If successful, it prints the **correct password** and exits.

3. Tracks and reports:
   - Total number of attempts
   - Time taken for the attack
   - Whether login was successful

---

## 🚀 Usage

### 🔧 Prerequisites

Install dependencies:

```bash
pip install paramiko
````

Ensure SSH server is running on your local machine and credentials are known/testable.

### ▶️ Running the Script

```bash
python ssh_bruteforce.py --host 127.0.0.1 --user testuser --wordlist wordlist.txt
```

**Arguments:**

* `--host`: IP address or hostname of the SSH server
* `--user`: Username to attempt login
* `--wordlist`: Path to your password wordlist file

---

## 📄 Sample Output

```text
[+] Trying password: 123456
[-] Incorrect
[+] Trying password: password
[-] Incorrect
[+] Trying password: securePass123
[✔] Success! Password found: securePass123
[*] Total attempts: 3
[*] Time taken: 5.43 seconds
```

---

## 🔐 Password Wordlist (wordlist.txt)

Provide a file (`wordlist.txt`) with one password per line. Example:

```
123456
password
admin
letmein
securePass123
```

> You can generate or download test wordlists from resources like [SecLists](https://github.com/danielmiessler/SecLists) or build your own.

---

## 🛡️ Recommendations Against Brute Force Attacks

* Use **strong, complex passwords**.
* Disable **password-based authentication** in favor of **SSH key pairs**.
* Enable **fail2ban** or similar intrusion prevention tools.
* Restrict SSH access to known IPs via firewall.
* Change the **default SSH port** from `22`.

---

## 🧪 Educational Value

This simulation offers insight into:

* Attack vectors used by malicious actors.
* Importance of secure authentication.
* Role of rate-limiting and intrusion detection systems.

---

## 🙌 Acknowledgements

* [Paramiko Documentation](http://docs.paramiko.org/)
* [SecLists Password Repositories](https://github.com/danielmiessler/SecLists)
* Cybersecurity courses and ethical hacking communities

---

## 📛 License

This project is licensed for educational use.
Do **not** use for any unauthorized penetration testing or illegal activities.

---

```

---

✅ You can now **copy-paste** this entire block directly into your `README.md` file — no splitting needed. Let me know if you want to add a demo video link, a screenshot, or the actual code as well!
```
