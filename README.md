# Google Cybersecurity Certificate Portfolio

Portfolio activities I completed for the Google Cybersecurity Professional Certificate on Coursera. Apart from the professional statement, each one is based on a fictional scenario from the course: I worked through the task (an audit, an incident analysis, Linux and SQL work, a risk assessment, incident documentation, and a Python algorithm) and wrote up my approach and findings.

## Portfolio items

| # | Item | What it covers |
|---|---|---|
| 1 | [Professional statement](01-professional-statement.md) | My background and why I'm moving into AI security, with a focus on agentic AI systems. |
| 2 | [Controls and compliance checklist](02-controls-and-compliance-checklist.md) | An internal audit of a fictional toy company, Botium Toys, against common security controls and PCI DSS, GDPR, and SOC best practices, with recommendations. |
| 3 | [Incident report analysis](03-incident-report-analysis.md) | An ICMP flood (DoS) attack, analyzed using the five functions of the NIST Cybersecurity Framework. |
| 4 | [File permissions in Linux](04-file-permissions-in-linux.md) | Reviewing and correcting file and directory permissions with `ls` and `chmod`. |
| 5 | [Apply filters to SQL queries](05-apply-filters-to-sql-queries.md) | Investigating login attempts and employee machines with SQL filters (`AND`, `OR`, `NOT`, `LIKE`). |
| 6 | [Vulnerability assessment report](06-vulnerability-assessment-report.md) | A risk assessment of a publicly accessible database server using NIST SP 800-30 Rev. 1, with a remediation plan. |
| 7 | [Incident handler's journal](07-incident-handlers-journal.md) | Five entries documenting incident investigations and tool use (Wireshark, tcpdump, VirusTotal), mapped to the phases of the NIST incident response lifecycle. |
| 8 | [Algorithm for file updates in Python](08-algorithm-for-file-updates-in-python.md) | A Python algorithm that removes IP addresses from an allow list file. |

## Notes

- **Fictional scenarios:** All organizations, people, incidents, and IP addresses in items 2-8 come from the course's fictional scenarios. The IP addresses are private (`192.168.x.x`) addresses.
- **NIST Cybersecurity Framework version:** Item 3 uses the five core functions of NIST CSF 1.1 (Identify, Protect, Detect, Respond, Recover), as taught in the course. NIST CSF 2.0, released on February 26, 2024, added a sixth function, Govern.
- **NIST incident response lifecycle version:** Item 7 uses the four phases from NIST SP 800-61 Rev. 2 (Preparation; Detection and Analysis; Containment, Eradication, and Recovery; Post-Incident Activity), as taught in the course. NIST SP 800-61 Rev. 3, published in April 2025, supersedes Rev. 2 and organizes incident response around the CSF 2.0 functions instead.

## Credit

These activities are from the [Google Cybersecurity Professional Certificate](https://www.coursera.org/professional-certificates/google-cybersecurity) on Coursera. The scenarios, templates, section headings, and the journal's reflection questions were provided by the course. The code in item 8 was written in the course's lab notebook, which provided the comments and some of the starter code, and I completed the rest. The written analysis is my own.

## License

The written documents are © 2026 Jacob Ma and licensed under [CC BY 4.0](LICENSE). The code (the SQL queries, Linux commands, and Python code) is licensed under the [MIT License](LICENSE-CODE).

Neither license covers the course-provided material listed under Credit.
