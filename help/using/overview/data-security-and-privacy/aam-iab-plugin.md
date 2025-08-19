---
description: Adobe biedt u de middelen om de privacykeuzen van uw gebruikers te beheren en door te geven via de opt-in-functionaliteit en via de ondersteuning voor IAB TCF (Transparency and Consent Framework). In dit artikel worden Audience Manager-gebruiksscenario’s beschreven waarin de IAB TCF wordt ondersteund, en wordt beschreven hoe u IAB TCF-ondersteuning in Audience Manager implementeert.
seo-description: Adobe provides you with the means to manage and communicate your users' privacy choices through the Opt-in functionality and through IAB Transparency and Consent Framework (TCF) support. This article describes the Audience Manager use cases that support the IAB TCF and how to implement IAB TCF support in Audience Manager.
seo-title: Audience Manager Plug-in for IAB TCF
solution: Audience Manager
title: Audience Manager-plug-in voor IAB TCF
feature: Data Governance & Privacy
exl-id: aa6bc415-e52b-4900-951d-ccf51d907aa2
source-git-commit: 8b370a64d80b40124abee91351cbef09711243d4
workflow-type: tm+mt
source-wordcount: '2173'
ht-degree: 29%

---

# [!DNL Audience Manager Plug-in for IAB TCF] {#aam-iab-plugin}

## Overzicht

Een belangrijk aspect in de privacyverplichtingen die u jegens uw gebruikers kunt hebben, is de verwerving en doorgifte van keuzemogelijkheden voor gebruikers over de manier waarop hun persoonsgegevens kunnen worden gebruikt (d.w.z. &quot;doeleinden&quot;) en door wie (d.w.z. &quot;bedrijven&quot;).

