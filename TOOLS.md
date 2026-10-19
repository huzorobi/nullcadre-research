# Toolchain

**NullCadre is 553 offensive tool modules of its own code**, 312 of them behind the authorisation gate
because they can reach a live target, driven by a catalogue of 157 read-only action specifications.
That is the platform.

Beneath those sit the **79 third-party binaries** listed on this page. They were read, evaluated and wrapped behind
a single interface so that each exposes version, health, capabilities, structured output, errors,
timeouts, cancellation and evidence uniformly. They are the commodity layer: anyone can install them.

**Every one is open source. No commercial scanner is integrated, and none is required to run the
platform.**

Studying their output formats and failure modes was itself a research task: a tool that fails silently
reports nothing, and nothing reads exactly like a clean result.

---

<div align="center">

| Area | | Tools |
|---|---|--:|
| Subdomain and DNS | `██████████████████████` | **9** |
| Web and API scanning | `██████████████████████` | **9** |
| Host and port discovery | `████████████████████` | **8** |
| Mobile and binary analysis | `█████████████████` | **7** |
| Crawl and URL collection | `███████████████` | **6** |
| TLS and protocol posture | `███████████████` | **6** |
| Platform-specific | `███████████████` | **6** |
| Secrets and source exposure | `███████████████` | **6** |
| Content and parameter discovery | `████████████` | **5** |
| Injection | `██████████` | **4** |
| Credentials and tokens | `██████████` | **4** |
| Windows and directory services | `██████████` | **4** |
| Cloud and infrastructure posture | `███████` | **3** |
| Vulnerability intelligence | `█████` | **2** |

</div>

The platform's own modules outnumber these by seven to one, and **312 of its 553 sit behind the
authorisation gate** because they can reach a live target. The remainder parse, correlate, score and
report, and never touch anything.

| Area | Tools |
|---|---|
| Host and port discovery | nmap · masscan · naabu · fping · arp-scan · nbtscan · traceroute · fingerprintx |
| Subdomain and DNS | amass · subfinder · puredns · massdns · dnsgen · dnsrecon · subzy · bbot · theHarvester |
| Crawl and URL collection | katana · gau · waymore · uro · hakoriginfinder · gowitness |
| Content and parameter discovery | ffuf · feroxbuster · gobuster · arjun · kiterunner |
| Web and API scanning | nuclei · nikto · whatweb · wafw00f · OWASP ZAP · domdig · grpcurl · proxify · mitmdump |
| Injection | sqlmap · commix · dalfox · ssrfmap |
| TLS and protocol posture | sslscan · ssh-audit · tlsx · snmpwalk · onesixtyone · ldapsearch |
| Credentials and tokens | hydra · patator · kerbrute · jwt_tool |
| Platform-specific | wpscan · joomscan · droopescan · aem-hacker · s3scanner · cloudbrute |
| Windows and directory services | smbmap · enum4linux-ng · Responder · Metasploit Framework |
| Secrets and source exposure | gitleaks · trufflehog · noseyparker · git-dumper · gitjacker · jsluice |
| Mobile and binary analysis | apktool · apkid · jadx · frida · objection · capa · floss |
| Cloud and infrastructure posture | trivy · prowler · checkov |
| Vulnerability intelligence | cvemap · searchsploit |

Vulnerability-intelligence feeds were integrated on the same terms. They include the national vulnerability
database, the known-exploited-vulnerabilities catalogue, exploit-prediction scoring and public exploit
archives, so that a version match is checked against an actual advisory instead of asserted from a
banner.

---

## What is not described here

These tools are the commodity layer: anyone can install them, and listing them gives nothing away. The
contribution sits above them: enforced scope validation, deterministic validation of every finding, a
confirmation-grade ceiling, and honest coverage reporting. **Which tool feeds which, in what order,
under what conditions, and how output becomes a verdict is not described.**
