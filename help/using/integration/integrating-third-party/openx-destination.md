---
description: Opstelling OpenX als bestemming en verzend de gegevens van het het segmentsegment van de Audience Manager naar dat platform.
seo-description: Opstelling OpenX als bestemming en verzend de gegevens van het het segmentsegment van de Audience Manager naar dat platform.
seo-title: OpenX als Audience Manager-bestemming
solution: Audience Manager
title: OpenX als Audience Manager-bestemming
uuid: 5e86ba73-281c-403b-af06-64a1d427526a
feature: Third Party Integrations
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '695'
ht-degree: 3%

---


# OpenX als Audience Manager-bestemming{#openx-as-an-audience-manager-destination}

Opstelling [!DNL OpenX] als bestemming en verzendt de gegevens van het het segmentsegment van de Audience Manager naar dat platform.

>[!NOTE]
>
>Alleen voor onsite en servergerichte toepassingen.

## Vereisten voor OpenX-bestemming {#openx-requirements}

Normen voor codeplaatsing, gesteunde zeer belangrijk-waardeformaten, rapporten, en het type van segmentgegevens die naar worden verzonden [!DNL OpenX].

<!-- aam-openx-requirements.xml -->

Controleer het volgende voordat u een Audience Manager als doel instelt: [!DNL OpenX]

* **[!UICONTROL DIL]:**[!UICONTROL Data Integration Library]code moet op uw site worden geïmplementeerd.[!UICONTROL DIL]helpt u te voorkomen dat u speciale code hoeft te schrijven voor gegevensverzameling, integratie, het lezen van cookiewaarden en het herstellen van paginagegevens.
* **`get_aamCookie`Functie:**Code waarmee de gebruikers-id en cookie-gegevens van de Audience Manager worden vastgelegd. Plaats[deze code](../../features/destinations/get-aam-cookie-code.md)boven aan de pagina of in de`<head>`codeblok.
* **Leveringslogboeken naar Audience Manager verzenden:** Als u (facultatief) een rapport van de segmentlevering wilt, verstrek Audience Manager van een dagelijks logboek dat indruk-vlakke leveringsgegevens bevat. De gegevens kunnen in een RAW-indeling zijn, maar elke record moet de Audience Manager bevatten `UUID`. Audience Managers kunnen deze ophalen of ontvangen via [!DNL FTP].

### Sleutelwaarde-gegevens: Formuliervereisten

Audience Manager verzendt gegevens in de vorm van sleutel-waardeparen. Maak sleutelwaardeparen volgens de volgende specificaties:

* Voorvertoningstoetsen met `c.` (bijv. `c.color` of `c.price`).
* Afzonderlijke geserialiseerde waarden die aan één toets zijn gekoppeld met een komma (bijvoorbeeld `c.color = red, green, blue`).
* Scheid meerdere sleutel-waardeparen met een en-teken (bijvoorbeeld, `c.color=red & c.price = 100 & c.condition = new`).
* Sleutelnamen mogen geen speciale tekens zoals accenten en leestekens of andere symbolen bevatten.

### Alleen gekwalificeerde segmenten worden verzonden naar OpenX

De hoeveelheid gegevens die wordt doorgegeven aan, is [!DNL OpenX] afhankelijk van het aantal segmenten waarvoor een bepaalde gebruiker in aanmerking komt. Stel bijvoorbeeld dat u 100 Audience Manager-segmenten instelt. Als een bezoeker van de site voor vijf van hen in aanmerking komt, worden alleen die vijf segmenten verzonden naar [!DNL OpenX] (niet alle 100).

## Een OpenX-doel maken {#openx-destination}

Maak een cookiebestemming voor [!DNL OpenX] in de Audience Manager.

<!-- aam-openx-destination.xml -->

In Audience Manager, a *destination* is any other system (ad server, [!DNL DSP], ad network, etc.) waarmee u data wilt delen. [!UICONTROL Destination Builder] biedt de gereedschappen waarmee u deze processen voor gegevenslevering kunt maken en beheren. De bestemmingseigenschappen van de Audience Manager worden gevestigd in de Gegevens van het *Publiek > Doelen*. Klik op de onderstaande stappen **[!UICONTROL Add New Destination]** en volg deze om aan de slag te gaan.

