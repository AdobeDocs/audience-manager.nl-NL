---
description: Stel een Google-groep in om uw Google Campagne Manager-gegevensbestanden in de Audience Manager te plaatsen. De inhoud in deze sectie geeft een overzicht van het integratieproces en bevat koppelingen naar Google Campaign Manager-bronnen om u te helpen aan de slag te gaan.
seo-description: Set up a Google group to bring your Google Campaign Manager data files into Audience Manager. The content in this section summarizes the integration process and provides you with links to Google Campaign Manager resources to help you get started.
seo-title: Import Google Campaign Manager Data Files Into Audience Manager
solution: Audience Manager
title: Google Campagne Manager-gegevensbestanden importeren in Audience Manager
uuid: 3578cfe1-6d30-4a73-ab75-8d272bebcd60
feature: Audience Optimization Reports
exl-id: 045eed94-100f-460d-83bb-78fbd7beb51c
source-git-commit: 95b7b4347f3da16be05be60cbefc0e236022a4a7
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Google Campagne Manager-gegevensbestanden importeren in Audience Manager {#import-dcm-data-files-into-audience-manager}

Een [!DNL Google] groep om uw [!DNL Google Campaign Manager] gegevensbestanden in Audience Manager. De inhoud in deze sectie geeft een overzicht van het integratieproces en bevat koppelingen naar [!DNL Google Campaign Manager] bronnen om u te helpen aan de slag te gaan.

## Overzicht van integratie

[!DNL Google Campaign Manager] is de vervanging van [!DNL Google] voor [!DNL DoubleClick for Advertisers] (DFA). Vergelijkbaar met DFA, [!DNL Google Campaign Manager] klanten kunnen hun gegevens importeren, weergeven en ermee werken in [!DNL Audience Manager]. [!DNL Audience Manager] kan echter niet rechtstreeks uw [!UICONTROL Data Transfer]- en [!UICONTROL Match Table]-bestanden openen en importeren. Het importeren van deze bestanden is een taak voor de klant.

De oprichtingsprocedure is echter goed gedocumenteerd in de [Dubbelklikken op Help Campagnebeheer](https://support.google.com/dcm/partner/answer/2941575?hl=en&amp;ref_topic=6107456). U kunt ook de onderstaande stappen doornemen om aan de slag te gaan.

>[!CAUTION]
>
>[!DNL Google Campaign Manager] gegevensbestanden bevatten gegevens voor al uw adverteerders of klanten. Als u specifieke clients moet weglaten, moet u de bestanden bewerken voordat u ze beschikbaar maakt voor [!DNL Audience Manager].

## Frequentie en beschikbaarheid van gegevensoverdracht

[!DNL Audience Manager] controleert elke dag op gegevens en draagt deze over. Gegevens zijn gewoonlijk beschikbaar in [!DNL Audience Manager] na 24 uur.

## Stappen

1. [Een groep maken](https://support.google.com/dcm/partner/answer/3370419?hl=en&amp;ref_topic=6107456).

   Groepen beheren toegang tot uw [!DNL Google Campaign Manager] gegevens. Uiteindelijk, zult u uitnodigen en zult toevoegen [!DNL Audience Manager] aan deze groep.

1. [De status van Google Cloud Storage controleren](https://support.google.com/dcm/partner/answer/3370481?hl=en&amp;ref_topic=6107456).

   Google Cloud Storage bevat het gegevenssegment dat uw [!UICONTROL Data Transfer] en [!UICONTROL Match Tables]. U zult een emmertje moeten opstelling of ervoor zorgen uw nieuwe groep toegang tot een bestaand emmertje van de gegevensopslag heeft.

1. [URL van gegevensbestand ophalen](https://support.google.com/dcm/partner/answer/3370482?hl=en&amp;ref_topic=6107456).

   Werk met uw [!DNL Google Campaign Manager] Accountmanager of consultant voor Platform-oplossingen. Ze geven u een URL naar uw gegevensbestanden. [!DNL Google] In toekomstige versies kan de indeling voor bucket- en bestandsnamen veranderen. Opnieuw, werk met uw [!DNL Google Campaign Manager] Accountmanager om te controleren of u de juiste indelingen gebruikt.

1. [Machtigingen voor emmertjes instellen](https://cloud.google.com/storage/docs/cloud-console?csw=1#_bucketpermission).

   De [!DNL Cloud Storage Manager] Hiermee kunt u gegevens delen en emmer-toegang beheren. Geef uw groep lees toegang tot de emmer die uw [!UICONTROL Data Transfer] en [!UICONTROL Match Table] bestanden.

1. [Delen van gegevens instellen](https://support.google.com/dcm/partner/answer/6206106?hl=en).

   Gedeeld [!DNL Google Campaign Manager] gebruikers-id&#39;s zijn gecodeerd om de privacy te beschermen. De encryptie voegt 2 kolommen aan het eind van uw dossier van de Overdracht van Gegevens toe, `PartnerId1` en `PartnerId2`. Deze kolommen bevatten gecodeerde gebruikers-id&#39;s die specifiek zijn voor elk bedrijf dat deze bestanden ontvangt.

   Als geautoriseerde derde [!DNL Audience Manager] kan ontvangen [!DNL Google Campaign Manager] gegevens, maar kan de id&#39;s niet decoderen. De [!DNL Audience Manager] Bovendien weten we hoe de gecodeerde id&#39;s overeenkomen met onze id&#39;s. Dit betekent dat we gebruikers met vertrouwen en nauwkeurigheid kunnen afstemmen en synchroniseren.

   >[!NOTE]
   >U kunt niet importeren [!DNL Google Campaign Manager] bestanden in [!DNL Audience Manager] als u reeds gegevens met 2 andere derdepartners deelt.

1. Uitnodigen [!DNL Audience Manager] om deel te nemen aan de groep.

   Nadat u een groep creeert en het toegang tot een gegevensemmer geeft, nodig uit [!DNL Audience Manager] om deel te nemen aan de groep. Verzend een uitnodigings-e-mail naar dfaaam@adobe.com. Zorg ervoor dat u de URL van het gegevensbestand uit stap 3 opneemt. Onze interne teams zullen met u samenwerken om toegang te verifiëren nadat het goedkeuren van de uitnodiging. 1. Twee gegevensbronnen instellen voor [!DNL Google Campaign Manager] gegevens in de [!DNL Audience Manager] Gebruikersinterface.

   Geef de gegevensbronnen een naam `Advertiser Analytics: DCM Platform` en `Advertiser Analytics: AAM+DCM Platform`. In de [Gegevensbronnen maken](../../../features/manage-datasources.md#create-data-source) workflow, stel het id-type in op `Cookie`. Deel de id&#39;s van de twee nieuwe gegevensbronnen met onze interne teams.

1. U kunt gemakkelijk eigenschappen tot stand brengen van [!DNL Google Campaign Manager] bestanden die u importeert in [!DNL Audience Manager]. Zie [Werkbare logbestanden](../../../integration/media-data-integration/actionable-log-files.md) en vraag uw [!DNL Audience Manager] consultant of klantenservice om de functie voor u in te schakelen.
