---
description: Stel Open Ad Server in als een doel en verstuur de gegevens van de Audience Manager naar dat platform.
seo-description: Stel Open Ad Server in als een doel en verstuur de gegevens van de Audience Manager naar dat platform.
seo-title: OAS als Audience Manager-bestemming
solution: Audience Manager
title: OAS als Audience Manager-bestemming
uuid: 5891a063-5a4b-4ea7-865f-b24e17ca735f
feature: Third Party Integrations
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '656'
ht-degree: 4%

---


# OAS als Audience Manager-bestemming {#oas-as-an-audience-manager-destination}

Stel [!DNL Open Ad Server] in als een doel en verstuur de gegevens van de Audience Manager naar dat platform.

## OAS-bestemmingsvereisten {#oas-requirements}

Standaarden voor plaatsing van code, ondersteunde sleutel-waardeformaten, rapporten, en het type segmentgegevens die naar [!DNL OAS] worden verzonden.

<!-- aam-oas-requirements.xml -->

Voor dit doeltype is het volgende vereist:

* **[!UICONTROL DIL]:** [!UICONTROL Data Integration Library] code moet in uw voorraad worden geïmplementeerd. [!UICONTROL DIL] helpt u te voorkomen dat u speciale code hoeft te schrijven voor gegevensverzameling, integratie, het lezen van cookiewaarden en het herstellen van paginagegevens.
* **`get_aamCookie`Functie:** Code waarmee de gebruikers-id en cookie-gegevens van de Audience Manager worden vastgelegd. Plaats [deze code](../../features/destinations/get-aam-cookie-code.md) boven aan de pagina of in het `<head>` codeblok.
* **Verzend de Logboeken van de Levering aan Audience Manager:** Als u een (facultatief) segmentleveringsrapport wilt, verstrek Audience Manager van een dagelijks logboek dat indruk-vlakke leveringsgegevens bevat. De gegevens kunnen een RAW-indeling hebben, maar elke record moet de Audience Manager [!UICONTROL UUID] bevatten. Audience Managers kunnen deze ophalen of ontvangen via [!DNL FTP].

### Cookie-indeling en sleutelwaardengegevens

Audience Manager kan segmentgegevens als volgt naar een browsercookie verzenden:

* enkele toetsen (`x=1&x=2`);
* Meerdere toetsen (`x=1&x=2&y=3&y=4`);
* Geserialiseerde waarden (`x=1,2,3`);
* Een scheidingsteken voor standaardwaarden dat wordt gebruikt voor het scheiden van afzonderlijke sleutel-waardeparen.

### Alleen gekwalificeerde segmenten worden naar OAS verzonden

De hoeveelheid gegevens die aan [!DNL OAS] worden doorgegeven, is afhankelijk van het aantal segmenten waarvoor een bepaalde gebruiker in aanmerking komt. Stel bijvoorbeeld dat u 100 Audience Manager-segmenten instelt. Als een bezoeker van de site voor vijf van hen in aanmerking komt, worden alleen die vijf segmenten naar OAS verzonden (niet alle 100).

>[!MORELIKETHIS]
>
>* [get_aamCookie-code](../../features/destinations/get-aam-cookie-code.md)
>* [Sleutelwaardeparen](../../reference/key-value-pairs-explained.md)


## Een OAS-doel maken {#oas-dest-setup}

Maak een op cookies gebaseerd doel voor [!DNL OAS] in Audience Manager.

<!-- aam-oas-destination-setup.xml -->

In Audience Manager is een *doel* elk ander systeem (ad server, [!DNL DSP], netwerk, enz.) waarmee u data wilt delen. [!UICONTROL Destination Builder] biedt de gereedschappen waarmee u deze processen voor gegevenslevering kunt maken en beheren. De bestemmingseigenschappen van de Audience Manager worden gevestigd in *Gegevens van het publiek > Doelen*. Klik **[!UICONTROL Add New Destination]** en volg de onderstaande stappen om aan de slag te gaan.

### Stap 1: Basisinformatie

De sectie [!UICONTROL Basic Information] voltooien:

1. Geef het doel een naam.
1. Selecteer **[!UICONTROL "Cookie"]** in de vervolgkeuzelijst [!UICONTROL Type].
1. Klik op **[!UICONTROL Save]** en ga naar de secties [!UICONTROL Configuration] en [!UICONTROL Segment Mappings].

### Stap 2: Configuratiegegevens

De sectie [!UICONTROL Configuration] voltooien:

1. **Naam cookie:** Geef een korte, beschrijvende naam op voor uw cookie.
1. **Cookie-domein:leeg** laten om een cookie in te stellen in het domein van de huidige pagina van de gebruiker. Als u een domein wilt specificeren, prefix de naam met een periode zoals dit, `.mydomain.com`.
1. Kies een zeer belangrijke optie in [!UICONTROL Data Format] sectie.
1. Als uw sleutels gegevens met geserialiseerde waarden gebruiken, selecteer **[!UICONTROL Serialize]** controle en specificeer het periodieke afbakening (het karakter dat de geserialiseerde waarden scheidt).
1. Klik **[!UICONTROL Save]** en breid [!UICONTROL Segment Mappings] sectie uit.

### Stap 3: Segmenttoewijzingen

Een segment toevoegen aan een cookiebestemming:

1. **Segmenten zoeken:** de  [!UICONTROL Segment Mappings] sectie bevat twee zoekgereedschappen waarmee u segmenten kunt zoeken. Een segment zoeken:
   * Optie 1: Typ een segmentnaam in het zoekveld. Het veld wordt automatisch bijgewerkt op basis van de tekst. Klik **[!UICONTROL Add]** zodra u het segment vindt u wilt gebruiken.
   * Optie 2: Klik **[!UICONTROL Browse All Segments]** om een venster te openen dat u voor segmenten door naam of opslagplaats laat doorbladeren. Klik **[!UICONTROL Add Selected Segments]** wanneer gereed.
1. **Toewijzingen toevoegen:** Voer in het pop-upmenu Toewijzingen de segment-id in het toewijzingsveld in en klik op  **[!UICONTROL Save]**.
1. Klik op **[!UICONTROL Done]**.

## OAS-instelling {#oas-code-setup}

Wijzig [!DNL OAS] montages om met Audience Manager segmentgegevens te werken.

<!-- aam-oas-code.xml -->

[!DNL OAS] instellen

* Installeer [!UICONTROL DIL] code over uw plaats.
* OAS maken als een cookiebestemming in Audience Manager.
* Plaats de functie `get_aamCookie` boven aan de pagina, idealiter binnen de codeblok `<head>`. De `get_aamCookie`-code is [hier](../../features/destinations/get-aam-cookie-code.md) beschikbaar.
* Wijzig uw advertentietag om de `get_aamCookie` functie te roepen en omvat de koekjesnaam u toen het plaatsen van [!DNL OAS] bestemming verstrekte. Als u bijvoorbeeld het cookie `test_cookie` een naam hebt gegeven, moet de tag ad `get_aamCookie` aanroepen en naar de naam van het cookie verwijzen.
* De advertentietag kan er ongeveer zo uitzien als hieronder.

   ```js
   <a href= "https://client.adserver.net/?" + get_aamCookie('test_cookie') +
    "&etc&u=" + get_aamCookie('aam_uuid')
   ```

Vergeet niet de variabele `u=` op te nemen. Het houdt werkelijk unieke gebruiker - identiteitskaart ([!UICONTROL UUID]) binnen die tijdens een ad vraag wordt overgegaan.
