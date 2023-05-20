---
description: Stel Open Ad Server in als een doel en verstuur de gegevens van de Audience Manager naar dat platform.
seo-description: Set up Open Ad Server as a destination and send Audience Manager data to that platform.
seo-title: OAS as an Audience Manager Destination
solution: Audience Manager
title: OAS als Audience Manager-bestemming
uuid: 5891a063-5a4b-4ea7-865f-b24e17ca735f
feature: Third-party Integration
exl-id: cf919c27-691f-424b-be83-040f03e34455
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '634'
ht-degree: 4%

---

# OAS als Audience Manager-bestemming {#oas-as-an-audience-manager-destination}

Instellen [!DNL Open Ad Server] als een bestemming en verzendt de gegevens van de Audience Manager naar dat platform.

## OAS-bestemmingsvereisten {#oas-requirements}

Normen voor codeplaatsing, gesteunde zeer belangrijk-waardeformaten, rapporten, en het type segmentgegevens die naar worden verzonden [!DNL OAS].

<!-- aam-oas-requirements.xml -->

Voor dit doeltype is het volgende vereist:

* **[!UICONTROL DIL]:** [!UICONTROL Data Integration Library] code moet in uw voorraad worden geïmplementeerd. [!UICONTROL DIL] helpt u te voorkomen dat u speciale code hoeft te schrijven voor gegevensverzameling, integratie, het lezen van cookiewaarden en het herstellen van paginagegevens.
* **`get_aamCookie`Functie:** Code waarmee de gebruikers-id en cookie-gegevens van de Audience Manager worden vastgelegd. Plaatsen [deze code](../../features/destinations/get-aam-cookie-code.md) boven aan of binnen de pagina `<head>` codeblok.
* **Leveringslogboeken naar Audience Manager verzenden:** Als u (facultatief) een rapport van de segmentlevering wilt, verstrek Audience Manager van een dagelijks logboek dat indruk-vlakke leveringsgegevens bevat. De gegevens kunnen een Raw-indeling hebben, maar elke record moet de Audience Manager bevatten [!UICONTROL UUID]. Audience Managers kunnen deze ophalen of ontvangen via [!DNL FTP].

### Cookie-indeling en sleutelwaardengegevens

Audience Manager kan segmentgegevens als volgt naar een browsercookie verzenden:

* Enkele toetsen (`x=1&x=2`);
* Meerdere toetsen (`x=1&x=2&y=3&y=4`);
* Geserichte waarden (`x=1,2,3`);
* Een scheidingsteken voor standaardwaarden dat wordt gebruikt voor het scheiden van afzonderlijke sleutel-waardeparen.

### Alleen gekwalificeerde segmenten worden naar OAS verzonden

De hoeveelheid gegevens die wordt doorgegeven aan [!DNL OAS] is afhankelijk van het aantal segmenten waarvoor een bepaalde gebruiker in aanmerking komt. Stel bijvoorbeeld dat u 100 Audience Manager-segmenten instelt. Als een bezoeker van de site voor vijf van hen in aanmerking komt, worden alleen die vijf segmenten naar OAS verzonden (niet alle 100).

>[!MORELIKETHIS]
>
>* [get_aamCookie-code](../../features/destinations/get-aam-cookie-code.md)
>* [Sleutelwaardeparen](../../reference/key-value-pairs-explained.md)


## Een OAS-doel maken {#oas-dest-setup}

Een op cookies gebaseerd doel maken voor [!DNL OAS] in de Audience Manager.

<!-- aam-oas-destination-setup.xml -->

In de Audience Manager *doel* is een ander systeem (advertentieserver), [!DNL DSP], en netwerk, enz.) waarmee u data wilt delen. [!UICONTROL Destination Builder] biedt de gereedschappen waarmee u deze processen voor gegevenslevering kunt maken en beheren. De bestemmingseigenschappen van de Audience Manager worden gevestigd in *Poortgegevens > Doelen*. Klik op **[!UICONTROL Add New Destination]** en volgt u de onderstaande stappen.

### Stap 1: Basisinformatie

Als u het dialoogvenster [!UICONTROL Basic Information] sectie:

1. Geef het doel een naam.
1. Selecteren **[!UICONTROL "Cookie"]** van de [!UICONTROL Type] vervolgkeuzelijst.
1. Klikken **[!UICONTROL Save]** en gaat u verder naar de [!UICONTROL Configuration] en [!UICONTROL Segment Mappings] secties.

### Stap 2: Configuratiegegevens

Als u het dialoogvenster [!UICONTROL Configuration] sectie:

1. **Naam cookie:** Geef een korte, beschrijvende naam op voor uw cookie.
1. **Cookie-domein:** Laat leeg om een cookie in te stellen in het domein van de huidige pagina van de gebruiker. Als u een domein wilt specificeren, prefix de naam met een periode als dit, `.mydomain.com`.
1. Kies een sleuteloptie in het dialoogvenster [!UICONTROL Data Format] sectie.
1. Als uw sleutels gegevens met geserialiseerde waarden gebruiken, selecteer **[!UICONTROL Serialize]** besturen en specificeren het periodieke scheidingsteken (het karakter dat de geserialiseerde waarden scheidt).
1. Klikken **[!UICONTROL Save]** en breid de [!UICONTROL Segment Mappings] sectie.

### Stap 3: Segmenttoewijzingen

Een segment toevoegen aan een cookiebestemming:

1. **Segmenten zoeken:** De [!UICONTROL Segment Mappings] de sectie verstrekt twee onderzoekshulpmiddelen helpen van segmenten de plaats bepalen. Een segment zoeken:
   * Optie 1: Typ een segmentnaam in het zoekveld. Het veld wordt automatisch bijgewerkt op basis van de tekst. Klikken **[!UICONTROL Add]** wanneer u het segment vindt u wilt gebruiken.
   * Optie 2: Klikken **[!UICONTROL Browse All Segments]** om een venster te openen dat u naar segmenten op naam of opslagplaats laat doorbladeren. Klikken **[!UICONTROL Add Selected Segments]** wanneer gereed.
1. **Toewijzingen toevoegen:** Voer in het pop-upmenu Toewijzingen de segment-id in het toewijzingsveld in en klik op **[!UICONTROL Save]**.
1. Klik op **[!UICONTROL Done]**.

## OAS Setup {#oas-code-setup}

Wijzigen [!DNL OAS] instellingen voor het werken met Audience Manager-segmentgegevens.

<!-- aam-oas-code.xml -->

Aan opstelling [!DNL OAS]

* Installeren [!UICONTROL DIL] code op uw site.
* OAS maken als een cookiebestemming in Audience Manager.
* Plaats de `get_aamCookie` functie boven aan de pagina, ideaal binnen de `<head>` codeblok. De `get_aamCookie` code is beschikbaar [hier](../../features/destinations/get-aam-cookie-code.md).
* Wijzig uw advertentietag om te roepen `get_aamCookie` en neemt u de cookienaam op die u hebt opgegeven bij het instellen van de [!DNL OAS] bestemming. Als u bijvoorbeeld de cookie een naam hebt gegeven `test_cookie`, moet de tag ad `get_aamCookie` en verwijs naar de naam van het cookie.
* De advertentietag kan er ongeveer zo uitzien als hieronder.

   ```js
   <a href= "https://client.adserver.net/?" + get_aamCookie('test_cookie') +
    "&etc&u=" + get_aamCookie('aam_uuid')
   ```

Vergeet niet de `u=` variabele. Het bevat de werkelijke unieke gebruikersnaam ([!UICONTROL UUID]) die tijdens een advertentieaanroep is doorgegeven.
