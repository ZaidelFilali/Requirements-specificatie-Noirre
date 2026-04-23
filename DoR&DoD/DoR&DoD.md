# User Stories – BI-tool (Apache Superset) voor The Chocolate Firm

## Definition of Ready (DoR)

Een user story mag pas de sprint in als aan **alle** onderstaande criteria is voldaan:

1. De user story is geschreven in het standaardformaat: *"Als [rol] wil ik [functionaliteit] zodat [waarde]."*
2. De acceptatiecriteria zijn concreet en toetsbaar geformuleerd (SMART).
3. De story is besproken met en begrepen door het hele team (refinement is gedaan).
4. De benodigde databronnen zijn geïdentificeerd (bijv. welke Odoo-modules, Excel-bestanden of externe bronnen nodig zijn).
5. Afhankelijkheden met andere stories of systemen (Odoo ERP/CRM, leveranciersportalen) zijn in kaart gebracht en geborgd.
6. De story is ingeschat door het team (story points).
7. De story is klein genoeg om binnen één sprint af te ronden.
8. Eventueel benodigde wireframes, mock-ups of KPI-definities zijn beschikbaar.
9. De betrokken stakeholder of product owner is beschikbaar voor vragen tijdens de sprint.

---

## Definition of Done (DoD)

Een user story is pas "Done" als aan **alle** onderstaande criteria is voldaan:

1. De functionaliteit voldoet aan alle geformuleerde acceptatiecriteria.
2. De code/configuratie is gereviewd door minimaal één ander teamlid (peer review).
3. De dataverbinding met de juiste bron (Odoo, Excel, extern) is werkend en gevalideerd op correctheid.
4. Het dashboard of de rapportage toont correcte, actuele data (steekproefcontrole uitgevoerd).
5. De oplossing is getest door een eindgebruiker van de betreffende afdeling (verkoop, productie, financiën, etc.).
6. De KPI-berekeningen zijn uniform en komen overeen met de afgestemde definities (single source of truth).
7. De documentatie in GitHub (Markdown) is bijgewerkt: technische beschrijving, gebruikte databronnen en eventuele configuratiestappen.
8. De oplossing werkt in de afgesproken omgeving (test- of acceptatieomgeving).
9. Eventuele bekende beperkingen of bugs zijn gedocumenteerd in de backlog.
10. De product owner heeft de story geaccepteerd na een demo.

---

## Story Point Referentie

| Punten | Omvang | Voorbeeld |
|--------|--------|-----------|
| 1–2    | Zeer klein, minimale complexiteit | Tekstaanpassing, filter toevoegen |
| 3      | Klein, weinig onzekerheid | Eenvoudige tabelweergave |
| 5      | Gemiddeld, bekende techniek | Dashboard met één databron |
| 8      | Groot, meerdere databronnen of complexe logica | Dashboard met gecombineerde data en berekeningen |
| 13     | Zeer groot, veel afhankelijkheden | Overkoepelend dashboard met drilldowns naar meerdere afdelingen |

---

## User Stories

### Verkoop & Marketing

#### US-01 | Campagne-effectiviteit dashboard

> *Als marketingmanager wil ik een dashboard dat de omzet per campagne en klantsegment toont, zodat ik kan zien welke campagnes het meest effectief zijn.*

**Acceptatiecriteria:**

- Het dashboard toont omzet uitgesplitst per campagne en per klantsegment.
- Data wordt opgehaald uit Odoo CRM (campagnedata) en ERP (orderdata).
- Resultaten zijn filterbaar op periode (week, maand, kwartaal, jaar).
- Het dashboard laadt binnen 5 seconden bij een dataset van minimaal 10.000 records.

**Databronnen:** Odoo CRM, Odoo ERP  
**Inschatting:** 8 story points

---

#### US-02 | Seizoensvoorspelling verkoop

> *Als verkoopmanager wil ik een trendvisualisatie op basis van historische verkoopdata, zodat ik seizoenspieken (Pasen, Kerst) kan voorspellen en de voorraad hierop kan afstemmen.*

