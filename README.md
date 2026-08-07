# Practicing---DevSecOps-Theory---SDLC

SDLC = Software Development Life Cycle – životní cyklus vývoje softwaru.

V cybersecurity je SDLC důležitý proto, že bezpečnost by neměla přijít až na konci vývoje. Ideálně je Security součástí každé fáze („Secure SDLC“).

Typické fáze SDLC jsou:
Planning – plánování
Co budeme vyvíjet?
Pro koho?
Jaké jsou požadavky, rozpočet a rizika?
Requirements – požadavky
Funkční požadavky
Nefunkční požadavky
Security requirements – např. MFA, šifrování, RBAC
Design – návrh
Architektura aplikace
Databáze, API, autentizace
Threat modeling
Např. „Co když útočník pošle škodlivý input?“
Development / Implementation – vývoj
Programátoři píší kód
Secure coding
Code review
SAST
Testing – testování
Unit/integration testing
Security testing
DAST
Penetration testing
Hledání zranitelností
Deployment – nasazení
Produkční prostředí
Bezpečná konfigurace
Secrets management
CI/CD security
Maintenance – údržba
Monitoring
Patching
Aktualizace dependencies
Reakce na incidenty
Řešení nových CVE

SDLC vs. Secure SDLC

Klasické SDLC:

Plan → Requirements → Design → Development → Testing → Deployment → Maintenance

Secure SDLC přidává bezpečnost napříč celým procesem:

Security requirements → Threat modeling → Secure coding → Security testing → Secure deployment → Monitoring & vulnerability management

Pro tebe jako budoucí Cybersecurity Specialist je důležité hlavně chápat, kde se do SDLC zapojují bezpečnostní činnosti. Například:

Fáze	Cybersecurity úkol
Requirements	Security requirements
Design	Threat modeling
Development	Secure coding, code review
Testing	SAST, DAST, pentesting
Deployment	Hardening, secrets
Maintenance	Monitoring, patching, CVE management
