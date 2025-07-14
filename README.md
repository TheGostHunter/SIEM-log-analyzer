import re
import sys
from collections import defaultdict

def analyze_logs(filepath):
    failed_logins = defaultdict(int)

    with open(filepath, 'r') as file:
        for line in file:
            if "Failed password" in line:
                ip_match = re.search(r'from (\d+\.\d+\.\d+\.\d+)', line)
                if ip_match:
                    ip = ip_match.group(1)
                    failed_logins[ip] += 1

    for ip, count in failed_logins.items():
        print(f"[!] {count} failed login attempts from {ip}")
        if count >= 5:
            print("[!] Possible brute force attack detected")

if __name__ == "__main__":
    if len(sys.argv) != 2:
        print("Usage: python3 log_analyzer.py <logfile_path>")
        sys.exit(1)

    log_file = sys.argv[1]
    analyze_logs(log_file)
