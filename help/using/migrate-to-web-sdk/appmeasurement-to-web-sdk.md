---
title: Werk uw bibliotheek van de gegevensinzameling voor Audience Manager van de bibliotheek van JavaScript van het AppMeasurement aan de bibliotheek van JavaScript van SDK van het Web bij.
description: Begrijp de stappen om uw bibliotheek van de gegevensinzameling voor Audience Manager van de bibliotheek van JavaScript van het AppMeasurement aan de bibliotheek van JavaScript van SDK van het Web bij te werken.
exl-id: 9c771d6c-4cfa-4929-9a79-881d4e8643e4
source-git-commit: f8d8eb722e7b5cc4371f400a76fbd548a1318668
workflow-type: tm+mt
source-wordcount: '2589'
ht-degree: 0%

---


# Werk uw bibliotheek van de gegevensinzameling voor Audience Manager van de AppMeasurement JavaScript bibliotheek aan de bibliotheek van de JavaScript van SDK van het Web bij

## Beoogd publiek {#intended-audience}

Deze pagina is bestemd voor Audience Manager- en Adobe Analytics-klanten die de JavaScript-bibliotheek van [!DNL AppMeasurement] gebruiken om webgegevens naar de Audience Manager te verzenden.

Verwijs naar de lijst hieronder voor hulp bij migratiestappen aan Web SDK, afhankelijk van uw huidige methode van de gegevensinzameling.

| Uw bestaande gegevensverzamelingsmethode | Web SDK-migratieinstructies |
|---------|----------|
| [!DNL AppMeasurement] JavaScript-bibliotheek | Volg de instructies in deze handleiding. |
| [!DNL Audience Manager] [ markeringsuitbreiding ](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/audience-manager/overview) | Volg de instructies in [ het bijwerken van uw bibliotheek van de gegevensverzameling van de de markeringsuitbreiding van de Audience Manager aan de de markeringsuitbreiding van SDK van het Web ](dil-extension-to-web-sdk.md). |
| [!DNL AppMeasurement] de bibliotheek van JavaScript + [!DNL Audience Manager] [ DIL bibliotheek ](../dil/dil-overview.md) | Volg de instructies in [ het bijwerken van uw bibliotheek van de gegevensverzameling van de de markeringsuitbreiding van de Audience Manager aan de de markeringsuitbreiding van SDK van het Web ](dil-extension-to-web-sdk.md). |

## Migratieoverzicht {#overview}

Het migreren van [!DNL AppMeasurement] aan [ SDK van het Web ](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/home) is hoofdzakelijk een migratie van Adobe Analytics. Voor klanten van de Audience Manager, omvat deze migratie ook Audience Manager. Beide moeten samen worden gemigreerd. Als u voornamelijk met Audience Manager werkt, dient u het Analyseteam bij deze migratie te betrekken.

Als u [!DNL AppMeasurement] gebruikt voor het verzamelen van gegevens van Audience Managers, gebruikt u momenteel de [!DNL Server-side Forwarding (SSF)] -benadering om analysegegevens naar de Audience Manager te verzenden. In deze opstelling, door:sturen het verzoek van de gegevensinzameling van de Analyse aan Audience Manager, die ook de reactie van de Audience Manager op de pagina behandelt.

Dit is al vele jaren de standaardbenadering en is waarschijnlijk uw huidige opstelling. Als uw [!DNL AppMeasurement] bibliotheek de `AudienceManagement` module bevat en uw vraag van de gegevensinzameling `/10/` weg in het verzoek (`/b/ss/examplereportsuite/10/`) omvat, dan is deze gids voor u.

## Server-side Forwarding (SSF) versus Web SDK gegevensstromen {#data-flows}

Kennis van de verschillen in gegevensstroom tussen Analytics en Audience Manager bij de overgang naar Web SDK (en de Edge Network) is van cruciaal belang voor de onderstaande instructies.

Met server-kant door:sturen, verzamelt de regionale knoop van de gegevensinzameling van Analytics de gegevens, transformeert het in een signaal dat door Audience Manager wordt goedgekeurd, verzendt het naar Audience Manager, en keert de reactie van de Audience Manager op de pagina terug. De module [!DNL AudienceManagement] in de [!DNL AppMeasurement] -bibliotheek handelt vervolgens het antwoord af (bijv. het neerzetten van cookies, het verzenden van URL-doelen). Dit proces wordt genoemd server-kant door:sturen omdat de Analytics de gegevens aan Audience Manager door:sturen gebruikend de servers van de Adobe.

