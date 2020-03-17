---
description: De Rapportering van het Gebruik van de activiteit helpt u het activiteitengebruik voor uw instantie van de Manager van de Publiek bekijken en volgen, zodat kunt u uw daadwerkelijke gebruik met uw contractuele verplichting vergelijken.
keywords: activity, usage, reporting, commitment
seo-description: De Rapportering van het Gebruik van de activiteit helpt u het activiteitengebruik voor uw instantie van de Manager van de Publiek bekijken en volgen, zodat kunt u uw daadwerkelijke gebruik met uw contractuele verplichting vergelijken.
seo-title: Activiteitenverbruik rapporteren
solution: Audience Manager
title: Activiteitenverbruik rapporteren
topic: Activity Usage Reporting
translation-type: tm+mt
source-git-commit: 7a3914af8fb225508f57724a75fe2547aac3f241

---


# Activiteitenverbruik rapporteren

## Overzicht {#overview}

De [!UICONTROL Activity Usage Report] hulp u het activiteitengebruik van uw instantie van de Manager van de Publiek bekijkt en volgt, die u een duidelijk idee geeft van hoe uw activiteitengebruik met uw contractuele verplichting vergelijkt.

Bovendien kunt u de gegevens op elk gewenst moment downloaden voor het bijhouden van records en aangepaste analyses. [!UICONTROL Activity Usage Report]

## Overwegingen {#considerations}

Het [!UICONTROL Activity Usage Report] is beschikbaar voor alle gebruikers van Audience Manager met [beheerdersrechten](edit-account-settings.md).

> [!IMPORTANT]
>
> Het [!UICONTROL Activity Usage Report] toont u de statistieken van het activiteitengebruik van uw instantie van de Manager van de Publiek. Neem contact op met uw Adobe-vertegenwoordiger voor alle vragen over facturering die betrekking hebben op uw gebruik van activiteiten.

## Gevallen gebruiken {#use-cases}

Er zijn twee belangrijke gevallen van gebruik van het [!UICONTROL Activity Usage Report]volgende:

* **Actief gebruik van instance-activiteiten bijhouden op basis van uw verplichting** om activiteiten te gebruiken: De meeste klanten hebben een maandelijkse geschatte activiteitenverplichting per instantie van de Manager van de Audience, die dan in een jaarlijkse activiteitenverplichting over alle gevallen wordt gecumuleerd. Hoewel dit rapport geen factureringsrapport is, kan het nuttige begeleiding verstrekken over of u het toegewijde activiteitengebruik overschrijdt.
* **Validatie voor implementatiewijzigingen**: Als u onlangs uw implementatie, zoals vestiging Analytics server-kant het door:sturen, of het veranderen van uw montages van de de servervraag van het Doel hebt bijgewerkt, kan dit rapport u helpen controleren of het nieuwe activiteitenvolume in lijn met uw verwacht activiteitenvolume is.

## Het rapport Activiteitsverbruik gebruiken {#using}

Als u de [!UICONTROL Activity Usage Report]optie wilt weergeven, meldt u zich aan bij uw account Audience Manager en gaat u naar **[!UICONTROL Administration]** > **[!UICONTROL Usage]**.

![aur-ui](assets/aur-ui.png)

Vervolgens gebruikt u het **[!UICONTROL Reporting Interval]** filter om het tijdsinterval te selecteren waarvoor het rapport moet worden gegenereerd. U kunt kiezen tussen 30, 60, 90 dagen of een aangepast datumbereik.

Zodra uw rapport laadt, kunt u een onderbreking van uw [!UICONTROL Activities] voor de geselecteerde periode zien.

[!UICONTROL Activities] het totale totaal van alle onsite en externe interacties met Audience Manager definiëren, gesplitst in de volgende categorieën:

* **[!UICONTROL Server Calls]**: Alle gegevensverzamelings- of ophaalgebeurtenissen die via websites, servers, e-mail, mobiele toepassingen of andere systemen naar Audience Manager worden verzonden.
* **[!UICONTROL Pixel Calls](voorheen bekend als[!UICONTROL Impression Server Calls])**: Gegevens die zijn verzameld op advertenties (zoals het impressievolume van een doelplatform) of e-mailimpressies die zijn uitgevoerd op Audience Manager. Deze vereisen de aanwezigheid van de`d_event`parameter in het vraagkoord.
* **[!UICONTROL On-Boarded Records]**: Unieke verslagen die van uw eigen systeem van het klantenrelatiebeheer (CRM) of andere off-line gegevensdossiers, zoals de verslagen van het vraagcentrum, apparaat IDs, en de voer van douanegegevens van externe gegevensleveranciers worden opgenomen.
* **[!UICONTROL Log File Records]**: Unieke verslagen van logboekdossiers die in de Manager van het Publiek van een gericht platform worden opgenomen.

> [!NOTE]
> Een unieke record definieert elke afzonderlijke record met gegevens in een bestand dat door Adobe wordt opgeslagen namens een klant van Audience Manager.

Bovendien kunt u de [!UICONTROL Activity Usage Trends] grafiektypen gebruiken om te schakelen tussen twee typen grafieken.

![aur-ui-grafieken](assets/aur-ui-graphs.png)

U kunt de cursor ook boven een bepaalde datum in de tijdlijn plaatsen om het gedetailleerde gebruik voor die datum te zien.

![aur-hover](assets/aur-hover.png)

## Rapporten van activiteitenverbruik exporteren {#export}

Voor een beter overzicht van uw het activiteitengebruiksniveau van de Manager van de Publiek, kunt u het uitvoeren [!UICONTROL Activity Usage Report] gebaseerd op het type van verslagen die u wilt omvatten.

![automatisch exporteren](assets/aur-export.png)

De **[!UICONTROL Onboarded Records Breakdown]** en **[!UICONTROL Onsite Server Calls Breakdown]** rapporten bieden het meest gedetailleerde inzicht in de brongegevens die voor deze activiteiten beschikbaar zijn. Het volume dat aan deze uitsplitsingen wordt toegewezen is gebaseerd op uw implementatie.

### Indeling van geregistreerde records aan boord {#onboarded-breakdown}

Dit rapport bevat niet-geregistreerde records uitgesplitst naar gegevensbron.

### On-site servercall-down {#onsite-breakdown}

Dit rapport bevat een verdeling van servervraag uit drie bronnen: [!UICONTROL Analytics], [!UICONTROL Target], en [!UICONTROL Other].

* **[!UICONTROL Analytics]**: Dit zijn factureerbare servervraag die van alle instanties van de Analyse van Adobe aan de Manager van het Publiek, met inbegrip van server-zijhet door:sturen wordt overgegaan. De secundaire servervraag of dubbele servervraag (zoals in het geval van server zijdoor:sturen van veelvoudige rapportreeksen) zijn geen factureerbare activiteiten, zodat zij niet inbegrepen in deze mislukking zijn.
* **[!UICONTROL Target]**: Dit zijn serveraanroepen van Adobe Target naar Audience Manager om de segmentgegevens van Audience Manager op te halen als onderdeel van een server-naar-server integratie.
* **[!UICONTROL Other]**: Omvat vraag van een andere website of systeem (partnerplaatsen, directe servervraag, enz.), mobiele browser/app vraag via [!DNL SDK], [!DNL DIL], gebeurtenisvraag, en [!DNL DCS] vraag. Omvat ook vraag van [!DNL Target] als opstelling als koekjesintegratie (eerder dan server-aan-server).
