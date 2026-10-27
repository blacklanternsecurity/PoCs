# Black Lantern Security PoCs

[![License](https://img.shields.io/badge/license-AGPLv3-FF8400.svg)](https://github.com/blacklanternsecurity/PoCs/blob/main/LICENSE)

Proof-of-concept exploits and [Nuclei](https://github.com/projectdiscovery/nuclei) templates published by [Black Lantern Security](https://www.blacklanternsecurity.com) (BLS) to raise awareness of security vulnerabilities and help defenders identify and remediate them.

> [!WARNING]
> Everything in this repository is provided for informational and educational purposes only. Use it only against systems you own or have explicit, written permission to test. You use this content entirely at your own risk. Read the full [Disclaimer](#disclaimer) before using anything here.

## Repository Layout

Each vulnerability has its own directory named after its CVE identifier:

```
CVE-YYYY-NNNNNN/
├── nuclei-template.yaml          # Nuclei detection template
├── nuclei-template-active.yaml   # Active verification variant, where provided
└── ...                           # Exploit code and notes, where published
```

Each template's `info` block documents the affected product and versions, the vulnerability, references (CVE identifiers, advisories), and remediation guidance.

| CVE | Name | Templates |
| --- | --- | --- |
| [CVE-2026-109618](CVE-2026-109618/) | PHP OOM corruption (php2shell) | `nuclei-template.yaml` |
| [CVE-2026-109619](CVE-2026-109619/) | PHP `session.upload_progress` use-after-free (php2shell) | `nuclei-template.yaml`, `nuclei-template-active.yaml` |
| [CVE-2026-111497](CVE-2026-111497/) | Node.js Brotli decoder out-of-bounds write (Node2Shell) | `nuclei-template.yaml` |
| [CVE-2026-115560](CVE-2026-115560/) | PHP session serialize handler mismatch | `nuclei-template.yaml` |

## Usage

### Nuclei Templates

```bash
# Run a single template against a target
nuclei -u https://target.example.com -t CVE-2026-109619/nuclei-template.yaml

# Run a template against a list of targets
nuclei -l targets.txt -t CVE-2026-109619/nuclei-template.yaml
```

Templates tagged `active` or `destructive` send large or malformed requests that can crash worker processes. Read the template's `description` before running it.

### Exploits

Exploit code, where published, sits in the CVE's directory alongside usage notes.

## Disclaimer

The contents of this repository, including all proof-of-concept code, exploits, Nuclei templates, and documentation, are provided for informational, educational, and security awareness purposes only. They are intended to help security professionals, system administrators, and vendors understand vulnerabilities, verify exposure, and prioritize remediation.

By accessing or using any content in this repository, you acknowledge and agree to the following:

1. **Authorized use only.** You will use this content only against systems that you own or that you have explicit, written authorization to test. Unauthorized access to computer systems is illegal in most jurisdictions, including under the U.S. Computer Fraud and Abuse Act (CFAA) and equivalent laws in other countries.
2. **Disclaimer of Warranties.** TO THE MAXIMUM EXTENT PERMITTED BY APPLICABLE LAW, ALL CONTENT IS PROVIDED “AS IS” AND “AS AVAILABLE,” WITH ALL FAULTS, AND BLS OPS DISCLAIMS ALL WARRANTIES, EXPRESS, IMPLIED, OR STATUTORY, INCLUDING WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE, TITLE, NON-INFRINGEMENT, ACCURACY, COMPLETENESS, AND THAT THE CONTENT IS SAFE, ERROR-FREE, OR WILL DETECT ANY VULNERABILITY. Content may be unstable and may cause crashes, data loss, service disruption, security degradation, or other harm, even on authorized systems. Detection templates may produce false positives or false negatives.
3. **Limitation of Liability.** TO THE MAXIMUM EXTENT PERMITTED BY APPLICABLE LAW, IN NO EVENT WILL BLS OPS, LLC, ITS AFFILIATES, OR ITS OR THEIR OFFICERS, DIRECTORS, EMPLOYEES, CONTRACTORS, AGENTS, CONTRIBUTORS, LICENSORS, SUCCESSORS, OR ASSIGNS (THE “BLS PARTIES”) BE LIABLE FOR ANY DIRECT, INDIRECT, INCIDENTAL, SPECIAL, CONSEQUENTIAL, EXEMPLARY, OR PUNITIVE DAMAGES, OR FOR LOSS OF DATA, PROFITS, REVENUE, OR BUSINESS, BUSINESS INTERRUPTION, OR ANY FINES, PENALTIES, OR THIRD-PARTY CLAIMS, ARISING OUT OF OR RELATING TO THE CONTENT OR ITS USE OR MISUSE, UNDER ANY THEORY OF LIABILITY (CONTRACT, TORT INCLUDING NEGLIGENCE, STRICT LIABILITY, OR OTHERWISE), EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGES. THE BLS PARTIES' AGGREGATE LIABILITY WILL NOT EXCEED US$100. Nothing in this Notice excludes liability that cannot be excluded under applicable law; in such jurisdictions, liability is limited to the minimum extent permitted.
4. **Compliance is your responsibility.** You are solely responsible for ensuring that your use complies with all applicable laws, regulations, contractual obligations, and rules of engagement.
5. **No endorsement of misuse.** BLS does not condone or support the use of this content for malicious or illegal purposes.
6. **Purpose of Publication; Non-U.S. Law.** BLS publishes this content for defensive security research, vulnerability verification, and remediation, and not with intent that it be used to commit any offense. If the laws of your jurisdiction restrict the possession, creation, or distribution of security testing tools, do not download or use this content.
7. **Data Protection.** If your testing may process personal data, you act as the controller (or equivalent) and are solely responsible for compliance with the GDPR, UK GDPR, and other data protection laws. BLS does not receive or process data through your use of the content.

The disclaimer of warranty and limitation of liability in Sections 15 and 16 of the [GNU Affero General Public License v3.0](LICENSE) also apply.

You may not be bound by contract merely by viewing this repository. However, by downloading, cloning, executing, modifying, or redistributing any content, you represent that you have read and understood this Notice. If you do not agree to these terms, do not use the contents of this repository.

## License

This project is licensed under the [GNU Affero General Public License v3.0](LICENSE).