**Acceptatiecriteria:**

- De grafiek toont verkoopdata van minimaal de afgelopen 2 jaar op maandbasis.
- Seizoenspieken worden visueel gemarkeerd in de grafiek.
- Data is afkomstig uit Odoo ERP (verkooporders).
- De gebruiker kan filteren op productlijn en regio.

**Databronnen:** Odoo ERP  
**Inschatting:** 5 story points

---

#### US-03 | Klantmarge-analyse

> *Als verkoopmanager wil ik inzicht in de marge per klant, zodat ik kan bepalen welke klanten het meest winstgevend zijn.*

**Acceptatiecriteria:**

- Het overzicht toont omzet, kosten en marge per klant.
- De data combineert verkoopdata en kostendata uit Odoo ERP.
- Resultaten zijn sorteerbaar op hoogste en laagste marge.
- Het rapport is exporteerbaar naar Excel (CSV).

**Databronnen:** Odoo ERP  
**Inschatting:** 5 story points

---

### Productie & Logistiek

#### US-04 | Verspillingsmonitor productie

> *Als productiemanager wil ik een dashboard dat verspilling per productbatch toont, zodat ik kan ingrijpen wanneer de verspilling boven de norm komt.*

**Acceptatiecriteria:**

- Het dashboard toont verspillingspercentage per batch.
- Er is een drempelwaarde instelbaar waarboven een visuele waarschuwing verschijnt.
- Data wordt opgehaald uit het maatwerksysteem op productie via API.
- Historische trends zijn zichtbaar over minimaal 6 maanden.

**Databronnen:** Maatwerk productiesysteem (API)  
**Inschatting:** 8 story points

---

#### US-05 | Realtime voorraadniveaus

> *Als logistiek medewerker wil ik realtime inzicht in voorraadniveaus van grondstoffen, zodat ik tijdig kan bijbestellen en productiestilstand voorkom.*

**Acceptatiecriteria:**

- Het dashboard toont actuele voorraadniveaus per grondstof.
- Minimumvoorraden zijn instelbaar met een visueel signaal bij onderschrijding.
- Data wordt minimaal elke 15 minuten vernieuwd vanuit Odoo ERP.
- De gebruiker kan filteren op productcategorie en magazijnlocatie.

**Databronnen:** Odoo ERP  
**Inschatting:** 5 story points

---

#### US-06 | Productie-KPI overzicht

> *Als productiemanager wil ik een overzicht van KPI's zoals productie per uur, afgekeurde batches en doorlooptijd per order, zodat ik de productie-efficiëntie kan bewaken.*

**Acceptatiecriteria:**

- Het dashboard toont de drie genoemde KPI's in één weergave.
- KPI-definities zijn uniform vastgelegd en gedocumenteerd.
- Data is afkomstig uit Odoo ERP en het productiesysteem.
- Resultaten zijn filterbaar op productielijn en periode.

**Databronnen:** Odoo ERP, maatwerk productiesysteem (API)  
**Inschatting:** 8 story points

---

### Financiën

#### US-07 | Marge per productlijn

> *Als financieel manager wil ik een analyse van marges per productlijn en klantsegment, zodat ik kan adviseren over pricing en assortiment.*

**Acceptatiecriteria:**

- Het dashboard toont bruto- en nettomarge per productlijn en per klantsegment.
- De berekening van marges is afgestemd met de financiële afdeling en gedocumenteerd.
- Data combineert verkoop- en kostendata uit Odoo ERP.
- Vergelijking met vorige perioden is mogelijk.

**Databronnen:** Odoo ERP  
**Inschatting:** 8 story points

---

#### US-08 | Cashflow dashboard

> *Als financieel manager wil ik een realtime cashflow-dashboard, zodat ik de liquiditeitspositie van het bedrijf kan monitoren.*

**Acceptatiecriteria:**

