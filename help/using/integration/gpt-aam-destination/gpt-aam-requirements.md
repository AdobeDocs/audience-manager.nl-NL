---
description: U kunt gekwalificeerde segmenten naar DFP of door een cliënt-kant of door een server-zijintegratie verzenden. Vereisten en gerelateerde informatie over beide methoden worden hieronder vermeld.
seo-description: U kunt gekwalificeerde segmenten naar DFP of door een cliënt-kant of door een server-zijintegratie verzenden. Vereisten en gerelateerde informatie over beide methoden worden hieronder vermeld.
seo-title: Vereisten en methoden voor het verzenden van segmenten naar DFP met Google Publisher-tags (GPT)
solution: Audience Manager
title: Vereisten en methoden voor het verzenden van segmenten naar DFP met Google Publisher-tags (GPT)
uuid: 4b2ea81c-29bb-42d3-93d3-1d8e677790b6
feature: Third Party Integrations
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '512'
ht-degree: 0%

---


# Vereisten en methoden voor het verzenden van segmenten naar DFP met Google Publisher-tags (GPT) {#requirements-and-methods-of-sending-segments-to-dfp-using-google-publisher-tags-gpt}

U kunt gekwalificeerde segmenten naar [!DNL DFP] of door een cliënt-kant of door een server-zijintegratie verzenden. Vereisten en gerelateerde informatie over beide methoden worden hieronder vermeld.

## Integratie op de client {#client-side-integration}

Voor een cliënt-zijintegratie, moet u opstelling een [!DNL GPT] bestemming in Audience Manager. Houd rekening met de volgende punten wanneer u een Audience Manager wilt instellen [!DNL GPT] als doel:

* **Toevoegen[!UICONTROL DIL]:** Implementeer [!UICONTROL Data Integration Library (DIL)] code op alle pagina&#39;s waarop u wilt verwijzen. [!UICONTROL DIL] schrijft het segmentgegevens van de Audience Manager en gebruikers IDs aan koekjes die door [!DNL GPT] voor het richten worden gebruikt.

* **Maak een[!UICONTROL Cookie Destination]:** [!DNL GPT] moet worden ingesteld als een op cookies gebaseerde bestemming in de Audience Manager.

* **Cookie-controlecode implementeren:** Plaats de [!DNL GPT] API-methode in de aanbevolen `.setTargeting` code [](../../integration/gpt-aam-destination/gpt-aam-modify-api.md)voor cookies. Deze code voorkomt fouten door naar geldige AAM-cookies te zoeken voordat de `.setTargeting` methode wordt aangeroepen.

* **Voeg de`AamGpt`functie toe:** De `AamGpt` code vangt gegevens van de koekjes van de Audience Manager en verzendt het naar [!DNL GPT]. Plaats de [Audience Manager Code for Google Publisher Tags](../../integration/gpt-aam-destination/gpt-aam-aamgpt-code.md) ( `AamGpt`) boven aan de pagina of in het `<head>` codeblok.

   >[!NOTE]
   >
   >De `AamGpt` functie is niet vereist als u uw eigen code gebruikt om de gegevens van de Audience Manager koekje te lezen.

* **Leveringslogboeken naar Audience Manager verzenden:** Als u (facultatief) een rapport van de segmentlevering wilt, verstrek Audience Manager van een dagelijks logboek dat indruk-vlakke leveringsgegevens bevat. De gegevens kunnen in een RAW-indeling zijn, maar elke record moet de Audience Manager bevatten `UUID`. Audience Managers kunnen deze ophalen of ontvangen via [!DNL FTP].

### Alleen gekwalificeerde segmenten worden naar GPT verzonden

De hoeveelheid gegevens die wordt doorgegeven aan, is [!DNL GPT] afhankelijk van het aantal segmenten waarvoor een bepaalde gebruiker in aanmerking komt. Stel bijvoorbeeld dat u 100 Audience Manager-segmenten instelt. Als een bezoeker van de site voor vijf van hen in aanmerking komt, worden alleen die vijf segmenten verzonden naar [!DNL GPT] (niet alle 100).

>[!NOTE]
>
>Er zijn geen limieten aan het aantal toetswaarden dat u kunt verzenden, maar de [!DNL Google] aanvraag [!DNL URL] bevat wel limieten aan het aantal tekens dat u kunt accepteren. Zie [Doelstellingen en grootten instellen met GPT](https://support.google.com/dfp_premium/bin/answer.py?hl=en&amp;answer=1697712).

## Integratie op de server {#server-side-integration}

Neem contact op met de consultant van de Audience Manager of de klantenservice als u een integratie op de server wilt instellen met [!DNL DFP]behulp van [!DNL GPT]de service. U zult uw identiteitskaart van het [!DNL DFP] RekeningNetwerk en identiteitskaart van de Verbinding van het Publiek moeten verstrekken.

>[!IMPORTANT]
>
>Als op uw webpagina&#39;s de bibliotheek [Accelerated Media Pages](https://www.ampproject.org/) ([!DNL AMP]) wordt uitgevoerd, moet u de integratie op de server met Audience Manager gebruiken. Als u aan [!DNL AMP] [!DNL AMP]en een cliënt-zijintegratie met hebt, moet u aan de server-zijintegratie migreren. Neem contact op met uw Audience Manager consultant of klantenservice om de migratie te bespreken.

>[!MORELIKETHIS]
>
>* [GPT API-naslaggids](https://support.google.com/dfp_premium/bin/answer.py?hl=en&amp;answer=1650154)

