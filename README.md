# Samuel Yoder

**M.S. Cybersecurity @ NYU Tandon · Offensive security · OSIRIS Lab**

I'm a graduate student working toward offensive security and red team roles. Most of my time goes to vulnerability research and fuzzing of C/C++ code, with detection engineering on the side so I understand what the defender sees.

[Portfolio](https://dreadpiratesamuel.github.io/portfolio/) · [LinkedIn](https://www.linkedin.com/in/samueldyoder/) · sy5017@nyu.edu

## Right now

- Member of the OSIRIS Lab, NYU's student-run offensive security research lab (reverse engineering, binary exploitation, vulnerability research), and training to join its infrastructure team
- Organizing staff for the 2026 CSAW CTF Qualifiers
- Waiting on an upstream fix for a vulnerability I reported, so I can publish the harness and writeup
- Studying for CompTIA Security+ (December 2026)

## Featured work

### [Sigma Detection Lab](https://github.com/DreadPirateSamuel/Sigma-Detection-Lab)

Six Windows detection rules written in Sigma, each mapped to a MITRE ATT&CK technique, converted to Elastic EQL and measured against real data instead of synthetic logs.

- Replayed 37,364 events from recorded attack simulations into an Elasticsearch/Kibana lab, alongside live Sysmon telemetry from my own host
- Evaluated every rule against 1.79 million benign Windows events and published the false-positive counts per rule, including the ones that are not zero
- Tuned the LSASS-access and scheduled-task rules from that evidence, and kept the original versions in the repo for comparison
- Verified each converted query against an exact-count query (24 of 24 match), with offline regression tests so the results can be reproduced

`Sigma` `Elastic EQL` `Sysmon` `MITRE ATT&CK` `Docker` `Python`

### Open-source vulnerability research (coordinated disclosure in progress)

A fuzzing campaign against the model-file parser of an open-source C++ machine-learning inference library.

- Wrote a libFuzzer harness and instrumented the full build with AddressSanitizer and UndefinedBehaviorSanitizer
- Found an uncontrolled memory allocation (CWE-789) reachable from a small crafted model file, triaged it to root cause, and checked advisories and the issue tracker to confirm it was unreported
- Reported it privately to the maintainer. The target, harness, triage notes and writeup will be published here once a fix ships

`C++` `libFuzzer` `ASan/UBSan` `GDB`

## More projects

| Project | What it is |
|---|---|
| [Malware Traffic Classifier](https://github.com/DreadPirateSamuel/Malware-Traffic-Classifier) | XGBoost model that labels network flows as benign or malicious, trained on UNSW-NB15, with a Streamlit front end |
| [Deep-TAO Replication](https://github.com/DreadPirateSamuel/Deep-TAO-Replication) | CNN that classifies astronomical transients from about 17,000 FITS images; average F1 of 0.94 across six classes |
| [Portfolio](https://github.com/DreadPirateSamuel/portfolio) | Source for my portfolio site (React, Vite, GitHub Pages) |

## Toolbox

| Area | Tools |
|---|---|
| Languages | C, C++, Python, x86-64 assembly, Bash, SQL, Java, JavaScript |
| Vulnerability research | libFuzzer, ASan/UBSan, GDB, Ghidra, pwntools, strace |
| Web and network | Burp Suite, Netcat, packet analysis, TCP/IP |
| Detection engineering | Sigma, Elasticsearch/Kibana, EQL, Sysmon, Winlogbeat, MITRE ATT&CK |
| Systems | Linux, Docker, WSL2, QEMU/KVM, AWS EC2, Git |

## Education

- **New York University, Tandon School of Engineering** · M.S. Cybersecurity, expected May 2028 · Merit Scholarship
- **Florida State University** · Computer Science, May 2026 · magna cum laude

## Get in touch

I'm looking for Summer 2027 internships in penetration testing, red teaming, vulnerability research and application security. Email is the fastest way to reach me: sy5017@nyu.edu
