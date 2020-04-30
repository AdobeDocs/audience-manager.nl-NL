---
description: Adobe biedt u de middelen om de privacykeuzes van uw gebruikers te beheren en door te geven via de aanmeldingsfunctionaliteit en via de ondersteuning voor IAB-transparantie en Consent Framework (TCF). In dit artikel worden de gevallen beschreven waarin Audience Manager de IAB TCF ondersteunt en hoe u de IAB TCF-ondersteuning implementeert in Audience Manager.
seo-description: Adobe biedt u de middelen om de privacykeuzes van uw gebruikers te beheren en door te geven via de aanmeldingsfunctionaliteit en via de ondersteuning voor IAB-transparantie en Consent Framework (TCF). In dit artikel worden de gevallen beschreven waarin Audience Manager de IAB TCF ondersteunt en hoe u de IAB TCF-ondersteuning implementeert in Audience Manager.
seo-title: Insteekmodule Audience Manager voor IAB TCF
solution: Audience Manager
title: Insteekmodule Audience Manager voor IAB TCF
translation-type: tm+mt
source-git-commit: 412972b9d9a633d09de411c46528b93c74a64e3f

---


# Insteekmodule Audience Manager voor IAB TCF {#aam-iab-plugin}

## Overzicht

Een belangrijk aspect in de privacyverplichtingen die u jegens uw gebruikers hebt, is de verwerving en doorgifte van keuzemogelijkheden voor gebruikers over de manier waarop hun persoonsgegevens kunnen worden gebruikt (d.w.z. &quot;doeleinden&quot;) en door wie (d.w.z. &quot;bedrijven&quot;).

