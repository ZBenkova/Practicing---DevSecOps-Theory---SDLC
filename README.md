# Practicing DevSecOps — SDLC a vyplněný EXERCISE (THREAT MODELLING) 

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



# Threat Modeling & Incident Response — Cybersecurity Practice

Praktická cvičení zaměřená na:

* **Threat Modeling** – modelování hrozeb
* **Risk Assessment** – hodnocení rizik
* **STRIDE** – klasifikace bezpečnostních hrozeb
* **DFIR** – Digital Forensics and Incident Response
* **Incident Response** – reakce na bezpečnostní incident
* **Containment & Eradication** – omezení a odstranění útoku
* **Recovery** – bezpečná obnova infrastruktury
* **Resilience** – odolnost infrastruktury proti útoku

Cílem těchto cvičení je naučit se přemýšlet nad bezpečností nejen z pohledu jednotlivých zranitelností, ale především z pohledu **architektury, dopadu útoku, blast radius, dostupnosti důkazů a schopnosti organizace obnovit provoz**.

---

# 📚 Exercises

| Exercise | Téma                            | Hlavní zaměření                                         |
| -------- | ------------------------------- | ------------------------------------------------------- |
| **01**   | Threat Modeling – Síť poboček   | Centralizace, logy, storage, blast radius               |
| **02**   | Threat Modeling – Cloud         | Bezpečné experimentování s PII a third-party knihovnami |
| **03**   | Incident Response – Síť poboček | Ransomware, containment, forensics, recovery            |
| **04**   | DFIR – Síť poboček              | Forenzní analýza a obnova po kompromitaci               |

---

# 01 — Threat Modeling: Síť poboček

## 🎯 Zadání

Zákazník je středně velká organizace s kancelářemi ve většině krajských měst.

Centrála obsahuje přibližně 10 fyzických serverů. Na serverech běží VMware virtualizace se sdíleným úložištěm a všechny potřebné aplikace jsou provozovány ve virtuálním prostředí.

Pobočky jsou propojeny s centrálou pomocí **SD-WAN**, tedy šifrovaných tunelů.

Na podporovaných platformách je používán antivirus.

Síťová bezpečnost je zajištěna redundantními firewally. Logy z firewallů a serverů jsou odesílány na lokální virtuální server, který běží ve stejné virtualizační infrastruktuře.

### Co musí fungovat

1. Přístup poboček k aplikacím.
2. Dostupnost a důvěryhodnost bezpečnostních logů během útoku.
3. Možnost správy a obnovy infrastruktury po útoku.

### Omezení

Veškerá řešení musí být schopná fungovat **on-premises**. Data nesmí být posílána mimo organizaci do cloudu.

---

## ❓ Hlavní otázka

> **Jaká opatření umožní firmě provozovat síť poboček s přístupem na centrálu, ale omezí škodu, pokud centrála bude napadena nebo nedostupná?**

---

# 🗺️ 1. Data Flow Diagram

Zjednodušený model prostředí:

```text
                         ┌──────────────────────┐
                         │      CENTRÁLA        │
                         │                      │
                         │  VMware Cluster      │
                         │       │              │
                         │       ▼              │
                         │ Shared Storage       │
                         │       │              │
                         │       ▼              │
                         │ Applications         │
                         │                      │
                         │ Log Server           │
                         └──────────┬───────────┘
                                    │
                              Trust Boundary
                                    │
                    ┌───────────────┴───────────────┐
                    │                               │
              ┌─────▼─────┐                   ┌─────▼─────┐
              │  Pobočka  │                   │  Pobočka  │
              │           │                   │           │
              │ Firewall  │                   │ Firewall  │
              │    │      │                   │    │      │
              └────┼──────┘                   └────┼──────┘
                   │                               │
                   └────────── SD-WAN ─────────────┘
```

### Trust Boundary

**Trust boundary** je hranice mezi částmi systému s odlišnou úrovní důvěry.

Například:

* pobočka ↔ centrála
* uživatel ↔ aplikace
* management ↔ produkce
* produkční infrastruktura ↔ backup infrastruktura

Čím více systémů sdílí stejnou důvěryhodnost, tím větší může být **blast radius**.

### Blast radius

**Blast radius** znamená rozsah škody, kterou může jeden bezpečnostní incident způsobit.

