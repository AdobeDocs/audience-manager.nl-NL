---
description: Audience Manager neemt gegevensbeveiliging en privacy zeer serieus. We werken eraan om onze systemen veilig te houden en uw waardevolle gegevens te beschermen.
seo-description: Audience Manager neemt gegevensbeveiliging en privacy zeer serieus. We werken eraan om onze systemen veilig te houden en uw waardevolle gegevens te beschermen.
seo-title: Gegevensbeveiliging in Audience Manager
solution: Audience Manager
title: Gegevensbeveiliging in Audience Manager
uuid: 33ad19ca-4690-4d97-853b-1882d7d4ac01
translation-type: tm+mt
source-git-commit: 0869e016d7f80710cb194449c48675b82fdfa865
workflow-type: tm+mt
source-wordcount: '1025'
ht-degree: 0%

---


# Gegevensbeveiliging in Audience Manager {#data-security}

Audience Manager neemt gegevensbeveiliging en privacy zeer serieus. We werken eraan om onze systemen veilig te houden en uw waardevolle gegevens te beschermen.

De veiligheidspraktijken van de Audience Manager omvatten externe en interne controles, activiteitenregistreren, opleiding, en andere procedures die worden ontworpen om onze systemen en uw waardevolle gegevens te helpen beschermen. Wij zijn van mening dat een veilig product helpt bij het opbouwen en onderhouden van het vertrouwen dat klanten in ons hebben.

In de Audience Manager denken we aan veiligheid in drie hoofdcategorieën:

| Beveiligingstype | Biedt ondersteuning voor |
|---|---|
| **Informatiebeveiliging** | Verificatie, codering en gegevensopslag op bedrijfsniveau |
| **Gegevenslekken/transparantie** | Diep en actief inzicht in activiteiten ter plaatse die gegevenslekkage vormen of tot gegevenslekkage bijdragen |
| **Verbeteringen in proces/beleid** | Clients, door samen te werken met de best practices uit de branche voor privacy en gegevensbeveiliging |

## Systemen, training en toegang {#systems-training-access}

Processen die helpen ons systeem en uw gegevens veilig te houden.

**Validatie voor externe beveiliging:**  Audience Manager test de beveiliging op jaarbasis en driemaandelijks.

* Jaarlijks: Eenmaal per jaar voert Audience Manager een volledige penetratietest uit die door een onafhankelijke derde onderneming wordt uitgevoerd. De test is ontworpen om beveiligingskwetsbaarheden in de toepassing te identificeren. De tests omvatten het aftasten voor dwars-plaats scripting, SQL injecties, de manipulatie van de vormparameter, en andere application-level kwetsbaarheid.
* Driemaandelijks: Eenmaal per kwartaal controleren interne teams op beveiligingskwetsbaarheden. Deze tests omvatten netwerkscans voor open havens en de dienstkwetsbaarheid.

**Systeembeveiliging:**  Audience Manager voor het veilig en privé houden van gegevens:

* Blokkeert verzoeken van onbevoegde IP adressen.
* Beschermt gegevens achter firewalls, VPNs, en met Virtuele Privé opslag van de Wolk.
* De veranderingen van sporen in de klant en controle-informatie gegevensbestanden met op trekker-gebaseerd controleregistreren. Deze logboeken volgen alle veranderingen op het gegevensbestandniveau, met inbegrip van gebruiker - identiteitskaart en IP adres waarvan veranderingen worden aangebracht.

**Beveiligingselementen:**  Audience Manager heeft een specifiek team van netwerkverrichtingen dat firewalls en indringingsapparaten controleert. Alleen sleutelpersoneel heeft toegang tot onze beveiligingstechnologie en -gegevens.

**Beveiligingstraining:**  Intern geldt onze inzet voor veiligheid ook voor ontwikkelaars die aan ons product werken. Adobe biedt ontwikkelaars formele training voor het maken van veilige toepassingen en services.

**Beveiligde toegang:**  De Audience Manager vereist sterke wachtwoorden om aan het systeem het programma te openen. Zie [wachtwoordvereisten](../../reference/password-requirements.md).

## Privacy en persoonlijk identificeerbare informatie (PII) {#pii}

