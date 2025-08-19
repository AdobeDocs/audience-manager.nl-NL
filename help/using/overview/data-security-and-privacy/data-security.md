---
description: Audience Manager neemt databeveiliging en privacy zeer serieus. We doen ons best om onze systemen te beveiligen en uw waardevolle data te beschermen.
seo-description: Audience Manager takes data security and privacy very seriously. We work to keep our systems secure and protect your valuable data.
seo-title: Data Security in Audience Manager
solution: Audience Manager
title: Databeveiliging in Audience Manager
uuid: 33ad19ca-4690-4d97-853b-1882d7d4ac01
feature: Data Governance & Privacy
exl-id: 94b70250-dca3-4c50-b4dd-bc37178a587e
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '988'
ht-degree: 92%

---

# Databeveiliging in Audience Manager {#data-security}

Audience Manager neemt databeveiliging en privacy zeer serieus. We doen ons best om onze systemen te beveiligen en uw waardevolle data te beschermen.

Audience Manager-beveiligingspraktijken omvatten externe en interne audits, activiteitenlogboekregistratie, training en andere procedures die zijn ontworpen om onze systemen en uw waardevolle data te helpen beschermen. Wij geloven dat een veilig product helpt bij het opbouwen en onderhouden van het vertrouwen dat klanten in ons hebben.

In Audience Manager zien we beveiliging in drie hoofdcategorieën:

| Beveiligingstype | Biedt ondersteuning voor |
|---|---|
| **Informatiebeveiliging** | Verificatie, versleuteling en dataopslag op bedrijfsniveau |
| **Datalekken/transparantie** | Diep en actiegericht inzicht in onsite activiteiten die bestaan in, of bijdragen aan datalekkage |
| **Verbeteringen in proces/beleid** | Clients, door samen te werken met de best practices uit de branche voor privacy en databeveiliging |

## Systemen, training en toegang {#systems-training-access}

Processen die helpen ons systeem en uw data te beveiligen.

**Validatie voor externe beveiliging:**  Audience Manager test de beveiliging elk jaar en elk kwartaal.

* Elk jaar: Eenmaal per jaar ondergaat Audience Manager een volledige penetratietest die wordt uitgevoerd door een onafhankelijk, extern bedrijf. De test is ontworpen om zwakke punten in de beveiliging van de applicatie te identificeren. De tests omvatten het scannen op cross-site scripting, SQL-injecties, manipulatie van formulierparameters, en andere kwetsbaarheden op applicatieniveau.
* Elk kwartaal: Eenmaal per kwartaal controleren interne teams op zwakke punten in de beveiliging. Deze tests omvatten netwerkscans voor open poorten en servicekwetsbaarheden.

**Systeembeveiliging:**  Om data veilig en privé te houden doet Audience Manager het volgende:

* Blokkeert aanvragen van onbevoegde IP-adressen.
* Beschermt data achter firewalls en VPN’s, en met Virtual Private Cloud-opslag.
* Houdt wijzigingen bij in de databases van klant- en beheerinformatie met op triggers gebaseerde auditlogboekregistratie. Deze logboeken volgen alle wijzigingen op databaseniveau, inclusief de gebruikers-id en het IP-adres vanwaar de wijzigingen worden aangebracht.

**Beveiligingsasets:**  Audience Manager heeft een speciaal netwerkteam dat firewalls en apparaten voor indringerdetectie controleert. Alleen het belangrijkste personeel heeft toegang tot onze beveiligingstechnologie en -data.

**Beveiligingstraining:**  Intern geldt ons streven naar veiligheid ook voor ontwikkelaars die aan ons product werken. Adobe biedt ontwikkelaars een formele training voor het maken van veilige toepassingen en services.

**Beveiligde toegang:**  Audience Manager vereist sterke wachtwoorden voor aanmelding bij het systeem. Zie [wachtwoordvereisten](../../reference/password-requirements.md).

## Privacy en persoonlijk identificeerbare informatie (PII) {#pii}