Pokud kompromitace jednoho systému umožní útočníkovi ovládnout celou centrální infrastrukturu, máme velmi vysoký blast radius.

---

# 🛡️ 2. STRIDE – Threat Modeling

Pro identifikaci hrozeb používám metodiku **STRIDE**.

STRIDE představuje:

* **S — Spoofing**
* **T — Tampering**
* **R — Repudiation**
* **I — Information Disclosure**
* **D — Denial of Service**
* **E — Elevation of Privilege**

---

## S — Spoofing

**Spoofing = vydávání se za jinou identitu.**

Možné hrozby:

* krádež administrátorských účtů
* zneužití VPN / SD-WAN identity
* kompromitace servisních účtů

### Dopad

Útočník může získat přístup k infrastruktuře pod legitimní identitou.

---

## T — Tampering

**Tampering = neoprávněná změna dat nebo konfigurace.**

Možné hrozby:

* úprava nebo mazání logů
* zašifrování VMware a storage
* manipulace konfigurace firewallů

### Dopad

Útočník může změnit infrastrukturu nebo zničit důkazy o své aktivitě.

---

## R — Repudiation

**Repudiation = možnost popřít provedení určité akce.**

Možné hrozby:

* chybějící důvěryhodné logy během útoku
* útočník smaže auditní stopu

### Dopad

Bez spolehlivých logů může být velmi obtížné zjistit:

* kdo provedl akci
* kdy byla provedena
* odkud byla provedena
* jak se útočník pohyboval v síti

---

## I — Information Disclosure

**Information Disclosure = neoprávněné zpřístupnění informací.**

Možné hrozby:

* únik dat z centrály může ovlivnit všechny pobočky
* sdílené úložiště je vysoce hodnotný cíl

### Dopad

Kompromitace centrály může způsobit rozsáhlý únik dat.

---

## D — Denial of Service

**Denial of Service = ztráta dostupnosti systému nebo služby.**

Možné hrozby:

* výpadek centrály znamená nedostupnost aplikací
* výpadek SD-WAN hubu
* ransomware způsobí nedostupnost virtualizovaných systémů

---

## E — Elevation of Privilege

**Elevation of Privilege = získání vyšších oprávnění, než měl útočník původně mít.**

Možné hrozby:

* kompromitace VMware administrátora
* převzetí Domain Admin účtu

### Dopad

Kompromitace privilegovaného účtu může znamenat kontrolu nad velkou částí infrastruktury.

---

# 🔴 3. Top 3 Risks

## Risk #1 — Kompromitace centrály

### Hrozba

**Kompromitace centrální infrastruktury může způsobit laterální dopad na všechny pobočky.**

Centrála představuje kritický bod důvěry.

Pokud útočník získá přístup k virtualizaci, storage nebo privilegovaným účtům, může se jeho působení rozšířit do dalších částí infrastruktury.

### Dopad

* výpadek aplikací
* kompromitace poboček
* ransomware
* únik dat
* ztráta kontroly nad administrací

### Opatření

* network segmentation
* oddělení management plane
* least privilege
* oddělené administrátorské účty
* segmentované SD-WAN tunely
* omezení vzájemné důvěry mezi pobočkami a centrálou

### Cíl

**Snížit blast radius.**

---

# 🔴 Risk #2 — Log server běží ve stejné virtualizaci jako produkce

### Proč je to problém?

Log server je umístěn ve stejné virtualizační infrastruktuře jako produkční systémy.

Pokud útočník kompromituje VMware infrastrukturu, může:

```text
Compromise VMware
       ↓
Compromise Log Server
       ↓
Delete / Modify Logs
       ↓
Loss of Forensic Evidence
```

To znamená, že během útoku můžeme přijít o důkazy, které potřebujeme pro vyšetřování.

### Opatření

* oddělený fyzický nebo izolovaný log collector
* immutable / WORM storage
* write-only syslog forwarding
* SIEM mimo hlavní VMware cluster
* on-premises SIEM

### Ověření

Nestačí pouze říct:

> „Máme oddělený log server.“

Musíme ověřit, že skutečně funguje.

Například:

* simulace kompromitace VM administrátora
* test, zda lze logy smazat
* kontrola příjmu logů
* monitoring heartbeat každého log source

