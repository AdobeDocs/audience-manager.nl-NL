---
description: Deze procedure vereist een AdWords remarketing lijst, pixelcode, en een Audience Manager URL bestemming. Het is ook gekend als remarketing lijst voor de integratie van onderzoeksadvertenties (RLSA). Alleen van toepassing op betaalde zoekopdrachten.
seo-description: Deze procedure vereist een AdWords remarketing lijst, pixelcode, en een Audience Manager URL bestemming. Het is ook gekend als remarketing lijst voor de integratie van onderzoeksadvertenties (RLSA). Alleen van toepassing op betaalde zoekopdrachten.
seo-title: Segmenten verzenden naar een Google AdWords-remarketinglijst
solution: Audience Manager
title: Segmenten verzenden naar een Google AdWords-remarketinglijst
uuid: 5ad821c6-48b4-42c0-b912-1563331e93a2
feature: Third Party Integrations
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '332'
ht-degree: 5%

---


# Segmenten verzenden naar een Google Ads-opmerkinglijst {#send-segments-to-a-google-adwords-remarketing-list}

Deze procedure vereist een [!DNL Google Ads] lijst van opnieuw in de handel brengen, pixelcode, en een Audience Manager [!DNL URL] [!DNL destination]. Het wordt ook wel een lijst met wederverkoopmogelijkheden genoemd voor integratie met zoekadvertenties ([!DNL RLSA]). Alleen van toepassing op betaalde zoekopdrachten.

>[!IMPORTANT]
>Dit is geen productieve integratie van de twee systemen.

Een [!DNL Google Ads] lijst voor het opnieuw in de handel brengen instellen als een [!DNL Audience Manager] [!DNL URL destination]:

1. [maak in uw [!DNL Google Ads]-account een lijst voor het opnieuw op de markt brengen van websites](https://support.google.com/adwords/answer/2454064?hl=en) en noteer uw conversie-id.
1. Gebruik de volgende URL als sjabloon voor de Basis URL en Veilige URL. Vervang de sectie xxxxxxxx door uw omzettings ID.

   ```
    //googleads.g.doubleclick.net/pagead/viewthroughconversion/xxxxxxxx/?value=0&guid=ON&script=0&data=%ALIAS%
   ```

1. In Audience Manager, [creeer a [!DNL URL destination]](../../features/destinations/create-url-destination.md) of geef bestaand [!DNL destination] uit. Gebruik de volgende instellingen bij het maken van de [!DNL destination]:
   * Type: URL
   * Serienummering: Ingeschakeld
   * Scheidingsteken: Puntkomma (;)

1. Voeg in de sectie [!UICONTROL Segment Mappings] van uw [!DNL URL] [!DNL destination] de code van stap 2 toe aan de velden [!DNL URL] en [!DNL Secure URL]. Plaats de code in de velden [!DNL URL] en [!DNL Secure URL] vooraf in `http:` en &lt;a3/>.`https:`

   >[!IMPORTANT]
   >
   >Gecodeerde ampersands `&` vervangen door niet-gecodeerde ampersands `&`

   Onveilige [!DNL URL]-code:

   ```
    http://googleads.g.doubleclick.net/pagead/viewthroughconversion/xxxxxxxx/?
    value=0&guid=ON&script=0&data=%ALIAS%
   ```

   Beveiligde [!DNL URL]-code:

   ```
    https://googleads.g.doubleclick.net/pagead/viewthroughconversion/xxxxxxxx/?
    value=0&guid=ON&script=0&data=%ALIAS%
   ```

1. Klik op **[!UICONTROL Save]**.

   >[!NOTE]
   >
   >Als u met veelvoudige segmenten werkt, krijg een nieuwe pixel voor elk segment u aan [!DNL Google Ads] [!DNL destination] wilt in kaart brengen. Dit zorgt ervoor dat de gegevens worden toegepast op de juiste vervolgkeuzelijst.

1. Wanneer u een nieuw segment in Audience Manager toewijst aan deze [!DNL destination], definieert u de toewijzing als `aam=segmentID` en vervangt u `segmentID` door de id van het segment.
1. Wanneer het bepalen van een emmertje in [!DNL Google Ads], creeer een regel die de afbeelding aanpast die bij stap 6 wordt bepaald.

Een voltooide afbeelding kan er ongeveer als volgt uitzien:

![](../assets/rlsa_mapping.png)

>[!MORELIKETHIS]
>
>* [[!DNL Destinations]](../../features/destinations/destinations.md)
>* [Een [!DNL URL Destination]](../../features/destinations/create-url-destination.md)
>* [Info over ADWoorden markeringslijsten](https://support.google.com/adwords/answer/2472738)
>* [Procedure voor markeren van woorden](https://support.google.com/adwords/answer/2454000)

