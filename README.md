# Python Ethical Hacking

Learning Python and ethical hacking - building security tools from scratch

This repository documents my journey learning penetration testing and Python development. Each tool is built from scratch with detailed documentation, demonstrating practical applications of network security concepts.

## ⚠️ Disclaimer

**FOR EDUCATIONAL PURPOSES ONLY**

These tools are intended for educational purposes and authorized penetration testing only.

- ✅ Use only on networks and devices you own or have explicit permission to test
- ❌ Unauthorized access to computer networks is illegal
- ⚠️ I am not responsible for misuse or damage caused by these tools

Always comply with local laws and regulations.

## 📚 Course

Currently following: **"Learn Python & Ethical Hacking From Scratch"** by Zaid Sabih (Zsecurity)

**Adaptations made:**
- Python 3.x compatibility (course uses Python 2)
- Modern Linux utilities and best practices
- Enhanced error handling and user experience
- Additional input validation and security checks

## 📊 Progress

- [x] **Git and GitHub Setup** - Repository structure and version control
- [x] **MAC Changer** - Network interface MAC address spoofing ✅
- [ ] **Network Scanner** - Discover devices on local network
- [ ] **ARP Spoofer** - Man-in-the-middle attack demonstration
- [ ] **Packet Sniffer** - Capture and analyze network traffic
- [ ] **DNS Spoofer** - Redirect DNS queries
- [ ] **File Interceptor** - Intercept and replace file downloads
- [ ] **Code Injector** - Inject code into HTTP responses
- [ ] **Keylogger** - Capture keyboard input (ethical demonstration)
- [ ] **Credentials Harvester** - Capture login credentials
- [ ] **Vulnerability Scanner** - Detect common web vulnerabilities

## 🛠️ Tools Built

### ✅ Completed

#### [01 - MAC Changer](./01-mac-changer/)
Spoof network interface MAC addresses for privacy, testing, and bypassing network restrictions.

**Features:**
- Command-line interface with argument parsing
- Validates MAC address changes
- User-friendly output with success/failure verification
- Python 3 compatible

**Status:** ✅ Complete | **Version:** 1.0 | **Roadmap:** v2 planned with `ip` command and input validation

---

### 🚧 In Progress
_(Tools currently being developed will appear here)_

---

### 📋 Planned
- **Network Scanner** - ARP-based network device discovery
- **ARP Spoofer** - Position system between target and gateway
- **Packet Sniffer** - Intercept and analyze network packets
- **DNS Spoofer** - Redirect DNS requests to malicious sites
- More tools to be added as course progresses...

## 💻 Requirements

### System Requirements
- Linux-based OS (Kali Linux recommended, Ubuntu/Debian compatible)
- Python 3.x (Python 3.6 or higher)
- Root/sudo privileges for network manipulation
- Active network interface

### Knowledge Prerequisites
- Basic Python programming
- Understanding of networking fundamentals (IP, MAC, ARP, DNS)
- Linux command-line familiarity
- Ethical hacking principles

### Common Dependencies
Most tools use Python standard library modules:
- `subprocess` - Execute system commands
- `optparse`/`argparse` - Parse command-line arguments
- `re` - Regular expression pattern matching
- `scapy` - Packet manipulation (for advanced tools)

## 📂 Repository Structure
```
python-ethical-hacking/
├── README.md                    # This file
├── 01-mac-changer/
│   ├── README.md               # Detailed tool documentation
│   └── mac_changer.py          # Main script
├── 02-network-scanner/         # Coming soon
├── 03-arp-spoofer/            # Coming soon
└── ...
```

Each tool directory contains:
- `README.md` - Complete documentation, usage examples, and technical details
- Source code with comments explaining key concepts
- Version history and planned improvements

## 🚀 Quick Start
```bash
# Clone the repository
git clone https://github.com/Janik00/python-ethical-hacking.git

# Navigate to a specific tool
cd python-ethical-hacking/01-mac-changer

# Read the tool's documentation
cat README.md

# Run with help flag to see usage
python mac_changer.py --help

# Execute with sudo (most tools require root privileges)
sudo python mac_changer.py -i eth0 -m 00:11:22:33:44:55
```

## 🎓 Learning Objectives

Through building these tools, I'm developing skills in:

**Python Development:**
- Command-line tool creation
- System programming with subprocess
- Regular expressions and pattern matching
- Error handling and user input validation
- Code organization and documentation

**Networking & Security:**
- Network protocols (ARP, DNS, HTTP, TCP/IP)
- Packet manipulation and analysis
- Man-in-the-middle attack vectors
- Network reconnaissance techniques
- Security testing methodologies

**Linux Administration:**
- Network interface manipulation
- Privilege escalation and sudo usage
- System command integration
- Cross-platform compatibility considerations

## 📖 Usage Guidelines

### Ethical Usage
- **Only test systems you own or have written permission to test**
- Document all testing activities
- Report vulnerabilities responsibly
- Respect privacy and legal boundaries

### Best Practices
- Always read tool-specific README before use
- Test in isolated/virtual environments first
- Understand what each command does before executing
- Keep backups of system configurations
- Use version control for your modifications

## 🤝 Contributing

This is a personal learning project, but I welcome:
- Bug reports and fixes
- Suggestions for improvements
- Python 3 compatibility updates
- Documentation enhancements

Feel free to open an issue or submit a pull request!

## 📝 Version History

- **v1.0** (Current) - MAC Changer complete, repository structure established
- **v2.0** (Planned) - Network Scanner, improved MAC Changer with validation

## 🔗 Resources

- **Course:** [Udemy - Learn Python & Ethical Hacking From Scratch](https://www.udemy.com/course/learn-python-and-ethical-hacking-from-scratch/)
- **Python Documentation:** [https://docs.python.org/3/](https://docs.python.org/3/)
- **Kali Linux Tools:** [https://www.kali.org/tools/](https://www.kali.org/tools/)
- **OWASP:** [https://owasp.org/](https://owasp.org/)

## 📧 Contact

**GitHub:** [@Janik00](https://github.com/Janik00)

Questions, feedback, or collaboration opportunities welcome!

## 📜 License

Educational use only. Not licensed for commercial use.

---

**⚡ Stay curious, stay ethical, keep learning! ⚡**
