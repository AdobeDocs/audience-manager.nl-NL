---
description: Voor deze procedure zijn een vervolgkeuzelijst voor AdWords, pixelcode en een Audience Manager URL-doel vereist. Het is ook gekend als remarketing lijst voor de integratie van onderzoeksadvertenties (RLSA). Alleen van toepassing op betaalde zoekopdrachten.
seo-description: This procedure requires an AdWords remarketing list, pixel code, and an Audience Manager URL destination. It is also known as a remarketing list for search ads (RLSA) integration. Applies to paid search only.
seo-title: Send Segments to a Google AdWords Remarketing List
solution: Audience Manager
title: Segmenten verzenden naar een Google AdWords-opmerkinglijst
uuid: 5ad821c6-48b4-42c0-b912-1563331e93a2
feature: Third-party Integration
exl-id: 76676eae-de4f-4fee-8774-ee215525306a
source-git-commit: b8d65ef8c27100d174a997eb24a75f37b4e75d40
workflow-type: tm+mt
source-wordcount: '284'
ht-degree: 0%

---

# Segmenten verzenden naar een Google Ads-opmerkinglijst {#send-segments-to-a-google-adwords-remarketing-list}

Voor deze procedure is een [!DNL Google Ads] lijst met opnieuw in de handel brengen, pixelcode en een Audience Manager [!DNL URL] [!DNL destination] vereist. Dit wordt ook wel een lijst met wederverkoopmogelijkheden voor integratie met zoekadvertenties ([!DNL RLSA]) genoemd. Alleen van toepassing op betaalde zoekopdrachten.

>[!IMPORTANT]
>Dit is geen productieve integratie van de twee systemen.

Een [!DNL Google Ads] lijst voor opnieuw in de handel brengen instellen als een [!DNL Audience Manager] [!DNL URL destination] :

1. In uw [!DNL Google Ads] rekening, [ creeer een website re-marketing lijst ](https://support.google.com/tagmanager/answer/6106960?hl=en) en schrijf uw omzettingsidentiteitskaart neer.
1. Gebruik de volgende URL als sjabloon voor de Basis URL en Veilige URL. Vervang de sectie xxxxxxxx door uw omzettings ID.

   ```
    //googleads.g.doubleclick.net/pagead/viewthroughconversion/xxxxxxxx/?value=0&guid=ON&script=0&data=%ALIAS%
   ```

1. In Audience Manager, [ creeer a  [!DNL URL destination]](../../features/destinations/create-url-destination.md) of geef bestaand uit [!DNL destination]. Gebruik de volgende instellingen bij het maken van de [!DNL destination] :
   * Type: URL
   * Serialiseren: Ingeschakeld
   * Scheidingsteken: puntkomma (&puntkomma; )

1. Voeg in de sectie [!UICONTROL Segment Mappings] van de [!DNL URL] [!DNL destination] -sectie de code uit stap 2 toe aan de velden [!DNL URL] en [!DNL Secure URL] . Plaats een voorvoegsel voor de code tussen `http:` en `https:` in respectievelijk de velden [!DNL URL] en [!DNL Secure URL] .

   >[!IMPORTANT]
   >
   >Gecodeerde ampersands vervangen `&` door niet-gecodeerde ampersands `&`

   Onveilige [!DNL URL] code:

   ```
    http://googleads.g.doubleclick.net/pagead/viewthroughconversion/xxxxxxxx/?
    value=0&guid=ON&script=0&data=%ALIAS%
   ```

   Secure [!DNL URL] -code:

   ```
    https://googleads.g.doubleclick.net/pagead/viewthroughconversion/xxxxxxxx/?
    value=0&guid=ON&script=0&data=%ALIAS%
   ```

1. Klik op **[!UICONTROL Save]**.

   >[!NOTE]
   >
   >Als u met meerdere segmenten werkt, krijgt u een nieuwe pixel voor elk segment dat u wilt toewijzen aan een [!DNL Google Ads] [!DNL destination] . Dit zorgt ervoor dat de gegevens worden toegepast op de juiste vervolgkeuzelijst.

1. Wanneer u in Audience Manager een nieuw segment aan dit [!DNL destination] segment toewijst, definieert u de toewijzing als `aam=segmentID` en vervangt u `segmentID` door de id van het segment.
1. Wanneer u een emmertje definieert in [!DNL Google Ads] , maakt u een regel die overeenkomt met de toewijzing die is gedefinieerd in stap 6.

Een voltooide afbeelding kan er ongeveer als volgt uitzien:

![](../assets/rlsa_mapping.png)

>[!MORELIKETHIS]
>
>* [[!DNL Destinations]](../../features/destinations/destinations.md)
>* [ creeer a  [!DNL URL Destination]](../../features/destinations/create-url-destination.md)
>* [ Ongeveer AdWords die Lijsten van de Nota&#39;s ](https://support.google.com/adwords/answer/2472738) markeren
>* [ hoe AdWords het Markeren werkt ](https://support.google.com/adwords/answer/2454000)
