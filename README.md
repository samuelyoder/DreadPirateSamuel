# Samuel Yoder

**M.S. Cybersecurity @ NYU Tandon · Offensive Security · OSIRIS Lab**

I'm a graduate student working toward offensive security and red team roles.

[Portfolio](https://samuelyoder.github.io/portfolio/) · [LinkedIn](https://www.linkedin.com/in/samueldyoder/) · sam061704@icloud.com · sy5017@nyu.edu

## Right now

- Member of [OSIRIS Lab](https://osiris.cyber.nyu.edu/), NYU's student-run offensive security research lab (reverse engineering, binary exploitation, vulnerability research), and training to join its infrastructure team
- Organizing staff for the 2026 CSAW CTF Qualifiers
- Waiting on an upstream fix for a vulnerability I reported, so I can publish the harness and writeup
- Working through Hack The Box's AI Red Teamer path (target: November 2026)
- Studying for CompTIA Security+ (December 2026)

## Featured work

### Open-source vulnerability research (coordinated disclosure in progress)

A fuzzing campaign against the model-file parser of an open-source C++ machine-learning inference library.

- Wrote a libFuzzer harness and instrumented the full build with AddressSanitizer and UndefinedBehaviorSanitizer
- Found an uncontrolled memory allocation (CWE-789) reachable from a small crafted model file, triaged it to root cause, and checked advisories and the issue tracker to confirm it was unreported
- Reported it privately to the maintainer. The target, harness, triage notes and writeup will be published here once a fix ships

`C++` `libFuzzer` `ASan/UBSan` `GDB`

### [Sigma Detection Lab](https://github.com/samuelyoder/Sigma-Detection-Lab)

Six Windows detection rules written in Sigma, each mapped to a MITRE ATT&CK technique, converted to Elastic EQL and measured against real data instead of synthetic logs.

- Replayed 37,364 events from recorded attack simulations into an Elasticsearch/Kibana lab, alongside live Sysmon telemetry from my own host
- Evaluated every rule against 1.79 million benign Windows events and published the false-positive counts per rule, including the ones that are not zero
- Tuned the LSASS-access and scheduled-task rules from that evidence, and kept the original versions in the repo for comparison
- Verified each converted query against an exact-count query (24 of 24 match), with offline regression tests so the results can be reproduced

`Sigma` `Elastic EQL` `Sysmon` `MITRE ATT&CK` `Docker` `Python`

### [Secure Flask eCommerce Application](https://github.com/samuelyoder/eCommerce-Website-Project)

A Flask/SQLite store with customer and admin roles and tiered rewards pricing. I reviewed it as an attacker would, reproduced each finding against the running app, then fixed it.

- Found and fixed privilege escalation through public registration, admin session forgery from a hardcoded signing key, plaintext password storage and missing CSRF protection
- Found a data-file injection: line breaks in a registration name were written to the app's data file as new records, which created a working admin account on the next restart
- Fixed integrity bugs that moved purchases and discounts between customers after deletes and restarts
- Added a 26-test regression suite that checks each fix and that shopping and rewards still work

`Python` `Flask` `SQLite` `Web security` `Secure code review`

### [Linux Kernel Elevator Scheduler](https://github.com/samuelyoder/linux-kernel-elevator)

A loadable kernel module in C that runs an elevator scheduler inside the Linux kernel, driven by three custom system calls added to a self-built 6.16 kernel.

- A kernel thread runs a SCAN-style scheduling loop over per-floor FIFO queues, with weight and passenger limits
- One mutex protects all shared state across the worker thread, system-call callers and `/proc` readers. The worker never sleeps while holding it
- An unload-safe bridge lets the built-in system calls reach the module and return `-ENOSYS` while it is not loaded
- Also includes system-call tracing with `strace` and a `/proc/timer` module built with `seq_file`

`C` `Linux kernel` `kthreads` `System calls` `/proc`

## More projects

| Project | What it is |
|---|---|
| [Malware Traffic Classifier](https://github.com/samuelyoder/Malware-Traffic-Classifier) | XGBoost model that labels network flows as benign or malicious, trained on UNSW-NB15, with a Streamlit front end |
| [Deep-TAO Replication](https://github.com/samuelyoder/Deep-TAO-Replication) | CNN that classifies astronomical transients from about 17,000 FITS images; average F1 of 0.94 across six classes |
| [Portfolio](https://github.com/samuelyoder/portfolio) | Source for my portfolio site (React, Vite, GitHub Pages) |

## Toolbox

| Area | Tools |
|---|---|
| Languages | C, C++, Python, x86-64 assembly, Bash, SQL, Java, JavaScript |
| Vulnerability research | libFuzzer, ASan/UBSan, GDB, Ghidra, pwntools, strace |
| Web and network | Burp Suite, Flask, Netcat, packet analysis, TCP/IP |
| Detection engineering | Sigma, Elasticsearch/Kibana, EQL, Sysmon, Winlogbeat, MITRE ATT&CK |
| Systems | Linux, Linux kernel modules, Docker, WSL2, QEMU/KVM, AWS EC2, Git |

## Education

- **New York University, Tandon School of Engineering** · M.S. Cybersecurity, expected May 2028 · Merit Scholarship
- **Florida State University** · B.A. Computer Science, May 2026 · Magna Cum Laude· Florida Bright Futures Scholarship

## Get in touch

I'm looking for Summer 2027 internships in penetration testing, red teaming, vulnerability research and application security. Email is the fastest way to reach me: sam061704@icloud.com · sy5017@nyu.edu
