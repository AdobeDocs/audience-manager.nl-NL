---
description: Het uitgaande proces van de Overdracht van Gegevens voor klanten die de Eenvoudige Dienst van de Opslag van Amazon (Amazon S3) gebruiken vereist ons om uw Amazon S3 toegangssleutel en geheime sleutel te vragen, om de uitgaande gegevensdossiers aan uw emmer te leveren.
seo-description: The Outbound Data Transfer process for customers using Amazon Simple Storage Service (Amazon S3) requires us to ask for your Amazon S3 access key and secret key, in order to deliver the outbound data files to your bucket.
seo-title: Leverage Amazon S3 Cross-Account Bucket Permissions for Your Outbound Files
solution: Audience Manager
title: Gebruik Amazon S3-machtigingen voor emmertjes voor andere accounts voor uitgaande bestanden
uuid: 400a8d67-ebf3-48be-aa3f-498a5441f498
feature: Outbound Data Transfers
exl-id: e52f5bc0-7dc0-4c73-833c-5a778e8b5891
source-git-commit: 9c0254e8a29ffeb0353ed6faa898b74bcae7cef1
workflow-type: tm+mt
source-wordcount: '186'
ht-degree: 0%

---

# Gebruik Amazon S3-machtigingen voor emmertjes voor andere accounts voor uitgaande bestanden {#leverage-amazon-s-cross-account-bucket-permissions-for-your-outbound-files}

Het [!UICONTROL Outbound Data Transfer] -proces voor klanten die [!DNL Amazon Simple Storage Service] ([!DNL Amazon S3]) gebruiken, vereist dat wij om uw [!DNL Amazon S3] toegangstoets en geheime sleutel vragen, om de uitgaande gegevensbestanden aan uw emmer te leveren.

Als u uw [!DNL Amazon S3] toegangstoets en geheime sleutel liever niet met ons deelt, neemt u contact op met uw [!DNL Audience Manager] consultant of de klantenservice en stelt u [!DNL Cross-Account Bucket Permissions] voor u in.

U moet slechts onze [!DNL Amazon S3] rekeningsidentiteitskaart aan een lijst van gewenste personen voor het [!DNL S3] emmertje toevoegen waar u wenst om de uitgaande gegevensdossiers te ontvangen, zoals die in de [&#x200B; S3 documentatie van Amazon &#x200B;](https://docs.aws.amazon.com/AmazonS3/latest/dev/example-walkthroughs-managing-access-example2.html) worden beschreven. Uw [!DNL Audience Manager] consultant of klantenservice zal u onze [!DNL Amazon S3] account-id verstrekken.

>[!NOTE]
>
>Vanwege de Amazon S3-limiet voor objectgrootte ondersteunt Audience Manager splitsingsgrootten van maximaal 1 TB. Als u geen gesplitste grootte opgeeft, wordt de limiet van 1 TB automatisch toegepast.

