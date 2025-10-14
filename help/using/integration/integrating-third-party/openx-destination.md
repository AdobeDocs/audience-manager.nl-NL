---
description: Stel OpenX in als een doel en verzend Audience Manager-segmentgegevens naar dat platform.
seo-description: Set up OpenX as a destination and send Audience Manager segment data to that platform.
seo-title: OpenX as an Audience Manager Destination
solution: Audience Manager
title: OpenX als Audience Manager-doel
uuid: 5e86ba73-281c-403b-af06-64a1d427526a
feature: Third-party Integration
exl-id: 938a518b-c8b0-4e86-885f-daf79b2cba38
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '681'
ht-degree: 0%

---

# OpenX als Audience Manager-doel{#openx-as-an-audience-manager-destination}

Stel [!DNL OpenX] in als een doel en verzend Audience Manager-segmentgegevens naar dat platform.

>[!NOTE]
>
>Alleen voor onsite en servergerichte toepassingen.

## Vereisten voor OpenX-bestemming {#openx-requirements}

Standaarden voor plaatsing van code, ondersteunde indelingen voor sleutelwaarden, rapporten en het type segmentgegevens dat naar [!DNL OpenX] wordt verzonden.

<!-- aam-openx-requirements.xml -->

Lees het volgende voordat u [!DNL OpenX] instelt als Audience Manager-doel:

* **[!UICONTROL DIL]:** [!UICONTROL Data Integration Library] code moet op uw site worden geïmplementeerd. Met [!UICONTROL DIL] voorkomt u de noodzaak om speciale code te schrijven voor gegevensverzameling, integratie, het lezen van cookiewaarden en het herstellen van paginagegevens.
* **`get_aamCookie`Functie:** Code waarmee de Audience Manager-gebruikers-id en -cookie worden vastgelegd. Plaats [&#x200B; deze code &#x200B;](../../features/destinations/get-aam-cookie-code.md) op de bovenkant van de pagina of binnen de `<head>` codeblok.
* **verzend Logboeken van de Levering naar Audience Manager:** als u een (facultatief) rapport van de segmentlevering wilt, Audience Manager van een dagelijks logboek voorzien dat indruk-vlakke leveringsgegevens bevat. De gegevens kunnen in onbewerkte indeling worden opgeslagen, maar elke record moet de Audience Manager `UUID` bevatten. Audience Manager kan deze ophalen of ontvangen via [!DNL FTP] .

### Sleutelwaarde-gegevens: vereisten voor indeling

Audience Manager verzendt gegevens in de vorm van sleutel-waardeparen. Maak sleutelwaardeparen volgens de volgende specificaties:

* Voorvertoningstoetsen met `c.` (bijvoorbeeld `c.color` of `c.price` ).
* Afzonderlijke geserialiseerde waarden die aan één toets zijn gekoppeld met een komma (bijvoorbeeld `c.color = red, green, blue` ).
* Scheid meerdere sleutel-waardeparen met een en-teken (bijvoorbeeld `c.color=red & c.price = 100 & c.condition = new` ).
* Sleutelnamen mogen geen speciale tekens zoals accenten en leestekens of andere symbolen bevatten.

### Alleen gekwalificeerde segmenten worden verzonden naar OpenX

De hoeveelheid gegevens die aan [!DNL OpenX] wordt doorgegeven, is afhankelijk van het aantal segmenten waarvoor een bepaalde gebruiker in aanmerking komt. Stel dat u 100 Audience Manager-segmenten instelt. Als een bezoeker van de site voor vijf van hen in aanmerking komt, worden alleen die vijf segmenten verzonden naar [!DNL OpenX] (niet alle 100).

## Een OpenX-doel maken {#openx-destination}

Maak een cookiebestemming voor [!DNL OpenX] in Audience Manager.

<!-- aam-openx-destination.xml -->

In Audience Manager, is a *bestemming* een ander systeem (ad server, [!DNL DSP], en netwerk, enz.) dat u gegevens met wilt delen. [!UICONTROL Destination Builder] biedt de gereedschappen waarmee u deze processen voor gegevenslevering kunt maken en beheren. De bestemmingseigenschappen van Audience Manager worden gevestigd in *Gegevens van het publiek > Doelen*. Klik op **[!UICONTROL Add New Destination]** en volg de onderstaande stappen om aan de slag te gaan.

### Stap 1: Basisinformatie

De sectie [!UICONTROL Basic Information] voltooien:

1. Geef het doel een naam.
1. Selecteer **[!UICONTROL "Cookie"]** in de vervolgkeuzelijst [!UICONTROL Type] .
1. Klik op **[!UICONTROL Next]** en ga naar de secties [!UICONTROL Configuration] en [!UICONTROL Segment Mappings] .

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

## OpenX instellen {#openx-code-setup}

Wijzig [!DNL OpenX] instellingen om met Audience Manager-segmentgegevens te werken.

<!-- aam-openx-code.xml -->

Instellen [!DNL OpenX] :

* Installeer [!UICONTROL DIL] -code op uw site.
* Maak [!DNL OpenX] als een cookiedoel in Audience Manager.
* Plaats de functie `get_aamCookie` boven aan de pagina, in het ideale geval in de `<head>` -codeblok. De `get_aamCookie` code is beschikbaar [&#x200B; hier &#x200B;](../../features/destinations/get-aam-cookie-code.md).
* Wijzig de advertentietag om de functie `get_aamCookie` aan te roepen en neem de cookienaam op die u hebt opgegeven bij het instellen van de bestemming [!DNL OpenX] . Als u bijvoorbeeld de cookie `test_cookie` een naam hebt gegeven, moet de tag ad `get_aamCookie` aanroepen en naar de naam van de cookie verwijzen.
* De advertentietag kan er ongeveer zo uitzien als hieronder.

  ```
  <a href= "https://client.adserver.net/?" + get_aamCookie('test_cookie') +
   "&etc&xid=" + get_aamCookie('aam_uuid')
  ```

Vergeet niet `xid=` op te nemen. Het houdt werkelijk unieke gebruiker - identiteitskaart ([!UICONTROL UUID]) binnen overgegaan tijdens een ad vraag.

De volledig gevormde ad call zou als dit kunnen kijken:

```
https://client.adserver.net/?c.key1=val1&c.key2=val2&etc& xid =3286487458745343
```
