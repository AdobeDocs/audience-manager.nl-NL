---
description: Stel een Google-groep in om uw Google Campagne Manager-gegevensbestanden in de Audience Manager te plaatsen. De inhoud in deze sectie geeft een overzicht van het integratieproces en bevat koppelingen naar Google Campagne Manager-bronnen om u te helpen aan de slag te gaan.
seo-description: Stel een Google-groep in om uw Google Campagne Manager-gegevensbestanden in de Audience Manager te plaatsen. De inhoud in deze sectie geeft een overzicht van het integratieproces en bevat koppelingen naar Google Campagne Manager-bronnen om u te helpen aan de slag te gaan.
seo-title: Google Campagne Manager-gegevensbestanden importeren in Audience Manager
solution: Audience Manager
title: Google Campagne Manager-gegevensbestanden importeren in Audience Manager
uuid: 3578cfe1-6d30-4a73-ab75-8d272bebcd60
feature: Audience Optimization Reports
exl-id: 045eed94-100f-460d-83bb-78fbd7beb51c
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '648'
ht-degree: 4%

---

# Google Campagne Manager-gegevensbestanden importeren in Audience Manager {#import-dcm-data-files-into-audience-manager}

Stel een [!DNL Google]-groep in om uw [!DNL Google Campaign Manager]-gegevensbestanden in de Audience Manager te plaatsen. De inhoud in deze sectie vat het integratieproces samen en voorziet u van verbindingen aan [!DNL Google Campaign Manager] middelen om u te helpen begonnen worden.

## Overzicht van integratie

[!DNL Google Campaign Manager] is de vervanging van [!DNL Google] voor [!DNL DoubleClick for Advertisers] (DFA). Net als DFA kunnen klanten [!DNL Google Campaign Manager] hun gegevens importeren, weergeven en ermee werken in [!DNL Audience Manager]. [!DNL Audience Manager] kan echter niet rechtstreeks uw [!UICONTROL Data Transfer]- en [!UICONTROL Match Table]-bestanden openen en importeren. Het importeren van deze bestanden is een taak voor de klant.

Nochtans, is de opstellingsprocedure goed gedocumenteerd in [Dubbelklik de Manager van de Campagne Help](https://support.google.com/dcm/partner/answer/2941575?hl=en&amp;ref_topic=6107456). U kunt ook de onderstaande stappen doornemen om aan de slag te gaan.

>[!CAUTION]
>
>[!DNL Google Campaign Manager] gegevensbestanden bevatten gegevens voor al uw adverteerders of klanten. Als u specifieke clients moet weglaten, moet u de bestanden bewerken voordat u ze beschikbaar maakt voor [!DNL Audience Manager].

## Frequentie en beschikbaarheid van gegevensoverdracht

[!DNL Audience Manager] controleert elke dag op gegevens en draagt deze over. De gegevens zijn gewoonlijk beschikbaar in [!DNL Audience Manager] na 24 uur.

## Stappen

1. [Maak een groep](https://support.google.com/dcm/partner/answer/3370419?hl=en&amp;ref_topic=6107456).

   Groepen beheren de toegang tot uw [!DNL Google Campaign Manager] gegevens. Uiteindelijk, zult u [!DNL Audience Manager] aan deze groep uitnodigen en toevoegen.

1. [Controleer uw Google Cloud Storage-status](https://support.google.com/dcm/partner/answer/3370481?hl=en&amp;ref_topic=6107456).

   Google Cloud Storage bevat het gegevensemmertje dat uw [!UICONTROL Data Transfer] en [!UICONTROL Match Tables] bevat. U zult een emmertje moeten opstelling of ervoor zorgen uw nieuwe groep toegang tot een bestaand emmertje van de gegevensopslag heeft.

1. [Hiermee wordt de URL](https://support.google.com/dcm/partner/answer/3370482?hl=en&amp;ref_topic=6107456) van een gegevensbestand opgehaald.

   Werk met uw [!DNL Google Campaign Manager] Accountmanager of consultant voor oplossingen van Platforms. Ze geven u een URL naar uw gegevensbestanden. [!DNL Google] In toekomstige versies kan de indeling voor bucket- en bestandsnamen veranderen. Werk opnieuw met uw [!DNL Google Campaign Manager] Accountmanager om ervoor te zorgen dat u de juiste indelingen gebruikt.

1. [Machtigingen](https://cloud.google.com/storage/docs/cloud-console?csw=1#_bucketpermission) voor emmertje instellen.

   Met [!DNL Cloud Storage Manager] kunt u gegevens delen en emmer-toegang beheren. Geef uw groep leestoegang tot de emmer die uw [!UICONTROL Data Transfer] en [!UICONTROL Match Table] dossiers bevat.

1. [Gegevens delen](https://support.google.com/dcm/partner/answer/6206106?hl=en) instellen.

   Gedeelde [!DNL Google Campaign Manager] gebruikers-id&#39;s zijn gecodeerd om de privacy te beschermen. De encryptie voegt 2 kolommen aan het eind van uw dossier van de Overdracht van Gegevens toe, `PartnerId1` en `PartnerId2`. Deze kolommen bevatten gecodeerde gebruikers-id&#39;s die specifiek zijn voor elk bedrijf dat deze bestanden ontvangt.

   Als geautoriseerde derde kan [!DNL Audience Manager] [!DNL Google Campaign Manager] gegevens ontvangen, maar de id&#39;s kunnen niet worden gedecodeerd. Aan de zijde [!DNL Audience Manager] weten we echter hoe de gecodeerde id&#39;s overeenkomen met onze id&#39;s. Dit betekent dat we gebruikers met vertrouwen en nauwkeurigheid kunnen afstemmen en synchroniseren.

   >[!NOTE]
   >U kunt geen [!DNL Google Campaign Manager] dossiers in [!DNL Audience Manager] invoeren als u reeds gegevens met 2 andere derdepartners deelt.

1. [!DNL Audience Manager] uitnodigen om deel te nemen aan de groep.

   Nadat u een groep creeert en het toegang tot een gegevensemmer geeft, nodig [!DNL Audience Manager] om zich bij de groep aan te sluiten. Verzend een uitnodigings-e-mail naar DFA-AAM@adobe.com. Zorg ervoor dat u de URL van het gegevensbestand uit stap 3 opneemt. Onze interne teams zullen met u samenwerken om toegang te verifiëren nadat het goedkeuren van de uitnodiging. 1. Stel twee gegevensbronnen in voor [!DNL Google Campaign Manager]-gegevens in de gebruikersinterface [!DNL Audience Manager].

   Geef de gegevensbronnen `Advertiser Analytics: DCM Platform` en `Advertiser Analytics: AAM+DCM Platform` een naam. Stel in de [Gegevensbronnen maken](../../../features/manage-datasources.md#create-data-source)-workflow het id-type in op `Cookie`. Deel de id&#39;s van de twee nieuwe gegevensbronnen met onze interne teams.

1. U kunt gemakkelijk eigenschappen van de [!DNL Google Campaign Manager] dossiers tot stand brengen u in [!DNL Audience Manager] invoert. Zie [Handbare logbestanden](../../../integration/media-data-integration/actionable-log-files.md) en vraag uw [!DNL Audience Manager] consultant of de klantenservice om de functie voor u in te schakelen.
