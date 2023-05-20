---
description: U kunt gekwalificeerde segmenten naar Google Ad Manager verzenden via een client-side of via een serverintegratie. Vereisten en gerelateerde informatie over beide methoden worden hieronder vermeld.
seo-description: You can send qualified segments to Google Ad Manager either through a client-side or through a server-side integration. Requirements and related information about both methods are listed below.
seo-title: Requirements and Methods of Sending Segments to Google Ad Manager Using Google Publisher Tags (GPT)
solution: Audience Manager
title: Vereisten en methoden voor het verzenden van segmenten naar Google Ad Manager met behulp van Google Publisher-tags (GPT)
uuid: 4b2ea81c-29bb-42d3-93d3-1d8e677790b6
feature: Third-party Integration
exl-id: 04bf6fb5-ce38-4de1-bf19-e130b7e47616
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '481'
ht-degree: 0%

---

# Vereisten en methoden voor het verzenden van segmenten naar Google Ad Manager met behulp van Google Publisher-tags (GPT) {#requirements-and-methods-of-sending-segments-to-dfp-using-google-publisher-tags-gpt}

U kunt gekwalificeerde segmenten naar [!DNL Google Ad Manager] (voorheen DFP) via een client-side of via een server-side integratie. Vereisten en gerelateerde informatie over beide methoden worden hieronder vermeld.

## Integratie op de client {#client-side-integration}

Voor een integratie op de client moet u een [!DNL GPT] bestemming in Audience Manager. Houd rekening met de volgende punten wanneer u de configuratie wilt instellen [!DNL GPT] als bestemming Audience Manager:

* **Toevoegen [!UICONTROL DIL]:** Implementeren [!UICONTROL Data Integration Library (DIL)] code op alle pagina&#39;s wilt richten u. [!UICONTROL DIL] schrijft het segmentgegevens van de Audience Manager en gebruiker - IDs aan koekjes die door worden gebruikt [!DNL GPT] voor doelwitten.

* **Een [!UICONTROL Cookie Destination]:** [!DNL GPT] moet worden ingesteld als een op cookies gebaseerde bestemming in de Audience Manager.

* **Cookie-controlecode implementeren:** Omloop de [!DNL GPT] `.setTargeting` API-methode in onze aanbevolen [code voor cookie controleren](../../integration/gpt-aam-destination/gpt-aam-modify-api.md). Deze code helpt fouten te voorkomen door te zoeken naar geldige AAM cookies vóór de `.setTargeting` wordt aangeroepen.

* **Voeg de `AamGpt` Functie:** De `AamGpt` code legt gegevens van de koekjes van de Audience Manager vast en verzendt het naar [!DNL GPT]. Plaats de [Audience Manager Code voor Google Publisher-tags](../../integration/gpt-aam-destination/gpt-aam-aamgpt-code.md) ( `AamGpt`) boven aan de pagina of binnen de pagina `<head>` codeblok.

   >[!NOTE]
   >
   >De `AamGpt` Deze functie is niet vereist als u uw eigen code gebruikt om Audience Manager cookie data te lezen.

* **Leveringslogboeken naar Audience Manager verzenden:** Als u (facultatief) een rapport van de segmentlevering wilt, verstrek Audience Manager van een dagelijks logboek dat indruk-vlakke leveringsgegevens bevat. De gegevens kunnen een Raw-indeling hebben, maar elke record moet de Audience Manager bevatten `UUID`. Audience Managers kunnen deze ophalen of ontvangen via [!DNL FTP].

### Alleen gekwalificeerde segmenten worden naar GPT verzonden

De hoeveelheid gegevens die wordt doorgegeven aan [!DNL GPT] is afhankelijk van het aantal segmenten waarvoor een bepaalde gebruiker in aanmerking komt. Stel bijvoorbeeld dat u 100 Audience Manager-segmenten instelt. Als een bezoeker van de site voor vijf van hen in aanmerking komt, worden alleen die vijf segmenten verzonden naar [!DNL GPT] (niet alle 100).

>[!NOTE]
>
>Er zijn geen limieten aan het aantal sleutelwaarden dat u kunt verzenden, maar de waarden [!DNL Google] verzoek [!DNL URL] bevat geen limiet voor het aantal tekens dat wordt geaccepteerd. Zie [Doelstellingen en grootten instellen met GPT](https://support.google.com/dfp_premium/bin/answer.py?hl=en&amp;answer=1697712).

## Integratie op de server {#server-side-integration}

Neem contact op met uw consultant van de Audience Manager of de klantenservice als u een integratie op de server wilt instellen met [!DNL Google Ad Manager], gebruiken [!DNL GPT]. U moet uw [!DNL Google Ad Manager] account Network ID and Audience Link ID.

>[!IMPORTANT]
>
>Als uw webpagina&#39;s worden uitgevoerd, [Versnelde mediapagina&#39;s](https://www.ampproject.org/) ([!DNL AMP]), moet u de integratie op de server met Audience Manager gebruiken. Als u aan [!DNL AMP] en een clientintegratie met [!DNL AMP], moet u migreren naar de integratie op de server. Neem contact op met uw Audience Manager consultant of klantenservice om de migratie te bespreken.

>[!MORELIKETHIS]
>
>* [GPT API-naslaggids](https://support.google.com/dfp_premium/bin/answer.py?hl=en&amp;answer=1650154)

