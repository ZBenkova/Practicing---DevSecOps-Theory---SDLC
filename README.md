# Practicing DevSecOps — SDLC

## 📚 Overview

**SDLC (Software Development Life Cycle)** is the process used to plan, design, develop, test, deploy, and maintain software.

**SDLC = životní cyklus vývoje softwaru.**

From a cybersecurity perspective, security should **not be treated as the final step of development**. Security should be integrated throughout the entire software development lifecycle.

This approach is known as **Secure SDLC** and is an important part of **DevSecOps**.

> 🔐 **Key principle:** Security should be considered from the beginning of the project, not added only at the end.

---

# 🔄 SDLC Phases

## 1. Planning — Plánování

The initial phase where the project goals, scope, resources, and risks are defined.

V této fázi se rozhoduje, **co budeme vytvářet, proč to vytváříme a jaká rizika mohou vzniknout**.

### Key questions

* **What are we going to build?**
  Co budeme vytvářet?

* **Who is the target user?**
  Kdo bude software používat?

* **What are the business requirements?**
  Jaké jsou požadavky firmy nebo zákazníka?

* **What are the risks?**
  Jaká rizika mohou projekt ohrozit?

* **What are the budget and resource requirements?**
  Kolik bude projekt stát a jaké zdroje budeme potřebovat?

### 🔐 Security perspective

Už během plánování bychom měli přemýšlet o bezpečnostních rizicích a požadavcích.

Například:

> What sensitive data will the application process?
> Jaká citlivá data bude aplikace zpracovávat?

---

## 2. Requirements — Požadavky

Requirements define **what the software should do** and **what constraints it must satisfy**.

Požadavky určují, jaké funkce má aplikace mít a jaké vlastnosti musí splňovat.

### Functional requirements — Funkční požadavky

Popisují, **co má systém dělat**.

Examples:

* **User registration**
  Registrace uživatele.

* **Login**
  Přihlášení uživatele.

* **File upload**
  Nahrávání souborů.

* **Payment processing**
  Zpracování plateb.

### Non-functional requirements — Nefunkční požadavky

Popisují, **jak dobře má systém fungovat**.

Examples:

* **Performance** — výkon aplikace
* **Availability** — dostupnost
* **Scalability** — schopnost systému růst při větším zatížení
* **Reliability** — spolehlivost

### Security requirements — Bezpečnostní požadavky

Definují bezpečnostní mechanismy, které musí být součástí aplikace.

Examples:

* **MFA (Multi-Factor Authentication)**
  Vícefaktorové ověřování uživatele.

* **Encryption**
  Šifrování dat, například při přenosu nebo uložení.

* **RBAC (Role-Based Access Control)**
  Přístupová práva jsou určena podle role uživatele.

* **Password policies**
  Pravidla pro bezpečná hesla.

* **Secure session management**
  Bezpečná správa přihlašovacích relací uživatelů.

---

# 3. Design — Návrh

V této fázi se navrhuje **technická architektura aplikace**.

Řešíme například:

* **Application architecture**
  Jak budou jednotlivé části aplikace spolupracovat.

* **Database design**
  Jak budou strukturována a ukládána data.

* **API design**
  Jak spolu budou komunikovat různé systémy a služby.

* **Authentication and authorization**
  Jak ověříme identitu uživatele a co mu dovolíme.

* **Data flow**
  Jak budou data procházet systémem.

* **Network architecture**
  Jak bude aplikace propojena se sítí a dalšími systémy.

### Threat modeling — Modelování hrozeb

Threat modeling znamená systematické hledání možných bezpečnostních hrozeb **ještě před napsáním kódu**.

Například:

> **What happens if an attacker sends malicious input to the application?**

Co se stane, pokud útočník pošle aplikaci škodlivý vstup?

Můžeme například přemýšlet o:

* SQL Injection
* XSS
* Authentication bypass
* Privilege escalation
* Data leakage

---

# 4. Development / Implementation — Vývoj

V této fázi programátoři implementují aplikaci podle požadavků a návrhu.

### Secure coding — Bezpečné programování

Programátoři používají postupy, které minimalizují vznik bezpečnostních zranitelností.

Například:

* validace vstupů
* bezpečná práce s hesly
* správná práce s oprávněními
* bezpečná práce s API
* ochrana proti injection útokům

### Code review — Kontrola kódu

Jiný developer kontroluje napsaný kód.

Cílem je najít:

* chyby
* špatný design
* bezpečnostní problémy
* potenciální vulnerabilities

### SAST — Static Application Security Testing

Automatizovaná analýza zdrojového kódu.

SAST může například hledat potenciálně nebezpečné konstrukce **ještě před spuštěním aplikace**.

---

# 5. Testing — Testování

Aplikace se testuje z hlediska funkčnosti, výkonu i bezpečnosti.

### Unit testing

Testování jednotlivých malých částí aplikace, například konkrétní funkce.

### Integration testing

Testování, zda spolu jednotlivé části systému správně komunikují.

### Security testing

Testování aplikace z pohledu bezpečnosti.

Cílem je najít vulnerabilities před nasazením do produkce.

### DAST — Dynamic Application Security Testing

Testování **běžící aplikace** z pohledu externího útočníka.

Na rozdíl od SAST tedy neanalyzuje pouze zdrojový kód, ale chování aplikace během jejího běhu.

### Penetration testing

Simulovaný útok na systém, jehož cílem je zjistit, zda lze objevené zranitelnosti skutečně zneužít.

### Vulnerability scanning

Automatizované hledání známých zranitelností v aplikacích, systémech nebo dependencies.