### Heartbeat

**Heartbeat** je pravidelný signál potvrzující, že určitý systém stále posílá data.

Pokud heartbeat přestane chodit, může vzniknout alert.

---

# 🔴 Risk #3 — Shared Storage jako Single Point of Failure

### Proč je to problém?

Pokud jsou všechny VM závislé na jednom shared storage:

```text
Storage failure
      ↓
VM unavailable
      ↓
Applications unavailable
      ↓
Branches affected
```

Ransomware může navíc zašifrovat storage a tím současně znepřístupnit velké množství systémů.

### Opatření

* immutable offline backup
* oddělená backup doména
* disaster recovery lokalita
* pravidelné recovery testy
* air-gapped backup

### Ověření

* měsíční restore test
* měření **RTO**
* kontrola air-gap
* test obnovitelnosti dat

### RTO

**Recovery Time Objective** = maximální přijatelný čas, během kterého má být služba obnovena.

Například:

> RTO = 4 hodiny

znamená, že cílem je obnovit službu do 4 hodin.

---

# 🟡 4. Odložená rizika

## Antivirus bypass / Zero-Day Malware

### Proč není Top 3?

Antivirus je důležitá bezpečnostní vrstva, ale architektonické selhání centrály může mít výrazně větší dopad.

### Priorita by se zvýšila například při:

* absenci EDR
* zvýšeném počtu phishingových incidentů
* rostoucím počtu ransomware útoků

---

## DDoS proti centrále

### Proč není Top 3?

V tomto scénáři může být pravděpodobnost nižší než riziko interní kompromitace.

### Priorita by se zvýšila při:

* veřejně exponovaných službách
* politicky citlivém sektoru
* historii předchozích útoků

---

# 🛡️ 5. Strategická opatření

## Assume Central Compromise

Základní princip:

> **Nepředpokládat, že centrála je vždy důvěryhodná.**

Pobočky by neměly automaticky důvěřovat všemu, co přichází z centrály.

### Doporučení

* lokální minimální provozní režim
* cache / fallback služby
* segmentované tunely podle aplikací
* read-only authentication fallback

---

## Decentralizace kritických funkcí

Některé základní služby mohou mít lokální fallback:

* DNS
* DHCP
* identity cache
* nouzové procesy
* oddělený backup management plane

---

## Samostatná bezpečnostní vrstva

Bezpečnostní systémy by neměly být závislé pouze na stejné infrastruktuře, kterou mají chránit.

Doporučení:

* out-of-band management
* izolovaný SIEM
* offline recovery
* oddělené logovací prostředí

---

# ❓ 6. Hlavní nejistoty

Před implementací opatření je nutné zjistit:

* Je Active Directory centralizované?
* Existuje oddělený backup systém?
* Mohou pobočky fungovat offline?
* Kde běží firewall management?
* Jsou administrátorské účty oddělené?
* Je storage immutable?
* Je SIEM oddělený od VMware?

Tyto informace mohou významně změnit výslednou prioritizaci rizik.

---

# 📌 Executive Summary — Exercise 01

### Největší problém

> **Přílišná centralizace vytváří vysoký provozní i bezpečnostní dopad při kompromitaci centrály.**

### Priority

1. **Omezit blast radius centrály.**
2. **Zajistit nezničitelné bezpečnostní logy.**
3. **Zajistit obnovu i při kompromitaci virtualizace.**

### Cíl

> **Napadení centrály nesmí automaticky znamenat kolaps všech poboček.**

Architektura by se měla posouvat od modelu:

```text
Central Trust
```

k modelu:

```text
Segmented Resilience
```

---

# 02 — Threat Modeling: Cloud Research Environment

## 🎯 Zadání

Zákazník je velká společnost, která provozuje služby sběru a analýzy zákaznických dat.

Data obsahují **PII — Personally Identifiable Information**, tedy osobně identifikovatelné informace.

Data jsou uložena v cloudu a následně analyzována.

Analytici potřebují rychle experimentovat s:

* vlastním kódem
* nástroji třetích stran
* knihovnami třetích stran

Analytici ale nejsou experti na software engineering ani cybersecurity.

Současně není možné každý experiment blokovat dlouhou bezpečnostní kontrolou.

