# Threat Model Documentation


This repository provides a comprehensive, professional threat modeling report for a sample vulnerable web application, following industry best practices and frameworks such as STRIDE, PASTA, Trike, VAST, OCTAVE, and OWASP. The report is modular, reference-rich, and includes technical diagrams, Linux-based labs, and actionable recommendations.


## Contents
- `threat-model.tex`: Main LaTeX document, modularly structured with `\input` for each chapter.
- `chapters/01_introduction.tex` ... `chapters/12_references.tex`: Each chapter of the report as a separate file.
- `sample.bib`: Bibliography with references to key threat modeling literature.
- `diagrams/`: PlantUML source files for system context and STRIDE analysis diagrams.
- `images/`: PNG diagrams generated from PlantUML for inclusion in the report.


## Key Frameworks Covered
- **STRIDE** (Microsoft): Spoofing, Tampering, Repudiation, Information Disclosure, Denial of Service, Elevation of Privilege
- **PASTA**: Process for Attack Simulation and Threat Analysis
- **Trike, VAST, OCTAVE, OWASP**: Compared and discussed for context


## Structure
The report is organized into the following chapters:

1. Introduction
2. Background and Evolution of Threat Modeling
3. STRIDE: Microsoft’s Threat Modeling Framework
4. PASTA: Process for Attack Simulation and Threat Analysis
5. Other Frameworks: Trike, VAST, OCTAVE, and OWASP
6. Threat Modeling Methodology: Step-by-Step
7. Case Study: Threat Model of a Vulnerable Web Application
8. Security Controls, Mitigations, and Best Practices
9. Risk Assessment, Reporting, and Continuous Improvement
10. Lab: Practical Threat Modeling with Linux Commands
11. Conclusion and Future Directions
12. References

## Diagrams and Images
- All PlantUML diagrams are in the `diagrams/` folder. Generate PNGs using PlantUML and place them in `images/`.
- Example:
   ```sh
   plantuml diagrams/system-context.puml
   plantuml diagrams/stride-analysis.puml
   mv *.png images/
   ```

## Building the Report
To build the PDF:
```sh
pdflatex threat-model.tex
pdflatex threat-model.tex
```
All references are included in the final chapter. For bibliography, see `sample.bib`.

## References
- Bruce Schneier, "Secrets and Lies: Digital Security in a Networked World", Wiley, 1999.
- Adam Shostack, "Threat Modeling: Designing for Security", Wiley, 2014.
- [OWASP Threat Modeling Cheat Sheet](https://cheatsheetseries.owasp.org/cheatsheets/Threat_Modeling_Cheat_Sheet.html)
- [Microsoft STRIDE](https://docs.microsofhttps://verbose-adventure-7vw5jj5j94pp2p5xv.github.dev/t.com/en-us/security/engineering/stride-threat-modeling)
- [PASTA Methodology](https://www.securityinnovation.com/blog/pasta-threat-modeling-methodology/)