---
description: Adobe biedt u de middelen om de privacykeuzes van uw gebruikers te beheren en door te geven via de aanmeldingsfunctionaliteit en via de ondersteuning voor IAB-transparantie en Consent Framework (TCF). In dit artikel worden de gevallen beschreven waarin Audience Manager de IAB TCF ondersteunt en hoe u de IAB TCF-ondersteuning implementeert in Audience Manager.
seo-description: Adobe biedt u de middelen om de privacykeuzes van uw gebruikers te beheren en door te geven via de aanmeldingsfunctionaliteit en via de ondersteuning voor IAB-transparantie en Consent Framework (TCF). In dit artikel worden de gevallen beschreven waarin Audience Manager de IAB TCF ondersteunt en hoe u de IAB TCF-ondersteuning implementeert in Audience Manager.
seo-title: Insteekmodule Audience Manager voor IAB TCF
solution: Audience Manager
title: Insteekmodule Audience Manager voor IAB TCF
translation-type: tm+mt
source-git-commit: b5c56453a7278573dec2b80be7baa9833a847a4a
workflow-type: tm+mt
source-wordcount: '2432'
ht-degree: 0%

---


# Insteekmodule Audience Manager voor IAB TCF {#aam-iab-plugin}

## Overzicht

Een belangrijk aspect in de privacyverplichtingen die u jegens uw gebruikers kunt hebben, is de verwerving en doorgifte van keuzemogelijkheden voor gebruikers over de manier waarop hun persoonsgegevens kunnen worden gebruikt (d.w.z. &quot;doeleinden&quot;) en door wie (d.w.z. &quot;bedrijven&quot;).

