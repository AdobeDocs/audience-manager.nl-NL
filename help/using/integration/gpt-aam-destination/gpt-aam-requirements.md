---
description: U kunt gekwalificeerde segmenten naar DFP of door een cliënt-kant of door een server-zijintegratie verzenden. Vereisten en gerelateerde informatie over beide methoden worden hieronder vermeld.
seo-description: U kunt gekwalificeerde segmenten naar DFP of door een cliënt-kant of door een server-zijintegratie verzenden. Vereisten en gerelateerde informatie over beide methoden worden hieronder vermeld.
seo-title: Vereisten en methoden voor het verzenden van segmenten naar DFP met Google Publisher-tags (GPT)
solution: Audience Manager
title: Vereisten en methoden voor het verzenden van segmenten naar DFP met Google Publisher-tags (GPT)
uuid: 4b2ea81c-29bb-42d3-93d3-1d8e677790b6
translation-type: tm+mt
source-git-commit: d6abb45fa8b88248920b64db3ac4e72c53ecee13

---


# Vereisten en methoden voor het verzenden van segmenten naar DFP met Google Publisher-tags (GPT) {#requirements-and-methods-of-sending-segments-to-dfp-using-google-publisher-tags-gpt}

U kunt gekwalificeerde segmenten naar [!DNL DFP] of door een cliënt-kant of door een server-zijintegratie verzenden. Vereisten en gerelateerde informatie over beide methoden worden hieronder vermeld.

## Integratie op de client {#client-side-integration}

Voor een cliënt-zijintegratie, moet u opstelling een [!DNL GPT] bestemming in de Manager van het Publiek. Overweeg de volgende punten wanneer u opstelling [!DNL GPT] als bestemming van de Manager van de Publiek wilt:

* **Toevoegen[!UICONTROL DIL]:** Implementeer [!UICONTROL Data Integration Library (DIL)] code op alle pagina&#39;s waarop u wilt verwijzen. [!UICONTROL DIL] schrijft het segmentgegevens en gebruikers-id&#39;s van Audience Manager naar cookies die worden gebruikt door [!DNL GPT] voor het opgeven van doelen.

* **Maak een[!UICONTROL Cookie Destination]:** moet [!DNL GPT] in Audience Manager worden ingesteld als een op cookies gebaseerde bestemming.

* **Cookie-controlecode implementeren:** Plaats de [!DNL GPT] API-methode in de aanbevolen `.setTargeting` code [](../../integration/gpt-aam-destination/gpt-aam-modify-api.md)voor cookies. Deze code voorkomt fouten door naar geldige AAM-cookies te zoeken voordat de `.setTargeting` methode wordt aangeroepen.

* **Voeg de`AamGpt`functie toe:** De `AamGpt` code vangt gegevens van de koekjes van de Manager van de Publiek en verzendt het naar [!DNL GPT]. Plaats de code [Audience Manager voor Google Publisher-tags](../../integration/gpt-aam-destination/gpt-aam-aamgpt-code.md) ( `AamGpt`) boven aan de pagina of in het `<head>` codeblok.

   >[!NOTE]
   >
   >De `AamGpt` functie is niet vereist als u uw eigen code gebruikt om de koekjesgegevens van de Manager van de Audience te lezen.

* **Leveringslogboeken verzenden naar Audience Manager:** Als u (facultatief) een rapport van de segmentlevering wilt, verstrek de Manager van het Publiek van een dagelijks logboek dat indruk-vlakke leveringsgegevens bevat. De gegevens kunnen in onbewerkte indeling zijn, maar elke record moet de Audience Manager bevatten `UUID`. Audience Manager kan deze via ophalen of ontvangen [!DNL FTP].

### Alleen gekwalificeerde segmenten worden naar GPT verzonden

De hoeveelheid gegevens die wordt doorgegeven aan, is [!DNL GPT] afhankelijk van het aantal segmenten waarvoor een bepaalde gebruiker in aanmerking komt. Stel bijvoorbeeld dat u 100 segmenten van Audience Manager hebt ingesteld. Als een bezoeker van de site voor vijf van hen in aanmerking komt, worden alleen die vijf segmenten verzonden naar [!DNL GPT] (niet alle 100).

>[!NOTE]
>
>Er zijn geen limieten aan het aantal toetswaarden dat u kunt verzenden, maar de [!DNL Google] aanvraag [!DNL URL] bevat wel limieten aan het aantal tekens dat u kunt accepteren. Zie [Doelstellingen en grootten instellen met GPT](https://support.google.com/dfp_premium/bin/answer.py?hl=en&answer=1697712).

## Integratie op de server {#server-side-integration}

Neem contact op met de consultant van de Audience Manager of de klantenservice als u een integratie aan de serverzijde wilt instellen met [!DNL DFP]behulp van [!DNL GPT]. U zult uw identiteitskaart van het [!DNL DFP] RekeningNetwerk en identiteitskaart van de Verbinding van het Publiek moeten verstrekken.

>[!IMPORTANT]
>
>Als op uw webpagina&#39;s de bibliotheek [Accelerated Media Pages](https://www.ampproject.org/) ([!DNL AMP]) wordt uitgevoerd, moet u de integratie op de server met Audience Manager gebruiken. Als u aan [!DNL AMP] [!DNL AMP]en een cliënt-zijintegratie met hebt, moet u aan de server-zijintegratie migreren. Neem contact op met uw consultant of de klantenservice van de Audience Manager om de migratie te bespreken.

>[!MORELIKETHIS]
>
>* [GPT API-naslaggids](https://support.google.com/dfp_premium/bin/answer.py?hl=en&answer=1650154)

