# Bedrijfsprocessanalyse — BI-Rapportageproces Chocolate Firm

**Ist · Soll · Knelpunten · Gap-analyse · SIPOC**

| | |
|---|---|
| **Document** | Bedrijfsprocessanalyse |
| **Proces** | BI-rapportage & data-analyse |
| **Versie** | 1.0 — Definitief concept |
| **Methode** | SIPOC + Ist/Soll + Knelpunten + Gap |

---

## 1. Procesafbakening & Scope

Het te analyseren proces betreft de bedrijfsinterne rapportage- en data-analysecyclus van de Chocolate Firm. Dit proces loopt van het moment dat operationele data wordt gegenereerd in de bronsystemen (Odoo ERP, productiesystemen, CRM) tot en met het moment dat managers en medewerkers op basis van actuele inzichten beslissingen kunnen nemen.

| | |
|---|---|
| **Proceseigenaar** | Financieel directeur / MT |
| **Processtart** | Data gegenereerd in operationele systemen (orders, productie, inkoop) |
| **Proceseinde** | Manager of MT-lid heeft actueel inzicht en kan beslissing nemen |
| **In scope** | Dataverzameling, -verwerking, dashboarding, rapportage, besluitvorming (marges, cashflow, smaaktrends, voorraad) |
| **Buiten scope** | Operationele invoer in Odoo, facturatie, HR-processen, mobiele app klantprocessen |
| **Betrokken systemen** | Odoo ERP, Excel, CRM, productiesystemen (maatwerk), BI-tool (to-be) |

---

## 2. SIPOC — Huidige Situatie (Ist)

| S — Suppliers | I — Inputs | P — Process | O — Outputs | C — Customers |
|---|---|---|---|---|
| Odoo ERP | Exportbestanden (CSV/Excel) uit Odoo | 1. Exporteer data uit Odoo | Excel-rapport (statisch) | MT / Directie |
| Productiesystemen | Handmatige invoer medewerkers | 2. Kopieer naar Excel | E-mail met bijlage | Afdelingsmanagers |
| CRM-systeem | Verkoopdata (losse bestanden) | 3. Combineer bronnen handmatig | Presentatie (PowerPoint) | Financieel medewerkers |
| Inkoopafdeling | Productiecijfers (maatwerk export) | 4. Bouw/update grafieken | Mondelinge toelichting | Inkoop / Verkoop |
| Verkoopafdeling | Klantendata uit CRM | 5. Controleer formules | | |
| | | 6. Deel bestand via e-mail | | |
| | | 7. MT presenteert rapport | | |

---

## 3. Ist — Huidige Situatie

### 3.1 Procesverloop

| # | Processtap | Beschrijving (Ist) | Actor | Systeem/Tool | Frequentie |
|---|---|---|---|---|---|
| 1 | Data exporteren | Medewerker exporteert handmatig data uit Odoo als CSV of Excel-bestand | Financieel medewerker | Odoo ERP → CSV/Excel | Wekelijks / maandelijks |
| 2 | Data samenvoegen | Exportbestanden uit Odoo, CRM en productie worden handmatig samengevoegd in één Excel-werkmap | Financieel medewerker | Excel (handmatig) | Per rapportageperiode |
| 3 | Berekeningen uitvoeren | Marges, cashflows en KPI's worden berekend via handmatige Excel-formules. Formules worden soms gekopieerd zonder controle. | Financieel medewerker | Excel | Per rapportageperiode |
| 4 | Visualisaties maken | Grafieken en tabellen worden handmatig bijgewerkt of opnieuw aangemaakt in Excel of PowerPoint | Financieel medewerker | Excel / PowerPoint | Per rapport |
| 5 | Kwaliteitscontrole | Rapport wordt steekproefsgewijs gecheckt door een collega. Geen gestructureerd validatieproces. | Senior medewerker | Geen formeel systeem | Ad hoc |
| 6 | Distribueren | Rapport wordt als e-mailbijlage verspreid. Er bestaan meerdere versies tegelijkertijd in de omgeving. | Financieel medewerker | E-mail / SharePoint | Wekelijks / maandelijks |
| 7 | Besluitvorming | MT bespreekt rapport in vergadering. Aanvullende vragen leiden opnieuw tot handmatige Excel-aanpassingen. | MT / Directie | PowerPoint / mondeling | Maandelijks / kwartaal |

### 3.2 Doorlooptijd Ist

| Stap | Minimale tijd | Maximale tijd | Opmerking |
|---|---|---|---|
| Exporteren uit Odoo | 30 min | 2 uur | Afhankelijk van periode en aantal systemen |
| Samenvoegen bronnen | 1 uur | 4 uur | Sterk variabel: inconsistente kolomnamen, ontbrekende data |
| Berekeningen & controle | 1 uur | 3 uur | Formulefouten komen regelmatig voor |
| Visualisaties & layout | 30 min | 2 uur | Elke keer opnieuw handmatig aanpassen |
| **Totale cyclustijd** | **3 uur** | **11+ uur** | Per rapportageperiode, per medewerker |

---

