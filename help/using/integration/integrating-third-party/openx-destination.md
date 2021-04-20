---
description: Opstelling OpenX als bestemming en verzend de gegevens van het het segmentsegment van de Audience Manager naar dat platform.
seo-description: Opstelling OpenX als bestemming en verzend de gegevens van het het segmentsegment van de Audience Manager naar dat platform.
seo-title: OpenX als Audience Manager-bestemming
solution: Audience Manager
title: OpenX als Audience Manager-bestemming
uuid: 5e86ba73-281c-403b-af06-64a1d427526a
feature: Third-party Integration
exl-id: 938a518b-c8b0-4e86-885f-daf79b2cba38
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '697'
ht-degree: 3%

---

# OpenX als Audience Manager-bestemming{#openx-as-an-audience-manager-destination}

Stel [!DNL OpenX] in als een doel en verzend Audience Manager segmentgegevens naar dat platform.

>[!NOTE]
>
>Alleen voor onsite en servergerichte toepassingen.

## OpenX-doelvereisten {#openx-requirements}

Standaarden voor plaatsing van code, ondersteunde sleutel-waardeformaten, rapporten, en het type segmentgegevens die naar [!DNL OpenX] worden verzonden.

<!-- aam-openx-requirements.xml -->

Controleer het volgende voordat u [!DNL OpenX] instelt als bestemming van Audience Manager:

* **[!UICONTROL DIL]:** [!UICONTROL Data Integration Library] code moet op uw site worden geïmplementeerd. [!UICONTROL DIL] helpt u te voorkomen dat u speciale code hoeft te schrijven voor gegevensverzameling, integratie, het lezen van cookiewaarden en het herstellen van paginagegevens.
* **`get_aamCookie`Functie:** Code waarmee de gebruikers-id en cookie-gegevens van de Audience Manager worden vastgelegd. Plaats [deze code](../../features/destinations/get-aam-cookie-code.md) boven aan de pagina of in het `<head>` codeblok.
* **Verzend de Logboeken van de Levering aan Audience Manager:** Als u een (facultatief) segmentleveringsrapport wilt, verstrek Audience Manager van een dagelijks logboek dat indruk-vlakke leveringsgegevens bevat. De gegevens kunnen een RAW-indeling hebben, maar elke record moet de Audience Manager `UUID` bevatten. Audience Managers kunnen deze ophalen of ontvangen via [!DNL FTP].

### Sleutelwaarde-gegevens: Formuliervereisten

Audience Manager verzendt gegevens in de vorm van sleutel-waardeparen. Maak sleutelwaardeparen volgens de volgende specificaties:

* Voornaamsleutels met `c.` (bijvoorbeeld `c.color` of `c.price`).
* Afzonderlijke geserialiseerde waarden die aan één toets zijn gekoppeld met een komma (bijvoorbeeld `c.color = red, green, blue`).
* Scheid meerdere sleutel-waardeparen met een en-teken (bijvoorbeeld `c.color=red & c.price = 100 & c.condition = new`).
* Sleutelnamen mogen geen speciale tekens zoals accenten en leestekens of andere symbolen bevatten.

### Alleen gekwalificeerde segmenten worden verzonden naar OpenX

De hoeveelheid gegevens die aan [!DNL OpenX] worden doorgegeven, is afhankelijk van het aantal segmenten waarvoor een bepaalde gebruiker in aanmerking komt. Stel bijvoorbeeld dat u 100 Audience Manager-segmenten instelt. Als een bezoeker van de site voor vijf van hen in aanmerking komt, worden alleen die vijf segmenten verzonden naar [!DNL OpenX] (niet alle 100).

## Een OpenX-doel maken {#openx-destination}

Maak een cookiebestemming voor [!DNL OpenX] in Audience Manager.

<!-- aam-openx-destination.xml -->

In Audience Manager is een *doel* elk ander systeem (ad server, [!DNL DSP], netwerk, enz.) waarmee u data wilt delen. [!UICONTROL Destination Builder] biedt de gereedschappen waarmee u deze processen voor gegevenslevering kunt maken en beheren. De bestemmingseigenschappen van de Audience Manager worden gevestigd in *Gegevens van het publiek > Doelen*. Klik **[!UICONTROL Add New Destination]** en volg de onderstaande stappen om aan de slag te gaan.

### Stap 1: Basisinformatie

De sectie [!UICONTROL Basic Information] voltooien:

1. Geef het doel een naam.
1. Selecteer **[!UICONTROL "Cookie"]** in de vervolgkeuzelijst [!UICONTROL Type].
1. Klik op **[!UICONTROL Next]** en ga naar de secties [!UICONTROL Configuration] en [!UICONTROL Segment Mappings].

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

## OpenX-instelling {#openx-code-setup}

Wijzig [!DNL OpenX] montages om met Audience Manager segmentgegevens te werken.

<!-- aam-openx-code.xml -->

[!DNL OpenX] instellen:

* Installeer [!UICONTROL DIL] code over uw plaats.
* Maak [!DNL OpenX] als een koekjesbestemming in Audience Manager.
* Plaats de functie `get_aamCookie` boven aan de pagina, idealiter binnen de codeblok `<head>`. De `get_aamCookie`-code is [hier](../../features/destinations/get-aam-cookie-code.md) beschikbaar.
* Wijzig uw advertentietag om de `get_aamCookie` functie te roepen en omvat de koekjesnaam u toen het plaatsen van [!DNL OpenX] bestemming verstrekte. Als u bijvoorbeeld het cookie `test_cookie` een naam hebt gegeven, moet de tag ad `get_aamCookie` aanroepen en naar de naam van het cookie verwijzen.
* De advertentietag kan er ongeveer zo uitzien als hieronder.

   ```
   <a href= "https://client.adserver.net/?" + get_aamCookie('test_cookie') +
    "&etc&xid=" + get_aamCookie('aam_uuid')
   ```

Vergeet niet `xid=` op te nemen. Het houdt werkelijk unieke gebruiker - identiteitskaart ([!UICONTROL UUID]) binnen die tijdens een ad vraag wordt overgegaan.

De volledig gevormde ad call zou als dit kunnen kijken:

```
https://client.adserver.net/?c.key1=val1&c.key2=val2&etc& xid =3286487458745343
```