---

# 6. Deployment — Nasazení

Aplikace je nasazena do produkčního prostředí.

Security considerations:

* **Secure configuration**
  Bezpečné nastavení aplikace a infrastruktury.

* **System hardening**
  Odstranění nepotřebných služeb, funkcí a nastavení, která by mohla zvětšovat attack surface.

* **Secrets management**
  Bezpečné ukládání hesel, API keys, tokens a dalších secrets.

* **Access control**
  Nastavení toho, kdo může k jednotlivým systémům a zdrojům přistupovat.

* **Secure CI/CD pipelines**
  Zajištění bezpečnosti automatizovaných procesů pro build, testování a deployment.

* **Container security**
  Bezpečnost Docker images, containerů a jejich konfigurace.

---

# 7. Maintenance — Údržba

Bezpečnost nekončí nasazením aplikace.

Po nasazení je potřeba systém **průběžně monitorovat, aktualizovat a opravovat**.

### Monitoring

Sledování systému a hledání podezřelého nebo neobvyklého chování.

### Logging

Ukládání událostí, které mohou pomoci při analýze problémů nebo bezpečnostního incidentu.

### Vulnerability management

Proces identifikace, hodnocení, prioritizace a řešení bezpečnostních zranitelností.

### Security patching

Instalace bezpečnostních oprav.

### Dependency updates

Aktualizace knihoven a dalších závislostí.

Například:

> Pokud aplikace používá zranitelnou verzi knihovny, je potřeba ji aktualizovat na bezpečnou verzi.

### Incident response

Proces reakce na bezpečnostní incident.

Například:

1. Detection
2. Analysis
3. Containment
4. Eradication
5. Recovery
6. Lessons learned

### CVE management

Identifikace a řešení známých zranitelností označených pomocí **CVE (Common Vulnerabilities and Exposures)**.

---

# 🛡️ SDLC vs. Secure SDLC

## Traditional SDLC

```text
Planning
   ↓
Requirements
   ↓
Design
   ↓
Development
   ↓
Testing
   ↓
Deployment
   ↓
Maintenance
```

Klasické SDLC popisuje jednotlivé fáze vývoje softwaru.

---

## Secure SDLC

Security je integrována **do každé fáze vývoje**.

```text
Security Requirements
        ↓
Threat Modeling
        ↓
Secure Coding
        ↓
Security Testing
        ↓
Secure Deployment
        ↓
Monitoring & Vulnerability Management
```

### 🔐 Key principle

> **Security is not a single phase of SDLC. Security is a layer across the entire SDLC.**

**Bezpečnost není jedna fáze SDLC. Bezpečnost je vrstva prostupující celým SDLC.**

---

# 🔐 Security Activities Across SDLC

| SDLC Phase       | Cybersecurity Activity | Česká vysvětlivka                                    |
| ---------------- | ---------------------- | ---------------------------------------------------- |
| **Requirements** | Security requirements  | Definování bezpečnostních požadavků                  |
| **Design**       | Threat modeling        | Identifikace možných hrozeb a útoků                  |
| **Development**  | Secure coding          | Psaní bezpečného kódu                                |
| **Development**  | Code review            | Kontrola kódu z hlediska chyb a bezpečnosti          |
| **Testing**      | SAST                   | Analýza zdrojového kódu                              |
| **Testing**      | DAST                   | Testování běžící aplikace                            |
| **Testing**      | Penetration testing    | Simulovaný útok na aplikaci nebo systém              |
| **Deployment**   | Hardening              | Zabezpečení systému a odstranění nepotřebných funkcí |
| **Deployment**   | Secrets management     | Bezpečné ukládání hesel, tokenů a API keys           |
| **Maintenance**  | Monitoring             | Průběžné sledování systému                           |
| **Maintenance**  | Patching               | Instalace bezpečnostních oprav                       |
| **Maintenance**  | CVE management         | Identifikace a řešení známých zranitelností          |
| **Maintenance**  | Incident response      | Reakce na bezpečnostní incidenty                     |

---

# 🚀 DevSecOps Connection

**DevSecOps** rozšiřuje filozofii DevOps o bezpečnost.

Místo přístupu:

```text
Development → Operations → Security
```

DevSecOps prosazuje:

```text
Development + Security + Operations
```

Bezpečnost se tedy stává **sdílenou odpovědností celého týmu**, nikoliv úkolem, který se řeší až na konci projektu.

---

# 🎯 Learning Goals

Through this repository I am practicing and documenting:

* **SDLC fundamentals** — základy životního cyklu vývoje softwaru
* **Secure SDLC** — začlenění bezpečnosti do jednotlivých fází SDLC
* **DevSecOps principles** — principy propojení developmentu, security a operations
* **Security requirements** — definování bezpečnostních požadavků
* **Threat modeling** — identifikace a analýza bezpečnostních hrozeb
* **Secure coding** — bezpečné programovací postupy
* **SAST and DAST** — automatizované bezpečnostní testování
* **Vulnerability management** — řízení bezpečnostních zranitelností
* **CVE management** — práce s identifikovanými CVE
* **Secure CI/CD** — zabezpečení automatizovaných deployment pipeline
* **Application security** — ochrana aplikací před bezpečnostními hrozbami

---

## 📝 Notes

This repository is part of my ongoing **cybersecurity learning journey**.

It serves as a practical collection of:

* study notes
* exercises
* security concepts
* experiments
* DevSecOps practices
* application security examples

The goal is to connect **theory with practical cybersecurity skills** and gradually build a strong foundation for a career in cybersecurity.