Met Web SDK, verzendt de Edge Network gegevens naar Analytics en Audience Manager in afzonderlijke acties. SDK van het Web is één enkele bibliotheek die gegevens naar alle oplossingen verzendt, en de Edge Network zet oplossing-agnostische gegevenspunten in oplossing-specifieke formaten om.

In deze nieuwe gegevensstroom, wordt al gegeven verzonden naar een Edge Network [ datastream ](https://experienceleague.adobe.com/en/docs/experience-platform/datastreams/overview), die u [ kunt ](https://experienceleague.adobe.com/en/docs/experience-platform/datastreams/configure) vormen om gegevens naar de oplossingen van de Adobe te verzenden zoals nodig. Voor Audience Manager, transformeert het toelaten van de dienst van de Audience Manager op de gegevensstroom [!DNL XDM] en de gegevens van de Analyse in signalen die door Audience Manager worden aanvaard. De Edge Network retourneert ook de reactie van de Audience Manager op de pagina, waar de Web SDK de reactie verwerkt, vergelijkbaar met hoe [!DNL AppMeasurement] en de module [!DNL AudienceManagement] .

## Migratie van tags en niet-labels {#tags-vs-non-tags}

Of u nu Tags gebruikt met de extensie [!DNL AppMeasurement] , de [!DNL AppMeasurement] -bibliotheek in een ander tagbeheersysteem of [!DNL AppMeasurement] rechtstreeks op de pagina plaatst, de stappen voor het migreren van Audience Manager naar de Web SDK zijn hetzelfde. Aangezien de migratie van Audience Managers afhankelijk is van de migratie van Analytics, worden de stappen voor het migreren van [!DNL AppMeasurement] naar Web SDK tijdens de migratie van Analytics bepaald.

Die informatie wordt behandeld in de documentatie van Analytics voor [ Markeringen ](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/web-sdk/analytics-extension-to-web-sdk) of [ op JavaScript ](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/web-sdk/appmeasurement-to-web-sdk) gebaseerde implementaties.

## XDM en de `data.__adobe.` knooppunten {#xdm-data-nodes}

Één van de belangrijkste functies van [ SDK van het Web ](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/home) moet gegevens naar [ Real-time Customer Data Platform (RTCDP) ](https://experienceleague.adobe.com/en/docs/experience-platform/rtcdp/home) verzenden. Om dit te bereiken en nog gegevens voor andere Oplossingen van het Experience Cloud zonder volledige re-implementatie te verzamelen, worden de oplossing-specifieke gegevens verdeeld binnen de de servervraag van de gegevensinzameling. Deze vraag gebruikt een gestandaardiseerd schema JSON genoemd het [ Model van de Gegevens van de Ervaring (XDM) ](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/home)

Oplossing-agnostische elementen, zoals informatie over browser en apparaat, worden verzonden naar de Edge Network in een vooraf bepaalde structuur XDM. De Edge Network zet deze gegevens in oplossing-specifieke formaten om. Gegevens die specifiek zijn voor Doel, Analytics en Audience Manager worden echter opgeslagen in een toegewezen `data.__adobe` -knooppunt binnen de XDM-payload.

Bijvoorbeeld:

* De variabele Analytics `s.eVar1` wordt vertegenwoordigd in de XDM-payload als `data.__adobe.analytics.evar1` .
* Een parameter van het Doel met betrekking tot de status van de klantenloyaliteit wordt opgeslagen als `data.__adobe.target.loyaltyStatus`.

De gegevens in de `__adobe` knoop worden verzonden naar de respectieve oplossingen (zoals Analytics en Audience Manager) zonder worden verzonden naar Experience Platform, zelfs als de dienst van het Experience Platform op de datastream wordt toegelaten. Dit betekent u uw huidige configuraties voor Analytics en Audience Manager kunt houden terwijl het hebben van de flexibiliteit om het even welke noodzakelijke gegevenselementen aan XDM schemaelementen voor real time gebruiksgevallen in Experience Platform in kaart te brengen gebruikend [ Prep van Gegevens voor de Inzameling van Gegevens ](https://experienceleague.adobe.com/en/docs/experience-platform/datastreams/data-prep).

De tekenreeks Analytics `s.products` , die tijdens het uitchecken wordt gebruikt om de inhoud van het winkelwagentje te rapporteren, kan nog steeds in de oorspronkelijke indeling naar Analytics en Audience Manager worden verzonden. Tegelijkertijd kunt u de elementen van deze tekenreeks gebruiken om intuïtievere XDM-cartschema&#39;s te maken voor het gebruik van Experience Platforms.

Aangezien de meeste implementaties van de Audience Manager op de gegevens baseren die van Analytics aan Audience Manager worden doorgestuurd, zijn veel van uw uitdrukkingen van het de trekkengedrag van de Audience Manager waarschijnlijk gebaseerd op de variabelen van de Analytics (`c_evar#`, `c_prop#`, en `c_events`). Om het opnieuw samenstellen van eigenschapuitdrukkingen te vermijden gebruikend formaten XDM tijdens migratie, wordt de Edge Network gevormd door gebrek om het even welke variabelen te transformeren die van Analytics in de `data.__adobe.analytics` knoop in Audience Manager signalen worden gevonden. Dit proces is gelijkaardig aan server-kant het door:sturen werkschema.

De Edge Network kan deze transformatie uitvoeren omdat één enkele vraag van de gegevensinzameling van de pagina wordt verzonden naar één enkele gegevensstroom die veelvoudige oplossingen van de Adobe van voer voorziet. Daarom zullen de meeste migraties van [!DNL AppMeasurement] naar Web SDK voor zowel Analytics als Audience Manager hoofdzakelijk het `data.__adobe.analytics` knooppunt gebruiken.

De Edge Network transformeert apparaat- en browsergegevens van de XDM-payload en pakketheaders naar Audience Manager signalen. Op deze manier kunt u `h_` - en `d_` -platformtoetsen blijven gebruiken in Audience Manager trait-expressies.

## The `data.__adobe.audiencemanager` node {#data-note}

Het knooppunt `data.__adobe.audiencemanager` wordt gebruikt voor Audience Manager-implementaties die niet afhankelijk zijn van Analytics. Het slaat de sleutel/waardeparen van de douaneAudience Manager op die eerder via de ](../dil/dil-overview.md) bibliotheek 0} DIL {werden verzonden, zoals die in de [ gids van de de migratieuitbreiding van de markeringsuitbreiding ](dil-extension-to-web-sdk.md) wordt beschreven.[

Hoewel het knooppunt `data.__adobe.audiencemanager` niet nodig is voor de migratie die in deze handleiding wordt beschreven, staat de nieuwe gegevensstroom die hier wordt beschreven toe dat gegevens naar de Audience Manager worden verzonden zonder dat deze worden opgenomen in Analytics.

Als u een aangepast sleutel-/waardepaar naar de Audience Manager moet sturen zonder dit in Analytics op te nemen, kunt u het knooppunt `data.__adobe.audiencemanager` gebruiken. Om het even welke gegevensreeks in deze knoop zal aan de Audience Manager-getransformeerde gegevens van Analytics in de de servervraag van de gegevensinzameling worden toegevoegd.

## Voordelen en nadelen van dit implementatiepad

Het gebruik van deze migratiebenadering heeft zowel voor- als nadelen. Let zorgvuldig op elke optie om te bepalen welke benadering het beste is voor uw organisatie.

| Voordelen | Nadelen |
| --- | --- |
| <ul><li>**gebruikt uw bestaande implementatie**: Terwijl deze benadering sommige implementatieveranderingen vereist, vereist het geen volledig nieuwe implementatie van kras. U kunt uw bestaande gegevenslaag en code met minimale veranderingen in implementatielogica gebruiken.</li><li>**vereist geen schema**: voor dit stadium van het migreren aan het Web SDK, hebt u geen schema XDM nodig. In plaats daarvan kunt u het object `data` vullen, dat gegevens rechtstreeks naar de Audience Manager verzendt. Zodra de migratie naar SDK van het Web volledig is, dan kunt u een schema voor uw organisatie tot stand brengen en gegevensstroomafbeelding gebruiken om toepasselijke gebieden te bevolken XDM. Als een schema in dit stadium van het migratieproces werd vereist, zou uw organisatie worden gedwongen om een Audience Manager XDM schema te gebruiken. Het gebruik van dit schema maakt het voor uw organisatie moeilijker om uw eigen schema in de toekomst te gebruiken.</li></ul> | <ul><li>**Technische schuld van de Implementatie**: Aangezien deze benadering een gewijzigde vorm van uw bestaande implementatie gebruikt, kan het moeilijker zijn om implementatielogica te volgen en veranderingen in de toekomst uit te voeren wanneer nodig.</li><li>**vereist afbeelding om gegevens naar Platform** te verzenden: Wanneer uw organisatie klaar is om Real-Time CDP te gebruiken, moet u gegevens naar een gegevensreeks in Adobe Experience Platform verzenden. Deze actie vereist dat elk gebied in het `data` voorwerp een ingang in het hulpmiddel is van de gegevenstoewijzing dat het aan een XDM schemagebied toewijst. Voor deze workflow hoeft u slechts één keer toewijzingen uit te voeren, en dit betekent niet dat u implementatiewijzigingen aanbrengt. Het is echter een extra stap die niet vereist is bij het verzenden van gegevens in een XDM-object.</li></ul> |

De Adobe beveelt aan dit implementatiepad in de volgende scenario&#39;s te volgen:

* U hebt een bestaande implementatie met de Adobe Analytics AppMeasurement JavaScript-bibliotheek. Als u een implementatie gebruikend de de markeringsuitbreiding van de Audience Manager hebt, volg [ Migrate van de de markeringsuitbreiding van de Audience Manager aan de de markeringsuitbreiding van SDK van het Web ](dil-extension-to-web-sdk.md) in plaats daarvan.
* U bent van plan om Real-Time CDP in de toekomst te gebruiken, maar wilt niet uw implementatie van de Audience Manager met een implementatie van SDK van het Web van kras vervangen. Het vervangen van uw implementatie van kras op het Web SDK vereist de meeste inspanning, maar ook biedt de meest levensvatbare implementatiearchitectuur op lange termijn aan. Als uw organisatie bereid is door de inspanning van een schone implementatie van SDK van het Web te gaan, zie de [ documentatie van SDK van het Web ](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/home) voor meer details.

## Stappen vereist om naar SDK van het Web te migreren

Volg de stappen hieronder om uw integratie van de gegevensinzameling aan Web SDK te migreren.

+++**1. Migreer uw implementatie van Analytics**.

Het werk met uw team van Analytics om de stappen voor de migratie van Analytics in of de [ Codes ](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/web-sdk/analytics-extension-to-web-sdk) of [ op JavaScript ](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/web-sdk/appmeasurement-to-web-sdk) gebaseerde implementaties te volgen. Nadat u de implementatie van Analytics hebt gemigreerd, gaat u verder naar de volgende stap.

+++

+++**2. Voeg de dienst van de Audience Manager aan de datastream** toe

Voeg de dienst van de Audience Manager aan de gegevensstroom toe die u tijdens stap 1 creeerde.

1. Navigeer aan [ experience.adobe.com ](https://experience.adobe.com) en login gebruikend uw geloofsbrieven.
1. Gebruik de startpagina of de productkiezer rechtsboven om naar **[!UICONTROL Data Collection]** te navigeren.
1. Selecteer **[!UICONTROL Datastreams]** in de linkernavigatie.
1. Selecteer de gegevensstroom die u als deel van uw migratie Analytics in stap 1 creeerde.
1. Selecteer **[!UICONTROL Add Service]** .
1. Selecteer **[!UICONTROL Audience Manager]** in het vervolgkeuzemenu voor de service.
1. Controleer de opties **[!UICONTROL Cookie Destinations Enabled]** en **[!UICONTROL URL Destinations Enabled]** . Met deze opties kan de Edge Network deze doeltypen van de Audience Manager terugzetten naar de pagina.
1. Zorg ervoor dat **[!UICONTROL Enable XDM Flattened Fields]** is uitgeschakeld. Met deze optie schakelt u de automatische omzetting van analysevariabelen in Audience Manager-signalen uit. Deze optie is ontworpen om achterwaartse compatibiliteit te behouden voor gebruikers die naar Web SDK migreerden voordat de Edge Network de analysegegevens automatisch transformeerde naar Audience Manager signalen.

   >[!NOTE]
   >
   >Het migreren naar Web SDK met **[!UICONTROL Enabled XDM Flattened Fields]** toegelaten optie vereist dat om het even welke gegevens nodig in Audience Manager die als XDM wordt geformatteerd en alle Audience Manager die steunen, eVars, of gebeurtenissen gebruikt worden bijgewerkt om in plaats daarvan XDM-Geformatteerde gegevens te zoeken. Adobe raadt aan deze optie uit te schakelen.


   ![ voeg de dienst van de Audience Manager ](assets/add-service.png) toe {style="border:1px solid lightslategray"}

1. Selecteer **[!UICONTROL Save]** om de configuratie van de gegevensstroom op te slaan.

Uw gegevensstroom is nu klaar om gegevens te ontvangen en door te geven aan Audience Manager. Noteer de gegevensstroom-id, aangezien deze id vereist is voor het configureren van de Web SDK in code.

+++

+++**3. Laat de Syncs van identiteitskaart van derden toe en plaats identiteitskaart van de Container van de Audience Manager**

1. Navigeer aan [ experience.adobe.com ](https://experience.adobe.com) en login gebruikend uw geloofsbrieven.
1. Gebruik de startpagina of de productkiezer rechtsboven om naar **[!UICONTROL Data Collection]** te navigeren.
1. Selecteer **[!UICONTROL Datastreams]** in de linkernavigatie.
1. Selecteer de gegevensstroom die u als deel van uw migratie Analytics in stap 1 creeerde.
1. Selecteer **[!UICONTROL Edit]** in de rechterbovenhoek van de configuratiepagina voor de gegevensstroom.
1. Vouw het vervolgkeuzemenu **[!UICONTROL Advanced Options]** uit en schakel de functie **[!UICONTROL Third Party ID Sync]** in als dit nog niet is ingeschakeld. Deze optie vertelt de Edge Network om de Syncs van identiteitskaart van de Partner voor Audience Manager en de gegevenspartners van het Experience Platform terug te keren.

   ![ laat de synchronisatie van derdeidentiteitskaart toe.](assets/third-party-id-sync.png) {style="border:1px solid lightslategray"}

1. In de meeste gevallen kunt u het veld **[!UICONTROL Third Party ID Sync Container ID]** leeg laten. De standaardwaarde is `0` . Als u er echter voor wilt zorgen dat de juiste container-id wordt gebruikt, voert u de volgende stappen uit:
   * Open een browservenster in de incognito- of privémodus en navigeer naar een pagina die deel uitmaakt van de migratie.
   * Gebruik de ontwikkelaarsgereedschappen van de browser om te filteren op de netwerkaanroep naar `dpm.demdex.net/id` . Deze oproep wordt alleen op de eerste pagina van een eerste bezoek afgespeeld. Daarom is een incognito of een privébrowser nodig.
   * Bekijk de lading van het verzoek. Als de parameter `d_nsid` anders is dan nul, kopieert u deze naar het veld **[!UICONTROL Third Party ID Sync Container ID]** .

1. Selecteer **[!UICONTROL Save]** .

Uw gegevensstroom is nu klaar om gegevens naar Audience Manager te verzenden en de reacties van de Audience Manager tot het Web SDK over te gaan.

+++

+++**4. Clientid&#39;s toevoegen aan het identiteitsoverzicht**

De meeste implementaties van de Audience Manager gebruiken [ Regels van de Fusie van het Profiel ](../features/profile-merge-rules/merge-rules-overview.md) in cross-device verpersoonlijkingsscenario&#39;s en helpen controleren welke segmentbezoekers voor afhankelijk van hun authentificatiestatus (het programma geopend of het programma geopend) kunnen kwalificeren. De Regels van de Fusie van het profiel vereisen een klant-eigendom herkenningsteken (identiteitskaart van CRM, rekeningsaantal, enz.) om aan Audience Manager op elke vraag van de gegevensinzameling na authentificatie worden verzonden. Eerder, werd de `setCustomerIDs` functie van de Dienst van identiteitskaart van de Bezoeker ([!DNL visitor.js]) gebruikt om klant IDs aan elke de gegevensverzamelingsvraag van de Analyse toe te voegen, die toen aan Audience Manager werd doorgestuurd.

Met het Web SDK, moeten deze identiteiten nu naar de Edge Network worden verzonden gebruikend een speciale constructie XDM genoemd [ IdentityMap ](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/field-groups/profile/identitymap).

Het overgaan van identiteiten correct in een identiteitskaart vereist begrip [ identiteitsnamespaces ](https://experienceleague.adobe.com/en/docs/experience-platform/identity/features/namespaces) en zorgvuldig het overwegen van welke identiteiten om over te gaan, vooral wanneer het verzenden van gegevens naar een zandbak van het Experience Platform. [ dit artikel ](https://experienceleague.adobe.com/en/docs/experience-cloud-kcs/kbarticles/ka-21305) schetst deze overwegingen en instructies.

Zodra u bepaalt welke identiteiten om over te gaan en wanneer, de gidsen voor het gebruiken van het [!UICONTROL Identity map] **[!UICONTROL Identity map]** [ gegevenselement ](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/web-sdk/data-element-types#identity-map) binnen Markeringen volgt of manueel het zoals geschetst in het [ overzicht van identiteitsgegevens ](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/identity/overview) om met uw de plaatsingsstrategie van SDK van het Web te richten.

+++

## Server-Side Forwarding en Audience Analytics configureren in de gebruikersinterface van Analytics Report Suite Manager {#configure-ssf-analytics}

Als u met Analytics [ server-kant het door:sturen ](https://experienceleague.adobe.com/en/docs/analytics/admin/admin-tools/manage-report-suites/edit-report-suite/report-suite-general/server-side-forwarding/ssf) eigenschap vertrouwd bent, zou u zich kunnen afvragen: &quot;*zou ik server-kant het door:sturen van onbruikbaar maken die in de Manager UI van de Manager UI van de Reeks van het Rapport van Analytics plaatst om het verzenden van de gegevens van Analytics naar Audience Manager tweemaal te verhinderen?*&quot;.

Het antwoord is nee. Schakel deze instelling niet uit. Dit is de reden waarom:

Wanneer deze instelling is ingeschakeld en de module [!DNL AudienceManagement] wordt toegevoegd aan de [!DNL AppMeasurement] -bibliotheek op de pagina, worden alle gegevens die naar die rapportsuite worden verzonden ook naar de Audience Manager verzonden.

Om te voldoen aan de privacyregels van de GDPR, zijn er scenario&#39;s waar gegevens in Analytics maar niet in Audience Manager kunnen worden verzameld. Daarnaast zijn er gevallen met betrekking tot wereldwijde rapporteringssuites en regiospecifieke gebruiksgevallen waarin sommige uitnodigingen voor het verzamelen van gegevens niet naar de Audience Manager moeten worden gestuurd. Om dit op te lossen, introduceerde de Adobe een server-kant door:sturen &quot;van knoop&quot;.

Zoals verklaard in de [ Analytics en GDPR nalevingspagina die op server-zij het door:sturen ](https://experienceleague.adobe.com/en/docs/analytics/admin/admin-tools/manage-report-suites/edit-report-suite/report-suite-general/server-side-forwarding/ssf-gdpr) wordt geconcentreerd, verhindert het toevoegen van de `cm.ssf=1` contextvariabele aan een server van de de gegevensinzameling van de Analyse dat de vraag van de gegevensinzameling aan Audience Manager door:sturen.

Er zijn twee redenen waarom u deze instelling niet moet uitschakelen.

1. Wanneer de dienst van de Audience Manager op een gegevensstroom wordt toegelaten, voegt de Edge Network `cm.ssf` variabele aan alle verzoeken van de gegevensinzameling toe die naar Analytics worden verzonden. Hierdoor worden de analysegegevens niet ook naar de Audience Manager verzonden. In alle Assurance-logboeken die worden gebruikt om de migratie van Analytics te valideren, wordt de variabele `cm.ssf=1` weergegeven wanneer de service Audience Manager is ingeschakeld in de gegevensstroom.
1. Met deze instelling wordt ook de gegevensstroom ingeschakeld voor de [!DNL Audience Analytics] -integratie. Zoals die in het [ overzicht van het Audience Analytics ](https://experienceleague.adobe.com/en/docs/analytics/integration/audience-analytics/mc-audiences-aam) wordt geschetst, server-zij door:sturen wordt vereist voor deze integratie omdat de reactie van de Audience Manager op de server van de de gegevensinzameling van de Analyse aan de Bevolking van Analytics alvorens verwerking wordt toegevoegd. Een gelijkaardig proces komt binnen de Edge Network voor. Wanneer server-zij het door:sturen wordt toegelaten, voegt de Edge Network de noodzakelijke segmenten van de reactie van de Audience Manager aan de gegevens toe die naar Analytics worden verzonden.

Samenvattend, is het belangrijk dat dit het plaatsen wordt toegelaten zodat het Audience Analytics met een implementatie van SDK van het Web blijft functioneren en geen gegevens in Audience Manager zullen worden dubbel-geteld.
