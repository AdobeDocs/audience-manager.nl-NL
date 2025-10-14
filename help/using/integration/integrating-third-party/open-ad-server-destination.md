---
description: Stel Open Ad Server in als een doel en verstuur Audience Manager-gegevens naar dat platform.
seo-description: Set up Open Ad Server as a destination and send Audience Manager data to that platform.
seo-title: OAS as an Audience Manager Destination
solution: Audience Manager
title: OAS als Audience Manager-bestemming
uuid: 5891a063-5a4b-4ea7-865f-b24e17ca735f
feature: Third-party Integration
exl-id: cf919c27-691f-424b-be83-040f03e34455
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '640'
ht-degree: 0%

---

# OAS als Audience Manager-bestemming {#oas-as-an-audience-manager-destination}

Stel [!DNL Open Ad Server] in als een doel en verzend Audience Manager-gegevens naar dat platform.

## OAS-bestemmingsvereisten {#oas-requirements}

Standaarden voor plaatsing van code, ondersteunde indelingen voor sleutelwaarden, rapporten en het type segmentgegevens dat naar [!DNL OAS] wordt verzonden.

<!-- aam-oas-requirements.xml -->

Voor dit doeltype is het volgende vereist:

* **[!UICONTROL DIL]:** [!UICONTROL Data Integration Library] code zou op uw inventaris moeten worden opgesteld. Met [!UICONTROL DIL] voorkomt u de noodzaak om speciale code te schrijven voor gegevensverzameling, integratie, het lezen van cookiewaarden en het herstellen van paginagegevens.
* **`get_aamCookie`Functie:** Code waarmee de Audience Manager-gebruikers-id en -cookie worden vastgelegd. Plaats [&#x200B; deze code &#x200B;](../../features/destinations/get-aam-cookie-code.md) op de bovenkant van de pagina of binnen de `<head>` codeblok.
* **verzend Logboeken van de Levering naar Audience Manager:** als u een (facultatief) rapport van de segmentlevering wilt, Audience Manager van een dagelijks logboek voorzien dat indruk-vlakke leveringsgegevens bevat. De gegevens kunnen in onbewerkte indeling worden opgeslagen, maar elke record moet de Audience Manager [!UICONTROL UUID] bevatten. Audience Manager kan deze ophalen of ontvangen via [!DNL FTP] .

### Cookie-indeling en sleutelwaardengegevens

Audience Manager kan segmentgegevens als volgt naar een browsercookie verzenden:

* Enkele toetsen (`x=1&x=2`);
* Meerdere toetsen (`x=1&x=2&y=3&y=4`);
* Geserialiseerde waarden (`x=1,2,3`);
* Een scheidingsteken voor standaardwaarden dat wordt gebruikt voor het scheiden van afzonderlijke sleutel-waardeparen.

### Alleen gekwalificeerde segmenten worden naar OAS verzonden

De hoeveelheid gegevens die aan [!DNL OAS] wordt doorgegeven, is afhankelijk van het aantal segmenten waarvoor een bepaalde gebruiker in aanmerking komt. Stel dat u 100 Audience Manager-segmenten instelt. Als een bezoeker van de site voor vijf van hen in aanmerking komt, worden alleen die vijf segmenten naar OAS verzonden (niet alle 100).

>[!MORELIKETHIS]
>
>* [get_aamCookie-code](../../features/destinations/get-aam-cookie-code.md)
>* [Sleutelwaardeparen](../../reference/key-value-pairs-explained.md)

## Een OAS-doel maken {#oas-dest-setup}

Maak een op cookies gebaseerd doel voor [!DNL OAS] in Audience Manager.

<!-- aam-oas-destination-setup.xml -->

In Audience Manager, is a *bestemming* een ander systeem (ad server, [!DNL DSP], en netwerk, enz.) dat u gegevens met wilt delen. [!UICONTROL Destination Builder] biedt de gereedschappen waarmee u deze processen voor gegevenslevering kunt maken en beheren. De bestemmingseigenschappen van Audience Manager worden gevestigd in *Gegevens van het publiek > Doelen*. Klik op **[!UICONTROL Add New Destination]** en volg de onderstaande stappen om aan de slag te gaan.

### Stap 1: Basisinformatie

De sectie [!UICONTROL Basic Information] voltooien:

1. Geef het doel een naam.
1. Selecteer **[!UICONTROL "Cookie"]** in de vervolgkeuzelijst [!UICONTROL Type] .
1. Klik op **[!UICONTROL Save]** en ga naar de secties [!UICONTROL Configuration] en [!UICONTROL Segment Mappings] .

### Stap 2: Configuratiegegevens

De sectie [!UICONTROL Configuration] voltooien:

1. **Naam van het Koekje:** verstrek een korte, beschrijvende naam voor uw koekje.
1. **Domein van het Koekje:** verlaten leeg om een koekje in het domein van de huidige pagina van de gebruiker te plaatsen. Als u een domein wilt specificeren, prefix de naam met een periode zoals dit, `.mydomain.com`.
1. Kies een hoofdoptie in de sectie [!UICONTROL Data Format] .
1. Als uw sleutels gegevens met geserialiseerde waarden gebruiken, selecteer **[!UICONTROL Serialize]** controle en specificeer het periodieke afbakening (het karakter dat de geserialiseerde waarden scheidt).
1. Klik op **[!UICONTROL Save]** en vouw de sectie [!UICONTROL Segment Mappings] uit.

### Stap 3: Segmenttoewijzingen

Een segment toevoegen aan een cookiebestemming:

1. **vind segmenten:** de [!UICONTROL Segment Mappings] sectie verstrekt twee onderzoekshulpmiddelen helpen van segmenten de plaats bepalen. Een segment zoeken:
   * Optie 1: typ een segmentnaam in het zoekveld. Het veld wordt automatisch bijgewerkt op basis van de tekst. Klik op **[!UICONTROL Add]** als u het gewenste segment hebt gevonden.
   * Optie 2: klik op **[!UICONTROL Browse All Segments]** om een venster te openen waarin u naar segmenten kunt bladeren op naam of opslaglocatie. Klik op **[!UICONTROL Add Selected Segments]** als u klaar bent.
1. **voegt Toewijzingen toe:** in de afbeeldingen pop, ga segmentidentiteitskaart op het kaartingsgebied in en klik **[!UICONTROL Save]**.
1. Klik op **[!UICONTROL Done]**.

## OAS Setup {#oas-code-setup}

Wijzig [!DNL OAS] instellingen om met Audience Manager-segmentgegevens te werken.

<!-- aam-oas-code.xml -->

Instellen [!DNL OAS]

* Installeer [!UICONTROL DIL] -code op uw site.
* OAS maken als een cookiebestemming in Audience Manager.
* Plaats de functie `get_aamCookie` boven aan de pagina, in het ideale geval in de `<head>` -codeblok. De `get_aamCookie` code is beschikbaar [&#x200B; hier &#x200B;](../../features/destinations/get-aam-cookie-code.md).
* Wijzig de advertentietag om de functie `get_aamCookie` aan te roepen en neem de cookienaam op die u hebt opgegeven bij het instellen van de bestemming [!DNL OAS] . Als u bijvoorbeeld de cookie `test_cookie` een naam hebt gegeven, moet de tag ad `get_aamCookie` aanroepen en naar de naam van de cookie verwijzen.
* De advertentietag kan er ongeveer zo uitzien als hieronder.

  ```js
  <a href= "https://client.adserver.net/?" + get_aamCookie('test_cookie') +
   "&etc&u=" + get_aamCookie('aam_uuid')
  ```

Vergeet niet de variabele `u=` op te nemen. Het houdt werkelijk unieke gebruiker - identiteitskaart ([!UICONTROL UUID]) binnen overgegaan tijdens een ad vraag.