Je však nutné zajistit:

1. rychlé experimentování,
2. ochranu PII,
3. prokazatelný soulad s GDPR.

---

# ❓ Hlavní otázka

> **Jaká opatření umožní rychlé experimentování, ale omezí škodu, pokud analytický kód nebo knihovna nejsou důvěryhodné?**

---

# 🗺️ Data Flow Diagram

Navržený model:

```text
                  ┌─────────────────┐
                  │    ANALYST      │
                  │   👩‍💻           │
                  └────────┬────────┘
                           │
                           ▼
                  ┌─────────────────┐
                  │   ANALYTICAL    │
                  │   ENVIRONMENT   │
                  │   Notebook      │
                  │   Sandbox       │
                  └────────┬────────┘
                           │
                    Trust Boundary
                           │
              ┌────────────┴────────────┐
              │                         │
              ▼                         ▼
       ┌─────────────┐          ┌─────────────┐
       │  Data Lake  │          │   Internet  │
       │    PII      │          │  Libraries  │
       └─────────────┘          └─────────────┘
              │
              ▼
       ┌─────────────┐
       │ Audit / SIEM│
       └─────────────┘
```

---

# 🛡️ STRIDE Analysis

## Spoofing

Možné hrozby:

* kompromitovaný analytický účet
* stolen cloud credentials
* compromised service account

### Dopad

Útočník může získat přístup k analytickému prostředí nebo datům.

---

## Tampering

Možné hrozby:

* manipulace analytických výsledků
* změna datasetů
* škodlivá third-party knihovna
* modifikace analytického kódu

---

## Repudiation

Možné hrozby:

* chybějící auditní stopa
* nemožnost zjistit, kdo spustil konkrétní experiment
* nemožnost prokázat přístup k PII

To je problematické také z hlediska GDPR compliance.

---

## Information Disclosure

Toto je jedno z nejkritičtějších rizik.

Možné scénáře:

```text
Malicious Library
       ↓
Read PII
       ↓
Exfiltration
       ↓
Data Breach
```

---

## Denial of Service

Možné scénáře:

* škodlivý experiment spotřebuje příliš mnoho resources
* nekontrolovaný workload způsobí vysoké náklady
* analytické prostředí ovlivní dostupnost datového prostředí

---

## Elevation of Privilege

Například:

* analytik získá vyšší cloud permissions
* notebook získá přístup k produkčnímu datalake
* third-party library využije příliš široká oprávnění

---

# 🔴 Top 3 Risks — Exercise 02

## Risk #1 — Únik PII prostřednictvím škodlivého kódu

### Scénář

Analytik spustí knihovnu třetí strany.

Knihovna má přístup k PII a může data odeslat mimo organizaci.

### Opatření

* sandbox
* izolované workspaces
* least privilege
* omezený egress
* anonymizovaná data pro experimenty
* syntetická data
* oddělení analytického prostředí od produkčních dat

---

# 🔴 Risk #2 — Příliš široká oprávnění analytiků

Pokud analytik nebo notebook dostane přístup k celému datalake, kompromitace jediného účtu může mít rozsáhlý dopad.

### Opatření

* RBAC
* least privilege
* scoped credentials
* krátkodobé tokeny
* JIT access
* oddělené role pro experimenty a produkci

### Princip

> **Analytik by měl mít pouze taková oprávnění, která skutečně potřebuje.**

---

# 🔴 Risk #3 — Nekontrolované third-party dependencies

Analytici potřebují používat knihovny třetích stran.

To vytváří supply-chain risk.

### Opatření

* approved base images
* interní package mirror
* allowlist knihoven
* dependency scanning
* izolované sandbox prostředí
* omezený network egress

---

# 🟡 Odložená rizika

## Denial of Service / Resource Abuse

Není mezi Top 3, protože primární riziko představuje ochrana PII.

Priorita by vzrostla například při:

* vysokých cloud nákladech
* nedostatku resources
* opakovaných resource exhaustion incidentech

---

## Manipulace analytických výsledků

Riziko existuje, ale jeho priorita závisí na tom, jak jsou analytické výsledky používány.

Priorita by vzrostla například při:

* automatizovaném rozhodování
* regulatorně citlivých výsledcích
* použití výsledků pro důležitá obchodní rozhodnutí