### Stap 1: Basisinformatie

De [!UICONTROL Basic Information] sectie voltooien:

1. Geef het doel een naam.
1. Selecteer een optie **[!UICONTROL "Cookie"]** in de [!UICONTROL Type] vervolgkeuzelijst.
1. Klik **[!UICONTROL Next]** en ga naar de [!UICONTROL Configuration] en [!UICONTROL Segment Mappings] secties.

### Stap 2: Configuratiegegevens

De [!UICONTROL Configuration] sectie voltooien:

1. **Naam cookie:** Geef een korte, beschrijvende naam op voor uw cookie.
1. **Cookie-domein:** Laat leeg om een cookie in te stellen in het domein van de huidige pagina van de gebruiker. Als u een domein wilt specificeren, prefix de naam met een periode zoals dit, `.mydomain.com`.
1. Kies een sleuteloptie in de [!UICONTROL Data Format] sectie.
1. Als uw sleutels gegevens met geserialiseerde waarden gebruiken, selecteer de **[!UICONTROL Serialize]** controle en specificeer het periodieke afbakening (het karakter dat de geserialiseerde waarden) scheidt.
1. Klik **[!UICONTROL Save]** en breid de [!UICONTROL Segment Mappings] sectie uit.

### Stap 3: Segmenttoewijzingen

Een segment toevoegen aan een cookiebestemming:

1. **Segmenten zoeken:** De [!UICONTROL Segment Mappings] sectie bevat twee zoekgereedschappen waarmee u segmenten kunt zoeken. Een segment zoeken:
   * Optie 1: Typ een segmentnaam in het zoekveld. Het veld wordt automatisch bijgewerkt op basis van de tekst. Klik **[!UICONTROL Add]** zodra u het segment vindt u wilt gebruiken.
   * Optie 2: Klik **[!UICONTROL Browse All Segments]** om een venster te openen waarin u naar segmenten kunt bladeren op naam of opslaglocatie. Klik **[!UICONTROL Add Selected Segments]** wanneer gereed.
1. **Toewijzingen toevoegen:** Voer in het pop-upmenu Toewijzingen de segment-id in het toewijzingsveld in en klik op **[!UICONTROL Save]**.
1. Klik op **[!UICONTROL Done]**.

## OpenX instellen {#openx-code-setup}

Wijzig [!DNL OpenX] montages om met Audience Manager segmentgegevens te werken.

<!-- aam-openx-code.xml -->

Instellen [!DNL OpenX]:

* Installeer [!UICONTROL DIL] code op uw site.
* Maken [!DNL OpenX] als een koekjesdoel in de Audience Manager.
* Plaats de `get_aamCookie` functie boven aan de pagina, idealiter in de `<head>` codeblok. De `get_aamCookie` code is [hier](../../features/destinations/get-aam-cookie-code.md)beschikbaar.
* Wijzig uw advertentietag om de `get_aamCookie` functie te roepen en de koekjesnaam te omvatten u bij het opzetten van de [!DNL OpenX] bestemming verstrekte. Als u bijvoorbeeld de cookie een naam hebt gegeven `test_cookie`, moet de tag ad de naam van het cookie aanroepen `get_aamCookie` en ernaar verwijzen.
* De advertentietag kan er ongeveer zo uitzien als hieronder.

   ```
   <a href= "https://client.adserver.net/?" + get_aamCookie('test_cookie') +
    "&etc&xid=" + get_aamCookie('aam_uuid')
   ```

Vergeet niet om op te nemen `xid=` . Het houdt werkelijk unieke gebruiker - identiteitskaart ([!UICONTROL UUID]) binnen overgegaan tijdens een advertentievraag.

De volledig gevormde ad call zou als dit kunnen kijken:

```
https://client.adserver.net/?c.key1=val1&c.key2=val2&etc& xid =3286487458745343
```
