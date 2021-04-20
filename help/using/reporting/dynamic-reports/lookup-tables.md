---
description: Plaats gegevens in het rapport van de Prestaties van de Levering logboekdossiers in lijsten die slechts IDs bevatten. Plaats niet-id-metagegevens in aparte opzoektabellen om de bestandsgrootte en de verwerkingstijd te beperken.
seo-description: Plaats gegevens in het rapport van de Prestaties van de Levering logboekdossiers in lijsten die slechts IDs bevatten. Plaats niet-id-metagegevens in aparte opzoektabellen om de bestandsgrootte en de verwerkingstijd te beperken.
seo-title: Verwerkingstijd logboekbestanden verbeteren met opzoektabellen
solution: Audience Manager
title: Verwerkingstijd logboekbestanden verbeteren met opzoektabellen
uuid: ffc77618-474b-455e-9c91-15b32fc151a5
feature: Reporting Reference
exl-id: bab51406-21e9-4033-90d4-6100daf6a311
translation-type: tm+mt
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '503'
ht-degree: 13%

---

# Verwerkingstijd logboekbestanden verbeteren met opzoektabellen{#improve-log-file-processing-times-with-lookup-tables}

Plaats gegevens in het rapport van de Prestaties van de Levering logboekdossiers in lijsten die slechts IDs bevatten. Plaats niet-id-metagegevens in aparte opzoektabellen om de bestandsgrootte en de verwerkingstijd te beperken.

<!-- 

c_lookup_tables.xml

 -->

## Metagegevens logbestand vergroten bestandsgrootte en verwerkingstijd

Een logbestand dat gewoonlijk door het rapport [!UICONTROL Delivery Performance] wordt gebruikt, bevat doorgaans duizenden rijen en tientallen kolommen. Het bestaat uit numerieke id&#39;s en door mensen leesbare informatie, zoals namen voor creatieve personen, adverteerders, invoegorders, enz.

Deze niet-ID-informatie wordt *`metadata`* (d.w.z. informatie over andere informatie) genoemd en wordt in elke rij van het logbestand geschreven.

Het [!UICONTROL Delivery Performance]-rapport werkt echter vooral met de id&#39;s in het logbestand. De metagegevens zijn nuttig, maar herhaaldelijk. Hierdoor neemt de bestandsgrootte en de tijd die nodig is om gegevens in te voeren toe.

## Bestandsgrootte reduceren en verwerkingstijd verkorten met indextabellen

Om de prestaties te verbeteren, mag het hoofdgegevensbestand alleen id&#39;s bevatten. Plaats meta-gegevens in een afzonderlijke raadpleging (of index) lijst en verbind die verslagen met het belangrijkste dossier met een zeer belangrijke variabele gemeenschappelijk voor allebei.

## Hoe tabellen opzoeken de bestandsgrootte reduceren

Stel dat u een gegevensbestand hebt dat er ongeveer zo uitziet als hieronder.

| Gebruikers-id | ID advertentie | Advertentienaam | Order-id | Naam van bestelling | Adverteerder-id | Naam adverteerder |
|---|---|---|---|---|---|---|
| 1 | 111 | Shoe A | 456 | Sneakers | 27 | Onderneming A |
| 2 | 111 | Shoe A | 456 | Sneakers | 27 | Onderneming A |
| 3 | 111 | Shoe A | 456 | Sneakers | 27 | Onderneming A |
| 4 | 222 | Schoefschoen B | 789 | Hiking | 14 | Onderneming B |
| 5 | 222 | Schoefschoen B | 789 | Hiking | 14 | Onderneming B |

<br>

Hier is hetzelfde logbestand met de verwijderde metagegevens. Het bestand is kleiner en gemakkelijker te verwerken wanneer het alleen uit id&#39;s bestaat.

| Gebruikers-id | ID advertentie | Order-id | Adverteerder-id |
|---|---|---|---|
| 3 | 111 | 456 | 27 |
| 2 | 111 | 456 | 27 |
| 1 | 111 | 456 | 27 |
| 4 | 222 | 789 | 14 |
| 5 | 222 | 789 | 14 |

<br> 

Het opzoekbestand hieronder bevat de metagegevens en kan met de advertentie-id worden gekoppeld aan het hoofdbestand. Let ook op de grootte. In plaats van elke adverteerder meerdere keren te herhalen, hebt u slechts één referentie voor elke advertentie nodig.

| ID advertentie | Advertentienaam | Naam van bestelling | Naam adverteerder |
|---|---|---|---|
| 111 | Shoe A | Sneakers | Onderneming A |
| 222 | Schoefschoen B | Hiking | Onderneming B |

## API&#39;s kunnen de behoefte aan opzoektabellen wegnemen

Als uw ad-serving-systeem een API heeft, hoeft u mogelijk geen metagegevens in een opzoekbestand te verzenden. We kunnen die informatie mogelijk ophalen via de API. In dat geval mogen uw logbestanden alleen id&#39;s bevatten. We werken met u samen om te bepalen of metagegevens kunnen worden verkregen via een API.
