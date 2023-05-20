---
description: Veelgestelde vragen over CDF-bestanden (Customer Data Feed, ofwel klantdatafeeds).
seo-description: Frequently asked questions about Customer Data Feed (CDF) files.
seo-title: Customer Data Feed FAQ
solution: Audience Manager
title: Veelgestelde vragen over klantdatafeeds
uuid: 7183b3e2-e999-4e1e-892f-2bab335c13b6
feature: Customer Data Feeds
exl-id: a948accc-6bec-4748-bcc8-2b77acf6b96a
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '447'
ht-degree: 100%

---

# Veelgestelde vragen over klantdatafeeds{#customer-data-feed-faq}

Veelgestelde vragen over CDF-bestanden (Customer Data Feed, ofwel klantdatafeeds).

## Amazon S3-opslag {#amazon-s3-storage}

**Waar wordt mijn CDF-bestand opgeslagen op [!DNL Amazon]?**

Het CDF-bestand wordt opgeslagen in de `aam-cdf`-hoofdmap op een [!DNL Amazon S3]-server. Deze standaardbucket wordt beheerd door [!DNL Audience Manager]. Zie ook [Naamgevingsconventies voor klantdatafeeds](../features/cdf-files.md#cdf-naming-conventions).

<br>

**Is mijn opslagbucket veilig?**

Ja. Klanten krijgen alleen toegang tot hun eigen opslagruimte. U hebt alleen-lezen toegang tot uw opslagbucket. U hebt geen schrijftoegang.

<br>

**Kan ik mijn opslagbucket aanpassen of bestanden in een andere map opslaan?**

Nee. Er zijn geen opties beschikbaar voor aanpassing en alternatieve opslag.

<br>

**In mijn map ontbreekt een bestand voor een bepaald uur. Waar is het?**

Een ontbrekend bestand betekent dat [!DNL Audience Manager] uw CDF-bestanden gedurende dat uur niet kon verwerken. Dit gebeurt gewoonlijk wanneer onze servers achterop raken bij de verwerking van CDF-bestanden. In dit geval gaat uw bestand niet verloren. Het zal in een map van een later uur verschijnen nadat ons systeem de achterstand heeft kunnen inhalen. Zie ook [Voortgangsmeldingen voor klantdatafeedbestanden](../features/cdf-files.md#cdf-file-processing-notifications).

<br>

**Hoe weet ik wanneer mijn CDF-bestanden gereed zijn?**

Zie [Voortgangsmeldingen voor klantdatafeedbestanden](../features/cdf-files.md#cdf-file-processing-notifications).

<br>

## Bestandsgrootten {#file-sizes}

**Wat voor soort bestandsgrootten kan ik verwachten? Hoe groot is een gemiddeld CDF-bestand?**

Het is moeilijk om de bestandsgrootte in te schatten. En elk bestand kan een andere grootte hebben. De grootten variëren van uur tot uur en van dag tot dag. Als u CDF-bestanden gaat ontvangen, kunt u het best voorbereid zijn op veel data.

<br>

**Hoeveel bestanden zal ik ontvangen?**

Nogmaals, dit is moeilijk in te schatten. Maar als u CDF-bestanden gaat ontvangen, kunt u het best voorbereid zijn op veel data.

<br>

## Data-integriteit {#data-integrity}

**Hoe kan ik de integriteit controleren van de data die naar Amazon S3 zijn geüpload?**

[!DNL Amazon] splitst grote bestanden in kleinere onderdelen en uploadt deze naar [!DNL Amazon S3] via een upload met meerdere onderdelen. Vervolgens wordt een `ETag`-waarde gegenereerd voor de upload met meerdere onderdelen. Eerst worden de afzonderlijke MD5-controlesommen van elk geüpload onderdeel berekend, en vervolgens worden ze in één tekenreeks samengevoegd. Daarna wordt de MD5-controlesom van de tekenreeks berekend. Aan de resulterende controlesom (de `ETag`) worden vervolgens met een afbreekstreepje het totale aantal onderdelen toegevoegd dat voor de upload is gebruikt. De `ETag` voor een bestand dat tijdens het uploaden in vijf delen is gesplitst, ziet er bijvoorbeeld ongeveer zo uit: `2c51427d19021e88cf3395365895b6d4-5`

<br> 

## Dataretentie {#data-retension}

**Hoe lang slaat u CDF-bestanden op?**

Data worden na 8 (acht) dagen verwijderd.

<br>

**Kan ik CDF-bestanden retroactief ophalen, of voor voorgaande dagen?**

U kunt alleen CDF-bestanden genereren voor de afgelopen acht dagen. CDF-bestanden voor intervallen ouder dan de afgelopen acht dagen kunnen niet opnieuw worden gegenereerd.

>[!MORELIKETHIS]
>
>* [Klantdatafeeds](../features/cdf-files.md)

