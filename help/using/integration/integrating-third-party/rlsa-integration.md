---
description: Deze procedure vereist een AdWords remarketing lijst, pixelcode, en een Audience Manager URL bestemming. Het is ook gekend als remarketing lijst voor de integratie van onderzoeksadvertenties (RLSA). Alleen van toepassing op betaalde zoekopdrachten.
seo-description: This procedure requires an AdWords remarketing list, pixel code, and an Audience Manager URL destination. It is also known as a remarketing list for search ads (RLSA) integration. Applies to paid search only.
seo-title: Send Segments to a Google AdWords Remarketing List
solution: Audience Manager
title: Segmenten verzenden naar een Google AdWords-remarketinglijst
uuid: 5ad821c6-48b4-42c0-b912-1563331e93a2
feature: Third-party Integration
exl-id: 76676eae-de4f-4fee-8774-ee215525306a
source-git-commit: b8d65ef8c27100d174a997eb24a75f37b4e75d40
workflow-type: tm+mt
source-wordcount: '293'
ht-degree: 3%

---

# Segmenten verzenden naar een Google Ads-opmerkinglijst {#send-segments-to-a-google-adwords-remarketing-list}

Deze procedure vereist een [!DNL Google Ads] opnieuw op de markt brengen lijst, pixelcode en een Audience Manager [!DNL URL] [!DNL destination]. Het wordt ook wel een lijst voor het opnieuw op de markt brengen van zoekopdrachten genoemd ([!DNL RLSA]) integratie. Alleen van toepassing op betaalde zoekopdrachten.

>[!IMPORTANT]
>Dit is geen productieve integratie van de twee systemen.

Als u een [!DNL Google Ads] lijst voor opnieuw in de handel brengen als [!DNL Audience Manager] [!DNL URL destination]:

1. In uw [!DNL Google Ads] rekening, [een lijst voor het opnieuw op de markt brengen van websites maken](https://support.google.com/tagmanager/answer/6106960?hl=en) en noteer uw conversie-id.
1. Gebruik de volgende URL als sjabloon voor de Basis URL en Veilige URL. Vervang de sectie xxxxxxxx door uw omzettings ID.

   ```
    //googleads.g.doubleclick.net/pagead/viewthroughconversion/xxxxxxxx/?value=0&guid=ON&script=0&data=%ALIAS%
   ```

1. In Audience Manager, [Een [!DNL URL destination]](../../features/destinations/create-url-destination.md) of een bestaande [!DNL destination]. Gebruik de volgende instellingen bij het maken van de [!DNL destination]:
   * Type: URL
   * Serienummering: Ingeschakeld
   * Scheidingsteken: Puntkomma (&amp;puntkomma; )

1. In de [!UICONTROL Segment Mappings] deel van uw [!DNL URL] [!DNL destination]voegt u de code van stap 2 toe aan de [!DNL URL] en [!DNL Secure URL] velden. De code vooraf bevestigen met `http:` en `https:` in de [!DNL URL] en [!DNL Secure URL] respectievelijk velden.

   >[!IMPORTANT]
   >
   >Gecodeerde ampersands vervangen `&` met niet-gecodeerde ampersanden `&`

   Onveilig [!DNL URL] code:

   ```
    http://googleads.g.doubleclick.net/pagead/viewthroughconversion/xxxxxxxx/?
    value=0&guid=ON&script=0&data=%ALIAS%
   ```

   Beveiligen [!DNL URL] code:

   ```
    https://googleads.g.doubleclick.net/pagead/viewthroughconversion/xxxxxxxx/?
    value=0&guid=ON&script=0&data=%ALIAS%
   ```

1. Klik op **[!UICONTROL Save]**.

   >[!NOTE]
   >
   >Als u met veelvoudige segmenten werkt, krijg een nieuwe pixel voor elk segment u aan een segment wilt in kaart brengen [!DNL Google Ads] [!DNL destination]. Dit zorgt ervoor dat de gegevens worden toegepast op de juiste vervolgkeuzelijst.

1. Wanneer u een nieuw segment toewijst aan dit [!DNL destination] in Audience Manager, de afbeelding definiëren als `aam=segmentID` en vervangen `segmentID` met de id van uw segment.
1. Bij het definiëren van een emmertje in [!DNL Google Ads], maakt u een regel die overeenkomt met de toewijzing die is gedefinieerd in stap 6.

Een voltooide afbeelding kan er ongeveer als volgt uitzien:

![](../assets/rlsa_mapping.png)

>[!MORELIKETHIS]
>
>* [[!DNL Destinations]](../../features/destinations/destinations.md)
>* [Een [!DNL URL Destination]](../../features/destinations/create-url-destination.md)
>* [Info over ADWoorden markeringslijsten](https://support.google.com/adwords/answer/2472738)
>* [Procedure voor markeren van woorden](https://support.google.com/adwords/answer/2454000)