## 4. Knelpunten

| # | Knelpunt | Beschrijving | Categorie | Impact |
|---|---|---|---|---|
| K1 | Excel-afhankelijkheid | Het gehele rapportageproces draait op Excel. Er is geen centrale databron, geen versiebeheer en geen rolgebaseerde toegang. | Proces | Hoge foutgevoeligheid, veel tijdsverlies, geen schaalbaarheid |
| K2 | Geen real-time data | Data is altijd verouderd op het moment van rapportage. Een export is een momentopname, niet een levend beeld. | Data | Beslissingen op basis van verouderde informatie |
| K3 | Versnipperde databronnen | Odoo, CRM en productiesystemen zijn niet gekoppeld. Medewerkers combineren exports handmatig, met inconsistentie als gevolg. | Integratie | Fouten bij samenvoegen, dubbel werk, tijdsverlies |
| K4 | Versieproblematiek | Meerdere Excel-versies circuleren tegelijkertijd via e-mail. Onduidelijk welke versie de 'waarheid' is. | Governance | Foutieve besluitvorming, verwarring, herwerk |
| K5 | Geen dataisolatie | Geen rolgebaseerde toegangscontrole. Medewerkers zien potentieel data van andere afdelingen of hebben geen toegang tot wat ze nodig hebben. | Beveiliging | Privacyrisico, AVG-kwetsbaarheid |
| K6 | Hoge doorlooptijd | Rapportage kost per medewerker 3–11 uur per periode. Dit is niet schaalbaar naarmate het bedrijf groeit. | Efficiency | Verlies van productieve uren, te trage besluitcyclus |
| K7 | Geen MT-overzicht | Er is geen overkoepelend dashboard voor de directie. KPI's worden pas zichtbaar na handmatige rapportage. | Management | Beperkt stuurvermogen, reactief in plaats van proactief |
| K8 | Geen adoptie, ontevreden gebruikers | Medewerkers omzeilen systemen en werken buiten Odoo om. Kennis is persoonsgebonden en niet geborgd. | Mensen | Kennisrisico, inconsistentie, weerstand bij verandering |

---

## 5. SIPOC — Gewenste Situatie (Soll)

| S — Suppliers | I — Inputs | P — Process | O — Outputs | C — Customers |
|---|---|---|---|---|
| Odoo ERP (API) | Gestructureerde transactiedata via API | 1. Automatische data-extractie (ETL) | Real-time BI-dashboard (per rol) | MT / Directie |
| CRM (API-sync) | Real-time voorraad & orderdata | 2. Laden in datawarehouse | MT KPI-overzichtsdashboard | Afdelingsmanagers |
| Productiesystemen (API) | Klant- en smaakvoorkeurdata | 3. Datakwaliteitscheck (automatisch) | Automatisch gegenereerde rapporten | Financieel medewerkers |
| Externe marktdata (optioneel) | Productiecijfers (automatisch via API) | 4. Dashboard automatisch vernieuwd | Exportmogelijkheid (PDF/Excel) | Inkoop / Verkoop |
| | | 5. Gebruiker opent BI-tool (self-service) | Alerts bij afwijkende KPI's | Productontwikkeling |
| | | 6. Filter/drill-down op eigen afdelingsdata | | |
| | | 7. Inzicht direct beschikbaar voor besluit | | |

---

## 6. Soll — Gewenste Situatie

### 6.1 Procesverloop

| # | Processtap | Beschrijving (Soll) | Actor | Systeem/Tool | Doorlooptijd |
|---|---|---|---|---|---|
| 1 | Automatische extractie | ETL-pipeline haalt automatisch data op uit Odoo, CRM en productiesystemen via REST API. Geen handmatige export. | Systeem (automatisch) | ETL / Apache Airflow | Continu / scheduled |
| 2 | Laden in datawarehouse | Getransformeerde data wordt geladen in een centraal datawarehouse. Validatieregels filteren fouten automatisch. | Systeem (automatisch) | PostgreSQL / DuckDB | Automatisch |
| 3 | Dashboard vernieuwen | BI-dashboards worden automatisch bijgewerkt op basis van de meest recente data in het datawarehouse. | Systeem (automatisch) | Apache Superset / Metabase | Automatisch |
| 4 | Self-service analyse | Medewerker logt in op BI-tool, ziet alleen eigen afdelingsdata (RBAC) en gebruikt filters, drill-downs en grafieken. | Medewerker / Manager | BI-tool (browser) | Direct, <1 min |
| 5 | MT-dashboard raadplegen | MT opent overkoepelend KPI-dashboard. Alle kerncijfers (marge, cashflow, smaaktrend) zijn direct zichtbaar zonder voorbereiding. | MT / Directie | BI-tool MT-dashboard | Direct, <1 min |
| 6 | Export & rapportage | Indien nodig kan een rapport worden geëxporteerd naar PDF of Excel. Dit vervangt de handmatige opmaak. | Medewerker / Manager | BI-tool (export) | <2 min |
| 7 | Besluitvorming | MT neemt beslissing op basis van actuele dashboard-data. Aanvullende vragen worden direct beantwoord via drill-down. | MT / Directie | BI-tool / vergadering | Tijdens vergadering |

