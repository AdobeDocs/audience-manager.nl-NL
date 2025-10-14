---
description: Om gegevens van uw eigen Amazon S3 emmertje naar Audience Manager te verzenden, moet u eerst om de configuratie van een specifieke rol van Amazon S3 verzoeken.
solution: Audience Manager
title: Gebruik Amazon S3-machtigingen voor emmertjes voor andere accounts voor binnenkomende bestanden
feature: Inbound Data Transfers
exl-id: 56ecea5a-0621-4720-9e4c-f9086294c31f
source-git-commit: 65963c462f2a5abb1e2597b3d943628baa9d4730
workflow-type: tm+mt
source-wordcount: '191'
ht-degree: 0%

---

# Gebruik Amazon S3-machtigingen voor emmertjes voor andere accounts voor binnenkomende bestanden {#leverage-amazon-s-cross-account-bucket-permissions-for-your-inbound-files}

Om gegevens van uw eigen Amazon S3 emmertje naar Audience Manager te verzenden, moet u eerst om de configuratie van een specifieke rol van Amazon S3 verzoeken.

Volg de onderstaande stappen om dit te doen.

1. Neem contact op met de klantenservice en vraag een andere methode om bestanden naar Audience Manager te verzenden.
2. Zorg voor de klantenservice met de [!DNL Amazon Resource Name (ARN)] voor een rol in uw Amazon S3-account die u gebruikt om bestanden te verzenden. _Deze rol moet worden gecreeerd alvorens u de Zorg van de Klant_ contacteert. Nadat de configuratie is voltooid, biedt de klantenservice u de [!DNL Amazon Resource Name (ARN)] voor de nieuwe rol.
3. Bewerk de machtigingen van uw bestaande Amazon S3-rol om de rol op zich te nemen die de klantenservice biedt.

>[!NOTE]
>
>Wanneer het overbrengen van binnenkomende gegevens naar het Audience Manager Amazon S3 emmertje, zorg ervoor om de `bucket-owner-full-control` [&#x200B; toegangsbeheerlijst &#x200B;](https://docs.aws.amazon.com/AmazonS3/latest/userguide/about-object-ownership.html) te gebruiken opdat de Manager van het Publiek de gegevens correct verwerkt.
>
>Voorbeeld voor de Amazon Web Services-opdracht: `aws s3 cp <user_s3_uri> <AAM_s3_uri> --acl bucket-owner-full-control`
