# winPEAS – Windows Privilege Escalation Awesome Script

**winPEAS** is the Windows counterpart to linPEAS, part of the PEAS-ng suite. It’s a powerful enumeration tool for identifying potential **privilege escalation paths** on Windows systems. winPEAS collects detailed information about the system and highlights misconfigurations that may allow escalation to Administrator or SYSTEM.

🔗 [Run winPEAS Privilege Checks on SploitHQ](https://sploithq.com/winpeas)

---

## 🔍 What Does winPEAS Do?

- Identifies unquoted service paths, weak service permissions, and autologin credentials
- Finds AlwaysInstallElevated settings and startup applications
- Detects vulnerable software, DLL hijack opportunities, and token privileges
- Highlights insecure file/folder permissions
- Searches for saved credentials, password reuse, and vulnerable scheduled tasks

---

## ⚙️ Download & Execution

1. **Download from the official repo:**

```powershell
Invoke-WebRequest "https://github.com/carlospolop/PEASS-ng/releases/latest/download/winPEASx64.exe" -OutFile "winPEASx64.exe"
```

2. **Run from an interactive shell or reverse shell:**

```powershell
.\winPEASx64.exe
```

> 📝 You can also transfer and run via SMB, certutil, or PowerShell encoded commands depending on access level.

---

## 🧰 winPEAS Variants

| Binary            | Description                                |
|-------------------|--------------------------------------------|
| `winPEASx64.exe`  | 64-bit compiled binary (GUI + color)       |
| `winPEASx86.exe`  | 32-bit compiled binary                     |
| `winPEASany.exe`  | .NET version (good for AV evasion)         |
| `winPEAS.bat`     | Batch script version (lighter footprint)   |

---

## 🧪 Example Use Cases

### Run default checks:
```powershell
.\winPEASx64.exe
```

### Run all checks and dump to file:
```powershell
.\winPEASx64.exe > results.txt
```

### Run from a low-privilege shell:
```powershell
start winPEASany.exe
```

---

## 🎯 What winPEAS Detects

- Credential storage in registry, config files, browsers
- Misconfigured UAC and AlwaysInstallElevated
- Service misconfigurations and DLL injection paths
- Registry permissions, environment variables
- Insecure tokens and user privileges (e.g., SeImpersonatePrivilege)

---

## 🧠 Follow-Up Actions

- Use **SeImpersonatePrivilege** → Juicy Potato / PrintSpoofer
- Weak folder permissions → Replace service binary
- Unquoted service paths → Add malicious executable
- Insecure registry keys → Modify for persistence

---

## 🌐 SploitHQ Integration

👉 [Analyze winPEAS Output](https://sploithq.com/winpeas)

- Post-enumeration checklist
- Exploitable vectors categorized
- Reference links to CVEs and GTFOBins (Windows edition)

---

## 🔗 Useful Links

- [PEAS-ng GitHub (winPEAS)](https://github.com/carlospolop/PEASS-ng/tree/master/winPEAS)
- [HackTricks Windows PrivEsc](https://book.hacktricks.xyz/windows-hardening/windows-local-privilege-escalation)
- [SploitHQ winPEAS Page](https://sploithq.com/winpeas)

---

## 📄 License

winPEAS is developed by Carlos Polop as part of the PEAS-ng suite under the MIT License.  
This documentation is curated by [SploitHQ](https://sploithq.com) for authorized red team operations and ethical hacking training.
