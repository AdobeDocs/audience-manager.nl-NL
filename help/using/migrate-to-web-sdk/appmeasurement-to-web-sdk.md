---
title: Werk uw gegevensverzamelingsbibliotheek voor Audience Manager bij van de AppMeasurement JavaScript-bibliotheek naar de Web SDK JavaScript-bibliotheek.
description: Begrijp de stappen om uw bibliotheek van de gegevensinzameling voor Audience Manager van de bibliotheek van AppMeasurement JavaScript aan de bibliotheek van SDK van het Web bij te werken JavaScript.
exl-id: 9c771d6c-4cfa-4929-9a79-881d4e8643e4
source-git-commit: f180e423d4bdf5535d8dcc000e1d0f908bc54d7b
workflow-type: tm+mt
source-wordcount: '3385'
ht-degree: 0%

---


# Werk uw gegevensverzamelingsbibliotheek bij voor Audience Manager van AppMeasurement naar Web SDK

## Beoogd publiek {#intended-audience}

Deze pagina is bestemd voor Audience Manager- en Adobe Analytics-klanten die de [!DNL AppMeasurement] JavaScript-bibliotheek gebruiken om webgegevens naar Audience Manager te verzenden.

Raadpleeg de onderstaande tabel voor hulp bij migratiestappen naar Web SDK, afhankelijk van uw huidige methode voor gegevensverzameling.

