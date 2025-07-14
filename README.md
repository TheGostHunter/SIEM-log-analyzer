# 🛡️ SIEM Log Analyzer (Python)

A basic script to parse and analyze simulated log files — designed to mimic a real-world SIEM alert scenario.

## 🔍 What It Does
- Parses system logs (Linux-style auth.log format)
- Detects:
  - Failed login attempts
  - Brute force attack patterns
  - Suspicious IPs

## ⚙️ Usage
```bash
python3 log_analyzer.py logs/auth.log
```

## 🧪 Sample Output
```
[!] 5 failed login attempts from 192.168.1.100
[!] Possible brute force attack detected
```

## 📦 Dependencies
- Python 3.x
- `re` module
- `datetime` module

## 🎯 Why This Project?
To simulate what real SOC analysts do — parse logs and detect patterns using SIEM logic.

## 💡 Future Plans
- JSON log support
- Output to CSV report
- Real-time log tailing
