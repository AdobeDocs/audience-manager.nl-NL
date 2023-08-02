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
source-wordcount: '2353'
ht-degree: 34%

---

# [!DNL Audience Manager Plug-in for IAB TCF] {#aam-iab-plugin}

## Overzicht

Een belangrijk aspect in de privacyverplichtingen die u jegens uw gebruikers kunt hebben, is de verwerving en doorgifte van keuzemogelijkheden voor gebruikers over de manier waarop hun persoonsgegevens kunnen worden gebruikt (d.w.z. &quot;doeleinden&quot;) en door wie (d.w.z. &quot;bedrijven&quot;).

Adobe biedt u de middelen om de privacykeuzen van uw gebruikers te beheren en door te geven via de [Opt-in-functionaliteit](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/optin-overview.html) en via [IAB TCF-ondersteuning (Transparency and Consent Framework)](https://iabtechlab.com/standards/gdpr-transparency-and-consent-framework/).

In dit artikel worden Audience Manager-gebruiksscenario’s beschreven waarin de IAB TCF wordt ondersteund, en wordt beschreven hoe u IAB TCF-ondersteuning in Audience Manager implementeert.

>[!IMPORTANT]
>
>Audience Manager is geregistreerd in het [IAB TCF](https://iabeurope.eu/tcf-for-vendors/) met leverancier-id 565.

De Audience Manager-plug-in voor IAB TCF maakt gebruik van de [Opt-in-functionaliteit](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/iab.html), die weer onderdeel is van de [ Experience Platform Identity Service (ECID)](https://experienceleague.adobe.com/docs/id-service/using/home.html)-bibliotheek.

## Omvang en beperkingen {#scope-and-limitations}

Als uitgever of adverteerder die met Audience Manager werkt, kunt u opties van gebruikers overbrengen aan Audience Manager volgens IAB TCF.

>[!IMPORTANT]
>
>De TCF-regels van IAB zijn alleen van toepassing op bezoekers die in de Europese Economische Ruimte gevestigd zijn.

Met Audience Manager kunt u de privacyopties van uw gebruikers respecteren en beschikt u ook over een eenvoudige manier om deze keuzes door te geven aan alle partners waarmee u werkt.

Audience Manager biedt momenteel geen ondersteuning voor het volgende:

* workflows voor mobiele apparaten;
* Toevoeging van toestemming voor het segmenteren van de uitvoer.

## Upgrade uitvoeren naar [!DNL IAB TCF v2.2] {#upgrading}

Klanten die hun [!DNL Audience Manager Plug-in for IAB TCF] uitvoering van [!DNL IAB TCF] v1.1 t/m [!DNL IAB TCF] v2.2 of inschakelen [!DNL IAB TCF] v2.2 moet voor het eerst dezelfde richtsnoeren inzake voorwaarden en uitvoering volgen als hieronder beschreven.

## Vereisten {#prerequisites}

>[!IMPORTANT]
>
>Audience Manager ondersteunt IAB TCF v2.2.
>
>IAB TCF v1.1 steun zal op 15 augustus 2020 eindigen.
>
> Klanten die de plug-in Audience Manager voor IAB TCF willen blijven gebruiken voor het beheer van hun toestemming, dienen een upgrade uit te voeren naar de nieuwste versie van [ECID](https://github.com/Adobe-Marketing-Cloud/id-service/releases) voor verdere steun.
>
> Na de upgrade naar de nieuwste [ECID](https://github.com/Adobe-Marketing-Cloud/id-service/releases) Constante tekenreeksen voor de goedkeuring van IAB TCF v1.1 worden niet meer ondersteund. Zorg er dus voor dat u uw CMP bijwerkt voordat u een upgrade uitvoert naar de nieuwste ECID-versie.

U moet aan de volgende voorwaarden voldoen om de Plug-in van de Audience Manager voor IAB TCF met Audience Manager te gebruiken:

1. U moet Adobe Experience Platform Identity Service (ECID) versie 5 of hoger gebruiken. [Download](https://github.com/Adobe-Marketing-Cloud/id-service/releases) onze nieuwste ECID-release.
2. U moet Audience Manager gebruiken [!DNL Data Integration Library] (DIL) versie 9.0 of hoger, downloadbaar vanaf [hier](https://github.com/Adobe-Marketing-Cloud/dil/releases). Lees meer over [DIL in de Audience Manager-documentatie](../../dil/dil-overview.md). We raden u aan de [Adobe Audience Manager-tagextensie](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/audience-manager/overview.html) voor de eenvoudigste DIL-uitvoering van Audience Manager.
3. Als u [!DNL Server-Side Forwarding] (SSF) om gegevens in Audience Manager in te voeren, moet u aan de recentste versie van AppMeasurement bevorderen. Download AppMeasurement met behulp van de [Analytics Code Manager](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/code-manager-admin.html).
4. U moet een Platform van het Beheer van de Toestemming (CMP), of commercieel of uw gebruiken, dat met IAB TCF v2.2 geïntegreerd is, en met IAB TCF geregistreerd. Zie de lijst met [CMP’s die bij het IAB-kader](https://iabeurope.eu/cmp-list/) zijn geregistreerd.

>[!WARNING]
>
>Als u een Platform van het Beheer van de Toestemming gebruikt (CMP) dat geen IAB TCF v2.2 steunt, zal de Audience Manager automatisch verzenden `gdpr=0` -parameter in ID-syncs, zelfs als uw bezoekers zich in de Europese Unie bevinden. Om te bepalen of uw GDPR-validatie actief is, raden we u aan om met uw CMP (Consent Management Platform) te bevestigen dat ze IAB TCF v2.2 ondersteunen.

## Aanbevelingen en de implementatie daarvan {#recommendations}

Voor het inschakelen van IAB TCF-ondersteuning in Audience Manager leest u onze documentatie over het [instellen van IAB met Opt-in](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/iab.html).

De eenvoudigste manier om dit te doen is door te gebruiken [Adobe Experience Platform-tags](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=en) toevoegen [!DNL ECID Opt-in] op uw eigenschappen. Lees de documentatie voor de [ECID-extensie voor aanmelden](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/id-service/overview.html) om te leren hoe u de extensie Tags instelt.

## Workflow voor gebruikersopties bij gebruik van het IAB-kader {#user-choice-workflow}

Wanneer u een webeigenschap bezoekt, kunnen uw gebruikers hun opties opgeven voor de manier waarop hun data moeten worden gebruikt door de uitgever en door de externe leveranciers met wie de uitgever werkt.

Gebruikers geven hun keuze in de vorm van *instemming* voor IAB-doeleinden *externe leveranciers* geregistreerd in de algemene lijst met leveranciers.

De onderstaande afbeelding is een voorbeeld van een CMP-dialoogvenster dat wordt weergegeven voor een nieuwe bezoeker van een website. Bedenk dat het uiterlijk van dit dialoogvenster sterk kan variëren, afhankelijk van de implementatie van de klant.

![CMP-dialoogvenster](assets/cmp-example.png)

Details over de verschillende doelen en machtigingen die zijn opgenomen in IAB TCF v2.2 worden behandeld in de [IAB Europe Transparency &amp; Consent Framework Policies](https://iabeurope.eu/iab-europe-transparency-consent-framework-policies/#A_Purposes).

Gebruikers kunnen hun toestemming verlenen voor een combinatie van doeleinden en verkopers. Gebruikers zouden bijvoorbeeld hun toestemming kunnen verlenen om informatie op een apparaat op te slaan, producten te ontwikkelen en te verbeteren, en hun toestemming kunnen geven aan alle externe leveranciers die door het CMP worden weergegeven.

Of in een ander voorbeeld zouden zij hun toestemming voor alle doeleinden kunnen verlenen, maar slechts toestemming verlenen aan een aantal verkopers die door het CMP worden getoond.

Wanneer de gebruiker zijn privacyopties heeft geselecteerd, worden de keuzen van de gebruiker opgenomen in de IAB TC-tekenreeks. De IAB TC-tekenreeks slaat de combinatie van goedgekeurde doeleinden en leveranciers op, samen met andere metagegevensinformatie (zie de [IAB-pagina](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/TCFv2/IAB%20Tech%20Lab%20-%20Consent%20string%20and%20vendor%20list%20formats%20v2.md#about-the-transparency--consent-string-tc-string) voor meer informatie ) .

Elke leverancier die in IAB TCF wordt geregistreerd evalueert het koord IAB TC en neemt besluiten die op de privacykeuzen van de gebruikers worden gebaseerd. Houd er rekening mee dat de privacyopties van de gebruikers geldig zijn voor alle leveranciers die zijn geregistreerd bij IAB TCF.

## Door de Audience Manager vereiste doeleinden {#aam-standard-purposes}

Audience Manager evalueert de keuzes van de gebruikers die zijn opgeslagen in de IAB TC-tekenreeks voor de volgende doeleinden, gedefinieerd in de [IAB Europe Transparency &amp; Consent Framework Policies](https://iabeurope.eu/iab-europe-transparency-consent-framework-policies/#Appendix_A_Purposes_and_Features_Definitions).

* **Doel 1**: gegevens opslaan en/of openen op een apparaat;
* **Doel 10**: Ontwikkelen en verbeteren van producten;
* **Speciaal doel 1**: Zorgen voor beveiliging, fraude voorkomen en fouten opsporen.

>[!IMPORTANT]
>
>Audience Manager heeft toestemming nodig voor doel 1 en doel 10, plus toestemming van de leverancier, om cookies te implementeren en ID-syncs te initiëren of te respecteren.
>
>Per [IAB-verordeningen](https://iabeurope.eu/iab-europe-transparency-consent-framework-policies/#Special_Purpose_1__Ensure_security_prevent_fraud_and_debug_), Speciaal doel 1 (Beveiliging garanderen, fraude voorkomen en fouten opsporen) wordt altijd goedgekeurd en gebruikers kunnen er geen bezwaar tegen maken.

## Het gedrag van Audience Manager zijn afhankelijk van de toestemming van de gebruiker {#aam-behavior-consent}

Audience Manager werkt anders, afhankelijk van of de IAB TC-tekenreeks toestemming van de gebruiker voor de twee doeleinden bevat (opslag en/of toegang tot informatie op een apparaat en ontwikkeling en verbetering van producten) of niet.

Wij controleren ook gebruikerstoestemming voor alle bestemmingen die u in Audience Manager werkt, zolang die bestemmingen met IAB TCF worden geregistreerd.

| Wanneer uw gebruiker *toestemming verleent*, doet Audience Manager het volgende: | Als uw gebruiker *geen* toestemming verleent, doet Audience Manager het volgende: |
|---|---|
| <ul><li>voert alle Audience Manager-gebruiksscenario’s uit die u hebt aangevraagd.</li><li>Hiermee wordt instemming van derden met ID-syncs doorgegeven (door `gdpr = 1` en de tekenreeks voor toestemming als `gdpr_consent` bij ID-synchronisatieaanroepen).</li><li>evalueert en honoreert toestemming die door advertentieserverpixels is doorgegeven.</li><li>honoreert door partner geïnitieerde id-synchronisaties.</li></ul> | <ul><li>slaat geen nieuwe gebruikersdata op in uw instantie. Dit omvat partner-id’s, signalen, eigenschappen of pixeldata.</li><li>initieert geen id-synchronisaties van derden.</li><li>honoreert geen door partner geïnitieerde id-synchronisaties.</li><li>Hiermee wordt de gebruiker uitgesloten van verdere gegevensverzameling.</li></ul> |

## Gebruiksscenario voor uitgevers {#publisher-use-case}

Door de Audience Manager-plug-in voor IAB TCF te implementeren, hoeft u geen aangepaste code te onderhouden voor het beheer van de toestemming op uw wegeigenschappen via een ander mechanisme met Adobe of andere externe leveranciers. Het gebruiksscenario wordt beschreven in de afbeelding en in de onderstaande stappen. Begin aan de linkerkant van de afbeelding:

1. Een gebruiker bezoekt een van uw webeigenschappen. Zolang u de nieuwste versies van de ECID- en DIL-bibliotheken gebruikt (zie [Voorwaarden](/help/using/overview/data-security-and-privacy/aam-iab-plugin.md#prerequisites)), is de opt-in-stroom geactiveerd.
2. Audience Manager controleert of de IAB-stroom van toepassing is (`isIabContext=true`). Zie [Aanbevelingen en de implementatie daarvan](aam-iab-plugin.md#recommendations).
3. Audience Manager controleert of GDPR wordt toegepast (`gdpr = 1`) en of er een CMP is, geregistreerd bij IAB TCF, op uw Webbezit. Dit geldt bijvoorbeeld voor gebruikers die vanuit de Europese Unie bezoeken. Als uitgever is het uw verantwoordelijkheid om de GDPR-markering in te stellen.
4. Als GDPR van toepassing is, controleert de Audience Manager de tekenreeks IAB TC, die in het `gdpr_consent` voor de vereiste toestemming. Audience Managers hebben toestemming nodig voor het opslaan en/of het verkrijgen van toegang tot informatie op een apparaat ([IAB TCF doel 1](https://iabeurope.eu/iab-europe-transparency-consent-framework-policies/#A_Purposes)), de ontwikkeling en verbetering van producten ([IAB TCF doel 10](https://iabeurope.eu/iab-europe-transparency-consent-framework-policies/#A_Purposes)), plus de toestemming van de verkoper van de Audience Manager om gegevens op te slaan, te verwerken of te activeren.
5. Als de IAB TC-tekenreeks aanwezig is en deze de vereiste toestemming bevat, geeft de Audience Manager de IAB TC-tekenreeks door aan onze [gegevensverzamelingsservers](../../reference/system-components/components-data-collection.md) (DCS).
6. Audience Manager reageert door een [demdex cookie](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-am.html) in de browser en initieert en houdt rekening met syncs van derden.
7. Als de in stap 4 doorgegeven IAB TC-tekenreeks echter niet alle benodigde machtigingen bevat, worden door de Audience Manager geen gebruikersgegevens verzameld, verwerkt of geactiveerd en worden de id-syncs niet gerespecteerd of geïnitieerd. Bovendien, opteert het uit de gebruiker van de bestemmingen die u met werkt.

>[!IMPORTANT]
>
>Als u met de bestemmingspartners van de Audience Manager werkt die parameters vereisen IAB TCF, maar u hebt geen CMP die IAB TCF op uw website steunt, dan verzendt de Audience Manager `gdpr=0` in ID-syncs. Dit betekent dat GDPR niet van toepassing is op deze gebruikers.
>
> Als dat niet gewenst is, zou u de functionaliteit IAB TCF in Audience Manager moeten toelaten om de aangewezen koorden IAB TC naar de bestemmingspartners te verzenden.



![Gebruiksscenario voor uitgevers](assets/publisher-use-case.png)

## Gebruiksscenario voor adverteerders {#advertiser-use-case}

Audience Manager evalueert en honoreert de toestemming die is doorgegeven in [pixelcalls](../../integration/sending-audience-data/real-time-data-integration/pixel-based-data-transfer.md) in overeenstemming met het IAB TCF.

Pixels kunnen door klanten van de Audience Manager op hun partnerpagina&#39;s worden geplaatst of zij worden geplaatst in ad servers om in de advertentierespons te omvatten. In het eerste geval moet uw partner de toestemmingsparameter programmatisch ophalen en deze aan de pixel toevoegen voor activering. In het tweede geval, dat vaker voorkomt en hieronder in detail wordt beschreven, voegen de advertentieservers de toestemmingsparameters die ze van het SSP (Supply-Side Platform) of van de advertentieservers van uitgevers ontvangen, toe aan alle pixels.

Audience Manager gebruikt twee parameters om gebruikerstoestemming in pixelcalls door te geven:

* `gdpr` kan 0 (GDPR (AVG) is niet van toepassing) of 1 (GDPR (AVG) is van toepassing) zijn;
* `gdpr_consent` is de URL-veilige base64-gecodeerde GDPR (AVG)-toestemmingstekenreeks (zie [specificatie](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/TCFv2/IAB%20Tech%20Lab%20-%20Consent%20string%20and%20vendor%20list%20formats%20v2.md#about-the-transparency--consent-string-tc-string)). Een voorbeeldcall voor een impressiepixel met beide parameters kan er ongeveer zo uitzien:

```
https://yourcompany.demdex.net/event?d_event=imp&gdpr=1&gdpr_consent=consentstring&d_src=datasource_id&d_site=siteID&d_creative=creative_id&d_adgroup=adgroup_id&d_placement=placement_id
```

Het gebruiksscenario wordt beschreven in de afbeelding en in de onderstaande stappen. Begin aan de linkerkant van de afbeelding:

1. Uw gebruiker krijgt een impressie via een advertentieserver. Dit vertaalt zich in een [pixelaanroep](../../integration/media-data-integration/impression-data-pixels.md) naar onze gegevensverzamelingsservers (DCS).
2. Audience Manager controleert of de GDPR (AVG)-markering van toepassing is. Als dit niet het geval is, slaat Audience Manager de gegevens op die in het dialoogvenster `gdpr` en `gdpr_consent` variabelen in pixelaanroepen.
3. Als de IAB TC-tekenreeks aanwezig is en deze de vereiste machtigingen bevat, slaat de Audience Manager de gegevens op die in het dialoogvenster `gdpr` en `gdpr_consent` variabelen in pixelaanroepen.
4. Als de IAB TC-tekenreeks ontbreekt of als de vereiste machtigingen ontbreken, worden de gegevens die zijn doorgegeven, door de Audience Manager in het dialoogvenster `gdpr` en `gdpr_consent` variabelen in pixelaanroepen.

![Gebruiksscenario voor adverteerders](assets/advertiser-use-case.png)

## Activeringspartners die IAB TCF ondersteunen {#aam-activation-partners}

Met de insteekmodule Audience Manager voor IAB TCF kunt u de IAB TC-tekenreeks doorsturen naar activeringspartners met inachtneming van de privacyopties van de gebruikers. Raadpleeg onze [lijst met apparaatgebaseerde bestemmingen](/help/using/features/destinations/device-based-destinations-list.md) voor informatie over welke activeringspartners IAB TCF ondersteunen.

## Goedkeuring toevoegen aan URL&#39;s die naar URL-doelen zijn verzonden

De integratie van de Audience Manager met IAB TCF v2.2 steunt het toevoegen van instemming aan informatie die wordt verzonden naar [URL-doelen](../../features/destinations/create-url-destination.md) die geïntegreerd zijn met IAB TCF v2.2. Dit proces wordt echter niet automatisch door de Audience Manager uitgevoerd om te voorkomen dat specifieke URL-indelingen worden afgebroken.

Klanten die toestemming willen toevoegen aan gegevens die worden verzonden naar [!DNL URL destinations] moet handmatig de `${GDPR}` en `${GDPR_CONSENT_XXXX}` macro&#39;s naar hun URL-indeling, vervangen `XXXX` met de identiteitskaart van de bestemmingspartner.

Voorbeeld: `https://yourdomain.com?gdpr=${GDPR}&gdpr_consent=${GDPR_CONSENT_1234}`.

Zie [Gedefinieerde doelmacro&#39;s](../../features/destinations/destination-macros.md) voor meer details over de gesteunde bestemmingsmacro&#39;s.

## Beheer van apparaatinstemming

De Audience Manager-plug-in voor IAB TCF sluit automatisch de id&#39;s uit die aanwezig zijn op een aanvraag als uw sitebezoekers niet de juiste machtigingen bieden. Als de aanvraag een [cross-device ID (CRM ID)](../../reference/ids-in-aam.md), kiest de Audience Manager de id uit, samen met het laatste apparaat dat aan die id is gekoppeld [cross-device ID (CRM ID)](../../reference/ids-in-aam.md).

## Uw IAB-implementatie testen {#test-iab-implementation}

Om te testen dat u correct Audience ManagerPlug-in voor IAB TCF hebt uitgevoerd, lees [Hoofdlettergebruik 4 in de Validatie Opt-in Dienst](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/testing-optin-and-iab-plugin.html#section-64331998954d4892960dcecd744a6d88).

## IAB en opt-out in de Audience Manager. Rangorde. {#iab-and-optout}

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
