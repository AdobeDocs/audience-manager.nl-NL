---
description: Algemene vragen en problemen in verband met targeting.
seo-description: Algemene vragen en problemen in verband met targeting.
seo-title: Veelgestelde vragen over targeting
solution: Audience Manager
title: Veelgestelde vragen over targeting
uuid: ee96ef71-b903-4953-afc4-8ec8e48bd49e
feature: Match Rates
translation-type: tm+mt
source-git-commit: 27ce94084e35ffa770858027d12235ca9f1f8430
workflow-type: tm+mt
source-wordcount: '920'
ht-degree: 100%

---


# Veelgestelde vragen over targeting {#targeting-faq}

Algemene vragen en problemen in verband met targeting.

<br>

<!-- 

faq_targeting.xml

 -->

**Waar kan ik een volledige lijst vinden met externe dataproviders die door Audience Manager worden ondersteund?**

Raadpleeg [Adobe Exchange Marketplace](https://exchange.adobe.com/experiencecloud.html) voor een volledige lijst met externe dataproviders die door [!DNL Audience Manager] worden ondersteund.

<br> 

**Moet ik voor het targeten van gebruikers die ik nog nooit op mijn website met externe data heb gezien, externe data in Audience Manager gebruiken of in een DSP?**

Het antwoord hangt af van uw doelstellingen. Als uw campagne bijvoorbeeld is ontworpen om nieuwe klanten met externe data te vinden, werk dan rechtstreeks met een DSP. Bedenk dat Audience Manager data pas met een externe dataprovider synchroniseert wanneer we deze gebruiker zien. Als we een gebruiker nog nooit hebben gezien, heeft ons systeem geen informatie voor deze websitebezoeker. Maak deze segmenten via het DSP voor campagnes die alleen externe data willen gebruiken om gebruikers te targeten die nog nooit een van uw eigenschappen hebben bezocht.

<br> 

**Kan ik mijn marketing richten op individuen?**

Met Audience Manager kunt u gebruikers samenvoegen en uw marketing op hen richten op basis van gedeelde kenmerken of eigenschappen. Om aan de branchevoorschriften te voldoen kunnen [!DNL Audience Manager]-klanten echter geen persoonlijk identificeerbare informatie (PII) naar onze systemen verzenden. U kunt daarom geen e-mailadressen, individuele namen, fysieke adressen, enzovoort gebruiken voor targeting.

<br> 

**Hoe houd ik retargeting data veilig?**

We raden u aan een server-naar-server-verbinding te gebruiken om data uit te wisselen met uw geprefereerde retargetingplatform. Audience Manager wisselt data uit met de meeste belangrijke DSP’s via server-naar-server-verbindingen. Server-naar-server-dataoverdrachten helpen voorkomen dat andere instanties uw data onderscheppen en deze doelgroepinformatie doorverkopen.

<br> 

**Is de unieke gebruikers-id (UUID) van Audience Manager gekoppeld aan de unieke gebruikers-id van een advertentieserver door id-synchronisatie rechtstreeks op de pagina?**

Nee. Id-synchronisaties worden niet op de pagina uitgevoerd voor onsite uitgevers of servers. De Audience Manager-UUID wordt ingevoegd in het veld `u=` van de logboekbestanden van de advertentieserver. Dit gebeurt wanneer het segment wordt binnengehaald voor targeting. De DIL-codemodule voert deze functie uit. Dit is hetzelfde mechanisme waardoor we de gebruikers-id van de server kunnen toewijzen aan een Audience Manager-gebruiker voor rapportage van segmentprestaties. Als er echter een advertentieserver op de website aanwezig is, worden id’s rechtstreeks op de pagina gesynchroniseerd.

<br> 

**Telt Audience Manager een gebruiker mee die zich via verschillende apparaten aanmeldt als één unieke gebruiker of verschillende unieke gebruikers?**

Met [Declared ID Targeting](../features/declared-ids.md#declared-id-targeting) kan Audience Manager een bezoeker op meerdere apparaten identificeren met één unieke id. Maar vanuit het oogpunt van targeting of bestemming zijn dit nog steeds twee (of meer) gebruikers, omdat DSP’s deze id’s niet met elkaar in overeenstemming kunnen brengen.

<br> 

**Kan Audience Manager een gebruiker identificeren op basis van display en mobiele apparaten?**

Ja. Zie [Declared ID Targeting](../features/declared-ids.md#declared-id-targeting).

<br> 

**Kan ik gebruikers tellen met data die online zijn verzameld, en ze opnieuw toewijzen op basis van deze modelscore?**

Ja. Audience Manager kan databestanden verschaffen om u te helpen gebruikers te tellen, maar u moet met andere leveranciers of software werken om deze informatie te analyseren en te rangschikken. Verzend deze data naar Audience Manager in de vorm van sleutelwaardeparen. We kunnen deze informatie aan bestaande gebruikersprofielen toevoegen. Neem contact op met uw Partner Solutions-vertegenwoordiger om dit proces te beoordelen.

<br> 

**Wat is het percentage van cookieverwijderingen in een bepaalde periode van 1 tot 2 maanden?**

Het is moeilijk om de verwijdering van cookies te meten. De meeste cookies worden verwijderd door een paar bezoekers die cookies vaak verwijderen. De meeste browsercookies zijn echter minstens 30 dagen stabiel, ook al hebben sommige een beperkte levensduur. Sommige onderzoeken suggereren dat upper-funnel targeting gedurende meer dan 30 dagen in feite 7% van de browserdoelgroep verwijdert in een periode van 30 dagen. Zoals u weet zijn campagnes van 30 dagen voor een bepaalde creatieve boodschap standaard in de industrie. Uit wat we hebben gezien blijkt dat een uitval van 7% correct is.

Cookieverwijdering heeft een negatief effect op de berekeningen van bereik en frequentie. Daarom benadrukken we de waarde van gedragsdata wanneer we proberen de ware aard van consumententrends te begrijpen voor onze planning van displaycampagnes. Onze klanten kunnen Audience Manager-rapporten voor segmentoverlap, optimale impressiefrequentie en unieke gebruikerstrends binnen specifieke datumbereiken gebruiken om hun campagneplanning en optimale datumbereiken voor het voeren van campagnes wetenschappelijker aan te pakken.

<br> 

**Wat is het verloopvenster voor Audience Manager-cookies?**

In de gebruikersinterface kunt u het verloopinterval van cookies bepalen. U kunt cookies instellen om te verlopen na *n* dagen of nooit.

<br> 

**Zijn er meer kosten verbonden aan het implementeren van een creatieve campagne in een gebeurteniscall?**

Dat hangt ervan af. Kosten zijn gebaseerd op unieke gebruikers. Als een campagne netto nieuwe gebruikers oplevert, zal dat inderdaad meer kosten. Als uw campagne plaatsen bereikt waar wij al data verzamelen, zijn er geen extra kosten. Als uw campagne wordt gevoerd op verwante websites een aanzienlijke overlapping is, zijn er extra kosten voor de nieuwe unieke gebruikers die we zien.

<br> 

**Audience Manager geeft alleen [!UICONTROL Addressable Audiences]-cijfers en matchpercentages weer voor [!UICONTROL Server-to-Server]-bestemmingen. Kunt u uitleggen waarom we deze cijfers voor cookie- en URL-bestemmingen niet zien?**

Dat heeft te maken met id-synchronisaties. Voor [!UICONTROL Server-to-Server]-bestemmingen brengen we data offline (in real time of in batch) over en we moeten de id verzenden die de bestemmingspartner begrijpt, zodat ze deze kunnen weer kunnen toewijzen aan de browser. Het adresseerbare aantal van het segment is een subgroep van de totale segmentpopulatie.

Bij cookie- en URL-bestemmingen is de gebruiker al in de browser en wat [!DNL Audience Manager] verzendt, zijn alleen de segmenten waarvoor de gebruiker in aanmerking komt. De bestemmingspartner kan alleen de segmenttoewijzingen oppakken en met die informatie werken. Beschouw de matchpercentages voor cookie- en URL-bestemmingen dus altijd als 100%.