---

# 🔐 Doporučená architektura

```text
                    ANALYST
                       │
                       ▼
              ┌─────────────────┐
              │    SANDBOX      │
              │                 │
              │ Isolated        │
              │ Workspace       │
              └────────┬────────┘
                       │
                Restricted Egress
                       │
             ┌─────────┴─────────┐
             │                   │
             ▼                   ▼
      Approved Libraries    Controlled APIs
             │
             ▼
      ┌─────────────────┐
      │ Protected Data  │
      │     Lake        │
      │      PII        │
      └─────────────────┘
```

### Hlavní princip

Analytici mohou **rychle experimentovat**, ale experiment nemá automaticky přístup ke všem produkčním datům.

---

# 📋 GDPR & Auditability

Protože systém pracuje s PII, je důležité být schopen prokázat:

* kdo měl k datům přístup
* kdy k nim přistoupil
* jaká data použil
* jaký experiment spustil
* jaké oprávnění měl
* jaké změny byly provedeny

Proto je důležitý:

* audit logging
* access review
* immutable audit trail
* monitoring
* pravidelné kontroly oprávnění

---

# 📌 Executive Summary — Exercise 02

### Cíl

Umožnit analytikům rychlé experimentování bez toho, aby každý experiment představoval přímý přístup k produkčním PII.

### Priorita

1. **Protect PII**
2. **Limit analyst privileges**
3. **Control third-party code**

### Klíčový princip

> **Experimentation should be fast, but the blast radius should be small.**

---

# 03 — Incident Response: Síť poboček

## 🚨 Zadání

U zákazníka z prvního případu došlo k bezpečnostnímu incidentu.

Útočník pronikl do centrálního úložiště a kompletně jej zašifroval, včetně všech logů z bezpečnostních zařízení.

Cílem není určit přesnou vstupní cestu útočníka.

Cílem je zabránit dalším škodám.

---

# ❓ Hlavní otázky

1. Co stále funguje?
2. Co nefunguje?
3. K jakým důkazům jsme ztratili přístup?
4. Jaká data nebo funkcionalita musí být zachována?
5. Co izolujeme jako první?
6. Jak zjistíme kompletní rozsah útoku?
7. Jak provedeme bezpečné vyčištění?

---

# 1. Co víme jistě?

### Víme

* centrální storage je zašifrovaný
* logy uložené v této infrastruktuře jsou kompromitované nebo ztracené
* útočník získal dostatečná oprávnění pro přístup ke core infrastruktuře
* není uvedeno, že by byly kompromitovány pobočky

### Nevíme

* zda je kompromitovaný celý VMware cluster
* zda je v síti stále aktivní útočník
* zda byly kompromitovány AD nebo admin účty
* zda byly napadeny backupy
* jakým způsobem útočník vstoupil

---

# 2. Co pravděpodobně funguje?

## Pravděpodobně nefunguje

* shared storage
* aplikace běžící na tomto storage
* centrální logování
* část VMware management infrastruktury

## Pravděpodobně funguje

* pobočkové firewally
* SD-WAN síťová konektivita
* lokální endpointy
* infrastruktura, která není závislá na zašifrovaném storage

---

# 🚨 3. Containment

## Cíl

> **Zastavit šíření útoku a zabránit dalším škodám.**

### Okamžitá opatření

1. Odpojit centrální storage.
2. Pozastavit nebo omezit SD-WAN propojení.
3. Zablokovat kompromitované privilegované účty.
4. Pozastavit automatické synchronizace.
5. Izolovat VMware management plane.

---

## Co tím chráníme?

* pobočky
* identity
* backupy
* další infrastrukturu
* zbývající systémy

### Nevýhoda

Containment může způsobit:

* výpadek aplikací
* omezení provozu
* dočasnou nedostupnost služeb

To je však přijatelné, pokud zabráníme dalšímu šíření útoku.

---

# 🔎 4. Evidence Preservation

Protože byly zašifrovány centrální logy, musíme zachovat ostatní dostupné důkazy.

### Zachovat

* VMware snapshoty
* memory dump běžících systémů
* firewall logy z poboček
* SD-WAN traffic metadata
* AD audit logy
* konfigurace firewallů
* SD-WAN konfigurace
* časovou osu incidentu

