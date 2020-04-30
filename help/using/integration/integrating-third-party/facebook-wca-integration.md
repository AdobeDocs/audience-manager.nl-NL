---
description: Deze pagina illustreert het proces van het maken van WCA-pixels (Custom Audiences) op de Facebook-website om publiekssegmenten van de webgebaseerde Audience Manager naar Facebook te sturen, zodat deze online kunnen worden geplaatst en doelgericht kunnen worden met een verbeterde transparantie.
seo-description: Deze pagina illustreert het proces van het maken van WCA-pixels (Custom Audiences) op de Facebook-website om publiekssegmenten van de webgebaseerde Audience Manager naar Facebook te sturen, zodat deze online kunnen worden geplaatst en doelgericht kunnen worden met een verbeterde transparantie.
seo-title: Facebook WCA-integratie
solution: Audience Manager
title: Facebook WCA-integratie
translation-type: tm+mt
source-git-commit: 412972b9d9a633d09de411c46528b93c74a64e3f

---


# Facebook WCA-integratie {#facebook-wca-integration}

Deze pagina illustreert het proces van het maken van WCA-pixels (Custom Audiences) op de Facebook-website om publiekssegmenten van de webgebaseerde Audience Manager naar Facebook te sturen, zodat deze online kunnen worden geplaatst en doelgericht kunnen worden met een verbeterde transparantie.

## Overzicht {#overview}