Adobe biedt u de middelen om de privacykeuzes van uw gebruikers te beheren en door te geven via de [aanmeldingsfunctionaliteit](hhttps://docs.adobe.com/content/help/en/id-service/using/implementation/opt-in-service/optin-overview.html) en via de ondersteuning voor [IAB Transparency and Consent Framework (TCF)](https://iabtechlab.com/standards/gdpr-transparency-and-consent-framework/) .

In dit artikel worden de gevallen beschreven waarin Audience Manager de IAB TCF ondersteunt en hoe u de IAB TCF-ondersteuning implementeert in Audience Manager. Audience Manager is geregistreerd in IAB TCF met leverancier-id 565.

De plug-in Audience Manager voor IAB TCF maakt gebruik van de [plug-in Opt-in, die op zijn beurt onderdeel is van de Adobe](https://docs.adobe.com/content/help/en/id-service/using/implementation/opt-in-service/iab.html)Experience Platform Identity Service (ECID) [](https://docs.adobe.com/content/help/en/id-service/using/home.html) -bibliotheek.

## Toepassingsgebied en beperkingen {#scope-and-limitations}

Als Uitgever of Advertiser die met de Manager van de Publiek werkt, kunt u gebruikerskeuzen aan de Manager van de Publiek overeenkomstig IAB TCF overbrengen. Dit voorziet u van een gemakkelijke en verenigbare manier om gebruikerskeuzen aan alle partners mee te delen u werkt met en de Manager van de Publiek kan u helpen de privacykeuzen van uw gebruikers respecteren.

De IAB TCF steun die in dit artikel wordt beschreven vertegenwoordigt de eerste fase in de geplande steun van de Manager van de Audience voor het kader IAB. Audience Manager biedt momenteel geen ondersteuning voor:

* Workflows voor mobiele apparaten;
* beheer van toestemming tussen apparaten;
* toestemming toevoegen aan URL&#39;s die naar [URL-bestemmingen](../../features/destinations/create-url-destination.md)worden verzonden;
* Toestemming toevoegen aan segmenten.

## Vereisten {#prerequisites}

U moet aan de volgende voorwaarden voldoen om IAB TCF met de Manager van het Publiek te gebruiken:

1. U moet Adobe Experience Platform Identity Service (ECID) versie 4.1 of hoger gebruiken. [Download](https://github.com/Adobe-Marketing-Cloud/id-service/releases) onze nieuwste ECID-release.
1. U moet versie 9.0 of hoger van de Bibliotheek van de Integratie van Gegevens van de Manager van de Audience gebruiken, downloadbaar van [hier](https://github.com/Adobe-Marketing-Cloud/dil/releases). Lees meer over [DIL in de documentatie](../..//dil/dil-overview.md)van Audience Manager.
1. Alternatief, als u server-zij het Door:sturen (SSF) gebruikt om gegevens in de Manager van de Audience in te voeren, moet u aan de recentste versie van AppMeasurement bevorderen. Download AppMeasurement met behulp van [Analytics Code Manager](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/code-manager-admin.html).
1. U moet een platform van het Beheer van de Toestemming (CMP), of commercieel of uw gebruiken, dat IAB TCF steunt, en met IAB TCF geregistreerd is. Zie de lijst van [CMP&#39;s die in het IAB-kader](https://advertisingconsent.eu/cmp-list/)zijn geregistreerd.

## Aanbevelingen en de wijze van uitvoering {#recommendations}

Om de steun IAB TCF in de Manager van het Publiek toe te laten, lees onze documentatie over [hoe te opstelling IAB met Opt-in](https://docs.adobe.com/content/help/en/id-service/using/implementation/opt-in-service/iab.html).

Dit kunt u het gemakkelijkst doen met de functie [Adobe Experience Platform Launch](https://docs.adobelaunch.com/) om ECID Opt-in te installeren op uw eigenschappen. Lees de documentatie voor de [ECID Opt-in uitbreiding](https://docs.adobelaunch.com/extension-reference/web/experience-cloud-id-service-extension#opt-in) om te leren hoe te opstelling de uitbreiding van de Lancering.

## Gebruikerskeuzeworkflow bij gebruik van IAB-framework {#user-choice-workflow}

Wanneer u een webeigenschap bezoekt, kunnen uw gebruikers hun keuze opgeven voor de manier waarop hun gegevens door de uitgever en door de externe leveranciers waarmee de uitgever werkt moeten worden gebruikt. Gebruikers bieden hun keuzes in de vorm van *standaarddoeleinden* en machtigingen aan *externe leveranciers* die zijn geregistreerd in de algemene lijst met leveranciers. De onderstaande afbeelding is een voorbeeld van een CMP-dialoogvenster dat wordt weergegeven voor een nieuwe bezoeker van een website. Vergeet niet dat dit dialoogvenster er anders kan uitzien, op basis van de implementatie door de klant.

![CMP-dialoogvenster](assets/cmp.png)

De standaarddoelstellingen in het IAB-kader zijn:

* Opslag en toegang van informatie
* Personalisatie
* Selectie, levering en rapportage toevoegen
* Inhoud selecteren, leveren en rapporteren
* Meting

Raadpleeg de pagina [met specificaties van het](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/Consent%20string%20and%20vendor%20list%20formats%20v1.1%20Final.md#purposes-features) IAB-framework voor een beschrijving van de vijf standaarddoelen.

Gebruikers kunnen hun toestemming verlenen voor een combinatie van standaarddoeleinden en leveranciers. Gebruikers kunnen bijvoorbeeld hun toestemming verlenen voor opslag, personalisatie en meting en hun toestemming verlenen aan alle externe leveranciers die door het CMP worden weergegeven. Of in een ander voorbeeld zouden zij hun toestemming voor alle vijf de standaarddoeleinden kunnen verlenen, maar slechts toestemming verlenen aan een aantal verkopers die door het CMP worden getoond.

Wanneer de gebruiker zijn privacyopties heeft geselecteerd, worden de keuzen van de gebruiker vastgelegd in de TCF-toestemmingstekenreeks van IAB. De TCF toestemmingskoord IAB slaat de combinatie goedgekeurde doeleinden en verkopers, samen met andere meta-gegevensinformatie op (zie de pagina [](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/Consent%20string%20and%20vendor%20list%20formats%20v1.1%20Final.md#Consent-string-and-vendor-list-format) IAB voor meer informatie). Elke verkoper die in IAB TCF wordt geregistreerd evalueert het IAB TCF toestemmingskoord en neemt besluiten die op de privacykeuzen van de gebruikers worden gebaseerd. Houd er rekening mee dat de privacyopties van de gebruikers geldig zijn voor alle goedgekeurde leveranciers.

## Standaarddoelen vereist door Audience Manager {#aam-standard-purposes}

De Manager van de publiek evalueert de keuzen van de gebruikers die in het IAB TFC- toestemmingskoord worden opgeslagen voor:

* Opslag en toegang van informatie (doel-id 1 in de [algemene leverancierslijst](https://vendorlist.consensu.org/vendorlist.json))
* Personalisatie (doel-ID 2)
* Meting (doel-ID 5)
* De leverancier van de Manager van het publiek stemt toe om, gegevens voor een uitgever op te slaan, te verwerken of te activeren.

>[!IMPORTANT]
>
>Audience Manager heeft toestemming voor *alle drie de doeleinden nodig, plus toestemming* van de leverancier om cookies te implementeren en ID-syncs te initiëren of te respecteren.

## Het gedrag van Auditiebeheer is afhankelijk van het feit of de gebruiker toestemming verleent {#aam-behavior-consent}

De Manager van de Publiek werkt verschillend afhankelijk van of de Manager van de Publiek in het TCF toestemmingskoord ontdekt IAB dat de gebruiker toestemming voor de drie doeleinden (opslag, verpersoonlijking, meting) of niet heeft verleend.

| Wanneer uw gebruiker toestemming *verleent*, Manager van het Publiek: | Wanneer uw gebruiker *toestemming ontkent* , de Manager van het Publiek: |
|---|---|
| <ul><li>Hiermee voert u alle gewenste gevallen uit voor het gebruik van Audience Manager.</li><li>Hiermee geeft u toestemming aan derden in id-syncs (door gdpr = 1 en de toestemmingstekenreeks als gdpr_agreement door te geven voor id-synchronisatieaanroepen).</li><li>Evalueert en eerbiedigt toestemming die van de serverpixel wordt overgegaan.</li><li>Haalt partner-in werking gestelde syncs van identiteitskaart</li></ul> | <ul><li>Hiermee worden geen nieuwe gebruikersgegevens in uw instantie opgeslagen. Dit omvat partner IDs, signalen, eigenschappen, of pixelgegevens.</li><li>Hiermee initieert u geen syntaxis met id&#39;s van derden.</li><li>Hierbij worden de syncs van id&#39;s die door een partner zijn geïnitieerd, niet gerespecteerd.</li></ul> |

## Hoofdletters/kleine letters voor uitgever {#publisher-use-case}

Door IAB TCF uit te voeren, wordt u vereist niet om douanecode voor toestemmingsbeheer op uw Web-eigenschappen via een verschillend mechanisme met Adobe of andere derdeverkopers te handhaven. Het gebruiksscenario wordt beschreven in de afbeelding en in de onderstaande stappen. Begin links van de afbeelding:

1. Een gebruiker bezoekt een van uw wegeigenschappen. Zolang u de nieuwste versies van de ECID- en DIL-bibliotheken gebruikt (zie [Voorwaarden](/help/using/overview/data-security-and-privacy/aam-iab-plugin.md#prerequisites)), wordt de optiestroom geactiveerd.
2. Audience Manager controleert of de IAB-stroom wordt toegepast (`isIabContext=true`). Zie [Aanbevelingen en hoe te om uit te voeren](aam-iab-plugin.md#recommendations).
3. Audience Manager controleert of GDPR van toepassing is (`gdpr = 1`) en of er een CMP is, geregistreerd bij IAB, op uw webeigenschap. Dit geldt bijvoorbeeld voor gebruikers die vanuit de Europese Unie reizen. Als uitgever is het uw verantwoordelijkheid om de GDPR-markering in te stellen.
4. Als GDPR van toepassing is, controleert de Manager van de Publiek het IAB TCF toestemmingskoord, dat in de parameter wordt overgegaan `gdpr_consent`, voor de noodzakelijke toestemmingen. Audience Manager heeft machtigingen nodig voor opslag, personalisatie, meting en de toestemming van de leverancier van Audience Manager om gegevens op te slaan, te verwerken of te activeren.
5. Als de TCF toestemmingskoord van IAB aanwezig is en het de vereiste toestemmingen bevat, gaat de Manager van de Publiek het TCF toestemmingskoord van IAB over op onze servers [van de](../../reference/system-components/components-data-collection.md) gegevensinzameling (DCS).
6. Audience Manager reageert door een [indexcookie](https://docs.adobe.com/content/help/en/core-services/interface/ec-cookies/cookies-am.html) in te stellen op de browser. Audience Manager initieert en houdt tevens rekening met syntaxis van externe id&#39;s.
7. Alternatief, als het IAB TCF toestemmingskoord dat in stap 5 wordt overgegaan niet alle vereiste toestemmingen bevat, verzamelt, verwerkt of activeert de Manager van het publiek geen gegevens en respecteert of in werking stelt identiteitskaart- syncs.

![Hoofdletters/kleine letters voor uitgever](assets/publisher-use-case.png)

## Gebruiksscenario voor adverteerders {#advertiser-use-case}

Audience Manager evalueert en houdt rekening met toestemming die in [pixelaanroepen](../../integration/sending-audience-data/real-time-data-integration/pixel-based-data-transfer.md)is doorgegeven, in overeenstemming met IAB TCF.

De pixel worden over het algemeen geplaatst door de klanten van de Manager van de Publiek op hun partnerpagina&#39;s of zij worden geplaatst in ad servers om in de advertentierespons te omvatten. In het eerste geval, moet uw partner programmatically de toestemmingsparameter terugwinnen en het toevoegen aan het pixel alvorens te ontslaan. In het tweede geval, dat gemeenschappelijker is en hieronder in detail wordt beschreven, voegen de servers de toestemmingsparameters toe zij van het Platform van de levering-zij (SSP) of uitgever en servers aan alle pixel ontvangen.

De Manager van het publiek gebruikt twee parameters om gebruikerstoestemming in pixelvraag over te gaan:

* `gdpr` kan 0 zijn (GDPR is niet van toepassing) of 1 (GDPR is van toepassing);
* `gdpr_consent` is de URL-veilige base64-gecodeerde GDPR toestemmingstekenreeks (zie [specificatie](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/URL-based%20Consent%20Passing_%20Framework%20Guidance.md#specifications)). Een voorbeeldvraag naar een pixel waarop de indruk wordt gewekt, met de volgende twee parameters:

```
http://yourcompany.demdex.net/event?d_event=imp&gdpr=1&gdpr_consent=consentstring&d_src=datasource_id&d_site=siteID&d_creative=creative_id&d_adgroup=adgroup_id&d_placement=placement_id
```

Het gebruiksscenario wordt beschreven in de afbeelding en in de onderstaande stappen. Begin links van de afbeelding:

1. Uw gebruiker krijgt een indruk via een advertentieserver. Dit vertaalt in een pixelvraag aan onze Servers van de Inzameling van Gegevens (DCS).
2. Audience Manager controleert of de GDPR-markering van toepassing is. Als dit niet het geval is, slaat Audience Manager de gegevens op die in macrovariabelen in pixelaanroepen worden doorgegeven.
3. Als de toestemmingskoord aanwezig is en het de vereiste toestemmingen bevat, slaat de Manager van de Publiek de gegevens op die in macrovariabelen in pixelvraag worden overgegaan.
4. Als de toestemmingskoord mist of de vereiste toestemmingen mist, laat de Manager van de Publiek de gegevens vallen die in macrovariabelen in pixelvraag worden overgegaan.

![Gebruiksscenario voor adverteerders](assets/advertiser-use-case.png)

## Activeringspartners die IAB TCF steunen {#aam-activation-partners}

Met de plug-in Audience Manager voor IAB TCF kunt u de TCF-toestemmingstekenreeks van IAB doorsturen naar activeringspartners terwijl de privacyopties van de gebruikers worden gerespecteerd. Voor informatie waarop de activeringspartners IAB TCF steunen, verwijs naar onze [lijst van op apparaat-gebaseerde bestemmingen](/help/using/features/destinations/device-based-destinations-list.md).

## De IAB-implementatie testen {#test-iab-implementation}

Om te testen dat u correct het elektrische toestel van de Manager van de Publiek voor IAB TCF hebt uitgevoerd, lees [Gebruik Geval 4 in Methoden van de Bevestiging voor Opt-binnen en implementatie](https://docs.adobe.com/content/help/en/id-service/using/implementation/opt-in-service/testing-optin-and-iab-plugin.html#section-64331998954d4892960dcecd744a6d88)IAB.

## IAB en Opt-out in de Manager van het Publiek. Volgorde. {#iab-and-optout}

Een andere privacyoptie waarover uw gebruikers beschikken, is de mogelijkheid om zich af te melden voor het verzamelen van gegevens. Adobe biedt gebruikers de middelen om dit te doen op de pagina [Uw privacyopties](https://www.adobe.com/privacy/opt-out.html#customeruse) .

Audience Manager behandelt verzoeken om te weigeren in een [afzonderlijk artikel in onze documentatie](data-privacy-requests.md).

>[!NOTE]
>
>**Volgorde van Voorrang** - als uw gebruiker opteert uit gegevensinzameling gebruikend een globaal opt-out hulpmiddel, zoals die in de verbinding hierboven wordt beschreven, neemt dit belangrijkheid over opt-in en IAB controles.

## Aanvullende bronnen {#additional-resources}

* [Adobe Experience Platform Identity Service Opt-in](https://docs.adobe.com/content/help/en/id-service/using/implementation/opt-in-service/optin-overview.html)
* [IAB Europe GDPR-kader voor transparantie en instemming](https://iabtechlab.com/standards/gdpr-transparency-and-consent-framework/)
* [IAB Europe GDPR Transparency and Consent Framework Technische specificaties](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/Consent%20string%20and%20vendor%20list%20formats%20v1.1%20Final.md)
* [IAB TCF-plug-in - videodemonstratie](https://helpx.adobe.com/audience-manager/kt/using/iab-tcf-support-audience-manager-technical-video-implement.html)