### Ztracené důkazy

* centrální logy
* SIEM historie
* část auditní stopy

### Kritický princip

> **Nepracovat na live systému bez vytvoření kopie, pokud to situace dovoluje.**

---

# 🔎 5. Scope Analysis

Protože centrální logy nejsou dostupné, musíme použít **externí korelaci**.

## Identity layer

Kontrolujeme:

* nové administrátorské účty
* podezřelá přihlášení
* změny oprávnění
* token abuse

---

## Network layer

Kontrolujeme:

* SD-WAN anomálie
* laterální pohyb
* neobvyklý traffic
* možné známky exfiltrace

---

## Virtualization layer

Kontrolujeme:

* nové VM
* nové snapshoty
* změny konfigurace
* změny datastore

---

## Endpoint layer

Kontrolujeme:

* ransomware artefakty
* encryption activity
* podezřelé procesy
* bezpečnostní alerty

---

# 🧠 6. Hypothesis-Driven Forensics

Protože nemáme kompletní logy, pracujeme s hypotézami.

### H1

> Útok začal kompromitací administrátorského účtu.

### H2

> Útok využil zranitelnost nebo kompromitaci VMware/service layer.

### H3

> Pobočka byla vstupním bodem.

Každá hypotéza vede k jiným zdrojům důkazů.

---

# 🧹 7. Eradication

**Eradication = odstranění útočníka a jeho persistence ze systému.**

## Minimální varianta

* reset privilegovaných účtů
* rebuild storage z offline backupu
* reinstalace VMware management plane

## Pokud je podezření na AD compromise

* AD forest recovery / rebuild
* rotace secrets
* rotace VPN credentials
* rotace SD-WAN credentials
* rotace certifikátů
* rebuild privilegovaných systémů

## Worst-case

Pokud je kompromitována celá virtualizační infrastruktura:

* kompletní rebuild
* nové SD-WAN prostředí
* rotace všech secrets
* nový trust model
* postupný re-onboarding systémů

---

# 🔄 8. Recovery

Obnova musí probíhat postupně.

```text
Identity
   ↓
Management Plane
   ↓
Storage
   ↓
Applications
   ↓
Branches
```

### Základní princip

> **Do produkce nesmíme vracet systém pouze proto, že jsme ho obnovili ze zálohy. Nejprve musíme ověřit jeho důvěryhodnost.**

---

# 04 — DFIR: Digital Forensics & Incident Response

## 🎯 Cíle DFIR

V této situaci máme tři hlavní cíle:

### 1. Containment

Zastavit útok a zabránit dalšímu šíření.

### 2. Scope

Zjistit, co dalšího je kompromitované.

### 3. Recovery

Bezpečně obnovit provoz bez návratu útočníka.

---

# 🔬 DFIR Lifecycle

```text
Triage
  ↓
Evidence Preservation
  ↓
Scope Analysis
  ↓
Forensics
  ↓
Eradication
  ↓
Recovery
  ↓
Lessons Learned
```

---

# ⏱️ A. Triage

V prvních hodinách:

* izolace storage
* izolace VMware managementu
* omezení SD-WAN
* zastavení backup/replication synchronizací

### Proč?

Abychom ochránili:

* pobočky
* identity
* backupy
* nezasaženou infrastrukturu

---

# 📸 B. Evidence Preservation

### Co už bylo ztraceno?

* centrální logy
* SIEM historie

### Co musíme získat?

* snapshoty VM
* memory dump
* firewall logs
* SD-WAN metadata
* AD audit logs
* konfigurace síťových zařízení
* časová osa incidentu

---

# 🔍 C. Scope Analysis

## Identity

Hledáme:

* nové účty
* podezřelé login patterns
* změny privilegií
* token abuse

## Network

Hledáme:

* laterální pohyb
* anomální traffic
* exfiltraci
* komunikaci mezi pobočkami a centrálou

## VMware

Hledáme:

* neznámé VM
* změny snapshotů
* změny konfigurace
* změny datastore

## Endpoint

Hledáme:

* ransomware artefakty
* encryption activity
* podezřelé procesy

---

# 🧹 D. Eradication

## Minimální bezpečná varianta

* reset privilegovaných účtů
* rebuild storage
* reinstall VMware management
* kontrola integrity VM

