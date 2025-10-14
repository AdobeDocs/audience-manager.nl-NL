---
description: Stel een Google-groep in om uw Google Campagne Manager-gegevensbestanden naar Audience Manager te brengen. De inhoud in deze sectie geeft een overzicht van het integratieproces en bevat koppelingen naar Google Campaign Manager-bronnen om u te helpen aan de slag te gaan.
seo-description: Set up a Google group to bring your Google Campaign Manager data files into Audience Manager. The content in this section summarizes the integration process and provides you with links to Google Campaign Manager resources to help you get started.
seo-title: Import Google Campaign Manager Data Files Into Audience Manager
solution: Audience Manager
title: Google Campagne Manager-gegevensbestanden importeren in Audience Manager
uuid: 3578cfe1-6d30-4a73-ab75-8d272bebcd60
feature: Audience Optimization Reports
exl-id: 045eed94-100f-460d-83bb-78fbd7beb51c
source-git-commit: 95b7b4347f3da16be05be60cbefc0e236022a4a7
workflow-type: tm+mt
source-wordcount: '556'
ht-degree: 3%

---

# Google Campagne Manager-gegevensbestanden importeren in Audience Manager {#import-dcm-data-files-into-audience-manager}

Stel een [!DNL Google] -groep in om uw [!DNL Google Campaign Manager] -gegevensbestanden over te brengen naar Audience Manager. De inhoud in deze sectie geeft een overzicht van het integratieproces en bevat koppelingen naar [!DNL Google Campaign Manager] -bronnen om u te helpen aan de slag te gaan.

## Overzicht van integratie

[!DNL Google Campaign Manager] is [!DNL Google] ter vervanging van [!DNL DoubleClick for Advertisers] (DFA). Net als DFA kunnen [!DNL Google Campaign Manager] -klanten hun gegevens importeren, weergeven en ermee werken in [!DNL Audience Manager] . [!DNL Audience Manager] kan echter niet rechtstreeks uw [!UICONTROL Data Transfer]- en [!UICONTROL Match Table]-bestanden openen en importeren. Het importeren van deze bestanden is een taak voor de klant.

Nochtans, is de opstellingsprocedure goed gedocumenteerd in de [&#x200B; Hulp van de Manager van de Campagne DoubleClick &#x200B;](https://support.google.com/dcm/partner/answer/2941575?hl=en&ref_topic=6107456). U kunt ook de onderstaande stappen doornemen om aan de slag te gaan.

>[!CAUTION]
>
>[!DNL Google Campaign Manager] -gegevensbestanden bevatten gegevens voor al uw adverteerders of klanten. Als u specifieke clients moet weglaten, moet u de bestanden bewerken voordat u ze beschikbaar maakt voor [!DNL Audience Manager] .

## Frequentie en beschikbaarheid van gegevensoverdracht

[!DNL Audience Manager] controleert elke dag op gegevens en brengt deze over. De gegevens zijn doorgaans na 24 uur beschikbaar in [!DNL Audience Manager] .

## Stappen

1. [&#x200B; creeer een groep &#x200B;](https://support.google.com/dcm/partner/answer/3370419?hl=en&ref_topic=6107456).

   Groepen bepalen de toegang tot uw [!DNL Google Campaign Manager] -gegevens. Uiteindelijk gaat u [!DNL Audience Manager] uitnodigen en toevoegen aan deze groep.

1. [&#x200B; verifieer uw status van de Opslag van de Wolk van Google &#x200B;](https://support.google.com/dcm/partner/answer/3370481?hl=en&ref_topic=6107456).

   Google Cloud Storage bevat het gegevensemmertje dat uw [!UICONTROL Data Transfer] en [!UICONTROL Match Tables] bevat. U zult een emmertje moeten opstelling of ervoor zorgen uw nieuwe groep toegang tot een bestaand emmertje van de gegevensopslag heeft.

1. [&#x200B; krijgt een gegevensbestand URL &#x200B;](https://support.google.com/dcm/partner/answer/3370482?hl=en&ref_topic=6107456).

   Werk met uw [!DNL Google Campaign Manager] accountmanager of consultant voor platformoplossingen. Ze geven u een URL naar uw gegevensbestanden. [!DNL Google] kan in toekomstige versies de indeling voor bucket- en bestandsnamen wijzigen. Werk opnieuw met uw accountmanager van [!DNL Google Campaign Manager] om ervoor te zorgen dat u de juiste indelingen gebruikt.

1. [&#x200B; vastgestelde emmer toestemmingen &#x200B;](https://cloud.google.com/storage/docs/cloud-console?csw=1#_bucketpermission).

   Met [!DNL Cloud Storage Manager] kunt u gegevens delen en emmer-toegang beheren. Geef uw groep leestoegang tot de emmertje die uw [!UICONTROL Data Transfer] en [!UICONTROL Match Table] dossiers bevat.

1. [&#x200B; de opstellings gegevens die &#x200B;](https://support.google.com/dcm/partner/answer/6206106?hl=en) delen.

   Gedeelde [!DNL Google Campaign Manager] gebruikers-id&#39;s zijn gecodeerd om de privacy te beschermen. Met Versleuteling voegt u twee kolommen toe aan het einde van het gegevensoverdrachtbestand, `PartnerId1` en `PartnerId2` . Deze kolommen bevatten gecodeerde gebruikers-id&#39;s die specifiek zijn voor elk bedrijf dat deze bestanden ontvangt.

   Als geautoriseerde derde kan [!DNL Audience Manager] [!DNL Google Campaign Manager] -gegevens ontvangen, maar de id&#39;s kunnen niet worden gedecodeerd. Aan de zijde van [!DNL Audience Manager] weten we echter hoe de gecodeerde id&#39;s overeenkomen met onze id&#39;s. Dit betekent dat we gebruikers met vertrouwen en nauwkeurigheid kunnen afstemmen en synchroniseren.

   >[!NOTE]
   >U kunt [!DNL Google Campaign Manager] -bestanden niet importeren in [!DNL Audience Manager] als u al gegevens deelt met twee andere partners van derden.

1. Nodig [!DNL Audience Manager] uit om deel te nemen aan de groep.

   Nadat u een groep hebt gemaakt en deze toegang hebt tot een gegevensemmertje, nodigt u [!DNL Audience Manager] uit om lid te worden van de groep. Verzend een uitnodigings-e-mail naar dfaaam@adobe.com. Zorg ervoor dat u de URL van het gegevensbestand uit stap 3 opneemt. Onze interne teams zullen met u samenwerken om toegang te verifiëren nadat het goedkeuren van de uitnodiging. 1. Stel twee gegevensbronnen in voor [!DNL Google Campaign Manager] -gegevens in de [!DNL Audience Manager] -gebruikersinterface.

   Geef de gegevensbronnen een naam `Advertiser Analytics: DCM Platform` en `Advertiser Analytics: AAM+DCM Platform` . In [&#x200B; creeer Gegevensbronnen &#x200B;](../../../features/manage-datasources.md#create-data-source) werkschema, plaats het type van identiteitskaart aan `Cookie`. Deel de id&#39;s van de twee nieuwe gegevensbronnen met onze interne teams.

1. U kunt eenvoudig kenmerken maken van de [!DNL Google Campaign Manager] -bestanden die u in [!DNL Audience Manager] importeert. Zie [&#x200B; Acteerbare Dossiers van het Logboek &#x200B;](../../../integration/media-data-integration/actionable-log-files.md) en vraag uw [!DNL Audience Manager] consultant of de Zorg van de Klant om de eigenschap voor u toe te laten.
