---
description: Veelvoorkomende gerichte vragen en problemen.
seo-description: Veelvoorkomende gerichte vragen en problemen.
seo-title: Veelgestelde vragen over doelen
solution: Audience Manager
title: Veelgestelde vragen over doelen
uuid: ee96ef71-b903-4953-afc4-8ec8e48bd49e
translation-type: tm+mt
source-git-commit: f9a12cf38833cf243edf4bc4c4f4e91f83ee0ca2

---


# Veelgestelde vragen over doelen{#targeting-faq}

Veelvoorkomende gerichte vragen en problemen.

<br> 

<!-- 

faq_targeting.xml

 -->

**Waar kan ik een volledige lijst van derdegegevensleveranciers vinden die door de Manager van het Publiek wordt gesteund?**

Zie de [Adobe Exchange Marketplace](https://marketing.adobe.com/resources/content/resources/en/exchange/marketplace/audience.html) (https://marketing.adobe.com/resources/content/resources/en/exchange/marketplace/audience.html) voor een volledige lijst met externe gegevensproviders die [!DNL Audience Manager] ondersteuning bieden.

<br> 

**Om gebruikers te richten die ik nooit op mijn plaats met derdegegevens heb gezien, zou ik derdegegevens in de Manager van het Publiek of in DSP moeten gebruiken?**

Het antwoord hangt af van uw doelstellingen. Bijvoorbeeld, als uw campagne wordt ontworpen om nieuwe cliënten met derdegegevens te vinden, dan werk direct met DSP. Herinner me, de Manager van de Publiek synchroniseert gegevens met een derdegegevensleverancier slechts wanneer wij die gebruiker zien. Als we nog nooit een gebruiker hebben gezien, heeft ons systeem geen informatie voor die bezoeker van de site. Voor campagnes die slechts derdegegevens aan doelgebruikers willen gebruiken die nooit om het even welk van uw eigenschappen hebben bezocht, dan creeer die segmenten door DSP.

<br> 

**Kan ik mensen op de markt brengen?**

Met Audience Manager kunt u gebruikers samenvoegen en op basis van gedeelde kenmerken of kenmerken op de markt brengen. Om aan de industrieregels te voldoen, kunnen [!DNL Audience Manager] klanten echter geen persoonlijk identificeerbare informatie (PII) naar onze systemen verzenden. U kunt daarom geen e-mailadressen, individuele namen, fysieke adressen enzovoort gebruiken. voor doelwitten.

<br> 

**Hoe blijf ik het opnieuw richten gegevens veilig?**

We raden u aan een server-naar-server verbinding te gebruiken om gegevens uit te wisselen met uw voorkeursplatform. De Manager van de publiek ruilt gegevens met de meeste belangrijkste DSPs door server-aan-server verbindingen. De server-aan-server gegevensoverdrachten helpen andere actoren verhinderen uw gegevens te onderscheppen en die publieksinformatie opnieuw te verkopen.

<br> 

**Is de unieke gebruikers-id (UUID) van Audience Manager gekoppeld aan de unieke gebruikers-id van een advertentieserver door ID rechtstreeks op de pagina te synchroniseren?**

Nee. ID-synchrone versies worden niet op de pagina gemaakt voor onsite uitgevers of servers. De UUID van Audience Manager wordt ingevoegd in het `u=` veld van de logbestanden van de advertentieserver. Dit gebeurt als segment binnen wordt overgegaan voor het richten. De DIL-codemodule voert deze functie uit. Dit is het zelfde mechanisme dat ons toestaat om de gebruiker van de server in kaart te brengen - identiteitskaart aan een gebruiker van de Manager van de Publiek voor segmentprestaties rapporterend. Als er echter een advertentieserver aanwezig is op de site, worden id&#39;s rechtstreeks op de pagina gesynchroniseerd.

<br> 

**Telt Audience Manager een gebruiker die zich bij verschillende apparaten aanmeldt als één unieke gebruiker of verschillende unieke gebruikers?**

[Met gedeclareerde id-doelen](../features/declared-ids.md#declared-id-targeting) kan Audience Manager een bezoeker op meerdere apparaten identificeren met één unieke id. Nochtans, vanuit een gericht of bestemmingsperspectief, is dit nog 2 (of meer) gebruikers omdat DSPs die veelvoudige IDs niet kan in overeenstemming brengen.

<br> 

**Kan Audience Manager een gebruiker identificeren op basis van weergave en mobiele apparaten.**

Ja. Zie Waardering [voor gedeclareerde id&#39;s](../features/declared-ids.md#declared-id-targeting).

<br> 

**Kan ik gebruikers scoren met gegevens die online zijn verzameld en ze opnieuw toewijzen op basis van deze modelscore?**

Ja. De Manager van de publiek kan gegevensdossiers verstrekken om u te helpen gebruikers scoren, maar u moet met andere verkopers of software samenwerken om deze informatie te analyseren en te rangschikken. Verzend deze gegevens naar Audience Manager in de vorm van sleutel-waardeparen. We kunnen deze gegevens naar bestaande gebruikersprofielen kopiëren en deze toevoegen. Neem contact op met de vertegenwoordiger van de Partner Solutions om dit proces te beoordelen.

<br> 

**Wat zijn de cijfers voor het verwijderen van cookies in een bepaalde periode van 1 tot 2 maanden?**

Verwijderen van cookies is moeilijk te meten. De meeste cookies worden verwijderd door een paar bezoekers die cookies vaak verwijderen. De meeste cookies in de browser zijn echter minstens 30 dagen stabiel, ook al hebben sommige een beperkte levensduur. Sommige studies suggereren dat het richten van de bovenste-trechter die meer dan 30 dagen is 7% van het browser doelpubliek over een periode van 30 dagen effectief elimineert. Zoals u weet, zijn campagnes van 30 dagen voor een bepaalde creatieve boodschap standaard in de industrie. Uit wat we hebben gezien, blijkt dat 7% korting correct is.

Cookie-verwijdering heeft een negatief effect op bereik- en frequentieberekeningen. Als gevolg hiervan benadrukken we de waarde van gedragsgegevens wanneer we proberen de ware aard van de trends van de consument voor de planning van de weergavecampagne te begrijpen. Onze klanten kunnen de segmentoverlap van Audience Manager, de optimale rapporten van de impressiefrequentie, en unieke gebruikerstendensen over specifieke datumwaaiers gebruiken om wetenschappelijker over campagneplanning en optimale datumwaaiers voor het runnen van campagnes te zijn.

<br> 

**Wat is het verloopvenster voor de koekjes van de Manager van de Publiek?**

In de gebruikersinterface kunt u het interval voor het verlopen van het cookie bepalen. U kunt cookies instellen op verlopen na *n* dagen of nooit.

<br> 

**Zijn er meer kosten verbonden aan het uitvoeren van een creatieve campagne in een evenement?**

Het hangt ervan af. De kosten zijn gebaseerd op unieke gebruikers. Als een campagne nieuwe gebruikers oplevert, dan zal dat inderdaad meer kosten. Als uw campagne plaatsen bereikt waar wij reeds gegevens verzamelen, dan zijn er geen extra kosten. Als uw campagne op verwante plaatsen loopt waar er significante overlapping is, zullen er extra kosten voor de nieuwe unieke gebruikers zijn wij zien.

<br> 

**De Manager van de publiek toont[!UICONTROL Addressable Audiences]metriek en gelijke tarieven voor[!UICONTROL Server-to-Server]bestemmingen slechts. Kunt u verklaren waarom wij deze cijfers voor bestemmingen Cookie en URL niet zien?**

Het komt neer op ID syncs. Voor [!UICONTROL Server-to-Server] bestemmingen, brengen wij gegevens offline (of real time of partij) over en wij moeten identiteitskaart verzenden die de bestemmingspartner begrijpt, zodat kunnen zij het terug naar browser in kaart brengen. Het adresseerbare aantal van het segment is een ondergroep van de totale segmentpopulatie.

In het geval van Koekje en bestemmingen URL, is de gebruiker reeds op browser, en wat [!DNL Audience Manager] verzendt is enkel de segmenten die de gebruiker voor kwalificeerde. De bestemmingspartner kan enkel de segmentafbeeldingen opnemen en met die informatie werken. Neem dus de overeenkomende snelheden voor Cookie- en URL-doelen altijd 100% in overweging.