Processen die persoonlijke informatie helpen veilig te houden. Zie het [Adobe Privacy Center](https://www.adobe.com/privacy/advertising-services.html)voor meer privacyinformatie.

**PII-gegevens:**  Audience Manager verbiedt klanten en gegevenspartners contractueel PII-informatie naar ons systeem te verzenden. Bovendien bevat of gebruikt de unieke gebruikersnaam (UUID) geen PII-gegevens als onderdeel van het algoritme voor het genereren van id&#39;s.

**IP-adressen:**  Audience Manager verzamelt wel IP-adressen. IP de adressen worden gebruikt in gegevens-verwerking en logboek-samenvoeging processen. Ze zijn ook vereist voor geografische en locatieopzoekingen en doelwitten. Bovendien, worden alle IP adressen binnen behouden logboekdossiers verduisterd binnen 90 dagen.

## Gegevens partitioneren {#data-partitioning}

Processen die gegevens van individuele cliënten helpen beschermen.

**Verdeling van gegevens over overtrekken:**  Uw gegevens ([!UICONTROL traits], id&#39;s, enz.) wordt gepartitioneerd door de client. Dit helpt blootstelling aan onbedoelde informatie tussen verschillende clients te voorkomen. De gegevens van de eigenschap in cookies worden bijvoorbeeld door de klant verdeeld en in een client-specifiek subdomein opgeslagen. Het kan niet per ongeluk door een andere cliënt van de Audience Manager worden gelezen of worden gebruikt. Bovendien worden de in het [!UICONTROL Profile Cache Servers (PCS)] bedrijf opgeslagen gegevens ook door de klant gepartitioneerd. Zo voorkomt u dat andere clients uw gegevens per ongeluk gebruiken in een gebeurtenisaanroep of andere aanvraag.

**Gegevenspartitionering in rapporten:**  Clientid&#39;s maken deel uit van de identificatietoets in alle rapporttabellen en rapportquery&#39;s worden gefilterd op id. Zo voorkomt u dat uw gegevens worden weergegeven in de rapporten van een andere klant van de Audience Manager.

## Binnenkomende Server-aan-Server (S2S) Overdrachten {#inbound-s2s}

Adobe Audience Manager ondersteunt twee hoofdmethoden voor het overdragen van S2S-gegevensbestanden aan boord naar onze systemen:

Beide methodes worden ontworpen met de veiligheid van onze klant en partnergegevens in mening terwijl de gegevens tussen hun systemen en ons systeem in vlucht zijn.

**SFTP:** Voor de optie SFTP kiezen de meeste klanten ervoor bestanden te leveren via het SFTP-protocol (Secure FTP), dat het SSH-protocol (Secure Shell) gebruikt. Deze methode zorgt ervoor dat bestanden tijdens de vlucht worden versleuteld tussen de systemen van de klant en het systeem van Adobe. Voor elke klant, creëren wij een gevangen drop-box plaats op onze servers SFTP, die aan een gebruikersrekening op dat systeem wordt gebonden. Alleen de gearchiveerde en geprivilegieerde gebruikers van het interne systeem hebben toegang tot deze locatie in de gevangenis. Deze gevangenis is nooit toegankelijk voor andere klanten.

**[!UICONTROL Amazon Web Services S3]via HTTPS:**Voor de S3 leveringsoptie, adviseren wij dat alle klanten hun S3 cliënten vormen om de encryptiemethode HTTPS voor dossieroverdrachten te gebruiken (dit is niet het gebrek, zodat moet het uitdrukkelijk worden gevormd). De optie HTTPS wordt zowel ondersteund door het s3cmd-opdrachtregelprogramma als door de S3-bibliotheken die beschikbaar zijn in elke belangrijke programmeertaal. Als deze optie HTTPS is ingeschakeld, worden de gegevens van de klant gecodeerd tijdens de vlucht naar onze systemen. Voor elke klant, creëren wij een afzonderlijke subdirectory S3 emmertje die slechts door de geloofsbrieven van die klant en die van onze interne systeemgebruikers kan worden betreden.

Als u PGP-versleuteling wilt toevoegen aan uw gegevensbestanden, raadpleegt u PGP-codering van [bestand voor binnenkomende gegevenstypen](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-encryption.md).

## Gegevens beveiligen met Escaping {#escaping-data}

De uitgaande gegevens worden [!DNL Audience Manager] niet beschermd tegen mogelijke XSS (cross-site scripting), enz. Het is de verantwoordelijkheid van de klant om inkomende gegevens te verwijderen.

## HTTP Strikt vervoer-Veiligheid {#hsts}

[!DNL HTTP Strict-Transport-Security (HSTS)] is een beveiligingsmechanisme voor het hele bedrijfsleven dat bescherming biedt tegen het kapen van cookies en aanvallen die het protocol verlagen.

Het beleid draagt Webbrowser op dat zodra een veilige [!DNL HTTPS] vraag aan een bepaald domein werd gemaakt, geen verdere onveilige vraag ([!DNL HTTP]) aan dat domein zou moeten worden toegestaan. Dit beschermt tegen man-in-de-middenaanvallen, waar een aanvaller zou kunnen proberen om [!DNL HTTPS] vraag aan onbeveiligde [!DNL HTTP] vraag te degraderen.&quot;

Dit beleid verbetert de gegevensbeveiliging tussen clients en Adobe [Edge](../../reference/system-components/components-edge.md) -servers.

### Voorbeeld {#hsts-example}

Laten we zeggen dat het `yourcompany.demdex.com` domein verkeer naar [!DNL DCS] via verzendt [!DNL HTTP]. [!DNL HSTS] upgrades de vraag aan gebruik [!DNL HTTPS] in plaats daarvan, en alle verdere [!DNL DCS] vraag die uit `yourcompany.demdex.com` komt zal [!DNL HTTPS] in plaats van [!DNL HTTP]gebruiken.

Zie [HTTP Strikte Transport Security - Wikipedia](https://en.wikipedia.org/wiki/HTTP_Strict_Transport_Security) voor meer informatie over HSTS.