Adobe biedt u de middelen om de privacykeuzes van uw gebruikers te beheren en door te geven via de [aanmeldingsfunctionaliteit](https://docs.adobe.com/content/help/en/id-service/using/implementation/opt-in-service/optin-overview.html) en via de ondersteuning voor [IAB Transparency and Consent Framework (TCF)](https://iabtechlab.com/standards/gdpr-transparency-and-consent-framework/) .

In dit artikel worden de gevallen beschreven waarin Audience Manager de IAB TCF ondersteunt en hoe u de IAB TCF-ondersteuning implementeert in Audience Manager.

>[!IMPORTANT]
>
>Audience Manager is geregistreerd in de [IAB TCF](https://iabeurope.eu/tcf-for-vendors/) met leverancier-id 565.

De plug-in Audience Manager voor IAB TCF maakt gebruik van de [plug-in Opt-in, die op zijn beurt onderdeel is van de bibliotheek van](https://docs.adobe.com/content/help/en/id-service/using/implementation/opt-in-service/iab.html)Adobe Experience Platform Identity Service (ECID) [](https://docs.adobe.com/content/help/en/id-service/using/home.html) .

## Toepassingsgebied en beperkingen {#scope-and-limitations}

Als Uitgever of Advertiser die met de Manager van de Publiek werkt, kunt u gebruikerskeuzen aan de Manager van de Publiek overeenkomstig IAB TCF overbrengen.

>[!IMPORTANT]
>
>De TCF-regels van IAB zijn alleen van toepassing op bezoekers die in de Europese Economische Ruimte gevestigd zijn.

Met Audience Manager kunt u de privacyopties van uw gebruikers respecteren en beschikt u ook over een eenvoudige manier om deze keuzen door te geven aan alle partners waarmee u werkt.

Audience Manager biedt momenteel geen ondersteuning voor:

* Workflows voor mobiele apparaten;
* Toevoeging van toestemming voor het segmenteren van de uitvoer.

## Vereisten {#prerequisites}

>[!IMPORTANT]
>
>Audience Manager biedt ondersteuning voor IAB TCF v2.0.
>
>IAB TCF v1.1 steun zal op 15 augustus 2020 eindigen.
>
> Klanten die de plug-in Audience Manager voor IAB TCF willen blijven gebruiken voor het beheer van hun toestemming, dienen een upgrade uit te voeren naar de nieuwste versie van [ECID](https://github.com/Adobe-Marketing-Cloud/id-service/releases) voor verdere ondersteuning.
>
> Nadat u de upgrade naar de nieuwste [ECID](https://github.com/Adobe-Marketing-Cloud/id-service/releases) -versie hebt uitgevoerd, worden de CMP-goedkeuringstekenreeksen voor IAB TCF v1.1 niet meer ondersteund. Werk uw CMP dus bij voordat u de upgrade naar de nieuwste ECID-versie uitvoert.

U moet aan de volgende voorwaarden voldoen om de Plug-in van de Manager van de Publiek voor IAB TCF met de Manager van de Publiek te gebruiken:

1. U moet Adobe Experience Platform Identity Service (ECID) versie 5 of hoger gebruiken. [Download](https://github.com/Adobe-Marketing-Cloud/id-service/releases) onze nieuwste ECID-release.
2. U moet versie 9.0 of hoger van de Bibliotheek van de Integratie van Gegevens van de Manager van de Audience gebruiken, downloadbaar van [hier](https://github.com/Adobe-Marketing-Cloud/dil/releases). Lees meer over [DIL in de documentatie](../..//dil/dil-overview.md)van Audience Manager. We raden u aan [Adobe Launch](https://docs.adobe.com/content/help/en/launch/using/extensions-ref/adobe-extension/adobe-audience-manager-extension.html) te gebruiken voor de eenvoudigste DIL-implementatie voor Audience Manager.
3. Alternatief, als u server-zij het Door:sturen (SSF) gebruikt om gegevens in de Manager van de Audience in te voeren, moet u aan de recentste versie van AppMeasurement bevorderen. Download AppMeasurement met behulp van [Analytics Code Manager](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/code-manager-admin.html).
4. U moet een CMP (Consent Management Platform) gebruiken, commercieel of uw eigen platform, dat geïntegreerd is met IAB TCF v2.0 en geregistreerd is met IAB TCF. Zie de lijst van [CMP&#39;s die in het IAB-kader](https://iabeurope.eu/cmp-list/)zijn geregistreerd.

>[!WARNING]
>
>Als u een platform van het Beheer van de Toestemming gebruikt (CMP) dat geen IAB TCF v.2.0 steunt, zal de Manager van de Publiek automatisch de `gdpr=0` parameter in syncs van identiteitskaart verzenden, zelfs als uw bezoekers in de Europese Unie zijn. Om te bepalen of uw GDPR-validatie actief is, raden we u aan om met uw CMP (Consent Management Platform) te bevestigen dat zij IAB TCF v2.0 ondersteunen.

## Aanbevelingen en de wijze van uitvoering {#recommendations}

Om de steun IAB TCF in de Manager van het Publiek toe te laten, lees onze documentatie over [hoe te opstelling IAB met Opt-in](https://docs.adobe.com/content/help/en/id-service/using/implementation/opt-in-service/iab.html).

De eenvoudigste manier om dit te doen, is door het gebruik van [Adobe Experience Platform Launch](https://docs.adobe.com/content/help/en/launch/using/overview.html) om ECID Opt-in aan uw eigenschappen toe te voegen. Lees de documentatie voor de [ECID Opt-in uitbreiding](https://docs.adobe.com/content/help/en/launch/using/extensions-ref/adobe-extension/id-service-extension/overview.html) om te leren hoe te opstelling de uitbreiding van de Lancering.

## Gebruikerskeuzeworkflow bij gebruik van IAB-framework {#user-choice-workflow}

Wanneer u een webeigenschap bezoekt, kunnen uw gebruikers hun keuze opgeven voor de manier waarop hun gegevens door de uitgever en door de externe leveranciers waarmee de uitgever werkt moeten worden gebruikt.

Gebruikers bieden hun keuzes in de vorm van *toestemming* en *gewettigd belang* voor de IAB-doeleinden aan *externe leveranciers* die in de wereldwijde lijst van leveranciers zijn geregistreerd.

De onderstaande afbeelding is een voorbeeld van een CMP-dialoogvenster dat wordt weergegeven voor een nieuwe bezoeker van een website. Vergeet niet dat dit dialoogvenster er anders kan uitzien, op basis van de implementatie door de klant.

![CMP-dialoogvenster](assets/cmp-example.png)

Details over de verschillende doeleinden en toestemmingen inbegrepen in IAB TCF v2.0 zijn behandeld in het Beleid van het Kader van het Kader van de Transparantie &amp; van de Toestemming van [IAB Europa](https://iabeurope.eu/iab-europe-transparency-consent-framework-policies/#A_Purposes).

Gebruikers kunnen hun toestemming of gewettigd belang (indien beschikbaar) verlenen voor een combinatie van doeleinden en verkopers. Gebruikers zouden bijvoorbeeld hun toestemming kunnen verlenen om informatie op een apparaat op te slaan, producten te ontwikkelen en te verbeteren, en hun toestemming kunnen verlenen aan alle derde leveranciers die door het CMP worden weergegeven.

Of in een ander voorbeeld zouden zij hun toestemming of rechtmatig belang voor alle doeleinden kunnen verlenen, maar slechts toestemming of rechtmatig belang kunnen verlenen aan een aantal verkopers die door het CMP worden getoond.

Wanneer de gebruiker zijn privacyopties heeft geselecteerd, worden de keuzen van de gebruiker opgenomen in de IAB TC-tekenreeks. De koord IAB TC slaat de combinatie goedgekeurde doeleinden en verkopers, samen met andere meta-gegevensinformatie (zie de pagina [](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/TCFv2/IAB%20Tech%20Lab%20-%20Consent%20string%20and%20vendor%20list%20formats%20v2.md#about-the-transparency--consent-string-tc-string) IAB voor meer informatie) op.

Elke leverancier die in IAB TCF wordt geregistreerd evalueert het koord IAB TC en neemt besluiten die op de privacykeuzen van de gebruikers worden gebaseerd. Houd er rekening mee dat de privacyopties van de gebruikers geldig zijn voor alle leveranciers die zijn geregistreerd bij IAB TCF.

## Doelstellingen vereist door Audience Manager {#aam-standard-purposes}

Audience Manager evalueert de keuzes van de gebruikers die in de IAB TC-tekenreeks zijn opgeslagen voor de volgende doeleinden, gedefinieerd in het [IAB Europe Transparency &amp; Consent Framework-beleid](https://iabeurope.eu/iab-europe-transparency-consent-framework-policies/#A_Purposes). Bovendien kunt u de doelen ook vinden in de [algemene lijst met](https://vendorlist.consensu.org/vendorlist.json)leveranciers.

* **Doel 1**: Informatie over een apparaat opslaan en/of openen;
* **Doel 10**: Producten ontwikkelen en verbeteren;
* **Speciaal doel 1**: Zorgen voor beveiliging, fraude voorkomen en fouten opsporen.

>[!IMPORTANT]
>
>Audience Manager heeft toestemming nodig voor doel 1 en doel 10, plus toestemming van de leverancier, om cookies te implementeren en ID-syncs te initiëren of te respecteren.
>
>Conform [IAB-verordeningen](https://iabeurope.eu/iab-europe-transparency-consent-framework-policies/#Special_Purpose_1__Ensure_security_prevent_fraud_and_debug_), wordt Speciale Doelstelling 1 (Beveiliging, Fraude voorkomen en fouten opsporen) altijd goedgekeurd en kunnen gebruikers er geen bezwaar tegen maken.

## Het gedrag van Auditiebeheer is afhankelijk van het feit of de gebruiker toestemming verleent {#aam-behavior-consent}

Audience Manager werkt anders, afhankelijk van het feit of de IAB TC-tekenreeks toestemming van de gebruiker voor de twee doeleinden bevat (gegevens op een apparaat opslaan en/of openen en producten ontwikkelen en verbeteren) of niet.

Wij controleren ook gebruikerstoestemming voor alle bestemmingen die u met in de Manager van het Publiek werkt, zolang die bestemmingen met IAB TCF worden geregistreerd.

| Wanneer uw gebruiker toestemming *verleent*, Manager van het Publiek: | Als uw gebruiker *geen* toestemming geeft, wordt Audience Manager: |
|---|---|
| <ul><li>Hiermee voert u alle gewenste gevallen uit voor het gebruik van Audience Manager.</li><li>Hiermee geeft u toestemming aan derden in id-syncs (door `gdpr = 1` en de toestemmingstekenreeks door te geven als `gdpr_consent` bij ID-synchronisatieaanroepen).</li><li>Evalueert en eerbiedigt toestemming die van de serverpixel wordt overgegaan.</li><li>Haalt partner-in werking gestelde syncs van identiteitskaart</li></ul> | <ul><li>Hiermee worden geen nieuwe gebruikersgegevens in uw instantie opgeslagen. Dit omvat partner IDs, signalen, eigenschappen, of pixelgegevens.</li><li>Hiermee initieert u geen syntaxis met id&#39;s van derden.</li><li>Hierbij worden de syncs van id&#39;s die door een partner zijn geïnitieerd, niet gerespecteerd.</li><li>Hiermee wordt de gebruiker uitgesloten van verdere gegevensverzameling.</li></ul> |

## Hoofdletters/kleine letters voor uitgever {#publisher-use-case}

Door de plug-in Audience Manager voor IAB TCF te implementeren, hoeft u geen aangepaste code voor het beheer van de toestemming te onderhouden op uw wegeigenschappen via een ander mechanisme met Adobe of andere externe leveranciers. Het gebruiksscenario wordt beschreven in de afbeelding en in de onderstaande stappen. Begin links van de afbeelding:

1. Een gebruiker bezoekt een van uw wegeigenschappen. Zolang u de nieuwste versies van de ECID- en DIL-bibliotheken gebruikt (zie [Voorwaarden](/help/using/overview/data-security-and-privacy/aam-iab-plugin.md#prerequisites)), wordt de optiestroom geactiveerd.
2. Audience Manager controleert of de IAB-stroom wordt toegepast (`isIabContext=true`). Zie [Aanbevelingen en hoe te om uit te voeren](aam-iab-plugin.md#recommendations).
3. Audience Manager controleert of GDPR van toepassing is (`gdpr = 1`) en of er een CMP is, geregistreerd bij IAB TCF, op uw Webbezit. Dit geldt bijvoorbeeld voor gebruikers die vanuit de Europese Unie bezoeken. Als uitgever is het uw verantwoordelijkheid om de GDPR-markering in te stellen.
4. Als GDPR van toepassing is, controleert de Manager van de Publiek de koord IAB TC, die in de `gdpr_consent` parameter wordt overgegaan, voor de vereiste toestemming. Audience Manager heeft toestemming nodig voor het opslaan van en/of de toegang tot van informatie over een apparaat ([IAB TCF doel 1](https://iabeurope.eu/iab-europe-transparency-consent-framework-policies/#A_Purposes)), het ontwikkelen en het verbeteren van producten ([IAB TCF doel 10](https://iabeurope.eu/iab-europe-transparency-consent-framework-policies/#A_Purposes)), plus de verkoperstoestemming van de Manager van de Audience om gegevens op te slaan, te verwerken of te activeren.
5. Als de IAB TC-tekenreeks aanwezig is en deze de vereiste toestemming bevat, geeft Audience Manager de IAB TC-tekenreeks door aan onze [gegevensverzamelingsservers](../../reference/system-components/components-data-collection.md) (DCS).
6. Audience Manager reageert door een [indexcookie](https://docs.adobe.com/content/help/en/core-services/interface/ec-cookies/cookies-am.html) in te stellen op de browser en initieert en houdt zich aan de syntaxis van de id van derden.
7. Als de in stap 4 doorgegeven IAB TC-tekenreeks echter niet alle benodigde machtigingen bevat, worden gebruikersgegevens niet verzameld, verwerkt of geactiveerd en worden de id-syncs niet gerespecteerd of geïnitieerd. Bovendien, opteert het uit de gebruiker van de bestemmingen die u met werkt.

>[!IMPORTANT]
>
>Als u met de bestemmingspartners van de Manager van de Publiek werkt die parameters IAB TCF vereisen, maar u hebt geen CMP die IAB TCF op uw website steunt, dan verzendt de Manager van de Publiek `gdpr=0` in de syncs van identiteitskaart. Dit betekent dat GDPR niet van toepassing is op deze gebruikers.
>
> Als dat niet gewenst is, zou u de functionaliteit IAB TCF in de Manager van het Publiek moeten toelaten om de aangewezen koorden IAB TC naar de bestemmingspartners te verzenden.



![Hoofdletters/kleine letters voor uitgever](assets/publisher-use-case.png)

## Gebruiksscenario voor adverteerders {#advertiser-use-case}

Audience Manager evalueert en houdt rekening met toestemming die in [pixelaanroepen](../../integration/sending-audience-data/real-time-data-integration/pixel-based-data-transfer.md)is doorgegeven, in overeenstemming met IAB TCF.

De pixel kunnen door de klanten van de Manager van de Publiek op hun partnerpagina&#39;s worden geplaatst of zij worden geplaatst in ad servers om in de advertentierespons te omvatten. In het eerste geval, moet uw partner programmatically de toestemmingsparameter terugwinnen en het toevoegen aan het pixel alvorens te ontslaan. In het tweede geval, dat gemeenschappelijker is en hieronder in detail wordt beschreven, voegen de servers de toestemmingsparameters toe zij van het Platform van de levering-zij (SSP) of uitgever en servers aan alle pixel ontvangen.

De Manager van het publiek gebruikt twee parameters om gebruikerstoestemming in pixelvraag over te gaan:

* `gdpr` kan 0 zijn (GDPR is niet van toepassing) of 1 (GDPR is van toepassing);
* `gdpr_consent` is de URL-veilige base64-gecodeerde GDPR toestemmingstekenreeks (zie [specificatie](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/TCFv2/IAB%20Tech%20Lab%20-%20Consent%20string%20and%20vendor%20list%20formats%20v2.md#about-the-transparency--consent-string-tc-string)). Een voorbeeldvraag naar een pixel waarop de indruk wordt gewekt, met de volgende twee parameters:

```
http://yourcompany.demdex.net/event?d_event=imp&gdpr=1&gdpr_consent=consentstring&d_src=datasource_id&d_site=siteID&d_creative=creative_id&d_adgroup=adgroup_id&d_placement=placement_id
```

Het gebruiksscenario wordt beschreven in de afbeelding en in de onderstaande stappen. Begin links van de afbeelding:

1. Uw gebruiker krijgt een indruk via een advertentieserver. Dit vertaalt in een [pixelvraag](../../integration/media-data-integration/impression-data-pixels.md) aan onze Servers van de Inzameling van Gegevens (DCS).
2. Audience Manager controleert of de GDPR-markering van toepassing is. Als het niet, de Manager van de Publiek slaat de gegevens op die in de `gdpr` `gdpr_consent` en de variabelen in pixelvraag worden overgegaan.
3. Als de IAB TC-tekenreeks aanwezig is en deze de vereiste machtigingen bevat, slaat Audience Manager de gegevens op die worden doorgegeven in de `gdpr` en `gdpr_consent` variabelen in pixelaanroepen.
4. Als de IAB TC-tekenreeks ontbreekt of als de vereiste machtigingen ontbreken, worden de gegevens die zijn doorgegeven in de gegevensset `gdpr` en de `gdpr_consent` variabelen in pixelaanroepen door Audience Manager verwijderd.

![Gebruiksscenario voor adverteerders](assets/advertiser-use-case.png)

## Activeringspartners die IAB TCF steunen {#aam-activation-partners}

Met de plug-in Audience Manager voor IAB TCF kunt u de IAB TC-tekenreeks doorsturen naar activeringspartners met inachtneming van de privacyopties van de gebruikers. Voor informatie waarop de activeringspartners IAB TCF steunen, verwijs naar onze [lijst van op apparaat-gebaseerde bestemmingen](/help/using/features/destinations/device-based-destinations-list.md).

## Goedkeuring toevoegen aan URL&#39;s die naar URL-doelen zijn verzonden

De integratie van Audience Manager met IAB TCF v2.0 steunt het toevoegen van toestemming aan informatie die naar [URL bestemmingen](../../features/destinations/create-url-destination.md) wordt verzonden die met IAB TCF v2.0 geïntegreerd zijn. Dit proces wordt echter niet automatisch uitgevoerd door Audience Manager om te voorkomen dat specifieke URL-indelingen worden afgebroken.

Klanten die toestemming aan gegevens willen toevoegen die naar bestemmingen URL worden verzonden moeten manueel de `${GDPR}` en `${GDPR_CONSENT_XXXX}` `XXXX` macro&#39;s aan hun formaat toevoegen URL, die met identiteitskaart van de bestemmingspartner vervangen.

Voorbeeld: `http://yourdomain.com?gdpr=${GDPR}&gdpr_consent=${GDPR_CONSENT_1234}`.

Zie [Gedefinieerde](../../features/destinations/destination-macros.md) doelmacro&#39;s voor meer informatie over de ondersteunde doelmacro&#39;s.

## Beheer van apparaatinstemming

De insteekmodule Audience Manager voor IAB TCF sluit automatisch de id&#39;s uit die aanwezig zijn op een aanvraag wanneer uw sitebezoekers niet de juiste machtigingen bieden. Als het verzoek een [dwars-apparatenidentiteitskaart (identiteitskaart van CRM)](../../reference/ids-in-aam.md)bevat, opteert de Manager van de Publiek identiteitskaart, samen met het laatste apparaat verbonden aan die [dwars-apparatenidentiteitskaart (identiteitskaart van CRM)](../../reference/ids-in-aam.md).

## De IAB-implementatie testen {#test-iab-implementation}

Om te testen dat u correct de Plug-in van de Manager van de Audience voor IAB TCF hebt uitgevoerd, lees [Gebruik Geval 4 in het Bevalideren van Opt-in Dienst](https://docs.adobe.com/content/help/en/id-service/using/implementation/opt-in-service/testing-optin-and-iab-plugin.html#section-64331998954d4892960dcecd744a6d88).

## IAB en Opt-out in de Manager van het Publiek. Volgorde. {#iab-and-optout}

Een andere privacyoptie waarover uw gebruikers beschikken, is de mogelijkheid om zich af te melden voor het verzamelen van gegevens. Adobe biedt gebruikers de middelen om dit te doen op de pagina [Uw privacyopties](https://www.adobe.com/privacy/opt-out.html#customeruse) .

Audience Manager behandelt verzoeken om te weigeren in een [afzonderlijk artikel in onze documentatie](data-privacy-requests.md#opt-out-requests).

>[!IMPORTANT]
>
>Gebruikers die na hun weigering van toestemming uit de gegevensverzameling zijn gekomen, kunnen niet opnieuw worden ingeschakeld.

>[!NOTE]
>
>**Volgorde van Voorrang** - als uw gebruiker opteert uit gegevensinzameling gebruikend een globaal opt-out hulpmiddel, zoals die in de verbinding hierboven wordt beschreven, neemt dit belangrijkheid over opt-in en IAB controles.

## Aanvullende bronnen {#additional-resources}

* [Adobe Experience Platform Identity Service Opt-in](https://docs.adobe.com/content/help/en/id-service/using/implementation/opt-in-service/optin-overview.html)
* [IAB Europe GDPR-kader voor transparantie en instemming](https://iabtechlab.com/standards/gdpr-transparency-and-consent-framework/)
* [IAB Europe GDPR Transparency and Consent Framework Technische specificaties](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/Consent%20string%20and%20vendor%20list%20formats%20v1.1%20Final.md)
* [IAB TCF-plug-in - videodemonstratie](https://helpx.adobe.com/audience-manager/kt/using/iab-tcf-support-audience-manager-technical-video-implement.html)