---
description: U kunt gekwalificeerde segmenten naar Google Ad Manager verzenden via een client-side of via een serverintegratie. Vereisten en gerelateerde informatie over beide methoden worden hieronder vermeld.
seo-description: U kunt gekwalificeerde segmenten naar Google Ad Manager verzenden via een client-side of via een serverintegratie. Vereisten en gerelateerde informatie over beide methoden worden hieronder vermeld.
seo-title: Vereisten en methoden voor het verzenden van segmenten naar Google Ad Manager via Google Publisher-tags (GPT)
solution: Audience Manager
title: Vereisten en methoden voor het verzenden van segmenten naar Google Ad Manager via Google Publisher-tags (GPT)
uuid: 4b2ea81c-29bb-42d3-93d3-1d8e677790b6
feature: Third Party Integrations
translation-type: tm+mt
source-git-commit: e007279d81998031d2d61d0e68fe911813cadf8e
workflow-type: tm+mt
source-wordcount: '524'
ht-degree: 0%

---


# Vereisten en methoden voor het verzenden van segmenten naar Google Ad Manager via Google Publisher-tags (GPT) {#requirements-and-methods-of-sending-segments-to-dfp-using-google-publisher-tags-gpt}

U kunt gekwalificeerde segmenten naar [!DNL Google Ad Manager] (voorheen DFP) verzenden via een client-side of via een serverintegratie. Vereisten en gerelateerde informatie over beide methoden worden hieronder vermeld.

## Integratie op de client {#client-side-integration}

Voor integratie op de client moet u een [!DNL GPT]-doel instellen in Audience Manager. Houd rekening met de volgende punten wanneer u [!DNL GPT] wilt instellen als bestemming Audience Manager:

* **Toevoegen  [!UICONTROL DIL]:**  [!UICONTROL Data Integration Library (DIL)] Code implementeren op alle pagina&#39;s die u als doel wilt instellen. [!UICONTROL DIL] schrijft het segmentgegevens van de Audience Manager en gebruikers IDs aan koekjes die door  [!DNL GPT] voor het richten worden gebruikt.

* **Maak een  [!UICONTROL Cookie Destination]:** [!DNL GPT] moet zijn ingesteld als een op cookies gebaseerd doel in de Audience Manager.

* **Cookie-controlecode implementeren:** Plaats de  [!DNL GPT] `.setTargeting` API-methode in de aanbevolen  [code](../../integration/gpt-aam-destination/gpt-aam-modify-api.md) voor cookies. Deze code helpt fouten te voorkomen door geldige AAM cookies te zoeken voordat de methode `.setTargeting` wordt aangeroepen.

* **Voeg de  `AamGpt` Functie toe:** de  `AamGpt` code vangt gegevens van de koekjes van de Audience Manager en verzendt het naar  [!DNL GPT]. Plaats de [Code voor Audience Manager voor Google Publisher-tags](../../integration/gpt-aam-destination/gpt-aam-aamgpt-code.md) ( `AamGpt`) boven aan de pagina of in het `<head>`-codeblok.

   >[!NOTE]
   >
   >De functie `AamGpt` is niet vereist als u uw eigen code gebruikt om de gegevens van het de koekje van de Audience Manager te lezen.

* **Verzend de Logboeken van de Levering aan Audience Manager:** Als u een (facultatief) segmentleveringsrapport wilt, verstrek Audience Manager van een dagelijks logboek dat indruk-vlakke leveringsgegevens bevat. De gegevens kunnen een RAW-indeling hebben, maar elke record moet de Audience Manager `UUID` bevatten. Audience Managers kunnen deze ophalen of ontvangen via [!DNL FTP].

### Alleen gekwalificeerde segmenten worden naar GPT verzonden

De hoeveelheid gegevens die wordt doorgegeven aan [!DNL GPT], is afhankelijk van het aantal segmenten waarvoor een bepaalde gebruiker in aanmerking komt. Stel bijvoorbeeld dat u 100 Audience Manager-segmenten instelt. Als een bezoeker van de site voor vijf van hen in aanmerking komt, worden alleen die vijf segmenten verzonden naar [!DNL GPT] (niet alle 100).

>[!NOTE]
>
>Er zijn geen grenzen aan het aantal zeer belangrijke-waarden u kunt verzenden, maar [!DNL Google] verzoek [!DNL URL] heeft grenzen aan het aantal karakters het kan goedkeuren. Zie [Doelstellingen en grootten instellen met GPT](https://support.google.com/dfp_premium/bin/answer.py?hl=en&amp;answer=1697712).

## Integratie op de server {#server-side-integration}

Neem contact op met uw consultant voor Audience Managers of de klantenservice als u een integratie op de server wilt instellen met [!DNL Google Ad Manager], met behulp van [!DNL GPT]. U zult uw [!DNL Google Ad Manager] identiteitskaart van het accountnetwerk en identiteitskaart van de Verbinding van het Publiek moeten verstrekken.

>[!IMPORTANT]
>
>Als op uw webpagina&#39;s de bibliotheek [Versnelde mediapagina&#39;s](https://www.ampproject.org/) ([!DNL AMP]) wordt uitgevoerd, moet u de integratie op de server met Audience Manager gebruiken. Als u op [!DNL AMP] staat en een client-side integratie met [!DNL AMP] hebt, moet u migreren naar de integratie op de server. Neem contact op met uw Audience Manager consultant of klantenservice om de migratie te bespreken.

>[!MORELIKETHIS]
>
>* [GPT API-naslaggids](https://support.google.com/dfp_premium/bin/answer.py?hl=en&amp;answer=1650154)