## Při kompromitaci AD

* AD forest recovery / rebuild
* rotace VPN credentials
* rotace SD-WAN credentials
* rotace certifikátů
* rebuild privilegovaných systémů

## Při kompromitaci celé virtualizace

* kompletní rebuild infrastruktury
* izolace starého prostředí
* forenzní analýza offline
* nový SD-WAN overlay
* kompletní rotace secrets
* nový Zero Trust model

---

# 🔄 E. Recovery

Obnova:

```text
1. Identity
      ↓
2. Management Plane
      ↓
3. Storage
      ↓
4. Applications
      ↓
5. Branches
```

### Princip

> **Nepouštět nic zpět do produkce bez ověření čistoty.**

---

# 🧱 Lessons Learned

Incident ukázal několik architektonických problémů.

## 1. Logy nesmí sdílet stejný osud jako produkce

Doporučení:

* immutable log storage
* WORM
* oddělený SIEM
* logy mimo VMware cluster

### Immutable Storage

**Immutable storage** je úložiště, kde není možné data po určitou dobu změnit nebo smazat.

### WORM

**WORM = Write Once, Read Many**

Princip:

```text
Write Once
     ↓
Data jsou zapsána
     ↓
Read Many
     ↓
Lze je číst
     ↓
No Modify / No Delete
```

Cílem je zabránit útočníkovi, aby po kompromitaci administrátorského účtu jednoduše smazal auditní stopu.

---

# 💾 2. Backup nesmí být součástí stejné trust boundary

Doporučení:

* offline backup
* immutable backup
* oddělená backup doména
* pravidelné restore testy
* air-gap

### Air-gap

**Air-gap** znamená logické nebo fyzické oddělení systému tak, aby k němu nebylo možné běžně přistupovat z kompromitované produkční infrastruktury.

---

# 🔐 3. Least Privilege

Každý účet by měl mít pouze oprávnění, která skutečně potřebuje.

Místo:

```text
Admin → Everything
```

preferujeme:

```text
User → Required Access
Service → Required Access
Admin → Administrative Access
```

---

# ⏱️ 4. JIT Administration

**JIT = Just-In-Time access**

Administrátorský přístup je poskytnut pouze na nezbytně dlouhou dobu.

Výhoda:

* menší attack surface
* menší riziko kompromitace privilegovaného účtu
* lepší auditovatelnost

---

# 🧪 5. Recovery Testing

Backup bez testu obnovy není dostatečná záruka.

Proto je potřeba pravidelně provádět:

* restore test
* recovery drill
* tabletop exercise
* kontrolu integrity backupů
* měření RTO

---

# 🛠️ Reusable Security Controls

Tyto prvky lze použít napříč threat modeling a incident response scénáři.

## Segmentation

**Síťová segmentace** rozděluje infrastrukturu na části s omezenou komunikací.

Cíl:

> Snížit blast radius.

---

## Isolated Logging

Logovací infrastruktura je oddělena od produkce.

Cíl:

> Zajistit dostupnost důkazů i během kompromitace produkce.

---

## Management Plane Separation

Management infrastruktura je oddělena od běžného provozu.

Cíl:

> Zabránit tomu, aby kompromitace produkce automaticky znamenala kompromitaci administrace.

---

## Least Privilege

Uživatelé a služby dostávají pouze potřebná oprávnění.

Cíl:

> Omezit následky kompromitace účtu.

---

## JIT / JEA

* **JIT — Just-In-Time**
* **JEA — Just Enough Administration**

Cíl:

> Omezit privilegovaný přístup časově i rozsahem.

---

## Scoped Tokens

Token je omezen:

* oprávněními
* účelem
* systémem
* dobou platnosti

Cíl:

> Omezit škodu při jeho kompromitaci.

---

## Sandbox

Izolované prostředí pro experimentování.

Cíl:

> Umožnit práci s nedůvěryhodným kódem bez přímého ohrožení produkce.

---

## Synthetic Data

**Syntetická data** jsou uměle vytvořená data, která napodobují vlastnosti reálných dat.

Výhoda:

> Analytik může experimentovat bez přímého přístupu k reálným PII.

---

## Restricted Egress

**Egress** = odchozí komunikace ze systému.

