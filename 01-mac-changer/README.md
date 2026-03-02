# MAC Address Changer

A Python-based command-line tool for changing network interface MAC addresses on Linux systems.

## 📋 Overview

This tool allows you to spoof your network interface's MAC (Media Access Control) address, which is the unique hardware identifier assigned to network adapters. By changing your MAC address, you can bypass certain network restrictions, obtain new IP assignments, or test network security configurations.

**Version:** 1.0  
**Python:** 3.x  
**Platform:** Linux (Kali, Ubuntu, Debian)  
**Status:** ✅ Functional | 🚧 v2 in planning

## 🎯 Purpose & Use Cases

### Legitimate Uses:
- **Privacy Protection** - Prevent tracking across different networks
- **Network Testing** - Test MAC-based access controls and filters
- **DHCP Troubleshooting** - Obtain new IP address from DHCP server
- **Penetration Testing** - Authorized security assessments
- **Lab Environments** - Educational demonstrations of network concepts

### Common Scenarios:
- Bypassing MAC address filtering on routers
- Testing network access control policies
- Simulating different devices on a network
- Educational demonstrations of OSI Layer 2 addressing

## ✨ Features

- ✅ Change MAC address on any network interface
- ✅ Display current MAC address before modification
- ✅ Verify successful MAC address change
- ✅ Automatic interface up/down management
- ✅ Command-line argument parsing with help documentation
- ✅ Clear success/failure feedback
- ✅ Clean, user-friendly output

## 🛠️ Technical Details

### How It Works:
1. **Reads current MAC** - Uses `ifconfig` to retrieve existing MAC address via regex pattern matching
2. **Disables interface** - Brings network interface down to allow modification
3. **Changes MAC** - Uses `ifconfig hw ether` to set new MAC address
4. **Enables interface** - Brings network interface back up
5. **Verifies change** - Reads MAC again and compares with requested value

### Technologies Used:
- **Python 3** - Core programming language
- **subprocess module** - Execute system commands (`ifconfig`)
- **re module** - Regular expressions for MAC address pattern matching
- **optparse module** - Command-line argument parsing (will migrate to argparse in v2)

### System Commands:
```bash
ifconfig <interface> down                    # Disable interface
ifconfig <interface> hw ether <mac_address>  # Change MAC
ifconfig <interface> up                      # Enable interface
```

## 📦 Requirements

### System Requirements:
- **Operating System:** Linux-based (Kali Linux, Ubuntu, Debian, etc.)
- **Python Version:** 3.6 or higher
- **Privileges:** Root/sudo access required
- **Utilities:** `ifconfig` (net-tools package)

### Python Dependencies:
All dependencies are part of Python standard library:
- `subprocess` - Process execution
- `optparse` - Argument parsing
- `re` - Regular expressions

No external packages required! ✅

### Check Your System:
```bash
# Verify Python 3 is installed
python3 --version

# Verify ifconfig is available
which ifconfig

# If ifconfig is missing, install net-tools:
sudo apt-get install net-tools
```

## 🚀 Installation

### Step 1: Clone the Repository
```bash
git clone https://github.com/Janik00/python-ethical-hacking.git
cd python-ethical-hacking/01-mac-changer
```

### Step 2: Verify Files
```bash
ls -la
# You should see: mac_changer.py and README.md
```

### Step 3: Make Script Executable (Optional)
```bash
chmod +x mac_changer.py
```

### Step 4: Test Help Command
```bash
python3 mac_changer.py --help
```

## 💻 Usage

### Basic Syntax:
```bash
sudo python3 mac_changer.py -i <interface> -m <new_mac_address>
```

### Command-Line Arguments:

| Argument | Long Form | Required | Description |
|----------|-----------|----------|-------------|
| `-i` | `--interface` | ✅ Yes | Network interface to modify (e.g., eth0, wlan0) |
| `-m` | `--mac` | ✅ Yes | New MAC address in XX:XX:XX:XX:XX:XX format |
| `-h` | `--help` | ❌ No | Display help message and exit |

### Finding Your Interface Name:
```bash
# List all network interfaces
ifconfig

# Or use ip command (modern alternative)
ip link show

# Common interface names:
# - eth0, eth1     (Ethernet)
# - wlan0, wlan1   (Wireless)
# - enp0s3         (Predictable naming)
```

## 📸 Examples

