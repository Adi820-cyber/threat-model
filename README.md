# Threat Model Documentation

This repository provides a comprehensive threat modeling report for a sample vulnerable web application, following industry best practices and frameworks such as STRIDE and PASTA.

## Contents
- `threat-model.tex`: Main LaTeX document with diagrams, threat analysis, and security controls.
- `sample.bib`: Bibliography with references to key threat modeling literature.
- `system-context.puml` and `stride-analysis.puml`: PlantUML diagrams for system context and STRIDE analysis.
- `images/`: (To be generated) PNG diagrams for inclusion in the report.

## Key Frameworks Covered
- **STRIDE** (Microsoft): Spoofing, Tampering, Repudiation, Information Disclosure, Denial of Service, Elevation of Privilege
- **PASTA**: Process for Attack Simulation and Threat Analysis
- **Trike, VAST, OCTAVE**: Briefly discussed for context

## Example: STRIDE Threat Table

| Threat Category         | Example Attack         | Security Control                |
|------------------------|-----------------------|---------------------------------|
| Spoofing               | Credential theft      | MFA, strong password policy     |
| Tampering              | SQL injection         | Input validation, ORM           |
| Repudiation            | Log tampering         | Audit logs, digital signatures  |
| Information Disclosure | Data leak             | Encryption, access control      |
| Denial of Service      | API flooding          | Rate limiting, WAF              |
| Elevation of Privilege | Privilege escalation  | RBAC, least privilege           |

## Sample Code: Vulnerable Login (Python Flask)

```python
@app.route('/login', methods=['POST'])
def login():
	username = request.form['username']
	password = request.form['password']
	user = db.query(User).filter_by(username=username, password=password).first()
	if user:
		session['user_id'] = user.id
		return redirect('/dashboard')
	return 'Login failed', 401
```

**Threats:** Susceptible to SQL injection, credential stuffing, and session fixation.

**Mitigations:** Use parameterized queries, hash passwords, implement account lockout, and use secure session cookies.

## Lab/Simulation

To simulate a threat model:
1. Clone this repo and install PlantUML and LaTeX.
2. Generate diagrams:
   ```sh
   plantuml system-context.puml
   plantuml stride-analysis.puml
   mv *.png images/
   ```
3. Compile the report:
   ```sh
   pdflatex threat-model.tex
   bibtex threat-model
   pdflatex threat-model.tex
   pdflatex threat-model.tex
   ```

## References
- Bruce Schneier, "Secrets and Lies: Digital Security in a Networked World", Wiley, 1999.
- Adam Shostack, "Threat Modeling: Designing for Security", Wiley, 2014.
- [OWASP Threat Modeling Cheat Sheet](https://cheatsheetseries.owasp.org/cheatsheets/Threat_Modeling_Cheat_Sheet.html)
- [Microsoft STRIDE](https://docs.microsofhttps://verbose-adventure-7vw5jj5j94pp2p5xv.github.dev/t.com/en-us/security/engineering/stride-threat-modeling)
- [PASTA Methodology](https://www.securityinnovation.com/blog/pasta-threat-modeling-methodology/)