Omezený egress znamená, že například sandbox nemůže libovolně odesílat data na internet.

Cíl:

> Omezit data exfiltration.

---

# 📊 Long-Term Verification

Bezpečnostní opatření musí fungovat nejen v den implementace, ale i za několik měsíců.

Proto používáme:

| Control              | Verification                  |
| -------------------- | ----------------------------- |
| Network segmentation | Automated configuration check |
| Immutable logs       | Test mazání / modifikace      |
| Backup               | Monthly restore test          |
| Least privilege      | Periodic access review        |
| JIT access           | Audit privileged sessions     |
| Monitoring           | Test alert / benign trigger   |
| Egress filtering     | Controlled outbound test      |
| SIEM                 | Log source heartbeat          |
| Recovery             | Tabletop exercise             |
| Incident Response    | Regular simulation            |

---

# 🧠 Key Takeaways

## 1. Security není pouze antivirus nebo firewall

Bezpečnost je kombinace:

```text
People
   +
Process
   +
Technology
   +
Architecture
```

---

## 2. Centralization může být bezpečnostní riziko

Centralizace zjednodušuje správu, ale může vytvořit:

> **Single Point of Failure**

---

## 3. Logy jsou bezpečnostní důkaz

Pokud útočník dokáže smazat logy:

```text
Attack
  ↓
Log deletion
  ↓
No evidence
  ↓
Difficult investigation
```

Proto musí být logovací infrastruktura chráněna samostatně.

---

## 4. Backup není totéž jako Recovery

Mít backup nestačí.

Musíme vědět:

> **Can we actually restore?**

Proto je důležitý pravidelný restore test.

---

## 5. Assume Breach

Bezpečnostní architektura by měla počítat s tím, že:

> **Některá část infrastruktury může být kompromitována.**

Cílem není pouze zabránit útoku.

Cílem je také:

* omezit jeho rozsah
* zachovat důkazy
* zabránit laterálnímu pohybu
* obnovit provoz
* zabránit opakování incidentu

---

# 🎯 Final Security Model

Z jednotlivých cvičení vyplývá společný princip:

```text
                 ┌──────────────────────┐
                 │      SECURITY        │
                 │                      │
                 │  Assume Compromise   │
                 │  Least Privilege     │
                 │  Segmentation        │
                 │  Monitoring          │
                 │  Resilience          │
                 └──────────┬───────────┘
                            │
             ┌──────────────┼──────────────┐
             │              │              │
             ▼              ▼              ▼
        PREVENT          DETECT         RESPOND
             │              │              │
             ▼              ▼              ▼
        Hardening        Logging        Containment
        Segmentation     SIEM           Forensics
        Least Privilege  Monitoring     Eradication
                                          Recovery
                                             │
                                             ▼
                                      LESSONS LEARNED
```

# 📝 Final Summary

Nejdůležitější závěr těchto cvičení:

> **Cílem cybersecurity není pouze zabránit útoku. Cílem je také zajistit, aby kompromitace jednoho systému nevedla ke kompromitaci celé organizace a aby organizace dokázala útok detekovat, vyšetřit, zastavit a bezpečně obnovit provoz.**

Tento princip spojuje:

**Threat Modeling → Risk Assessment → Prevention → Detection → Incident Response → DFIR → Recovery → Resilience**

---

## 📚 Skills Practiced

* Threat Modeling
* STRIDE
* Risk Assessment
* Data Flow Diagrams
* Trust Boundaries
* Blast Radius Analysis
* Security Architecture
* Network Segmentation
* Least Privilege
* IAM
* SIEM
* Immutable Logging
* WORM Storage
* Backup & Recovery
* RTO
* Incident Response
* DFIR
* Digital Forensics
* Containment
* Eradication
* Recovery
* Zero Trust
* DevSecOps Security Principles

---

## 🚀 Learning Goal

This repository is part of my practical **cybersecurity learning journey**.

The goal is to connect cybersecurity theory with practical scenarios and develop the ability to:

* identify threats,
* prioritize risks,
* design security controls,
* analyze incidents,
* preserve evidence,
* limit blast radius,
* recover compromised infrastructure,
* and communicate security risks to stakeholders.

> **Think like an attacker. Design like a defender. Recover like an incident responder.**
