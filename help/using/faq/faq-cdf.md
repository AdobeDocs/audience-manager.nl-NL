---
description: Veelgestelde vragen over CDF-bestanden (Customer Data Feed).
seo-description: Veelgestelde vragen over CDF-bestanden (Customer Data Feed).
seo-title: Veelgestelde vragen over de gegevensfeed van de klant
solution: Audience Manager
title: Veelgestelde vragen over de gegevensfeed van de klant
uuid: 7183b3e2-e999-4e1e-892f-2bab335c13b6
translation-type: tm+mt
source-git-commit: 7018705c130bf7c65f3a69da5e4bd9e0666423bc

---


# Veelgestelde vragen over de gegevensfeed van de klant{#customer-data-feed-faq}

Veelgestelde vragen over CDF-bestanden (Customer Data Feed).

## Amazon S3-opslag {#amazon-s3-storage}

**Waar wordt mijn CDF-bestand opgeslagen op[!DNL Amazon]?**

Het CDF-bestand wordt opgeslagen in de `aam-cdf` hoofdmap op een [!DNL Amazon S3] server. Dit standaardemmertje wordt beheerd door [!DNL Audience Manager]. Zie ook conventies voor naamgeving van bestanden van [klantgegevens](../features/cdf-files.md#cdf-naming-conventions).

<br> 

**Is mijn opslagemmer veilig?**

Ja. Klanten krijgen alleen toegang tot hun eigen opslagruimte. U hebt alleen-lezen toegang tot uw opslagemmertje. U hebt geen schrijftoegang.

<br> 

**Kan ik mijn opslagemmertje aanpassen of dossiers in een andere folder opslaan?**

Nee. Aanpassings- en alternatieve opslagopties zijn niet beschikbaar.

<br> 

**Mijn map ontbreekt een bestand voor een bepaald uur. Waar is het?**

Een ontbrekend bestand betekent dat [!DNL Audience Manager] uw CDF-bestanden gedurende dat uur niet kunnen worden verwerkt. Dit gebeurt gewoonlijk wanneer onze servers achterop raken bij het verwerken van CDF-bestanden. In dit geval gaat uw bestand niet verloren. Het zal in een recentere uurfolder verschijnen nadat ons systeem een kans heeft om op te halen. Zie ook [Klantengegevens — meldingen](../features/cdf-files.md#cdf-file-processing-notifications)voor bestandsverwerking.

<br> 

**Hoe weet ik wanneer mijn CDF-bestanden gereed zijn?**

Zie Meldingen over bestandsverwerking door [klantgegevens](../features/cdf-files.md#cdf-file-processing-notifications).

<br> 

## Bestandsgrootten {#file-sizes}

**Wat voor soort bestandsgrootten moet ik verwachten? Hoe groot is een gemiddeld CDF-bestand?**

Het is moeilijk om de bestandsgrootte in te schatten. En elk bestand kan een andere grootte hebben. De grootten variëren van uur tot uur en dag tot dag. Als u CDF-bestanden ontvangt, kunt u beter een hoop gegevens beheren.

<br> 

**Hoeveel bestanden zal ik ontvangen?**

Nogmaals, het is moeilijk om dit in te schatten. Nochtans, als u CDF dossiers zult ontvangen helpt het om worden voorbereid om veel gegevens te beheren.

<br> 

## Gegevensintegriteit {#data-integrity}

**Hoe kan ik de integriteit controleren van de gegevens die naar Amazon S3 zijn geüpload?**

[!DNL Amazon] Hiermee splitst u grote bestanden in kleinere delen en uploadt u deze naar [!DNL Amazon S3] het uploaden van meerdere onderdelen. Vervolgens wordt een `ETag` waarde gegenereerd voor het uploaden van meerdere onderdelen. Eerst worden de afzonderlijke MD5-controlesommen van elk geüpload onderdeel berekend en vervolgens in één tekenreeks samengevoegd. Vervolgens wordt de MD5-controlesom van de tekenreeks berekend. De resulterende controlesom (de `ETag`) wordt vervolgens toegevoegd met een afbreekstreepje en het totale aantal onderdelen dat voor het uploaden wordt gebruikt. De `ETag` voor een bestand dat tijdens het uploaden in vijf delen is gesplitst, ziet er bijvoorbeeld ongeveer als volgt uit: `2c51427d19021e88cf3395365895b6d4-5`

<br> 

## Gegevens bewaren {#data-retension}

**Hoe lang slaat u CDF-bestanden op?**

Gegevens worden na 8 (8) dagen verwijderd.

<br> 

**Kan ik CDF-bestanden terugdraaien of voor vorige dagen?**

U kunt CDF-bestanden alleen gedurende de laatste 8 dagen genereren. CDF-bestanden voor intervallen ouder dan de afgelopen 8 dagen kunnen niet opnieuw worden gegenereerd.

>[!MORELIKETHIS]
>
>* [Gegevensinvoer van klant](../features/cdf-files.md)