[Met Facebook Website Custom Audiences (WCA)](https://www.facebook.com/business/help/449542958510885) kunt u een lijst maken met personen die bepaalde pagina&#39;s hebben bezocht of bepaalde handelingen op uw website hebben uitgevoerd. Audience Manager maakt activering in WCA mogelijk met behulp van URL-doelen, waarmee u een aangepaste pixelgebaseerde integratie kunt configureren om een op het web gebaseerd publiek naar Facebook te sturen voor activering.

![Facebook WCA-integratie](/help/using/integration/assets/facebook-wca-integration.png)

>[!IMPORTANT]
>
> Voor deze functie moet u de optie Websitepubliek selecteren voor sociale platforms in [URL-doelen](/help/using/features/destinations/create-url-destination.md). Sociale platforms vereisen dat de informatie van de verwijzer wordt ontmaskerd wanneer verzonden naar hun platform. Houd er rekening mee dat dit betekent dat het doelplatform/de doelpartner informatie kan zien in uw referentie-URL.

## Vereisten {#prerequisites}

1. Facebook Advertentieaccount
2. De segmenten van de Manager van het publiek, klaar om aan uw nieuwe bestemming van Facebook toe te wijzen. Hier is [hoe te om een segment](/help/using/features/segments/segment-builder.md) in de Manager UI van de Publiek tot stand te brengen.
3. Adobe Experience Platform Identity Service (ECID) Versie 4.1.0 of hoger. Download de nieuwste versie **[hier](https://github.com/Adobe-Marketing-Cloud/id-service/releases)**.
4. Audience Manager Data Integration Library (DIL) versie 9.0 of hoger, kan **[hier](https://github.com/Adobe-Marketing-Cloud/dil/releases)**worden gedownload. Als u ook[Server-Side Forwarding (SSF)](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/server-side-forwarding/ssf.html)gebruikt om gegevens te importeren in Audience Manager, moet u AppMeasurement versie 2.12 of hoger gebruiken. Download AppMeasurement met behulp van[Analytics Code Manager](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/code-manager-admin.html).

We raden u aan de bibliotheken in stap 3 en 4 te installeren of bij te werken met [Adobe Experience Platform Launch](https://docs.adobelaunch.com/) of [Adobe Dynamic Tag Management](https://docs.adobe.com/content/help/en/dtm/using/dtm-home.html).

## Stap 1 - Een Facebook-bestemming maken in Audience Manager {#step-1-create-facebook-destination}

Maak een nieuwe URL-bestemming in Audience Manager en geef deze de naam Aangepast publiek voor Facebook-website. Gebruik de onderstaande instellingen bij het maken van het doel. U kunt ook naar de pagina [Een URL-doel](/help/using/features/destinations/create-url-destination.md) configureren verwijzen.

**Basisinformatie**

* **Categorie**: Aangepast
* **Type**: URL
* Schakel het selectievakje Toewijzing bestemming **automatisch vullen** in en selecteer vervolgens **Segment-id**.

**Labels voor gegevensexport**

Selecteer de optie **Deze bestemming kan een combinatie met persoonlijk identificeerbare informatie (PII)** toelaten.

>[!NOTE]
>
> Dit exportlabel voorkomt dat gegevens en gegevens van derden die zijn afgeleid van apparaatgrafieken, in de segmenten worden opgenomen.

**Configuratie**

* **Type** URL: Selecteer **Websitepubliek voor sociale platforms**. Door deze optie voor URL-type te selecteren, verbergt Audience Manager de URL-informatie van de referentie niet wanneer een WCA-pixel op Facebook wordt afgevuurd.
* **Serienummering**: Selecteer **Inschakelen**.
* Voer in het veld **Basis-URL** en **Beveiligde URL** de Facebook WCA-pixel in.
* **Scheidingsteken**: ,

Voorbeeld van basis-URL: `https://www.facebook.com/tr/?id=XXXXXXXXX&ev=Adobe-Audience-Manager-Segment&cd[segID]=%ALIAS%&noscript=1`

Voorbeeld van pixel die van de pagina worden afgegaan. In dit voorbeeld wordt een gebruiker weergegeven die in aanmerking komt voor drie segmenten van Audience Manager, met de ID&#39;s 3401321, 2993399, 3263410:

`https://www.facebook.com/tr/?id=6876666666662303&ev=Adobe-Audience-Manager-Segment&cd[segID]=3401321,2993399,3263410&noscript=1`


| Parameter | Beschrijving |
---------|----------|
| `id` | Uw pixel-id van Facebook, die u kunt vinden in de interface van Advertentiebeheer op Facebook wanneer u publiekspixels creeert. |
| `ev` | Gebeurtenis. Dit is een willekeurige waarde, die wordt weergegeven in de interface van Advertentiebeheer op Facebook nadat de pixel op de site wordt geactiveerd. Zie het item Opnemen in [stap 3](/help/using/integration/integrating-third-party/facebook-wca-integration.md#step-3-create-audience)voor meer informatie. |
| `cd[segID]` | Een aanvullende parameter die wordt toegevoegd aan de interface van Advertentiemanager op Facebook nadat de pixel op de site wordt geactiveerd. `segID` is ook arbitrair. |
| `%ALIAS%` | Een macro van de Manager van de Publiek, die dynamisch zal worden vervangen met de segmentenIDs van de Manager van de Publiek die de plaatsbezoeker voor kwalificeert, door komma wordt afgebakend, |

Uw URL-doelconfiguratie moet er als volgt uitzien in de onderstaande afbeelding:

![Doelconfiguratie](/help/using/integration/assets/facebook-wca.png)

Sla het doel op. Vervolgens kunt u doorgaan naar de stap **Segmenttoewijzingen** .

## Stap 2 - de Toewijzingen van het segment - de Segment van de kaart aan Bestemming {#step-2-segment-mappings}

In het [Configure URL bestemmingswerkschema](/help/using/features/destinations/create-url-destination.md) , kaart het toepasselijke segment aan uw pas gecreëerde bestemming. Merk op dat de toewijzingswaarde auto-bevolkt met de het segmentidentiteitskaart van de Manager van de Publiek is.

Voer indien van toepassing een einddatum in, laat anders niets staan voor de einddatum.

## Stap 3 - Een publiek maken in Facebook Ads Manager {#step-3-create-audience}

Zie [Een aangepast publiek](https://www.facebook.com/business/help/666509013483225) voor websites maken in de Help-documentatie van Facebook. Selecteer de opties voor het publiek maken in de onderstaande tabel:


| Item | Beschrijving |
---------|----------|
| Websiteverkeer | Aangepaste combinatie |
| Inclusief | <ul><li>Selecteer **Gebeurtenis** > Selecteer **Adobe-Audience-Manager-Segment**. Dit was de waarde van de ev-parameter in de voorbeeldpixel in stap 1. Houd er rekening mee dat als de pixel nog moet worden geactiveerd, de optie **Gebeurtenis** of **Adobe-Audience-Manager-Segment** mogelijk niet wordt weergegeven in de Facebook-interface.</li><li>Een parameter toevoegen: Selecteer `segID`.</li><li><p>Selecteer de operator **contains** .</p><p>Dit is belangrijk, aangezien bezoekers voor veelvoudige segmenten kunnen kwalificeren, er veelvoudige segment IDs in de pixelparameter kunnen zijn. Het gebruik van de operator = (gelijk aan) kwalificeert uw bezoekers mogelijk niet voor het publiek en u ziet een lager volume.</p></li><li>Voeg een waarde toe: Voer de segment-id in van Audience Manager.</li></ul> |
| Nieuwe voorwaarde toevoegen | Optionele instelling. |
| In de laatste | Optionele instelling. |
| Auditienaam | Wij adviseren u de zelfde het segmentnaam van de Manager van de Publiek voor consistentie gebruikt, tenzij u extra voorwaarden aan dit Publiek toevoegt. |

## Stap 4 - Het publiek toewijzen aan een campagne in Facebook Ads Manager {#step-4-assign-audience-to-campaign}

Nadat u het aangepaste publiek hebt gemaakt, wijst u dit toe aan een advertentiecampagne. Maak een nieuwe campagne of bewerk een bestaande campagne en u ziet dat het nieuwe publiek wordt vermeld in de Facebook-interface. Uw advertentiecampagne richt zich op gebruikers die de pixelbrand op hun browser hebben gezien toen het bezoeken van uw plaats, als de Manager van het Publiek hen in het segment omvat.

## Samenvatting {#summary}

Nu u uw segment Audience Manager aan de bestemming van Facebook WCA hebt toegewezen, zal de Manager van de Publiek selectief de pixel van Facebook WCA aan gebruikers van een bepaald segment met respectieve segment identiteitskaart in de pixel in brand steken om het Publiek van Facebook te bevolken. Dit leidt tot een geleidelijke verhoging van het publiek van Facebook naarmate de tag meer op het toepasselijke publiek op uw site wordt afgevuurd.

>[!NOTE]
>
> Als een gebruiker buiten het segment Audience Manager valt, is er momenteel geen manier voor Audience Manager om Facebook op de hoogte te brengen om de gebruiker uit het segment Custom Audience te verwijderen.

