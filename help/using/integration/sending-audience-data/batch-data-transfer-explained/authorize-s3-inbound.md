---
description: Om gegevens van uw eigen Amazon S3 emmertje naar Audience Manager te verzenden, moet u eerst om de configuratie van een specifieke rol van Amazon S3 verzoeken.
solution: Audience Manager
title: Gebruik Amazon S3-machtigingen voor emmertjes voor andere accounts voor binnenkomende bestanden
feature: Inbound Data Transfers
source-git-commit: ff023fb57e2653ca65323313a37852d379e4b00c
workflow-type: tm+mt
source-wordcount: '196'
ht-degree: 0%

---


# Gebruik Amazon S3-machtigingen voor emmertjes voor andere accounts voor binnenkomende bestanden {#leverage-amazon-s-cross-account-bucket-permissions-for-your-inbound-files}

Om gegevens van uw eigen Amazon S3 emmertje naar Audience Manager te verzenden, moet u eerst om de configuratie van een specifieke rol van Amazon S3 verzoeken.

Volg de onderstaande stappen om dit te doen.

1. Neem contact op met de klantenservice en vraag een andere methode om bestanden naar de Audience Manager te verzenden.
2. De klantenondersteuning bieden met de [!DNL Amazon Resource Name (ARN)] voor een rol in uw Amazon S3-account die u gebruikt om bestanden te verzenden. _Deze rol moet worden aangemaakt voordat u contact opneemt met de klantenservice_. Nadat de configuratie is voltooid, zal de klantenservice u de [!DNL Amazon Resource Name (ARN)] voor de nieuwe rol.
3. Bewerk de machtigingen van uw bestaande Amazon S3-rol om de rol op zich te nemen die de klantenservice biedt.

>[!NOTE]
>
>Wanneer het overbrengen van binnenkomende gegevens naar de Audience Manager Amazon S3 emmertje, zorg ervoor om te gebruiken `bucket-owner-full-control` [toegangsbeheerlijst](https://docs.aws.amazon.com/AmazonS3/latest/userguide/about-object-ownership.html) om Audience Manger de gegevens correct te verwerken.
><br>
>Voorbeeld voor de opdracht Amazon Web Services: `aws s3 cp <user_s3_uri> <AAM_s3_uri> --acl bucket-owner-full-control`.

