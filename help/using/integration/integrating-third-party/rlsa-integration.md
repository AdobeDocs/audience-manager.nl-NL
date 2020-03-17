---
description: Deze procedure vereist een AdWords remarketing lijst, pixelcode, en een bestemming van de Manager van de Audience URL. Het is ook gekend als remarketing lijst voor de integratie van onderzoeksadvertenties (RLSA). Alleen van toepassing op betaalde zoekopdrachten.
seo-description: Deze procedure vereist een AdWords remarketing lijst, pixelcode, en een bestemming van de Manager van de Audience URL. Het is ook gekend als remarketing lijst voor de integratie van onderzoeksadvertenties (RLSA). Alleen van toepassing op betaalde zoekopdrachten.
seo-title: Segmenten verzenden naar een Google AdWords-opmerkinglijst
solution: Audience Manager
title: Segmenten verzenden naar een Google AdWords-opmerkinglijst
uuid: 5ad821c6-48b4-42c0-b912-1563331e93a2
translation-type: tm+mt
source-git-commit: d6abb45fa8b88248920b64db3ac4e72c53ecee13

---


# Segmenten verzenden naar een Google Ads-opmerkinglijst {#send-segments-to-a-google-adwords-remarketing-list}

Deze procedure vereist een [!DNL Google Ads] remarketing lijst, pixelcode, en een [!DNL URL] bestemming van de Manager van de Publiek. Het wordt ook wel een lijst met opnieuw op de markt gebrachte zoekopdrachten ([!DNL RLSA]) genoemd. Alleen van toepassing op betaalde zoekopdrachten.

>[!IMPORTANT]
>Dit is geen productieve integratie van de twee systemen.

Een [!DNL Google Ads] lijst voor opnieuw in de handel brengen instellen als een [!DNL Audience Manager] URL-doel:

1. In uw [!DNL Google Ads] account [maakt u een lijst](https://support.google.com/adwords/answer/2454064?hl=en) voor het opnieuw op de markt brengen van websites en schrijft u de conversie-id af.
1. Gebruik de volgende URL als sjabloon voor de Basis URL en Veilige URL. Vervang de sectie xxxxxxxx door uw omzettings ID.

   ```
    //googleads.g.doubleclick.net/pagead/viewthroughconversion/xxxxxxxx/?value=0&guid=ON&script=0&data=%ALIAS%
   ```

1. In Audience Manager [maakt u een URL-doel](../../features/destinations/create-url-destination.md) of bewerkt u een bestaand doel. Gebruik de volgende instellingen bij het maken van het doel:
   * Type: URL
   * Serienummering: Ingeschakeld
   * Scheidingsteken: Puntkomma (;)

1. Voeg in het [!UICONTROL Segment Mappings] gedeelte van uw [!DNL URL] bestemming de code van stap 2 toe aan de velden [!DNL URL] en [!DNL Secure URL] velden. Plaats een voorvoegsel voor de code tussen `http:` en `https:` in de [!DNL URL] velden en de [!DNL Secure URL] velden.

   >[!IMPORTANT]
   >
   >Gecodeerde ampersands vervangen `&` door niet-gecodeerde ampersands `&`

   Onveilige [!DNL URL] code:

   ```
    http://googleads.g.doubleclick.net/pagead/viewthroughconversion/xxxxxxxx/?
    value=0&guid=ON&script=0&data=%ALIAS%
   ```

   Beveiligde [!DNL URL] code:

   ```
    https://googleads.g.doubleclick.net/pagead/viewthroughconversion/xxxxxxxx/?
    value=0&guid=ON&script=0&data=%ALIAS%
   ```

1. Klik op **[!UICONTROL Save]**.

   >[!NOTE]
   >
   >Als u met meerdere segmenten werkt, krijgt u een nieuwe pixel voor elk segment dat u wilt toewijzen aan een Google Ads-doel. Dit zorgt ervoor dat de gegevens worden toegepast op de juiste vervolgkeuzelijst.

1. Wanneer het in kaart brengen van een nieuw segment aan deze bestemming in de Manager van het Publiek, bepaal de afbeelding als `aam=segmentID` en vervang `segmentID` met identiteitskaart van uw segment.
1. Wanneer het bepalen van een emmertje binnen [!DNL Google Ads], creeer een regel die de afbeelding aanpast die bij stap 6 wordt bepaald.

Een voltooide afbeelding kan er ongeveer als volgt uitzien:

![](../assets/rlsa_mapping.png)

>[!MORELIKETHIS]
>
>* [Doelen](../../features/destinations/destinations.md)
>* [Een URL-doel maken](../../features/destinations/create-url-destination.md)
>* [Info over ADWoorden markeringslijsten](https://support.google.com/adwords/answer/2472738)
>* [Procedure voor markeren van woorden](https://support.google.com/adwords/answer/2454000)

