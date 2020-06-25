---
description: Informatie over Amazon Simple Storage Service (Amazon S3).
seo-description: Informatie over Amazon Simple Storage Service (Amazon S3).
seo-title: Amazon S3 Info
solution: Audience Manager
title: Amazon S3 Info
uuid: 8197ecdf-df8f-488d-bbc0-d8d4205b42b4
feature: reference
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '293'
ht-degree: 0%

---


# Amazon S3: About{#amazon-s-about}

Informatie over Amazon Simple Storage Service (Amazon S3).

Als beste praktijken, adviseren wij gebruikend Amazon S3 in plaats van FTP als methode om dossiers van te krijgen en dossiers aan partners te leveren. Amazon S3 biedt een eenvoudige interface voor webservices die kan worden gebruikt om elke hoeveelheid gegevens op te slaan en op te halen, op elk gewenst moment, van op het web.

De voordelen van het gebruik van Amazon S3 zijn:

* **Schaalbaarheid:** Amazon S3 biedt bijna oneindige schaalbaarheid.
* **Betrouwbaarheid en beschikbaarheid:** Amazon S3 biedt opslagservices met hoge duurzaamheid en hoge beschikbaarheid.
* **Snelheid:** Amazon S3 maakt snelle gegevensoverdracht mogelijk.
* **Gebruiksgemak:** Amazon S3 is erg gebruiksvriendelijk en te implementeren. Uw implementatie kan binnen ongeveer een uur worden uitgevoerd. Het implementeren van een FTP-map duurt veel langer.
* **Meerdere deeluploads:** Grote bestanden kunnen snel en efficiënt worden geüpload wanneer bestanden met meerdere onderdelen worden geüpload.
* **Beveiliging:** Amazon S3 biedt sterke veiligheid.

   * Alle mappen zijn alleen toegankelijk voor de juiste klant of client.
   * Ondersteuning voor HTTPS-protocol voor uploads en downloads. Gebruik altijd HTTPS wanneer u bestanden overbrengt in [!DNL Audience Manager].
   * Amazon S3 biedt codering-bij-rust voor het coderen van [uitgaande gegevensbestanden](../integration/receiving-audience-data/batch-outbound-transfers/outbound-file-name-contents.md). Wij gebruiken de [encryptiemethode SSE-S3](https://docs.aws.amazon.com/AmazonS3/latest/dev/serv-side-encryption.html) , die encryptiesleutels toelaat automatisch worden geproduceerd en worden beheerd door Amazon S3.

* **Ondersteuning voor foutopsporing en back-up:** Met Amazon S3 kunt u exacte kopieën van bestanden behouden, zodat u gemakkelijker fouten kunt opsporen of opnieuw bestanden kunt overdragen. [!DNL Audience Manager]

Zie de volgende bronnen voor meer informatie over Amazon S3:

[Amazon Simple Storage Service (Amazon S3)](https://aws.amazon.com/s3/) op de website van Amazon Web Services.

[Ga aan de slag met de eenvoudige opslagservice](https://docs.aws.amazon.com/AmazonS3/latest/gsg/GetStartedWithS3.html) van Amazon op de AWS-documentatiewebsite.
