## 1. Actoren

Een actor is een persoon, systeem of organisatie die interactie heeft met de applicatie. Hieronder staan alle actoren beschreven met hun rol en verantwoordelijkheden.

---

### Consument (B2C-klant)

| Veld | Beschrijving |
|---|---|
| **Rol** | Eindgebruiker van de mobiele applicatie |
| **Beschrijving** | Particuliere klant die chocoladeproducten koopt en de app gebruikt voor productregistratie, informatie en ondersteuning |
| **Acties** | Producten registreren via QR-code of batchnummer, persoonlijk dashboard raadplegen, klachten indienen, bestellingen plaatsen, community gebruiken, evenementen inschrijven |

---

### B2B-klant

| Veld | Beschrijving |
|---|---|
| **Rol** | Zakelijke afnemer van de Chocolate Firm |
| **Beschrijving** | Bedrijf of organisatie dat een groothandels- of inkooprelatie heeft met de Chocolate Firm |
| **Acties** | Notificaties ontvangen over levertijden en voorraadstatus, productieplanning inzien, bestellingen plaatsen via de app, klachten en retouren indienen |

---

### Klantenservicemedewerker

| Veld | Beschrijving |
|---|---|
| **Rol** | Interne medewerker die klantcontact afhandelt |
| **Beschrijving** | Medewerker die live chats beantwoordt, terugbelverzoeken verwerkt en complexe klachten oppakt die de chatbot niet kan oplossen |
| **Acties** | Live chat voeren met klanten, klachtendossiers beheren, statusupdates doorsturen, terugbelafspraken inplannen |

---

### AI-chatbot

| Veld | Beschrijving |
|---|---|
| **Rol** | Geautomatiseerde actor (systeem) |
| **Beschrijving** | 24/7 beschikbare AI-assistent gekoppeld aan CRM-gegevens voor gepersonaliseerde antwoorden |
| **Acties** | Veelgestelde vragen beantwoorden, klanten doorverwijzen naar de juiste afdeling of medewerker, klachten herkennen en standaardoplossingen aanbieden |

---

### Productbeheerder / Content Manager

| Veld | Beschrijving |
|---|---|
| **Rol** | Interne beheerder van productcontent |
| **Beschrijving** | Medewerker verantwoordelijk voor het beheren en updaten van productkaarten, recepten, video's en achtergrondverhalen in de app |
| **Acties** | Productinformatie toevoegen en bijwerken, nieuwe recepten en content publiceren, meertalige vertalingen beheren, notificaties configureren voor productupdates |

---

### Marketingmedewerker

| Veld | Beschrijving |
|---|---|
| **Rol** | Interne actor verantwoordelijk voor promoties en campagnes |
| **Beschrijving** | Medewerker die exclusieve aanbiedingen, limited editions en gepersonaliseerde promoties beheert in de app |
| **Acties** | Pushnotificaties configureren, aanbiedingen en early-access deals aanmaken, community-challenges en gamification-elementen beheren |

---

### Beheerder / Systeembeheerder

| Veld | Beschrijving |
|---|---|
| **Rol** | Technisch beheerder van het systeem |
| **Beschrijving** | IT-medewerker verantwoordelijk voor de technische werking, integraties en beveiliging van de applicatie |
| **Acties** | Gebruikersrollen en toegangsrechten beheren, integraties met ERP, BI-tool en CRM monitoren, beveiligingsupdates uitvoeren, prestaties bewaken |

---

### ERP-systeem (Odoo)

| Veld | Beschrijving |
|---|---|
| **Rol** | Extern gekoppeld systeem |
| **Beschrijving** | Het ERP-systeem levert actuele informatie over voorraad, bestellingen, productie en kwaliteitsmeldingen aan de app |
| **Acties** | Voorraadstatus doorgeven, bestellingen verwerken, seizoensbeschikbaarheid synchroniseren, kwaliteitsmeldingen doorsturen |

---

### CRM-systeem(Odoo)

| Veld | Beschrijving |
|---|---|
| **Rol** | Extern gekoppeld systeem |
| **Beschrijving** | Het CRM-systeem beheert klantprofielen en zorgt voor gepersonaliseerde ervaringen op basis van aankoopgeschiedenis en voorkeuren |
| **Acties** | Klantprofielen synchroniseren, aankoopgeschiedenis doorgeven aan de aanbevelingsengine, klantcommunicatie loggen |

---

### BI-tool (Apache Superset)

| Veld | Beschrijving |
|---|---|
| **Rol** | Extern gekoppeld systeem |
| **Beschrijving** | Apache Superset ontvangt geanonimiseerde gebruiksdata van de app en levert inzichten terug over klantgedrag en smaaktrends via interactieve dashboards |
| **Acties** | Gebruiksdata verwerken, interactieve dashboards vullen met smaaktrends en aankooppatronen, inzichten beschikbaar maken voor productontwikkeling en marketing |

---

### Overzicht actoren

| # | Actor | Type | Primaire interactie |
|:---:|---|:---:|---|
| 1 | Consument (B2C-klant) | Mens | Productregistratie, informatie, community, bestellingen |
| 2 | B2B-klant | Mens | Bestellingen, voorraad, levertijden |
| 3 | Klantenservicemedewerker | Mens | Live chat, klachtafhandeling |
| 4 | AI-chatbot | Systeem | Geautomatiseerde klantvragen |
| 5 | Productbeheerder / Content Manager | Mens | Contentbeheer, productkaarten |
| 6 | Marketingmedewerker | Mens | Promoties, notificaties, gamification |
| 7 | Beheerder / Systeembeheerder | Mens | Technisch beheer, integraties, beveiliging |
| 8 | ERP-systeem (Odoo) | Systeem | Voorraad, bestellingen, kwaliteit |
| 9 | CRM-systeem | Systeem | Klantprofielen, personalisatie |
| 10 | BI-tool | Systeem | Data-analyse, smaaktrends |