| Uw bestaande gegevensverzamelingsmethode | Web SDK-migratieinstructies |
|---------|----------|
| [!DNL AppMeasurement] JavaScript-bibliotheek met de module AudienceManagement | Volg de instructies in deze handleiding. |
| [!DNL Audience Manager] [&#x200B; markeringsuitbreiding &#x200B;](https://experienceleague.adobe.com/nl/docs/experience-platform/tags/extensions/client/audience-manager/overview) | Volg de instructies in [&#x200B; het bijwerken van uw bibliotheek van de gegevensverzameling van de de markeringsuitbreiding van Audience Manager aan de de markeringsuitbreiding van SDK van het Web &#x200B;](dil-extension-to-web-sdk.md). |
| [!DNL AppMeasurement] de bibliotheek van JavaScript + standalone [!DNL Audience Manager] [&#x200B; bibliotheek van DIL &#x200B;](../dil/dil-overview.md) | Volg de instructies in [&#x200B; het bijwerken van uw bibliotheek van de gegevensverzameling van de de markeringsuitbreiding van Audience Manager aan de de markeringsuitbreiding van SDK van het Web &#x200B;](dil-extension-to-web-sdk.md). |

## Migratieoverzicht {#overview}

Het migreren van [!DNL AppMeasurement] aan [&#x200B; SDK van het Web &#x200B;](https://experienceleague.adobe.com/nl/docs/experience-platform/web-sdk/home) is hoofdzakelijk een migratie van Adobe Analytics. Voor Audience Manager-klanten omvat deze migratie ook Audience Manager. Beide moeten samen worden gemigreerd. Als u voornamelijk met Audience Manager werkt, dient u het Analyseteam bij deze migratie te betrekken.

Als u [!DNL AppMeasurement] gebruikt voor Audience Manager-gegevensverzameling, gebruikt u momenteel de [!DNL Server-side Forwarding (SSF)] -aanpak om analysegegevens naar Audience Manager te verzenden. In deze opstelling, door:sturen het de gegevensverzamelingsverzoek van Analytics aan Audience Manager, die ook de reactie van Audience Manager op de pagina behandelt.

Dit is al vele jaren de standaardbenadering en is waarschijnlijk uw huidige opstelling. Als uw [!DNL AppMeasurement] bibliotheek de `AudienceManagement` module bevat en uw vraag van de gegevensinzameling `/10/` weg in het verzoek (`/b/ss/examplereportsuite/10/`) omvat, dan is deze gids voor u.

## Server-side Forwarding (SSF) versus Web SDK gegevensstromen {#data-flows}

Kennis van de verschillen in gegevensstroom tussen Analytics en Audience Manager bij de overgang naar Web SDK (en de Edge Network) is van cruciaal belang voor de onderstaande instructies.

Met server-kant door:sturen, verzamelt de regionale knoop van de gegevensinzameling van Analytics de gegevens, transformeert het in een signaal dat door Audience Manager wordt goedgekeurd, verzendt het naar Audience Manager, en keert de reactie van Audience Manager op de pagina terug. De module [!DNL AudienceManagement] in de [!DNL AppMeasurement] -bibliotheek handelt vervolgens het antwoord af (bijv. het neerzetten van cookies, het verzenden van URL-doelen). Dit proces wordt server-side het door:sturen genoemd omdat de Analytics de gegevens aan Audience Manager door:sturen gebruikend de servers van Adobe.

Met Web SDK verzendt de Edge Network gegevens naar Analytics en Audience Manager in afzonderlijke acties. Het Web SDK is één enkele bibliotheek die gegevens naar alle oplossingen verzendt, en Edge Network zet oplossing-agnostische gegevenspunten in oplossing-specifieke formaten om.

In deze nieuwe gegevensstroom, worden alle gegevens verzonden naar een Edge Network [&#x200B; datastream &#x200B;](https://experienceleague.adobe.com/nl/docs/experience-platform/datastreams/overview), die u [&#x200B; kunt vormen &#x200B;](https://experienceleague.adobe.com/nl/docs/experience-platform/datastreams/configure) om gegevens naar de oplossingen van Adobe te verzenden zoals nodig. Voor Audience Manager transformeert het inschakelen van de Audience Manager-service op de gegevensstroom [!DNL XDM] en analysegegevens naar signalen die door Audience Manager worden geaccepteerd. De Edge Network geeft ook het Audience Manager-antwoord op de pagina, waar de Web SDK het antwoord verwerkt, vergelijkbaar met hoe [!DNL AppMeasurement] en de module [!DNL AudienceManagement] .

## Migratie van tags en niet-labels {#tags-vs-non-tags}

Of u nu Tags gebruikt met de extensie [!DNL AppMeasurement] , de [!DNL AppMeasurement] -bibliotheek in een ander tagbeheersysteem of [!DNL AppMeasurement] rechtstreeks op de pagina plaatst, de stappen voor het migreren van Audience Manager naar Web SDK zijn hetzelfde. Aangezien de migratie van Audience Manager afhankelijk is van de migratie van Analytics, worden de stappen voor het migreren van [!DNL AppMeasurement] naar Web SDK tijdens de migratie van Analytics bepaald.

Die informatie wordt behandeld in de documentatie van Analytics voor [&#x200B; Markeringen &#x200B;](https://experienceleague.adobe.com/nl/docs/analytics/implementation/aep-edge/web-sdk/analytics-extension-to-web-sdk) of [&#x200B; op JavaScript &#x200B;](https://experienceleague.adobe.com/nl/docs/analytics/implementation/aep-edge/web-sdk/appmeasurement-to-web-sdk) gebaseerde implementaties.

## XDM en de `data.__adobe.` knooppunten {#xdm-data-nodes}

Één van de belangrijkste functies van het [&#x200B; Web SDK &#x200B;](https://experienceleague.adobe.com/nl/docs/experience-platform/web-sdk/home) moet gegevens naar [&#x200B; Real-Time Customer Data Platform (RTCDP) verzenden &#x200B;](https://experienceleague.adobe.com/nl/docs/experience-platform/rtcdp/home). Om dit te bereiken en nog gegevens voor andere Oplossingen van Experience Cloud zonder volledige re-implementatie te verzamelen, worden de oplossing-specifieke gegevens verdeeld binnen de de servervraag van de gegevensinzameling. Deze vraag gebruikt een gestandaardiseerd schema JSON genoemd het [&#x200B; Model van de Gegevens van de Ervaring (XDM) &#x200B;](https://experienceleague.adobe.com/nl/docs/experience-platform/xdm/home)

Oplossing-agnostische elementen, zoals informatie over browser en apparaat, worden verzonden naar Edge Network in een vooraf bepaalde structuur XDM. De Edge Network transformeert deze gegevens naar specifieke oplossingen. Gegevens die specifiek zijn voor Doel, Analytics en Audience Manager, worden echter opgeslagen in een toegewezen `data.__adobe` -knooppunt binnen de XDM-payload.

Bijvoorbeeld:

* De variabele Analytics `s.eVar1` wordt vertegenwoordigd in de XDM-payload als `data.__adobe.analytics.evar1` .
* Een parameter van het Doel met betrekking tot de status van de klantenloyaliteit wordt opgeslagen als `data.__adobe.target.loyaltyStatus`.

Gegevens in het knooppunt `__adobe` worden naar de respectievelijke oplossingen verzonden (zoals Analytics en Audience Manager) zonder dat ze naar Experience Platform worden verzonden, zelfs als de Experience Platform-service op de datastream is ingeschakeld. Dit betekent u uw huidige configuraties voor Analytics en Audience Manager kunt houden terwijl het hebben van de flexibiliteit om het even welke noodzakelijke gegevenselementen aan XDM schemaelementen voor gebruiksgevallen in real time in Experience Platform in kaart te brengen gebruikend [&#x200B; Prep van Gegevens voor de Inzameling van Gegevens &#x200B;](https://experienceleague.adobe.com/nl/docs/experience-platform/datastreams/data-prep).

De Analytics `s.products` -tekenreeks, die tijdens het uitchecken wordt gebruikt om de inhoud van winkelwagentjes te rapporteren, kan nog steeds in de oorspronkelijke indeling naar Analytics en Audience Manager worden verzonden. Tegelijkertijd kunt u de elementen van deze tekenreeks gebruiken om intuïtievere XDM-cartschema&#39;s te maken voor Experience Platform-gebruiksgevallen.

Aangezien de meeste Audience Manager-implementaties afhankelijk zijn van analysegegevens die naar Audience Manager worden doorgestuurd, zijn veel van uw Audience Manager-standaardexpressies waarschijnlijk gebaseerd op analytische variabelen (`c_evar#`, `c_prop#` en `c_events` ). Om te voorkomen dat tekenreeksexpressies tijdens de migratie opnieuw worden opgebouwd met XDM-indelingen, is de Edge Network standaard geconfigureerd om alle variabelen van Analytics die in het knooppunt `data.__adobe.analytics` worden gevonden, om te zetten in Audience Manager-signalen. Een gelijkaardig transformatieproces gebeurt in de server-kant het door:sturen werkschema.

De Edge Network kan deze transformatie uitvoeren omdat één aanroep voor gegevensverzameling van de pagina wordt verzonden naar één gegevensstroom die meerdere Adobe-oplossingen voedt. Daarom zullen de meeste migraties van [!DNL AppMeasurement] naar Web SDK voor zowel Analytics als Audience Manager voornamelijk het knooppunt `data.__adobe.analytics` gebruiken.

De Edge Network transformeert apparaat- en browsergegevens van de XDM-payload en pakketheaders naar Audience Manager-signalen. Op deze manier kunt u de platformtoetsen `h_` en `d_` blijven gebruiken in Audience Manager trait-expressies.

## The `data.__adobe.audiencemanager` node {#data-note}

Het knooppunt `data.__adobe.audiencemanager` wordt gebruikt voor Audience Manager-implementaties die niet afhankelijk zijn van Analytics. Het slaat de sleutel/waardeparen van douaneAudience Manager op die eerder via de [&#x200B; bibliotheek van DIL &#x200B;](../dil/dil-overview.md) werden verzonden, zoals die in de [&#x200B; de migratiegids van de markeringsuitbreiding &#x200B;](dil-extension-to-web-sdk.md) wordt beschreven.

Hoewel het knooppunt `data.__adobe.audiencemanager` niet nodig is voor de migratie die in deze handleiding wordt beschreven, kunnen met de nieuwe gegevensstroom die hier wordt beschreven gegevens naar Audience Manager worden verzonden zonder dat deze worden opgenomen in Analytics.

Als u een aangepast sleutel-/waardepaar naar Audience Manager moet sturen zonder dit in Analytics op te nemen, kunt u het knooppunt `data.__adobe.audiencemanager` gebruiken. Om het even welke gegevensreeks in deze knoop zal aan de Audience Manager-getransformeerde gegevens van Analytics in de de servervraag van de gegevensinzameling worden toegevoegd.

## Voordelen en nadelen van dit implementatiepad

Het gebruik van deze migratiebenadering heeft zowel voor- als nadelen. Let zorgvuldig op elke optie om te bepalen welke benadering het beste is voor uw organisatie.

| Voordelen | Nadelen |
| --- | --- |
| <ul><li>**gebruikt uw bestaande implementatie**: Terwijl deze benadering sommige implementatieveranderingen vereist, vereist het geen volledig nieuwe implementatie van kras. U kunt uw bestaande gegevenslaag en code met minimale veranderingen in implementatielogica gebruiken.</li><li>**vereist geen schema**: voor dit stadium van het migreren aan het Web SDK, hebt u geen schema XDM nodig. In plaats daarvan kunt u het object `data` vullen, dat gegevens rechtstreeks naar Audience Manager verzendt. Zodra de migratie naar het Web SDK volledig is, dan kunt u een schema voor uw organisatie tot stand brengen en gegevensstroomafbeelding gebruiken om toepasselijke gebieden te bevolken XDM. Als een schema in dit stadium van het migratieproces werd vereist, zou uw organisatie worden gedwongen om een Audience Manager XDM schema te gebruiken. Het gebruik van dit schema maakt het voor uw organisatie moeilijker om uw eigen schema in de toekomst te gebruiken.</li></ul> | <ul><li>**Technische schuld van de Implementatie**: Aangezien deze benadering een gewijzigde vorm van uw bestaande implementatie gebruikt, kan het moeilijker zijn om implementatielogica te volgen en veranderingen in de toekomst uit te voeren wanneer nodig.</li><li>**vereist afbeelding om gegevens naar Platform** te verzenden: Wanneer uw organisatie klaar is om Real-Time CDP te gebruiken, moet u gegevens naar een gegevensreeks in Adobe Experience Platform verzenden. Deze actie vereist dat elk gebied in het `data` voorwerp een ingang in het hulpmiddel is van de gegevenstoewijzing dat het aan een XDM schemagebied toewijst. Voor deze workflow hoeft u slechts één keer toewijzingen uit te voeren, en dit betekent niet dat u implementatiewijzigingen aanbrengt. Het is echter een extra stap die niet vereist is bij het verzenden van gegevens in een XDM-object.</li></ul> |

Adobe raadt u aan dit implementatiepad in de volgende scenario&#39;s te volgen:

* U hebt een bestaande implementatie met de Adobe Analytics AppMeasurement JavaScript-bibliotheek. Als u een implementatie gebruikend de de markeringsuitbreiding van Audience Manager hebt, volg [&#x200B; Migrate van de de markeringsuitbreiding van Audience Manager aan de de markeringsuitbreiding van SDK van het Web &#x200B;](dil-extension-to-web-sdk.md) in plaats daarvan.
* U wilt Real-Time CDP in de toekomst gebruiken, maar u wilt uw Audience Manager-implementatie niet vervangen door een geheel nieuwe Web SDK-implementatie. Het alternatief om uw implementatie helemaal vanaf het begin te vervangen door de Web SDK vereist de meeste moeite, aangezien u al uw Audience Manager-kenmerken opnieuw moet opbouwen om te zoeken naar XDM-opgemaakte gegevens. Het is echter ook de meest levensvatbare implementatiearchitectuur voor de lange termijn. Als uw organisatie bereid is door de inspanning van een schone implementatie van SDK van het Web te gaan, zie de [&#x200B; documentatie van SDK van het Web &#x200B;](https://experienceleague.adobe.com/nl/docs/experience-platform/web-sdk/home) in plaats van het gebruiken van deze gids, voor meer details.

## Stappen die nodig zijn voor migratie naar de Web SDK

Volg de onderstaande stappen om uw integratie van de gegevensverzameling naar Web SDK te migreren.

+++**1. Plan uw migratie van Analytics**.

Het werk met uw team van Analytics om de stappen voor de migratie van Analytics in of de [&#x200B; Codes &#x200B;](https://experienceleague.adobe.com/nl/docs/analytics/implementation/aep-edge/web-sdk/analytics-extension-to-web-sdk) of [&#x200B; op JavaScript &#x200B;](https://experienceleague.adobe.com/nl/docs/analytics/implementation/aep-edge/web-sdk/appmeasurement-to-web-sdk) gebaseerde implementaties te volgen. Nadat u de migratie naar Analytics hebt gepland, gaat u terug naar deze handleiding en gaat u verder met de Audience Manager-stappen om te bepalen wat u moet doen voor Audience Manager, zodat u de migratie naar Analytics en Audience Manager samen kunt implementeren.

+++

+++**2. Voeg de dienst van Audience Manager aan de datastream toe**

Voeg de Audience Manager-service toe aan de gegevensstroom die u gebruikt in de migratie Analytics die wordt vermeld in stap 1.

1. Navigeer aan [&#x200B; experience.adobe.com &#x200B;](https://experience.adobe.com) en login gebruikend uw geloofsbrieven.
1. Gebruik de startpagina of de productkiezer rechtsboven om naar **[!UICONTROL Data Collection]** te navigeren.
1. Selecteer **[!UICONTROL Datastreams]** in de linkernavigatie.
1. Selecteer de gegevensstroom die u als deel van uw migratie Analytics in stap 1 creeerde.
1. Selecteer **[!UICONTROL Add Service]** .
1. Selecteer **[!UICONTROL Audience Manager]** in het vervolgkeuzemenu voor de service.
1. Controleer de opties **[!UICONTROL Cookie Destinations Enabled]** en **[!UICONTROL URL Destinations Enabled]** . Met deze opties kan de Edge Network die Audience Manager-doeltypen terugsturen naar de pagina.
1. Zorg ervoor dat **[!UICONTROL Enable XDM Flattened Fields]** is uitgeschakeld. Met deze optie wordt de automatische transformatie van analytische variabelen in Audience Manager-signalen uitgeschakeld. Deze optie is ontworpen om achterwaartse compatibiliteit te behouden voor gebruikers die naar Web SDK migreerden voordat de Edge Network de analysegegevens automatisch transformeerde naar Audience Manager-signalen.

   >[!NOTE]
   >
   >Voor het migreren naar Web SDK met de optie **[!UICONTROL Enabled XDM Flattened Fields]** ingeschakeld moeten alle gegevens die nodig zijn in Audience Manager en die als XDM zijn opgemaakt, en alle Audience Manager-traits met behulp van props, eVars of gebeurtenissen worden bijgewerkt om in plaats daarvan te zoeken naar gegevens met XDM-opmaak. Adobe raadt aan deze optie uit te schakelen.


   ![&#x200B; voegt de dienst van Audience Manager &#x200B;](assets/add-service.png) {style="border:1px solid lightslategray"} toe

1. Selecteer **[!UICONTROL Save]** om de configuratie van de gegevensstroom op te slaan.

Uw gegevensstroom is nu klaar om gegevens te ontvangen en door te geven aan Audience Manager. Noteer de gegevensstroom-id, aangezien deze id vereist is voor het configureren van de Web SDK in code.

+++

+++**3. De Syncs van identiteitskaart van de derde toelaten en plaatsen identiteitskaart van de Container van Audience Manager**

1. Navigeer aan [&#x200B; experience.adobe.com &#x200B;](https://experience.adobe.com) en login gebruikend uw geloofsbrieven.
1. Gebruik de startpagina of de productkiezer rechtsboven om naar **[!UICONTROL Data Collection]** te navigeren.
1. Selecteer **[!UICONTROL Datastreams]** in de linkernavigatie.
1. Selecteer de gegevensstroom die u als deel van uw migratie Analytics in stap 1 creeerde.
1. Selecteer **[!UICONTROL Edit]** in de rechterbovenhoek van de configuratiepagina voor de gegevensstroom.
1. Vouw het vervolgkeuzemenu **[!UICONTROL Advanced Options]** uit en schakel de functie **[!UICONTROL Third Party ID Sync]** in als dit nog niet is ingeschakeld. Deze optie vertelt de Edge Network om de Syncs van identiteitskaart van de Partner voor Audience Manager en de gegevenspartners van Experience Platform terug te keren.

   ![&#x200B; laat de synchronisatie van derdeidentiteitskaart toe.](assets/third-party-id-sync.png) {style="border:1px solid lightslategray"}

1. In de meeste gevallen kunt u het veld **[!UICONTROL Third Party ID Sync Container ID]** leeg laten. De standaardwaarde is `0` . Als u er echter voor wilt zorgen dat de juiste container-id wordt gebruikt, voert u de volgende stappen uit:
   * Open een browservenster in de incognito- of privémodus en navigeer naar een pagina die deel uitmaakt van de migratie.
   * Gebruik de ontwikkelaarsgereedschappen van de browser om te filteren op de netwerkaanroep naar `dpm.demdex.net/id` . Deze oproep wordt alleen op de eerste pagina van een eerste bezoek afgespeeld. Daarom is een incognito of een privébrowser nodig.
   * Bekijk de lading van het verzoek. Als de parameter `d_nsid` anders is dan nul, kopieert u deze naar het veld **[!UICONTROL Third Party ID Sync Container ID]** .

1. Selecteer **[!UICONTROL Save]** .

Uw gegevensstroom is nu klaar om gegevens naar Audience Manager te verzenden en de Audience Manager-reacties door te geven aan de Web SDK.

+++

+++**4. Clientid&#39;s toevoegen aan het identiteitsoverzicht**

De meeste implementaties van Audience Manager gebruiken [&#x200B; Regels van de Fusie van het Profiel &#x200B;](../features/profile-merge-rules/merge-rules-overview.md) in cross-device verpersoonlijkingsscenario&#39;s en helpen controleren welke segmentbezoekers voor afhankelijk van hun authentificatiestatus (het programma geopend of het programma geopend) kunnen kwalificeren. De regels van de Fusie van het profiel vereisen een klant-eigendom herkenningsteken (identiteitskaart van CRM, rekeningsaantal, enz.) worden verzonden naar Audience Manager op elke vraag van de gegevensinzameling na authentificatie. Eerder, werd de `setCustomerIDs` functie van de Dienst van identiteitskaart van de Bezoeker ([!DNL visitor.js]) gebruikt om klant IDs aan elke de gegevensverzamelingsvraag van de Analyse toe te voegen, die toen aan Audience Manager werd doorgestuurd.

Met het Web SDK, moeten deze identiteiten nu naar Edge Network worden verzonden gebruikend een speciale constructie XDM genoemd [&#x200B; IdentityMap &#x200B;](https://experienceleague.adobe.com/nl/docs/experience-platform/xdm/field-groups/profile/identitymap).

Het overgaan van identiteiten correct in een identiteitskaart vereist begrip [&#x200B; identiteitsnamespaces &#x200B;](https://experienceleague.adobe.com/nl/docs/experience-platform/identity/features/namespaces) en zorgvuldig het overwegen van welke identiteiten om over te gaan, vooral wanneer het verzenden van gegevens naar een zandbak van Experience Platform. [&#x200B; dit artikel &#x200B;](https://experienceleague.adobe.com/nl/docs/experience-cloud-kcs/kbarticles/ka-21305) schetst deze overwegingen en instructies.

Zodra u bepaalt welke identiteiten om over te gaan en wanneer, de gidsen voor het gebruiken van het [!UICONTROL Identity map] **[!UICONTROL Identity map]** [&#x200B; gegevenselement &#x200B;](https://experienceleague.adobe.com/nl/docs/experience-platform/tags/extensions/client/web-sdk/data-element-types#identity-map) binnen Markeringen volgt of manueel het zoals geschetst in het [&#x200B; overzicht van identiteitsgegevens &#x200B;](https://experienceleague.adobe.com/nl/docs/experience-platform/web-sdk/identity/overview) om met uw de plaatsingsstrategie van SDK van het Web te richten.

+++

+++**5. (Optioneel) Stel het cookie van de eerste partij in `aam_uuid`**

Een standaardpraktijk voor vele jaren was het plaatsen van de Audience Manager UUID (de waarde in het demdex-cookie van derden) in een cookie van de eerste partij met de naam `aam_uuid` .

Als u de cookie wilt instellen, moet u een naam voor een cookie invoeren in het veld **[!UICONTROL Name]** van de sectie **[!UICONTROL Unique User ID Cookie]** van de tagextensie Analytics of het veld `uuidCookie` wanneer u de `audienceManagementModule` -component configureert. Terwijl algemeen gevormd in de code, werd het koekje zelden gebruikt omdat de waarde van Audience Manager UUID een apparaat-specifieke, dwars-domein herkenningsteken is dat door reclameplatforms wordt gebruikt en weinig waarde als eerste-partijherkenningsteken verstrekt.

Als uw implementatie vereist dat dit `aam_uuid` -cookie na de migratie naar Web SDK wordt ingesteld, kunt u de Audience Manager UUID op twee manieren ophalen.

1. Elke reactie van [&#x200B; Edge Network wisselt eindpunt &#x200B;](https://developer.adobe.com/data-collection-apis/docs/endpoints/interact/) in een nuttige lading met `id` knopen. Het knooppunt `id` van de naamruimte `CORE` bevat de Audience Manager UUID.

2. Gebruik het [&#x200B; getIdentity &#x200B;](https://experienceleague.adobe.com/nl/docs/experience-platform/web-sdk/commands/getidentity) bevel van het Web SDK om het terug te winnen. Gebruik de naamruimte `CORE` zoals wordt beschreven in de documentatie en haalt de waarde op uit het veld `identity.CORE` in de reactie.

Ongeacht de methode die wordt gebruikt om Audience Manager UUID terug te winnen, is het aan uw ontwikkelingsteam om de reactie te ontleden, UUID terug te winnen, en het koekje te plaatsen. Er is geen automatische manier om deze cookie in te stellen via de Web SDK.

+++

## Server-Side Forwarding en Audience Analytics configureren in de gebruikersinterface van Analytics Report Suite Manager {#configure-ssf-analytics}

Als u met Analytics [&#x200B; server-kant het door:sturen &#x200B;](https://experienceleague.adobe.com/nl/docs/analytics/admin/admin-tools/manage-report-suites/edit-report-suite/report-suite-general/server-side-forwarding/ssf) eigenschap vertrouwd bent, zou u zich kunnen afvragen: &quot;*zou ik server-kant het door:sturen van onbruikbaar maken het plaatsen in de Manager UI van de Manager UI van de Reeks van het Rapport Analytics om het verzenden van de gegevens van Analytics naar Audience Manager tweemaal te verhinderen?*&quot;.

Het antwoord is nee, u zou deze het plaatsen niet moeten onbruikbaar maken, om de volgende redenen:

1. Wanneer de Audience Manager-service op een gegevensstroom is ingeschakeld, voegt de Edge Network de variabele `cm.ssf` toe aan alle verzoeken voor gegevensverzameling die naar Analytics worden verzonden. Zo voorkomt u dat de analysegegevens ook naar Audience Manager worden verzonden. In alle Assurance-logboeken waarmee de migratie naar Analytics wordt gevalideerd, wordt de variabele `cm.ssf=1` weergegeven wanneer de Audience Manager-service op de gegevensstroom is ingeschakeld. Zie [&#x200B; Analytics en GDPR nalevingspagina die op server-kant het door:sturen &#x200B;](https://experienceleague.adobe.com/nl/docs/analytics/admin/admin-tools/manage-report-suites/edit-report-suite/report-suite-general/server-side-forwarding/ssf-gdpr) voor meer details wordt geconcentreerd.

1. Met deze instelling wordt ook de gegevensstroom ingeschakeld voor de [!DNL Audience Analytics] -integratie. Zoals die in het [&#x200B; overzicht van Audience Analytics &#x200B;](https://experienceleague.adobe.com/nl/docs/analytics/integration/audience-analytics/mc-audiences-aam) wordt geschetst, server-zijdoor:sturen wordt vereist voor deze integratie omdat de reactie van Audience Manager op de server van de de gegevensinzameling van de Analytics aan de klap Analytics alvorens verwerking wordt toegevoegd. Een soortgelijk proces doet zich voor in de Edge Network. Wanneer server-zij het door:sturen wordt toegelaten, voegt Edge Network de noodzakelijke segmenten van de reactie van Audience Manager aan de gegevens toe die naar Analytics worden verzonden.

Samenvattend, is het belangrijk dat dit het plaatsen wordt toegelaten zodat Audience Analytics met een implementatie van SDK van het Web blijft functioneren en geen gegevens zullen worden dubbel-geteld in Audience Manager.

## De migratie valideren {#validation}

Met alle oplossingen van Adobe die nu door één enkele vraag van SDK van het Web worden onderhouden, kunnen de stappen voor bevestiging afhankelijk van de oplossingen veranderen die SDK van het Web dient.

Als Adobe Target of Adobe Journey Optimizer (inclusief [!DNL Decisioning]) deel uitmaken van de oplossingsstack die door uw implementatie wordt onderhouden, hebt u op de pagina meerdere netwerkaanroepen naar de Edge Network. Sommige hiervan zijn bedoeld voor het ophalen van persoonlijke gegevens en aanbiedingen, terwijl andere bedoeld zijn voor het verzamelen en rapporteren van gegevens.

Ongeacht uw implementatie gelden de onderstaande algemene principes voor het valideren van de juiste gegevensstroom van en naar Audience Manager via Web SDK.

1. De eerste netwerkaanroep voor een eerste pagina, eerste bezoeker, gaat naar het `adobedc.demdex.net` -domein en het `/interact` -eindpunt. U kunt de netwerkvraag zien die door Web SDK wordt gemaakt door het ontwikkelaarlusje op uw Webbrowser te openen, het lusje van het Netwerk te klikken, en dan het filtreren voor `/interact`.
Er zijn andere typen Web SDK-aanroepen, maar alleen `interact` -aanroepen verzenden gegevens naar en krijgen een antwoordlading van de Edge Network.

   ![&#x200B; Beeld van een browser netwerklusje die de interactie vraag tonen.](assets/network.png)

1. De reactie op de eerste netwerkvraag heeft veelvoudige ladingen. Een van deze ladingsknooppunten bevat verschillende subknooppunten van het type `url` . Deze `url` -knooppunten zijn de syncs van de id van derden die historisch zijn geactiveerd door de [!DNL Visitor ID] -service. Er zou één `url` knoop voor elke synchronisatie van derdeidentiteitskaart moeten zijn die in uw container wordt gevormd (zie stap 3 hierboven).

   ![&#x200B; Beeld van een lusje van het browser netwerk dat de nuttige ladingen toont.](assets/payload.png)

   Bovendien kunt u filteren op `demdex` en zien dat elk van de URL&#39;s waarnaar in de payload wordt verwezen, net als de [!DNL Visitor ID] -service hun eigen netwerkverzoek voor id-synchronisatie heeft geactiveerd. Deze ID-syncs mogen alleen op de eerste pagina van een eerste bezoeker worden getypt en slechts eenmaal om de 14 dagen daarna.

1. Alle volgende `/interact` -aanvragen die worden gebruikt voor Analytics en Audience Manager-gegevensverzameling moeten de `data.__adobe.analytics` -knooppunten in de payload bevatten.

   ![&#x200B; Beeld van een browser netwerklusje die de analytische knoop in de nuttige lading tonen.](assets/analytics-node.png)

   Audience Manager-kenmerken die afhankelijk zijn van deze analytische variabelen en eigenschappen die de `h_` - of `d_` -platformtoetsen gebruiken, moeten verder worden gevuld.

   >[!TIP]
   >
   >U kunt een testbezit met een regeluitdrukking willen tot stand brengen die slechts kan worden uitgedrukt als het Web SDK gegevens wordt verzameld. Aangezien er geen ontwikkelings-Audience Manager-omgeving is en meerdere sites gegevens naar dezelfde Audience Manager-instantie kunnen verzenden, is het mogelijk dat u niet de vereiste validatie krijgt als u alleen kijkt naar het totale aantal inwoners.

1. In dezelfde `/interact` -aanroep waarbij analysevariabelen worden doorgegeven, kunnen cookies of URL-doelen worden gevonden in de payload knooppunten van de reactie. URL-doelen worden geladen in ladingen van het type `url` (net als in id-synchronisaties van derden) en cookie-doelen worden geladen in ladingen van het type `cookie` .

   ![&#x200B; Beeld van een lusje van het browser netwerk dat de ladingsgegevens toont.](assets/destinations.png)

   Zorg er ook voor dat de cookies zijn neergezet in de cookie-opslag van de browser.

   >[!TIP]
   >
   >Net als bij de vorige validatiestap is het in aanmerking komen voor een segment dat een cookiebestemming moet retourneren een bepaalde manier om ervoor te zorgen dat gegevens van en naar Audience Manager stromen.

1. Als u extra klant IDs via de Kaart van de Identiteit moet overgaan, verifieer in de plaats en zorg ervoor dat de identiteiten en hun bijbehorende parameters in de knoop van de Kaart van de Identiteit van de verzoeklading worden overgegaan.

   ![&#x200B; Beeld van een browser netwerklusje dat identiteitskaartgegevens toont.](assets/pass-customer-ids.png)

   >[!TIP]
   >
   >Als Adobe Target één van de ontvangende oplossingen is en er de activiteiten zijn van het Doel die zich op de segmenten van Audience Manager baseren die de juiste identiteit vereisen om worden overgegaan, zorg ervoor dat de Kaart van de Identiteit in `/interact` vraag wordt overgegaan die wordt gebruikt om verpersoonlijkingen en niet alleen in de vraag van de gegevensinzameling terug te winnen. Adobe Target gebruikt die identiteiten in de server-zijvraag aan Audience Manager wanneer het terugwinnen van segmentinformatie.