### Example 1: Basic MAC Change
```bash
$ sudo python3 mac_changer.py -i eth0 -m 00:11:22:33:44:55

Current MAC address = aa:bb:cc:dd:ee:ff
[+] Changing interface for eth0 to 00:11:22:33:44:55
[+] MAC address changed successfully 00:11:22:33:44:55
```

### Example 2: Change Wireless Interface
```bash
$ sudo python3 mac_changer.py -i wlan0 -m 00:AA:BB:CC:DD:EE

Current MAC address = 12:34:56:78:90:ab
[+] Changing interface for wlan0 to 00:AA:BB:CC:DD:EE
[+] MAC address changed successfully 00:aa:bb:cc:dd:ee
```

### Example 3: Failed Change (Common Issue)
```bash
$ sudo python3 mac_changer.py -i eth0 -m 00:99:88:77:66:55

Current MAC address = 00:11:22:33:44:55
[+] Changing interface for eth0 to 00:99:88:77:66:55
[-] MAC address didn't change
```
**Note:** Failures can occur if the interface is in use or driver doesn't support MAC spoofing.

### Example 4: View Help
```bash
$ python3 mac_changer.py --help

Usage: mac_changer.py [options]

Options:
  -h, --help            show this help message and exit
  -i INTERFACE, --interface=INTERFACE
                        Interface to change MAC address
  -m NEW_MAC, --mac=NEW_MAC
                        New MAC address
```

### Example 5: Missing Arguments
```bash
$ sudo python3 mac_changer.py -i eth0

Usage: mac_changer.py [options]

mac_changer.py: error: [-] Please specify a new MAC address, use --help for more information.
```

## 🎓 What I Learned

Building this tool taught me:

### Python Skills:
- **Functions and modularity** - Organizing code into reusable functions
- **Subprocess module** - Executing system commands and capturing output
- **Regular expressions** - Pattern matching for MAC address extraction
- **Command-line parsing** - Using optparse for user input
- **String manipulation** - Formatting output and concatenation
- **Conditional logic** - Validating results and providing feedback

### Networking Concepts:
- **MAC addresses** - Layer 2 addressing in the OSI model
- **Network interfaces** - How operating systems manage network adapters
- **ifconfig utility** - Linux network configuration tool
- **DHCP behavior** - How MAC addresses affect IP assignment

### Security Principles:
- **Attack surface** - Understanding MAC-based access controls
- **Spoofing techniques** - Methods attackers use to hide identity
- **Defense mechanisms** - Why networks might filter by MAC address
- **Ethical considerations** - Importance of authorized testing only

### Linux Administration:
- **Privilege escalation** - When and why sudo is required
- **Network stack** - How interface state affects connectivity
- **System commands** - Integration between Python and shell utilities

## ⚠️ Important Warnings

### Legal Disclaimer:
**FOR EDUCATIONAL AND AUTHORIZED TESTING ONLY**

- ✅ **DO:** Use on your own devices and networks
- ✅ **DO:** Use in authorized penetration testing engagements
- ✅ **DO:** Use in isolated lab/VM environments
- ❌ **DON'T:** Use on networks without permission
- ❌ **DON'T:** Use to bypass security on public networks
- ❌ **DON'T:** Use for any illegal activities

**Unauthorized network access is illegal.** I am not responsible for misuse of this tool.

### Technical Limitations:
- **Requires root** - Won't work without sudo/root privileges
- **Interface disruption** - Network connection will drop briefly during change
- **Driver support** - Some network drivers don't support MAC spoofing
- **Detection** - Advanced networks may detect MAC changes
- **Persistence** - MAC reverts to original after reboot (not permanent)

## 🐛 Known Issues

### Current Limitations (v1.0):

1. **No Input Validation**
   - Accepts invalid MAC formats (e.g., "hello", "ZZ:ZZ:ZZ:ZZ:ZZ:ZZ")
   - No check for proper hexadecimal values
   - **Workaround:** User must ensure correct format XX:XX:XX:XX:XX:XX

2. **Uses Deprecated ifconfig**
   - `ifconfig` is deprecated in favor of `ip` command
   - May not be available on newer Linux distributions
   - **Workaround:** Install net-tools package

3. **Limited Error Handling**
   - Doesn't catch subprocess errors gracefully
   - No check if interface exists before attempting change
   - **Workaround:** User must verify interface name manually

4. **Python 2 vs 3 Differences**
   - Tutorial uses Python 2, code adapted for Python 3
   - Requires `.decode()` on subprocess output
   - **Solution:** Code already adapted, use Python 3

