---
draft: false
date: 2023-05-31
categories:
    - technology
    - python
    - cyber-security
    - hacking
---

# HELLO TEST


!!! Abtract 
    My review and open source contribution to "Violent Python: A Cookbook for Hackers, Forensic Analysts, Penetration Testers and Security Engineers" 

In early 2020 when I first ventured into the world of ethical computer hacking and cyber security, I stumbled upon an incredible book called [Violent Python](https://github.com/tanc7/hacking-books/blob/master/Violent%20Python%20-%20A%20Cookbook%20for%20Hackers%2C%20Forensic%20Analysts%2C%20Penetration%20Testers%20and%20Security%20Engineers.pdf) by TJ O'Connor. The book explores the practical applications and features of the now deprecated [Python 2.6](https://www.python.org/download/releases/2.6/) applied to offensive security techniques such as [network scanning](https://en.wikipedia.org/wiki/Port_scanner), [packet manipulation](https://en.wikipedia.org/wiki/Packet_crafting), [password cracking](https://en.wikipedia.org/wiki/Password_cracking) and [web reconnaissance](https://en.wikipedia.org/wiki/Reconnaissance). While the key takeaways from the book were invaluable, and the book offers a practical guide into the world of cyber security, it is important to note that at the time of writing this, Python 2.6 reached its end-of-life status in October 2013 and is no longer officially supported. 

> [Python 3](https://www.python.org/downloads/) introduced several backward-incompatible [changes](https://docs.python.org/3/howto/pyporting.html) including:

1. Print Statements
2. Integer Division
3. Unicode Handling 
4. Module Modifications 
5. Syntax Changes

This left me in a bind while following the book, as code snippets and step-by-step instructions didn't work on a python3 interpreter which I had installed at that time. Resulting in many unintended syntax errors and exception raises. 

---

### The Project

I found a [guy](https://github.com/EONRaider) on Github that had identified the same problem of language backward compatibility with programming books, 
at the time that I stumbled upon this problem he had made a full source code conversion of the book [Black Hat Python](https://github.com/bhavyagoel/BlackArch/blob/main/Black%20Hat%20Python%2C%202nd%20Edition%20by%20Justin%20Seitz%20%20Tim%20Arnold%20%5BJustin%20Seitz%5D.pdf), by Justin Seitz. He'd started a repository on the exact book I was looking to refactor, so I started submitting pull requests to his repository and we both started hacking on a [full release](https://github.com/EONRaider/violent-python3). 


> This project setup assumes you are on a linux environment

**1. Copy this snippet into a file called `setup.sh`** 
```bash
#!/bin/bash
git clone https://github.com/EONRaider/violent-python3
python3 -m venv venv
source venv/bin/activate
pip install -r requirements.txt
```

**2. Make the file an executable, and run the environment setup:**
```bash
user@host:~/DIR$ chmod +x setup.sh
user@host:~/DIR$ ./setup.sh
```
---

### Release Notes - [0.1.0](https://github.com/EONRaider/violent-python3)

!!! Info "Python 3 compatibility" 
    The code has been fully converted to Python 3, reformatted to comply with PEP8 standards and refactored to eliminate dependency issues involving the implementation of deprecated libraries.

**Added:**
- Directory and file names are now more intuitive and reflect chapter contents.
- Adopted PEP 8 naming conventions for files, variables, functions, classes, and methods.
- Refactored code in Chapter 5; however, note that some examples may be outdated or impractical.

**Updated:**
- Replaced string concatenation with string interpolation for better readability.
- Replaced deprecated 'optparse' library with 'argparse' for command-line argument parsing.
- Improved error handling by replacing generic exceptions with specific clauses.
- Employed context managers to ensure files and databases are properly closed.

**Removed:**
- Removed encoding comments, as UTF-8 is now the standard in Python 3.
- Kept global variables despite not being a best practice, to maintain the original code's logic.

**Unchanged:**
- Code in Chapter 6 for Google and Twitter APIs is outdated and not refactored. 

---

### Refactoring Summary

> The following includes the changes made in our full release, files not listed below can be assumed to have been refactored in one way or another as established in the [Realease Notes]() section.

| Sections | Changes |
| :--- | :--- | 
| [chapter01/vuln_scanner.py](https://github.com/EONRaider/violent-python3/blob/master/chapter01/vuln_scanner.py) | Moved iteration control into the conditional statement in the main function to handle OSError for non-existent files. |
| [chapter02/nmap_scan.py](https://github.com/EONRaider/violent-python3/blob/master/chapter02/nmap_scan.py) | Replaced deprecated optparse with argparse. Moved iteration into nmap_scan function for efficiency. |
| [chapter02/ssh_command.py](https://github.com/EONRaider/violent-python3/blob/master/chapter02/ssh_command.py) | Moved initialization code into __main__ scope, renamed conflicting variables, and decoded prompt information for readability. |
| [chapter02/ssh_brute.py](https://github.com/EONRaider/violent-python3/blob/master/chapter02/ssh_brute.py) | Fixed import statement and indentation errors. |
| [chapter02/ssh_brutekey.py](https://github.com/EONRaider/violent-python3/blob/master/chapter02/ssh_brutekey.py) | Added a compressed archive with necessary pre-generated keys due to an inaccessible URL. |
| [chapter02/ssh_botnet.py](https://github.com/EONRaider/violent-python3/blob/master/chapter02/ssh_botnet.py) | Removed an unused import, reorganized code under __main__, and unified command issuance. |
| [chapter02/conficker.py](https://github.com/EONRaider/violent-python3/blob/master/chapter02/conficker.py) | Removed an unused call to the sys library. |
| [chapter03/discover_networks.py](https://github.com/EONRaider/violent-python3/blob/master/chapter03/discover_networks.py) | Reimplemented using WiGLE API via the requests library, and added exception handling. |
| [chapter03/pdf_read.py](https://github.com/EONRaider/violent-python3/blob/master/chapter03/pdf_read.py) | Replaced deprecated PyPDF with PyPDF4. |
| [chapter03/exif_fetch.py](https://github.com/EONRaider/violent-python3/blob/master/chapter03/exif_fetch.py) | Added an argument to BeautifulSoup for compatibility. |
| [chapter03/skype_parse.py & firefox_parse.py](https://github.com/EONRaider/violent-python3/blob/master/chapter03/firefox_parse.py) | Added example files for convenience. |
| [chapter03/iphone_messages.py](https://github.com/EONRaider/violent-python3/blob/master/chapter03/iphone_messages.py) | Refactored but remains untested due to unavailability of files. |
| [chapter04/geo_ip.py](https://github.com/EONRaider/violent-python3/blob/master/chapter04/geo_ip.py) | Replaced deprecated pygeoip with geoip2, and added CLI via argparse. |
| [chapter04/print_direction.py](https://github.com/EONRaider/violent-python3/blob/master/chapter04/print_direction.py) | Fixed file opening argument to handle UnicodeDecodeError. |
| [chapter04/find_ddos.py](https://github.com/EONRaider/violent-python3/blob/master/chapter04/find_ddos.py) | Corrected the output to display the destination address. |
| [chapter04/test_domain_flux.py](https://github.com/EONRaider/violent-python3/blob/master/chapter04/test_domain_flux.py) | Modified packet analysis logic for accuracy. |
| [chapter05/blue_bug.py](https://github.com/EONRaider/violent-python3/blob/master/chapter05/blue_bug.py) | Fixed object reference and noted dependency installations. |
| [chapter05/ftp_sniff.py](https://github.com/EONRaider/violent-python3/blob/master/chapter05/ftp_sniff.py) | Corrected logic for displaying username and password. |
| [chapter05/ninja_print.py](https://github.com/EONRaider/violent-python3/blob/master/chapter05/ninja_print.py) | Noted the code remains in Python 2 due to library limitations. |
| [chapter05/ & chapter06/```__init__.py```](https://github.com/EONRaider/violent-python3/tree/master/chapter05) | module imports. |
| [chapter06/anon_proxy.py & anon_browser.py](https://github.com/EONRaider/violent-python3/blob/master/chapter06/anon_browser.py) | Re-implemented with MechanicalSoup library and updated related modifications. |
| [chapter06/link_parser.py](https://github.com/EONRaider/violent-python3/blob/master/chapter06/link_parser.py) | Updated implementations of re and bs4. |

### In conclusion

The changes encompass a series of significant refactoring efforts to improve the efficiency readability and compatibility of the Python project. With the update of deprecated libraries, restructuring of code examples, and the inclusion of dependency files. 

My exposure to this project has been an enlightening journey, particularly as it marked my first exploration into the expansive realm of computer exploitation. Through my involvement, I've gained a wealth of knowledge on hacking computer systems.

> I would like to take this opportunity to thank [TJ O'Connor](https://www.amazon.com/Violent-Python-Cookbook-Penetration-Engineers/dp/1597499579) for writing this marvellous book, and [EONRaider](https://github.com/EONRaider) for creating this project. 

---