Processen die persoonlijke informatie beveiligen. Zie het [Adobe Privacy Center](https://www.adobe.com/nl/privacy/advertising-services.html) voor meer privacyinformatie.

**PII-data:**  Audience Manager verbiedt klanten en datapartners contractueel om PII-informatie naar ons systeem te verzenden. Bovendien bevat of gebruikt de Unique User ID (UUID) geen PII-data als onderdeel van de algoritme voor het genereren van id’s.

**IP-adressen:**  Audience Manager verzamelt IP-adressen. IP-adressen worden gebruikt bij processen voor dataverwerking en logboeksamenvoeging. Ze zijn ook vereist voor opzoeken en targeting van geografische gebieden en locaties. Bovendien worden alle IP-adressen in bewaarde logboekbestanden binnen 90 dagen onzichtbaar gemaakt.

## Gegevens partitioneren {#data-partitioning}

Processen die data van individuele klanten helpen beschermen.

**het Verdelen van Gegevens van het Staal:** Uw gegevens ([!UICONTROL traits], IDs, enz.) wordt verdeeld door cliënt. Dit voorkomt onbedoelde openbaarmaking van informatie tussen verschillende clients. De data van eigenschappen in cookies worden bijvoorbeeld gepartitioneerd per klant en opgeslagen in een clientspecifiek subdomein. De data kunnen niet per ongeluk door een andere Audience Manager-client worden gelezen of gebruikt. Bovendien worden de eigenschapdata die op de [!UICONTROL Profile Cache Servers (PCS)] worden opgeslagen, eveneens per klant gepartitioneerd. Dit voorkomt dat andere clients uw data per ongeluk gebruiken in een gebeurteniscall of een andere aanvraag.

**Datapartitionering in rapporten:**  Client-id’s maken deel uit van de identificatiesleutel in alle rapportagetabellen en rapportquery’s worden gefilterd op id. Dit voorkomt dat uw data worden weergegeven in de rapporten van een andere klant van Audience Manager.

## Binnenkomende Server-aan-Server (S2S) Overdrachten {#inbound-s2s}

Adobe Audience Manager ondersteunt twee hoofdmethoden voor het overdragen van onboarded S2S-databestanden naar onze systemen:

Beide methodes zijn ontworpen met het oog op de veiligheid van onze klant- en partnerdata terwijl de data zich bewegen tussen hun systemen en ons systeem.

**SFTP:** Voor de optie SFTP kiezen de meeste klanten ervoor bestanden te leveren via het SFTP-protocol (Secure FTP), dat het SSH-protocol (Secure Shell) gebruikt. Deze methode zorgt ervoor dat bestanden versleuteld zijn terwijl ze onderweg zijn tussen de systemen van de klant en het systeem van Adobe. Voor elke klant maken we een jailed drop-boxlocatie op onze SFTP-servers, die is gekoppeld aan een gebruikersaccount op dat systeem. Alleen de interne systeemgebruikers met referenties en toestemmingen van de klant hebben toegang tot deze jailed drop-boxlocatie. Deze jail is nooit toegankelijk voor andere klanten.

**[!UICONTROL Amazon Web Services S3]via HTTPS:** Voor de S3 leveringsoptie, adviseren wij dat alle klanten hun S3 cliënten vormen om de encryptiemethode HTTPS voor dossieroverdrachten te gebruiken (dit is niet het gebrek, zodat moet het uitdrukkelijk worden gevormd). De HTTPS-optie wordt ondersteund door zowel het s3cmd-opdrachtregelprogramma als door de S3-bibliotheken die beschikbaar zijn in elke belangrijke programmeertaal. Als deze HTTPS-optie is ingeschakeld, worden de data van de klant versleuteld terwijl ze onderweg zijn tussen onze systemen. Voor elke klant maken we een afzonderlijke S3-bucket-submap die alleen toegankelijk is met de referenties van deze klant en die van onze interne systeemgebruikers.

Als u PGP-versleuteling wilt toevoegen aan uw databestanden, raadpleegt u [PGP-bestandsversleuteling voor binnenkomende datatypen](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-encryption.md).

## Gegevens beveiligen met Escaping {#escaping-data}

Merk op dat [!DNL Audience Manager] geen escape uitvoert op uitgaande data om deze te beveiligen tegen mogelijke cross-site scripting (XSS), enz. Het is de verantwoordelijkheid van de klant om een escape uit te voeren op binnenkomende data.

## HTTP Strikt vervoer-Veiligheid {#hsts}

[!DNL HTTP Strict-Transport-Security (HSTS)] is een branchebreed beveiligingsmechanisme dat bescherming biedt tegen het kapen van cookies en aanvallen die het protocol downgraden.

Het beleid instrueert de webbrowser dat zodra er een veilige [!DNL HTTPS]-call is uitgevoerd naar een bepaald domein, er geen verdere onveilige calls ([!DNL HTTP]) aan dat domein moeten worden toegestaan. Dit beschermt tegen man-in-the-middle-aanvallen, waar een aanvaller kan proberen om [!DNL HTTPS]-calls te downgraden naar onbeveiligde [!DNL HTTP]-calls.”

Dit beleid verbetert de databeveiliging tussen clients en Adobe [Edge](../../reference/system-components/components-edge.md)-servers.

### Voorbeeld {#hsts-example}

Laten we zeggen dat het `yourcompany.demdex.com` -domein verkeer verstuurt naar de [!DNL DCS] via [!DNL HTTP] . [!DNL HSTS] werkt de calls bij om in plaats daarvan [!DNL HTTPS] te gebruiken, en alle volgende [!DNL DCS] calls van `yourcompany.demdex.com` zullen [!DNL HTTPS] gebruiken in plaats van [!DNL HTTP].

Zie [HTTP Strict Transport Security - Wikipedia](https://nl.wikipedia.org/wiki/HTTP_Strict_Transport_Security) voor meer informatie over HSTS.