5. **No Restore Function**
   - Cannot easily restore original MAC address
   - **Workaround:** Reboot system or manually note original MAC

6. **Linux Only**
   - Doesn't work on Windows or macOS
   - Different commands needed for cross-platform support
   - **Future:** v2 will address this

## 🗺️ Roadmap (v2 - Planned Improvements)

### High Priority:
- [ ] **Input validation** - Regex validation for MAC address format
- [ ] **Modern ip command** - Replace `ifconfig` with `ip link set`
- [ ] **Error handling** - Try/catch blocks for subprocess failures
- [ ] **Interface validation** - Check if interface exists before modification
- [ ] **argparse migration** - Replace optparse with modern argparse

### Medium Priority:
- [ ] **Restore original MAC** - Save and restore original MAC address
- [ ] **Random MAC generator** - Option to generate random valid MAC
- [ ] **Verbose mode** - Detailed logging for debugging
- [ ] **Quiet mode** - Minimal output for scripting
- [ ] **Configuration file** - Save preferred settings

### Low Priority:
- [ ] **Cross-platform support** - Windows and macOS compatibility
- [ ] **GUI version** - Graphical interface option
- [ ] **Batch operations** - Change multiple interfaces at once
- [ ] **Whitelist/blacklist** - Specify allowed/disallowed MACs
- [ ] **Logging** - Save change history to file

## 🔧 Troubleshooting

### Common Issues:

**Issue: "Permission denied"**
```bash
# Solution: Run with sudo
sudo python3 mac_changer.py -i eth0 -m 00:11:22:33:44:55
```

**Issue: "MAC address didn't change"**
```bash
# Possible causes:
# 1. Interface is active/in use
# 2. Network driver doesn't support MAC spoofing
# 3. Invalid MAC address format

# Try:
sudo ifconfig eth0 down
sudo python3 mac_changer.py -i eth0 -m 00:11:22:33:44:55
```

**Issue: "ifconfig: command not found"**
```bash
# Solution: Install net-tools
sudo apt-get update
sudo apt-get install net-tools
```

**Issue: "No MAC address found"**
```bash
# Solution: Check interface name
ifconfig  # or: ip link show

# Verify interface exists
ip link show eth0
```

**Issue: Network connection lost**
```bash
# This is normal! Interface goes down during change.
# Connection should restore after change completes.
# If not, manually bring interface up:
sudo ifconfig eth0 up
```

## 📚 Additional Resources

### Learning Materials:
- **MAC Addresses:** [Wikipedia - MAC Address](https://en.wikipedia.org/wiki/MAC_address)
- **ifconfig Manual:** `man ifconfig`
- **Python subprocess:** [Python Docs - subprocess](https://docs.python.org/3/library/subprocess.html)
- **Regular Expressions:** [Python Docs - re module](https://docs.python.org/3/library/re.html)

### Related Tools:
- **macchanger** - Advanced Linux MAC changing utility
- **ip command** - Modern replacement for ifconfig
- **ethtool** - Network driver and hardware settings tool

### Security References:
- **OWASP** - Web application security
- **Kali Linux Tools** - Penetration testing toolkit
- **Metasploit** - Exploitation framework

## 🤝 Contributing

Found a bug? Have a suggestion? Contributions welcome!

### How to Contribute:
1. Fork the repository
2. Create a feature branch (`git checkout -b feature/improvement`)
3. Make your changes
4. Test thoroughly
5. Commit (`git commit -m 'Add feature'`)
6. Push (`git push origin feature/improvement`)
7. Open a Pull Request

### Contribution Ideas:
- Python 3 improvements
- Better error messages
- Input validation implementation
- Cross-platform support
- Documentation enhancements
- Bug fixes

## 📧 Contact

**Author:** Janik  
**GitHub:** [@Janik00](https://github.com/Janik00)  
**Repository:** [python-ethical-hacking](https://github.com/Janik00/python-ethical-hacking)

Questions, feedback, or collaboration welcome!

## 📝 License

Educational use only. Not licensed for commercial use.

## 🙏 Acknowledgments

- **Zaid Sabih** - Course instructor (Zsecurity)
- **Python Community** - Documentation and resources
- **Kali Linux Team** - Security testing platform
- **Open Source Contributors** - Tools and libraries used

---

**⚡ Part of my ethical hacking learning journey ⚡**

[← Back to Main Repository](../)