Adobe biedt u de middelen om de privacykeuzen van uw gebruikers te beheren en door te geven via de [Opt-in-functionaliteit](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/optin-overview.html) en via [IAB TCF-ondersteuning (Transparency and Consent Framework)](https://iabtechlab.com/standards/gdpr-transparency-and-consent-framework/).

In dit artikel worden Audience Manager-gebruiksscenario’s beschreven waarin de IAB TCF wordt ondersteund, en wordt beschreven hoe u IAB TCF-ondersteuning in Audience Manager implementeert.

>[!IMPORTANT]
>
>Audience Manager wordt geregistreerd in [ IAB TCF ](https://iabeurope.eu/tcf-for-vendors/) met verkoperidentiteitskaart 565.

De insteekmodule van Audience Manager voor IAB TCF gebruikt de [ Opt-in functionaliteit ](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/iab.html), die, beurtelings, deel van de [ Dienst van de Identiteit van Adobe Experience Platform (ECID) ](https://experienceleague.adobe.com/docs/id-service/using/home.html) bibliotheek is.

## Toepassingsgebied en beperkingen {#scope-and-limitations}

Als uitgever of Advertiser die met Audience Manager werkt, kunt u gebruikerskeuzen aan Audience Manager overbrengen volgens IAB TCF.

>[!IMPORTANT]
>
>De TCF-regels van IAB zijn alleen van toepassing op bezoekers die in de Europese Economische Ruimte gevestigd zijn.

Audience Manager helpt u bij het respecteren van de privacyopties van uw gebruikers en biedt u ook een eenvoudige manier om deze keuzes door te geven aan alle partners waarmee u werkt.

Audience Manager biedt momenteel geen ondersteuning voor het volgende:

* workflows voor mobiele apparaten;
* Toevoeging van toestemming voor het segmenteren van de uitvoer.

## Upgrade uitvoeren naar [!DNL IAB TCF v2.2] {#upgrading}

Klanten die hun [!DNL Audience Manager Plug-in for IAB TCF] -implementatie upgraden van [!DNL IAB TCF] v1.1 naar [!DNL IAB TCF] v2.2 of [!DNL IAB TCF] v2.2 voor het eerst inschakelen, dienen dezelfde richtlijnen voor voorwaarden en implementatie te volgen als hieronder wordt beschreven.

## Vereisten {#prerequisites}

>[!IMPORTANT]
>
>Audience Manager ondersteunt IAB TCF v2.2.
>
>IAB TCF v1.1 steun zal op 15 augustus 2020 eindigen.
>
> De klanten die willen blijven gebruiken Audience Manager stop-binnen voor IAB TCF voor toestemmingsbeheer zouden aan recentste versie van [ ECID ](https://github.com/Adobe-Marketing-Cloud/id-service/releases) voor verdere steun bevorderen.
>
> Na bevordering aan de recentste [ ECID ](https://github.com/Adobe-Marketing-Cloud/id-service/releases) versie, zal de de toestemmingskoorden van TCF van IAB v1.1 niet meer worden gesteund, zodat zorg ervoor om uw CMP bij te werken alvorens aan de recentste versie ECID te bevorderen.

U moet aan de volgende voorwaarden voldoen om de Audience Manager-plug-in voor IAB TCF met Audience Manager te kunnen gebruiken:

1. U moet Adobe Experience Platform Identity Service (ECID) versie 5 of hoger gebruiken. [Download](https://github.com/Adobe-Marketing-Cloud/id-service/releases) onze nieuwste ECID-release.
2. U moet Audience Manager [!DNL Data Integration Library] (DIL) versie 9.0 gebruiken of nieuwer, downloadbaar van [ hier ](https://github.com/Adobe-Marketing-Cloud/dil/releases). Lees over [ DIL in de documentatie van Audience Manager ](../../dil/dil-overview.md). Wij adviseren gebruikend de [ de markeringsuitbreiding van Adobe Audience Manager ](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/audience-manager/overview.html) voor de gemakkelijkste implementatie van DIL van Audience Manager.
3. Als u [!DNL Server-Side Forwarding] (SSF) gebruikt om gegevens te importeren naar Audience Manager, moet u een upgrade uitvoeren naar de nieuwste versie van AppMeasurement. Download AppMeasurement met behulp van de [Analytics Code Manager](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/code-manager-admin.html).
4. U moet een CMP (Consent Management Platform), commercieel of uw gebruiken, dat is geïntegreerd met IAB TCF v2.2 en is geregistreerd met IAB TCF. Zie de lijst met [CMP’s die bij het IAB-kader](https://iabeurope.eu/cmp-list/) zijn geregistreerd.

>[!WARNING]
>
>Als u een CMP (Consent Management Platform) gebruikt dat geen ondersteuning biedt voor IAB TCF v2.2, stuurt Audience Manager automatisch de parameter `gdpr=0` in ID-syncs, zelfs als uw bezoekers zich in de Europese Unie bevinden. Om te bepalen of uw GDPR-validatie actief is, raden we u aan om met uw CMP (Consent Management Platform) te bevestigen dat zij IAB TCF v2.2 ondersteunen.

## Aanbevelingen en de wijze van uitvoering {#recommendations}

Voor het inschakelen van IAB TCF-ondersteuning in Audience Manager leest u onze documentatie over het [instellen van IAB met Opt-in](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/iab.html).

De gemakkelijkste manier u dit kunt doen is door [ Markeringen van Adobe Experience Platform ](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=en) te gebruiken om [!DNL ECID Opt-in] op uw eigenschappen toe te voegen. Lees de documentatie voor de [ ECID open-binnen uitbreiding ](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/id-service/overview.html) om te leren hoe te opstelling de uitbreiding van Markeringen.

## Gebruikerskeuzeworkflow bij gebruik van IAB-framework {#user-choice-workflow}

Wanneer u een webeigenschap bezoekt, kunnen uw gebruikers hun keuze opgeven voor de manier waarop hun gegevens door de uitgever en door de externe leveranciers waarmee de uitgever werkt moeten worden gebruikt.

De gebruikers verstrekken hun keuzen in de vorm van *toestemming* voor de doeleinden IAB aan *derde verkopers* die in de globale verkoperslijst worden geregistreerd.

De onderstaande afbeelding is een voorbeeld van een CMP-dialoogvenster dat wordt weergegeven voor een nieuwe bezoeker van een website. Bedenk dat het uiterlijk van dit dialoogvenster sterk kan variëren, afhankelijk van de implementatie van de klant.

![CMP-dialoogvenster](assets/cmp-example.png)

De details op de diverse doeleinden en de toestemmingen inbegrepen in IAB TCF v2.2 worden behandeld in [ IAB het Beleid van het Kader van de Transparantie &amp; van de Goedkeuring van Europa ](https://iabeurope.eu/iab-europe-transparency-consent-framework-policies/#A_Purposes).

Gebruikers kunnen hun toestemming verlenen voor een combinatie van doeleinden en verkopers. Gebruikers zouden bijvoorbeeld hun toestemming kunnen verlenen om informatie op een apparaat op te slaan, producten te ontwikkelen en te verbeteren, en hun toestemming kunnen geven aan alle externe leveranciers die door het CMP worden weergegeven.

Of in een ander voorbeeld zouden zij hun toestemming voor alle doeleinden kunnen verlenen, maar slechts toestemming verlenen aan een aantal verkopers die door het CMP worden getoond.

Wanneer de gebruiker zijn privacyopties heeft geselecteerd, worden de keuzen van de gebruiker opgenomen in de IAB TC-tekenreeks. Het koord IAB TC slaat de combinatie goedgekeurde doeleinden en verkopers, samen met andere meta-gegevensinformatie (zie de [ pagina IAB ](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/TCFv2/IAB%20Tech%20Lab%20-%20Consent%20string%20and%20vendor%20list%20formats%20v2.md#about-the-transparency--consent-string-tc-string) voor meer informatie) op.

Elke leverancier die in IAB TCF wordt geregistreerd evalueert het koord IAB TC en neemt besluiten die op de privacykeuzen van de gebruikers worden gebaseerd. Houd er rekening mee dat de privacyopties van de gebruikers geldig zijn voor alle leveranciers die zijn geregistreerd bij IAB TCF.

## Door Audience Manager vereiste doeleinden {#aam-standard-purposes}

Audience Manager evalueert de keuzen van de gebruikers die in het koord IAB TC voor de volgende doeleinden worden opgeslagen, die in [ worden bepaald het Beleid van het Kader van de Transparantie &amp; van de Toestemming van het Kader van IAB Europa ](https://iabeurope.eu/iab-europe-transparency-consent-framework-policies/#Appendix_A_Purposes_and_Features_Definitions).

* **Doel 1**: opslag en/of toegangsinformatie over een apparaat;
* **Doel 10**: Ontwikkelen en verbeteren producten;
* **Speciaal Doel 1**: Zorg veiligheid, preventie fraude, en zuivert.

>[!IMPORTANT]
>
>Audience Manager heeft toestemming nodig voor Doelstelling 1 en Doelstelling 10, plus toestemming van de leverancier, om cookies te implementeren en ID-syncs te initiëren of te respecteren.
>
>Per [ verordeningen IAB ](https://iabeurope.eu/iab-europe-transparency-consent-framework-policies/#Special_Purpose_1__Ensure_security_prevent_fraud_and_debug_), speciaal Doel 1 (verzeker veiligheid, preventie fraude, en zuivert) altijd wordt goedgekeurd aan, en de gebruikers kunnen niet aan het bezwaar maken.

## Het gedrag van Audience Manager hangt af van de vraag of de gebruiker toestemming geeft {#aam-behavior-consent}

Audience Manager werkt anders afhankelijk van of de IAB TC-tekenreeks toestemming van de gebruiker voor de twee doeleinden bevat (opslag en/of toegang tot informatie op een apparaat en ontwikkeling en verbetering van producten) of niet.

Wij controleren ook gebruikerstoestemming voor alle bestemmingen die u in Audience Manager werkt, zolang die bestemmingen met IAB TCF worden geregistreerd.

| Wanneer uw gebruiker *toestemming verleent*, doet Audience Manager het volgende: | Als uw gebruiker *geen* toestemming verleent, doet Audience Manager het volgende: |
|---|---|
| <ul><li>voert alle Audience Manager-gebruiksscenario’s uit die u hebt aangevraagd.</li><li>Hiermee geeft u toestemming aan derden in id-syncs (door `gdpr = 1` en de tekenreeks voor toestemming door te geven als `gdpr_consent` voor aanroepen van id-synchronisatie).</li><li>evalueert en honoreert toestemming die door advertentieserverpixels is doorgegeven.</li><li>honoreert door partner geïnitieerde id-synchronisaties.</li></ul> | <ul><li>slaat geen nieuwe gebruikersdata op in uw instantie. Dit omvat partner-id’s, signalen, eigenschappen of pixeldata.</li><li>initieert geen id-synchronisaties van derden.</li><li>honoreert geen door partner geïnitieerde id-synchronisaties.</li><li>Hiermee wordt de gebruiker uitgesloten van verdere gegevensverzameling.</li></ul> |

## Hoofdletters/kleine letters voor uitgever {#publisher-use-case}

Door de Audience Manager-plug-in voor IAB TCF te implementeren, hoeft u geen aangepaste code te onderhouden voor het beheer van uw toestemming op uw wegeigenschappen via een ander mechanisme met Adobe of andere externe leveranciers. Het gebruiksscenario wordt beschreven in de afbeelding en in de onderstaande stappen. Begin aan de linkerkant van de afbeelding:

1. Een gebruiker bezoekt een van uw webeigenschappen. Zolang u de nieuwste versies van de ECID- en DIL-bibliotheken gebruikt (zie [Voorwaarden](/help/using/overview/data-security-and-privacy/aam-iab-plugin.md#prerequisites)), is de opt-in-stroom geactiveerd.
2. Audience Manager controleert of de IAB-stroom van toepassing is (`isIabContext=true`). Zie [Aanbevelingen en de implementatie daarvan](aam-iab-plugin.md#recommendations).
3. Audience Manager controleert of GDPR van toepassing is (`gdpr = 1`) en of er een CMP is, geregistreerd bij IAB TCF, op uw Webbezit. Dit geldt bijvoorbeeld voor gebruikers die vanuit de Europese Unie bezoeken. Als uitgever is het uw verantwoordelijkheid om de GDPR-markering in te stellen.
4. Als GDPR van toepassing is, controleert Audience Manager de CTC-tekenreeks voor IAB, die in de parameter `gdpr_consent` wordt doorgegeven, op de vereiste toestemming. Audience Manager heeft toestemming voor het opslaan van en/of de toegang tot van informatie over een apparaat ([ IAB TCF doel 1 ](https://iabeurope.eu/iab-europe-transparency-consent-framework-policies/#A_Purposes)), het ontwikkelen van en het verbeteren van producten ([ IAB TCF doel 10 ](https://iabeurope.eu/iab-europe-transparency-consent-framework-policies/#A_Purposes)), plus de verkoperstoestemming van Audience Manager om, gegevens op te slaan te verwerken of te activeren.
5. Als het koord IAB TC aanwezig is en het de vereiste toestemming bevat, gaat Audience Manager het koord IAB TC tot onze [ servers van de gegevensinzameling ](../../reference/system-components/components-data-collection.md) (DCS) over.
6. Audience Manager antwoordt door a [ demdex koekje ](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-am.html) op browser te plaatsen, en initieert en eersteert de syncs van derdeidentiteitskaart.
7. Als de in stap 4 doorgegeven IAB TC-tekenreeks echter niet alle benodigde machtigingen bevat, verzamelt, verwerkt of activeert Audience Manager geen gebruikersgegevens en worden de id-syncs niet gerespecteerd of geïnitieerd. Bovendien, opteert het uit de gebruiker van de bestemmingen die u met werkt.

>[!IMPORTANT]
>
>Als u met de bestemmingspartners van Audience Manager werkt die parameters vereisen IAB TCF, maar u hebt geen CMP die IAB TCF op uw website steunt, dan verzendt Audience Manager `gdpr=0` in de syncs van identiteitskaart. Dit betekent dat GDPR niet van toepassing is op deze gebruikers.
>
> Als dat niet gewenst is, zou u de functionaliteit IAB TCF in Audience Manager moeten toelaten om de aangewezen koorden IAB TC naar de bestemmingspartners te verzenden.



![Gebruiksscenario voor uitgevers](assets/publisher-use-case.png)

## Gebruiksscenario voor adverteerders {#advertiser-use-case}

Audience Manager evalueert en honoreert de toestemming die is doorgegeven in [pixelcalls](../../integration/sending-audience-data/real-time-data-integration/pixel-based-data-transfer.md) in overeenstemming met het IAB TCF.

Pixels kunnen door Audience Manager-klanten op hun partnerpagina&#39;s worden geplaatst of ze worden in advertentieservers geplaatst om in de advertentie-reactie op te nemen. In het eerste geval moet uw partner de toestemmingsparameter programmatisch ophalen en deze aan de pixel toevoegen voor activering. In het tweede geval, dat vaker voorkomt en hieronder in detail wordt beschreven, voegen de advertentieservers de toestemmingsparameters die ze van het SSP (Supply-Side Platform) of van de advertentieservers van uitgevers ontvangen, toe aan alle pixels.

Audience Manager gebruikt twee parameters om gebruikerstoestemming in pixelcalls door te geven:

* `gdpr` kan 0 (GDPR (AVG) is niet van toepassing) of 1 (GDPR (AVG) is van toepassing) zijn;
* `gdpr_consent` is de URL-veilige base64-gecodeerde GDPR (AVG)-toestemmingstekenreeks (zie [specificatie](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/TCFv2/IAB%20Tech%20Lab%20-%20Consent%20string%20and%20vendor%20list%20formats%20v2.md#about-the-transparency--consent-string-tc-string)). Een voorbeeldcall voor een impressiepixel met beide parameters kan er ongeveer zo uitzien:

```
https://yourcompany.demdex.net/event?d_event=imp&gdpr=1&gdpr_consent=consentstring&d_src=datasource_id&d_site=siteID&d_creative=creative_id&d_adgroup=adgroup_id&d_placement=placement_id
```

Het gebruiksscenario wordt beschreven in de afbeelding en in de onderstaande stappen. Begin aan de linkerkant van de afbeelding:

1. Uw gebruiker krijgt een impressie via een advertentieserver. Dit vertaalt in a [ pixelvraag ](../../integration/media-data-integration/impression-data-pixels.md) aan onze Servers van de Inzameling van Gegevens (DCS).
2. Audience Manager controleert of de GDPR (AVG)-markering van toepassing is. Als dit niet het geval is, slaat Audience Manager de gegevens op die in de variabelen `gdpr` en `gdpr_consent` worden doorgegeven in pixelaanroepen.
3. Als de IAB TC-tekenreeks aanwezig is en deze de vereiste machtigingen bevat, slaat Audience Manager de gegevens op die in de variabelen `gdpr` en `gdpr_consent` worden doorgegeven in pixelaanroepen.
4. Als de IAB TC-tekenreeks ontbreekt of niet de vereiste machtigingen heeft, zet Audience Manager de doorgegeven gegevens in de variabelen `gdpr` en `gdpr_consent` neer in pixelaanroepen.

![Gebruiksscenario voor adverteerders](assets/advertiser-use-case.png)

## Activeringspartners die IAB TCF steunen {#aam-activation-partners}

Met de Audience Manager-insteekmodule voor IAB TCF kunt u de IAB TC-tekenreeks doorsturen naar activeringspartners met inachtneming van de privacyopties van de gebruikers. Raadpleeg onze [lijst met apparaatgebaseerde bestemmingen](/help/using/features/destinations/device-based-destinations-list.md) voor informatie over welke activeringspartners IAB TCF ondersteunen.

## Goedkeuring toevoegen aan URL&#39;s die naar URL-doelen zijn verzonden

De integratie van Audience Manager met IAB TCF v2.2 steunt het toevoegen van toestemming aan informatie die naar [ wordt verzonden bestemmingen URL ](../../features/destinations/create-url-destination.md) die met IAB TCF v2.2 worden geïntegreerd. Dit proces wordt echter niet automatisch uitgevoerd door Audience Manager, om te voorkomen dat specifieke URL-indelingen worden afgebroken.

Klanten die toestemming willen toevoegen aan gegevens die naar [!DNL URL destinations] worden verzonden, moeten de macro&#39;s `${GDPR}` en `${GDPR_CONSENT_XXXX}` handmatig aan hun URL-indeling toevoegen en `XXXX` vervangen door de id van de doelpartner.

Voorbeeld: `https://yourdomain.com?gdpr=${GDPR}&gdpr_consent=${GDPR_CONSENT_1234}` .

Zie [ bepaalde Macro&#39;s van de Bestemming ](../../features/destinations/destination-macros.md) voor meer details over de gesteunde bestemmingsmacro&#39;s.

## Beheer van apparaatinstemming

De Audience Manager-plug-in voor IAB TCF sluit automatisch de id&#39;s uit die aanwezig zijn op een aanvraag wanneer bezoekers van de site niet de juiste machtigingen opgeven. Als het verzoek a [ dwars-apparaat identiteitskaart (identiteitskaart van CRM) ](../../reference/ids-in-aam.md) bevat, opteert Audience Manager uit identiteitskaart, samen met het laatste apparaat verbonden aan die [ dwars-apparaat identiteitskaart (identiteitskaart van CRM) ](../../reference/ids-in-aam.md).

## De IAB-implementatie testen {#test-iab-implementation}

Om te testen dat u correct Audience Manager stop-binnen voor IAB TCF hebt uitgevoerd, lees [ Geval 4 van het Gebruik in het Bevestigen van Opt-binnen Dienst ](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/testing-optin-and-iab-plugin.html#section-64331998954d4892960dcecd744a6d88).

## IAB en opt-out in de Audience Manager. Volgorde. {#iab-and-optout}

Een andere privacyoptie waarover uw gebruikers beschikken, is de mogelijkheid om zich af te melden voor het verzamelen van alle data. Adobe biedt gebruikers hiervoor een methode op de pagina [Uw privacyopties](https://www.adobe.com/nl/privacy/opt-out.html#customeruse).

Audience Manager behandelt opt-outaanvragen in een [afzonderlijk artikel in onze documentatie](data-privacy-requests.md#opt-out-requests).

>[!IMPORTANT]
>
>Gebruikers die na hun weigering van toestemming uit de gegevensverzameling zijn gekomen, kunnen niet opnieuw worden ingeschakeld.

>[!NOTE]
>
>**Rangorde** - als uw gebruiker zich afmeldt voor dataverzameling via een globale opt-outtool zoals in de bovenstaande koppeling wordt beschreven, krijgt dit voorrang boven de opt-in- en IAB-verificaties.

## Aanvullende bronnen {#additional-resources}

* [Adobe Experience Platform Identity Service Opt-in](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/optin-overview.html)
* [IAB Europe GDPR Transparency and Consent Framework](https://iabtechlab.com/standards/gdpr-transparency-and-consent-framework/)
* [Technische specificaties van IAB Europe GDPR Transparency and Consent Framework](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/Consent%20string%20and%20vendor%20list%20formats%20v1.1%20Final.md)
* [IAB TCF-plug-in - videodemonstratie](https://helpx.adobe.com/audience-manager/kt/using/iab-tcf-support-audience-manager-technical-video-implement.html)
