---
description: Opstelling OpenX als bestemming en verzend de gegevens van het het segmentsegment van de Audience Manager naar dat platform.
seo-description: Set up OpenX as a destination and send Audience Manager segment data to that platform.
seo-title: OpenX as an Audience Manager Destination
solution: Audience Manager
title: OpenX als Audience Manager-bestemming
uuid: 5e86ba73-281c-403b-af06-64a1d427526a
feature: Third-party Integration
exl-id: 938a518b-c8b0-4e86-885f-daf79b2cba38
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '674'
ht-degree: 2%

---

# OpenX als Audience Manager-bestemming{#openx-as-an-audience-manager-destination}

Instellen [!DNL OpenX] als bestemming en verzendt de gegevens van het segment van de Audience Manager naar dat platform.

>[!NOTE]
>
>Alleen voor onsite en servergerichte toepassingen.

## Vereisten voor OpenX-bestemming {#openx-requirements}

Normen voor codeplaatsing, gesteunde zeer belangrijk-waardeformaten, rapporten, en het type segmentgegevens die naar worden verzonden [!DNL OpenX].

<!-- aam-openx-requirements.xml -->

Controleer het volgende voordat u de configuratie instelt [!DNL OpenX] als bestemming Audience Manager:

* **[!UICONTROL DIL]:** [!UICONTROL Data Integration Library] code moet op uw site worden geïmplementeerd. [!UICONTROL DIL] helpt u te voorkomen dat u speciale code hoeft te schrijven voor gegevensverzameling, integratie, het lezen van cookiewaarden en het herstellen van paginagegevens.
* **`get_aamCookie`Functie:** Code waarmee de gebruikers-id en cookie-gegevens van de Audience Manager worden vastgelegd. Plaatsen [deze code](../../features/destinations/get-aam-cookie-code.md) boven aan of binnen de pagina `<head>` codeblok.
* **Leveringslogboeken naar Audience Manager verzenden:** Als u (facultatief) een rapport van de segmentlevering wilt, verstrek Audience Manager van een dagelijks logboek dat indruk-vlakke leveringsgegevens bevat. De gegevens kunnen een Raw-indeling hebben, maar elke record moet de Audience Manager bevatten `UUID`. Audience Managers kunnen deze ophalen of ontvangen via [!DNL FTP].

### Sleutelwaarde-gegevens: Formuliervereisten

Audience Manager verzendt gegevens in de vorm van sleutel-waardeparen. Maak sleutelwaardeparen volgens de volgende specificaties:

* Voorkeuren instellen met `c.` (bv. `c.color` of `c.price`).
* Afzonderlijke geserialiseerde waarden die aan één sleutel zijn gekoppeld met een komma (bijvoorbeeld `c.color = red, green, blue`).
* Scheid meerdere sleutel-waardeparen met een en-teken (bijvoorbeeld `c.color=red & c.price = 100 & c.condition = new`).
* Sleutelnamen mogen geen speciale tekens zoals accenten en leestekens of andere symbolen bevatten.

### Alleen gekwalificeerde segmenten worden verzonden naar OpenX

De hoeveelheid gegevens die wordt doorgegeven aan [!DNL OpenX] is afhankelijk van het aantal segmenten waarvoor een bepaalde gebruiker in aanmerking komt. Stel bijvoorbeeld dat u 100 Audience Manager-segmenten instelt. Als een bezoeker van de site voor vijf van hen in aanmerking komt, worden alleen die vijf segmenten verzonden naar [!DNL OpenX] (niet alle 100).

## Een OpenX-doel maken {#openx-destination}

Een cookiebestemming maken voor [!DNL OpenX] in de Audience Manager.

<!-- aam-openx-destination.xml -->

In de Audience Manager *doel* is een ander systeem (advertentieserver), [!DNL DSP], en netwerk, enz.) waarmee u data wilt delen. [!UICONTROL Destination Builder] biedt de gereedschappen waarmee u deze processen voor gegevenslevering kunt maken en beheren. De bestemmingseigenschappen van de Audience Manager worden gevestigd in *Poortgegevens > Doelen*. Klik op **[!UICONTROL Add New Destination]** en volgt u de onderstaande stappen.

### Stap 1: Basisinformatie

Als u het dialoogvenster [!UICONTROL Basic Information] sectie:

1. Geef het doel een naam.
1. Selecteren **[!UICONTROL "Cookie"]** van de [!UICONTROL Type] vervolgkeuzelijst.
1. Klikken **[!UICONTROL Next]** en gaat u verder naar de [!UICONTROL Configuration] en [!UICONTROL Segment Mappings] secties.

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

## OpenX instellen {#openx-code-setup}

Wijzigen [!DNL OpenX] instellingen voor het werken met Audience Manager-segmentgegevens.

<!-- aam-openx-code.xml -->

Aan opstelling [!DNL OpenX]:

* Installeren [!UICONTROL DIL] code op uw site.
* Maken [!DNL OpenX] als een koekjesbestemming in Audience Manager.
* Plaats de `get_aamCookie` functie boven aan de pagina, ideaal binnen de `<head>` codeblok. De `get_aamCookie` code is beschikbaar [hier](../../features/destinations/get-aam-cookie-code.md).
* Wijzig uw advertentietag om te roepen `get_aamCookie` en neemt u de cookienaam op die u hebt opgegeven bij het instellen van de [!DNL OpenX] bestemming. Als u bijvoorbeeld de cookie een naam hebt gegeven `test_cookie`, moet de tag ad `get_aamCookie` en verwijs naar de naam van het cookie.
* De advertentietag kan er ongeveer zo uitzien als hieronder.

   ```
   <a href= "https://client.adserver.net/?" + get_aamCookie('test_cookie') +
    "&etc&xid=" + get_aamCookie('aam_uuid')
   ```

Opnemen onthouden `xid=` . Het bevat de werkelijke unieke gebruikersnaam ([!UICONTROL UUID]) die tijdens een advertentieaanroep is doorgegeven.

De volledig gevormde ad call zou als dit kunnen kijken:

```
https://client.adserver.net/?c.key1=val1&c.key2=val2&etc& xid =3286487458745343
```