- Het dashboard toont inkomende en uitgaande geldstromen op dag-, week- en maandniveau.
- Data wordt opgehaald uit Odoo ERP (facturen, betalingen).
- De weergave is grafisch en lijkt qua opbouw op een Excel-overzicht.
- Data is maximaal 1 uur oud.

**Databronnen:** Odoo ERP  
**Inschatting:** 8 story points

---

### Duurzaamheid & Kwaliteit

#### US-09 | Duurzaamheidsdashboard

> *Als directielid wil ik een dashboard met KPI's over CO₂-uitstoot, energieverbruik en grondstoffenverspilling, zodat ik onze voortgang op duurzaamheidsdoelen kan rapporteren.*

**Acceptatiecriteria:**

- Het dashboard toont minimaal drie duurzaamheids-KPI's.
- Data is afkomstig uit productiesystemen en eventueel handmatige invoer (Excel-import).
- Trends zijn zichtbaar op maand- en kwartaalbasis.
- Het dashboard is toegankelijk voor directieleden via rolgebaseerde toegang.

**Databronnen:** Maatwerk productiesysteem (API), Excel-import  
**Inschatting:** 8 story points

---

#### US-10 | Klachtenoverzicht klantenservice

> *Als klantenservicemanager wil ik een overzicht van klachten, responstijden en klanttevredenheid, zodat ik knelpunten in de service kan identificeren.*

**Acceptatiecriteria:**

- Het dashboard toont aantal klachten, gemiddelde responstijd en klanttevredenheidsscore.
- Data wordt opgehaald uit Odoo CRM.
- Resultaten zijn filterbaar op productcategorie en periode.
- Er is een drilldown mogelijk van overzicht naar individuele klachten.

**Databronnen:** Odoo CRM  
**Inschatting:** 5 story points

---

### Overkoepelend / MT

#### US-11 | MT-overzichtsdashboard

> *Als directielid wil ik één centraal dashboard waarin de belangrijkste KPI's van alle afdelingen zichtbaar zijn, zodat ik in één oogopslag de bedrijfsprestaties kan beoordelen.*

**Acceptatiecriteria:**

- Het dashboard bevat minimaal één KPI per afdeling (verkoop, productie, financiën, kwaliteit).
- Elke KPI is doorklikbaar naar het gedetailleerde afdelingsdashboard.
- Het dashboard is alleen toegankelijk voor MT-leden (rolgebaseerde toegang).
- Data wordt minimaal dagelijks vernieuwd.

**Databronnen:** Alle gekoppelde bronnen  
**Inschatting:** 13 story points

---

#### US-12 | Rolgebaseerde toegangscontrole

> *Als IT-beheerder wil ik dat gebruikers alleen de data van hun eigen afdeling kunnen zien, zodat vertrouwelijke informatie beschermd blijft.*

**Acceptatiecriteria:**

- Elke afdeling heeft een eigen rol met bijbehorende datarechten.
- Het MT heeft een rol die inzicht geeft in alle afdelingen.
- Authenticatie verloopt via username/wachtwoord met tweefactorauthenticatie.
- Rechten zijn beheerbaar door het IT-team zonder externe hulp.

**Databronnen:** Apache Superset RBAC-configuratie  
**Inschatting:** 8 story points

## Bronvermelding
 
### Opdracht & Casus
 
- Hogeschool Utrecht. (2026). *Pakket/leverancier selectie & Implementatieplan*. Canvas HU. https://canvas.hu.nl/courses/50249/pages/pakket-slash-leverancier-selectie-and-implementatieplan

### Interview
 
- Manager IT & Financiën, The Chocolate Firm. (2026, 17 april). *Interview behoefteanalyse BI-tool* [Persoonlijk interview]. Hogeschool Utrecht.

### Odoo & Superset integratie
 
- Technaureus. (z.d.). *Data Potential: Integrating Odoo with Apache Superset*. Geraadpleegd op 22 april 2026, van https://www.technaureus.com/blog-detail/integrating-odoo-with-apache-superset