### 6.2 Doorlooptijd Soll (verwacht)

| Stap | Ist (gemiddeld) | Soll (verwacht) | Verbetering |
|---|---|---|---|
| Data verzamelen & samenvoegen | 3–6 uur | 0 min (automatisch) | Volledige eliminatie van handmatige stap |
| Berekeningen & validatie | 1–3 uur | 0 min (automatisch) | Validatieregels in ETL vervangen handmatige controle |
| Dashboard raadplegen | 30 min–2 uur | <1 minuut | Altijd actueel, direct beschikbaar per rol |
| Export voor MT-vergadering | 30 min–1 uur | <2 minuten | Automatisch gegenereerd vanuit BI-tool |
| **Totale cyclustijd** | **5–12 uur** | **<5 minuten** | **~95% reductie in handmatig werk per cyclus** |

---

## 7. Gap-analyse

| Dimensie | Ist (nu) | Soll (gewenst) | Prioriteit | Actie om gap te dichten |
|---|---|---|---|---|
| Dataverzameling | Handmatig exporteren uit Odoo (CSV), meerdere bronnen apart | Automatische ETL-pipeline via API, alle bronnen geïntegreerd | Kritiek | Ontwikkel ETL-pipeline; koppel Odoo, CRM en productie-API's aan datawarehouse |
| Dataactualiteit | Statische snapshot op moment van export, altijd verouderd | Real-time of near-real-time data in dashboards | Kritiek | Stel scheduled ETL in (bijv. elk uur); gebruik webhooks waar Odoo dit ondersteunt |
| Rapportagetool | Excel, verspreiding via e-mail, geen versiebeheer | Centrale BI-tool met live dashboards en rolgebaseerde toegang | Kritiek | Implementeer Apache Superset of Metabase; migreer bestaande Excel-rapporten naar dashboards |
| Toegangscontrole | Geen RBAC; iedereen ziet potentieel alle data | RBAC: elke afdeling ziet alleen eigen data, MT ziet alles | Hoog | Configureer rollen en rechten in BI-tool per afdeling en functie |
| Beveiliging | Geen 2FA, bestanden verspreid via e-mail | 2FA verplicht, encryptie, Europese hosting | Hoog | Activeer 2FA in BI-tool; host op Europese server; stel TLS in voor alle verbindingen |
| MT-inzicht | Geen overkoepelend dashboard; KPI's pas zichtbaar na handmatige rapportage | Live MT-dashboard met marges, cashflow, KPI's | Hoog | Bouw MT-dashboard als eerste use case; valideer KPI-definitie met MT voor go-live |
| Gebruikersadoptie | Ontevreden gebruikers, workarounds met Excel buiten systemen om | Brede adoptie, tool gebruikt als standaard voor rapportage | Hoog | Excel-achtige interface (Metabase); betrek eindgebruikers bij ontwerp; bied training aan |
| Schaalbaarheid | Excel crasht bij grote datasets; geen schaaloptie | Systeem verwerkt grote volumes zonder performanceverlies | Middel | Gebruik DuckDB of PostgreSQL als datawarehouse; test met productievolume vóór go-live |
| Datakwaliteit | Geen validatie; fouten in formules en kopieerpasta | Automatische validatieregels in ETL; datakwaliteitsrapportage | Middel | Definieer validatieregels per databron; bouw datakwaliteitsdashboard voor beheerteam |
| Excel-transitie | Excel is enige werktool; medewerkers kennen geen alternatief | Excel blijft mogelijk als exportformaat; invoer via BI-tool of Odoo | Middel | Behoud Excel-exportfunctie als 'vangnet'; stimuleer actief gebruik van dashboards |

### 7.1 Prioriteitenlegenda

| Prioriteit | Betekenis | Gaps |
|---|---|---|
| Kritiek | Direct aanpakken — blokkeert go-live | Dataverzameling, Dataactualiteit, Rapportagetool |
| Hoog | Aanpakken in fase 1–2 | Toegangscontrole, Beveiliging, MT-inzicht, Adoptie |
| Middel | Aanpakken in fase 2–3 | Schaalbaarheid, Datakwaliteit, Excel-transitie |

---

## 8. Conclusie

De gap-analyse toont aan dat het huidige rapportageproces structureel tekortschiet op drie kritieke dimensies: **dataverzameling is volledig handmatig**, **data is nooit actueel** en **er is geen centrale rapportagetool met rolgebaseerde toegang**. Deze drie gaps blokkeren een succesvolle go-live en moeten als eerste worden aangepakt.

De overige gaps (beveiliging, adoptie, schaalbaarheid) zijn oplosbaar binnen de bestaande kaders van een open source BI-tool zoals Apache Superset of Metabase, mits de implementatie gefaseerd wordt uitgevoerd en eindgebruikers vroeg worden betrokken.

De verwachte tijdsbesparing van **~95% per rapportagecyclus** rechtvaardigt de investering zelfs bij een minimaal budget.
