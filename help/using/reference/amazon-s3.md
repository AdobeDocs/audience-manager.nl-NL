---
description: Informatie over Amazon Simple Storage Service (Amazon S3).
seo-description: Information about Amazon Simple Storage Service (Amazon S3).
seo-title: Amazon S3  About
solution: Audience Manager
title: Amazon S3 Info
uuid: 8197ecdf-df8f-488d-bbc0-d8d4205b42b4
feature: Reference
exl-id: 12c4f00d-2916-4224-b834-d3a9ea86314a
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '269'
ht-degree: 0%

---

# Amazon S3: Informatie over{#amazon-s-about}

Informatie over Amazon Simple Storage Service (Amazon S3).

Als beste praktijken, adviseren wij gebruikend Amazon S3 in plaats van FTP als methode om dossiers van te krijgen en dossiers aan partners te leveren. Amazon S3 biedt een eenvoudige interface voor webservices die kan worden gebruikt om elke hoeveelheid gegevens op te slaan en op te halen, op elk gewenst moment, vanaf elke locatie op het web.

De voordelen van het gebruik van Amazon S3 zijn:

* **Schaalbaarheid:** Amazon S3 verstrekt bijna grenzeloze scalability.
* **Betrouwbaarheid en Beschikbaarheid:** Amazon S3 verleent de hoge duurzaamheid en de hoge beschikbaarheidsopslagdiensten.
* **Snelheid:** Amazon S3 staat snelle gegevensoverdrachten toe.
* **Gemak van Gebruik:** Amazon S3 is zeer gemakkelijk te gebruiken en uit te voeren. Uw implementatie kan binnen ongeveer een uur worden uitgevoerd. Het implementeren van een FTP-map duurt veel langer.
* **Van meerdere delen uploadt:** de grote dossiers kunnen snel en efficiënt als multi-deel dossier worden geupload uploadt.
* **Veiligheid:** Amazon S3 verstrekt sterke veiligheid.

   * Alle mappen zijn alleen toegankelijk voor de juiste klant of client.
   * Ondersteuning voor HTTPS-protocol voor uploads en downloads. Gebruik altijd HTTPS wanneer u bestanden overbrengt in [!DNL Audience Manager] .
   * Amazon S3 verstrekt encryptie-bij-rust voor het coderen van [ uitgaande gegevensdossiers ](../integration/receiving-audience-data/batch-outbound-transfers/outbound-file-name-contents.md). Wij gebruiken de [ SSE-S3 ](https://docs.aws.amazon.com/AmazonS3/latest/dev/serv-side-encryption.html) encryptiemethode, die encryptiesleutels toelaat om automatisch door Amazon S3 worden geproduceerd en worden beheerd.

* **zuivert en Steun:** Amazon S3 staat [!DNL Audience Manager] toe om nauwkeurige exemplaren van dossiers te behouden om het zuiveren of re-overdrachten gemakkelijker te maken.

Zie de volgende bronnen voor meer informatie over Amazon S3:

[ de Eenvoudige Dienst van de Opslag van Amazon (Amazon S3) ](https://aws.amazon.com/s3/) op de website van Amazon Web Services.

[ krijgt Begonnen met de Eenvoudige Dienst van de Opslag van Amazon ](https://docs.aws.amazon.com/AmazonS3/latest/gsg/GetStartedWithS3.html) op de website van de Documentatie van AWS.
