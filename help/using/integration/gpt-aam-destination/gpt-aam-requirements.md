---
description: U kunt gekwalificeerde segmenten naar Google Ad Manager verzenden via een client-side of via een serverintegratie. Vereisten en gerelateerde informatie over beide methoden worden hieronder vermeld.
seo-description: You can send qualified segments to Google Ad Manager either through a client-side or through a server-side integration. Requirements and related information about both methods are listed below.
seo-title: Requirements and Methods of Sending Segments to Google Ad Manager Using Google Publisher Tags (GPT)
solution: Audience Manager
title: Vereisten en methoden voor het verzenden van segmenten naar Google Ad Manager met Google Publisher-tags (GPT)
uuid: 4b2ea81c-29bb-42d3-93d3-1d8e677790b6
feature: Third-party Integration
exl-id: 04bf6fb5-ce38-4de1-bf19-e130b7e47616
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '466'
ht-degree: 0%

---

# Vereisten en methoden voor het verzenden van segmenten naar Google Ad Manager met Google Publisher-tags (GPT) {#requirements-and-methods-of-sending-segments-to-dfp-using-google-publisher-tags-gpt}

U kunt gekwalificeerde segmenten naar [!DNL Google Ad Manager] (voorheen DFP) verzenden via een client-side of via een serverintegratie. Vereisten en gerelateerde informatie over beide methoden worden hieronder vermeld.

## Integratie op de client {#client-side-integration}

Voor integratie op de client moet u een [!DNL GPT] -doel instellen in Audience Manager. Houd rekening met de volgende punten wanneer u [!DNL GPT] wilt instellen als Audience Manager-doel:

* **voeg [!UICONTROL DIL] toe:** stel [!UICONTROL Data Integration Library (DIL)] code op alle pagina&#39;s op u wilt richten. [!UICONTROL DIL] schrijft gegevens van Audience Manager-segmenten en gebruikers-id&#39;s naar cookies die door [!DNL GPT] worden gebruikt voor het opgeven van doelen.

* **creeer a [!UICONTROL Cookie Destination]:** [!DNL GPT] moet opstelling als op koekje-gebaseerde bestemming in Audience Manager zijn.

* **voert Koekjescontrole uit Code:** verpakt de [!DNL GPT] `.setTargeting` API methode in onze geadviseerde [ koekje controlerende code ](../../integration/gpt-aam-destination/gpt-aam-modify-api.md). Deze code helpt fouten te voorkomen door naar geldige AAM cookies te zoeken voordat de methode `.setTargeting` wordt aangeroepen.

* **voeg `AamGpt` Functie toe:** de `AamGpt` code vangt gegevens van de koekjes van Audience Manager en verzendt het naar [!DNL GPT]. Plaats de [ Code van Audience Manager voor de Markeringen van de Uitgever van Google ](../../integration/gpt-aam-destination/gpt-aam-aamgpt-code.md) ( `AamGpt`) bij de bovenkant van de pagina of binnen het `<head>` codeblok.

  >[!NOTE]
  >
  >De functie `AamGpt` is niet vereist als u uw eigen code gebruikt om Audience Manager cookie-gegevens te lezen.

* **verzend Logboeken van de Levering naar Audience Manager:** als u een (facultatief) rapport van de segmentlevering wilt, Audience Manager van een dagelijks logboek voorzien dat indruk-vlakke leveringsgegevens bevat. De gegevens kunnen in onbewerkte indeling worden opgeslagen, maar elke record moet de Audience Manager `UUID` bevatten. Audience Manager kan deze ophalen of ontvangen via [!DNL FTP] .

### Alleen gekwalificeerde segmenten worden naar GPT verzonden

De hoeveelheid gegevens die aan [!DNL GPT] wordt doorgegeven, is afhankelijk van het aantal segmenten waarvoor een bepaalde gebruiker in aanmerking komt. Stel dat u 100 Audience Manager-segmenten instelt. Als een bezoeker van de site voor vijf van hen in aanmerking komt, worden alleen die vijf segmenten verzonden naar [!DNL GPT] (niet alle 100).

>[!NOTE]
>
>Er zijn geen limieten aan het aantal toetswaarden dat u kunt verzenden, maar de [!DNL Google] request [!DNL URL] heeft wel beperkingen aan het aantal tekens dat de aanvraag kan accepteren. Zie [ Plaatsend het richten en grootte met GPT ](https://support.google.com/dfp_premium/bin/answer.py?hl=en&answer=1697712).

## Integratie op de server {#server-side-integration}

Neem contact op met uw Audience Manager-consultant of de klantenservice als u een integratie op de server met [!DNL Google Ad Manager] wilt instellen met [!DNL GPT] . U moet uw [!DNL Google Ad Manager] account-netwerk-id en Audience Link-id opgeven.

>[!IMPORTANT]
>
>Als uw Web-pagina&#39;s de [ versnelde bibliotheek van de Pagina&#39;s van Media ](https://www.ampproject.org/) ([!DNL AMP]) in werking stellen, moet u de server-zijintegratie met Audience Manager gebruiken. Als u [!DNL AMP] aanstaat en een client-side integratie met [!DNL AMP] hebt, moet u migreren naar de server-side integratie. Neem contact op met uw Audience Manager-consultant of klantenservice om de migratie te bespreken.

>[!MORELIKETHIS]
>
>* [ GPT API de Gids van de Verwijzing ](https://support.google.com/dfp_premium/bin/answer.py?hl=en&answer=1650154)
