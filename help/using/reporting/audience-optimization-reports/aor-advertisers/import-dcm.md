---
description: Stel een Google-groep in om uw DCM-gegevensbestanden (DoubleClick Campagne Manager) over te brengen naar Audience Manager. De inhoud in deze sectie geeft een overzicht van het integratieproces en bevat koppelingen naar DCM-bronnen om u te helpen aan de slag te gaan.
seo-description: Stel een Google-groep in om uw DCM-gegevensbestanden (DoubleClick Campagne Manager) over te brengen naar Audience Manager. De inhoud in deze sectie geeft een overzicht van het integratieproces en bevat koppelingen naar DCM-bronnen om u te helpen aan de slag te gaan.
seo-title: DCM-gegevensbestanden importeren in Auditiebeheer
solution: Audience Manager
title: DCM-gegevensbestanden importeren in Auditiebeheer
uuid: 3578cfe1-6d30-4a73-ab75-8d272bebcd60
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# DCM-gegevensbestanden importeren in Auditiebeheer {#import-dcm-data-files-into-audience-manager}

Stel een Google-groep in om uw DCM-gegevensbestanden (DoubleClick Campagne Manager) over te brengen naar Audience Manager. De inhoud in deze sectie geeft een overzicht van het integratieproces en bevat koppelingen naar DCM-bronnen om u te helpen aan de slag te gaan.

## Overzicht van integratie

DCM is de vervanging van [!DNL Google] voor [!DNL DoubleClick for Advertisers] (DFA). Net als bij DFA kunnen DCM-klanten hun data importeren, weergeven en ermee werken in [!DNL Audience Manager]. [!DNL Audience Manager] kan echter niet rechtstreeks uw [!UICONTROL Data Transfer]- en [!UICONTROL Match Table]-bestanden openen en importeren. Het importeren van deze bestanden is een taak voor de klant.

Nochtans, is de opstellingsprocedure goed gedocumenteerd in de Hulp [van de Manager van de Campagne](https://support.google.com/dcm/partner/answer/2941575?hl=en&ref_topic=6107456)Dubbelklik. U kunt ook de onderstaande stappen doornemen om aan de slag te gaan.

>[!CAUTION]
>
>DCM-gegevensbestanden bevatten gegevens voor al uw adverteerders of klanten. Als u specifieke clients moet weglaten, moet u de bestanden bewerken voordat u ze beschikbaar maakt voor [!DNL Audience Manager].

## Frequentie en beschikbaarheid van gegevensoverdracht

[!DNL Audience Manager] controleert elke dag op gegevens en draagt deze over. De gegevens zijn meestal beschikbaar binnen [!DNL Audience Manager] 24 uur.

## Stappen

1. [Maak een groep](https://support.google.com/dcm/partner/answer/3370419?hl=en&ref_topic=6107456).

   Groepen beheren de toegang tot uw DCM-gegevens. Uiteindelijk, zult u uitnodigen en [!DNL Audience Manager] aan deze groep toevoegen.

1. [Controleer uw Google Cloud Storage-status](https://support.google.com/dcm/partner/answer/3370481?hl=en&ref_topic=6107456).

   Google Cloud Storage bevat het gegevensemmertje dat uw [!UICONTROL Data Transfer] en [!UICONTROL Match Tables]. U zult een emmertje moeten opstelling of ervoor zorgen uw nieuwe groep toegang tot een bestaand emmertje van de gegevensopslag heeft.

1. [Hiermee wordt de URL](https://support.google.com/dcm/partner/answer/3370482?hl=en&ref_topic=6107456)van een gegevensbestand opgehaald.

   Werk met uw DCM-accountmanager of consultant voor platformoplossingen. Ze geven u een URL naar uw gegevensbestanden. [!DNL Google] In toekomstige versies kan de indeling voor bucket- en bestandsnamen veranderen. Werk opnieuw met uw DCM-accountmanager om te controleren of u de juiste indelingen gebruikt.

1. [Machtigingen](https://cloud.google.com/storage/docs/cloud-console?csw=1#_bucketpermission)voor emmertje instellen.

   Met [!DNL Cloud Storage Manager] deze optie kunt u gegevens delen en emmer-toegang beheren. Geef uw groep leestoegang tot de emmer die uw [!UICONTROL Data Transfer] en [!UICONTROL Match Table] dossiers bevat.

1. [Gegevens delen](https://support.google.com/dcm/partner/answer/6206106?hl=en)instellen.

   Gedeelde DCM-gebruikers-id&#39;s zijn gecodeerd om de privacy te beschermen. De encryptie voegt 2 kolommen aan het eind van uw dossier van de Overdracht van Gegevens toe, `PartnerId1` en `PartnerId2`. Deze kolommen bevatten gecodeerde gebruikers-id&#39;s die specifiek zijn voor elk bedrijf dat deze bestanden ontvangt.

   Als geautoriseerde derde partij [!DNL Audience Manager] kan deze DCM-gegevens ontvangen, maar de id&#39;s kunnen niet worden gedecodeerd. Aan de [!DNL Audience Manager] kant weten we echter hoe de gecodeerde id&#39;s overeenkomen met onze id&#39;s. Dit betekent dat we gebruikers met vertrouwen en nauwkeurigheid kunnen afstemmen en synchroniseren.

   >[!NOTE]
   >U kunt geen DCM- dossiers invoeren in [!DNL Audience Manager] als u reeds gegevens met twee andere derdepartners deelt.

1. Uitnodigen [!DNL Audience Manager] om deel te nemen aan de groep.

   Nadat u een groep creeert en het toegang tot een gegevensemmer geeft, nodig uit [!DNL Audience Manager] om zich bij de groep aan te sluiten. Verzend een uitnodigings-e-mail naar DFA-AAM@adobe.com. Zorg ervoor dat u de URL van het gegevensbestand uit stap 3 opneemt. Onze interne teams zullen met u samenwerken om toegang te verifiëren nadat het goedkeuren van de uitnodiging. 1. Stel twee gegevensbronnen voor DCM-gegevens in de [!DNL Audience Manager] gebruikersinterface in.

   Geef de gegevensbronnen `Advertiser Analytics: DCM Platform` en `Advertiser Analytics: AAM+DCM Platform`. Stel het id-type in op [Gegevensbronnen](../../../features/manage-datasources.md#create-data-source) maken in de workflow Gegevensbronnen maken `Cookie`. Deel de id&#39;s van de twee nieuwe gegevensbronnen met onze interne teams.

1. U kunt eenvoudig kenmerken maken van de DCM-bestanden waarin u importeert [!DNL Audience Manager]. Zie [Handbare logbestanden](../../../integration/media-data-integration/actionable-log-files.md) en vraag uw [!DNL Audience Manager] consultant of de klantenservice om deze functie voor u in te schakelen.
