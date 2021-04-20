---
description: Informatie over Amazon Simple Storage Service (Amazon S3).
seo-description: Informatie over Amazon Simple Storage Service (Amazon S3).
seo-title: Amazon S3 Info
solution: Audience Manager
title: Amazon S3 Info
uuid: 8197ecdf-df8f-488d-bbc0-d8d4205b42b4
feature: Reference
exl-id: 12c4f00d-2916-4224-b834-d3a9ea86314a
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '294'
ht-degree: 1%

---

# Amazon S3: Info{#amazon-s-about}

Informatie over Amazon Simple Storage Service (Amazon S3).

Als beste praktijken, adviseren wij gebruikend Amazon S3 in plaats van FTP als methode om dossiers van te krijgen en dossiers aan partners te leveren. Amazon S3 biedt een eenvoudige interface voor webservices die kan worden gebruikt om elke hoeveelheid gegevens op te slaan en op te halen, op elk gewenst moment, van op het web.

De voordelen van het gebruik van Amazon S3 zijn:

* **Schaalbaarheid:** Amazon S3 biedt vrijwel oneindige schaalbaarheid.
* **Betrouwbaarheid en beschikbaarheid:** Amazon S3 biedt opslagservices met hoge duurzaamheid en hoge beschikbaarheid.
* **Snelheid:** Amazon S3 maakt snelle gegevensoverdracht mogelijk.
* **Gebruiksgemak:** Amazon S3 is heel eenvoudig te gebruiken en te implementeren. Uw implementatie kan binnen ongeveer een uur worden uitgevoerd. Het implementeren van een FTP-map duurt veel langer.
* **Meerdere delen uploaden:** grote bestanden kunnen snel en efficiënt worden geüpload als bestanden met meerdere delen worden geüpload.
* **Beveiliging:** Amazon S3 biedt sterke beveiliging.

   * Alle mappen zijn alleen toegankelijk voor de juiste klant of client.
   * Ondersteuning voor HTTPS-protocol voor uploads en downloads. Gebruik altijd HTTPS wanneer u bestanden overbrengt in [!DNL Audience Manager].
   * Amazon S3 verstrekt encryptie-bij-rust voor het coderen [uitgaande gegevensdossiers](../integration/receiving-audience-data/batch-outbound-transfers/outbound-file-name-contents.md). Wij gebruiken de [SSE-S3](https://docs.aws.amazon.com/AmazonS3/latest/dev/serv-side-encryption.html) encryptiemethode, die encryptiesleutels toelaat automatisch worden geproduceerd en worden beheerd door Amazon S3.

* **Ondersteuning voor foutopsporing en back-up:** Amazon S3 staat toe exacte kopieën van bestanden  [!DNL Audience Manager] te behouden om foutopsporing of heroverdracht eenvoudiger te maken.

Zie de volgende bronnen voor meer informatie over Amazon S3:

[Amazon Simple Storage Service (Amazon S3) ](https://aws.amazon.com/s3/) op de website van Amazon Web Services.

[Ga aan de slag met Amazon Simple Storage ](https://docs.aws.amazon.com/AmazonS3/latest/gsg/GetStartedWithS3.html) Service op de website van de AWS-documentatie.
