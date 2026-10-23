# Black Lantern Security PoCs

[![License](https://img.shields.io/badge/license-AGPLv3-FF8400.svg)](https://github.com/blacklanternsecurity/PoCs/blob/main/LICENSE)

Proof-of-concept exploits and [Nuclei](https://github.com/projectdiscovery/nuclei) templates published by [Black Lantern Security](https://www.blacklanternsecurity.com) (BLS) to raise awareness of security vulnerabilities and help defenders identify and remediate them.

> [!WARNING]
> Everything in this repository is provided for informational and educational purposes only. Use it only against systems you own or have explicit, written permission to test. You use this content entirely at your own risk. Read the full [Disclaimer](#disclaimer) before using anything here.

## Repository Layout

| Directory | Contents |
| --- | --- |
| `nuclei-templates/` | Nuclei templates for detecting vulnerable systems |
| `exploits/` | Proof-of-concept exploit code |

Each entry documents the affected product and versions, the vulnerability, references (CVE identifiers, advisories), and remediation guidance where available.

## Usage

### Nuclei Templates

```bash
# Run a single template against a target
nuclei -u https://target.example.com -t nuclei-templates/<template>.yaml

# Run every template in the directory against a list of targets
nuclei -l targets.txt -t nuclei-templates/
```

### Exploits

See the README in each exploit's directory for requirements and usage instructions.

## Disclaimer

The contents of this repository, including all proof-of-concept code, exploits, Nuclei templates, and documentation, are provided for informational, educational, and security awareness purposes only. They are intended to help security professionals, system administrators, and vendors understand vulnerabilities, verify exposure, and prioritize remediation.

By accessing or using any content in this repository, you acknowledge and agree to the following:

1. **Authorized use only.** You will use this content only against systems that you own or that you have explicit, written authorization to test. Unauthorized access to computer systems is illegal in most jurisdictions, including under the U.S. Computer Fraud and Abuse Act (CFAA) and equivalent laws in other countries.
2. **Use at your own risk.** All content is provided "as is," without warranty of any kind, express or implied. Proof-of-concept code may be unstable and may cause crashes, data loss, service disruption, or other unintended effects, even on systems you are authorized to test.
3. **No liability.** In no event shall Black Lantern Security, its employees, or contributors be liable for any direct, indirect, incidental, special, consequential, or other damages, or for any legal consequences, arising from the use or misuse of this content.
4. **Compliance is your responsibility.** You are solely responsible for ensuring that your use complies with all applicable laws, regulations, contractual obligations, and rules of engagement.
5. **No endorsement of misuse.** BLS does not condone or support the use of this content for malicious or illegal purposes.

The disclaimer of warranty and limitation of liability in Sections 15 and 16 of the [GNU Affero General Public License v3.0](LICENSE) also apply.

If you do not agree to these terms, do not use the contents of this repository.

## License

This project is licensed under the [GNU Affero General Public License v3.0](LICENSE).
