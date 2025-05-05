---
description: De bètaomgeving is bedoeld voor het testen van de implementatie van uw Audience Manager. Wijzigingen in bèta hebben geen invloed op de productiegegevens. Neem contact op met de vertegenwoordiger van de Partner Solutions van uw Audience Manager als u geïnteresseerd bent in het gebruik van de bètaomgeving.
keywords: sandbox
seo-description: The beta environment is for testing your Audience Manager implementation. Changes made in beta do not affect production data. Contact your Audience Manager Partner Solutions representative if you're interested in using the beta environment.
seo-title: Beta Environment
solution: Audience Manager
title: Bètaomgeving
uuid: de4a1a46-cfa4-4f64-8569-48a7650fd8cf
feature: Reference
exl-id: a6a5e1c2-29a2-40bf-972c-87fb8716a394
source-git-commit: fce39268f1c8c4dd1b7ff21b61a9830a20fa0b4e
workflow-type: tm+mt
source-wordcount: '373'
ht-degree: 2%

---

# Bètaomgeving {#beta-environment}

De bètaomgeving is bedoeld voor het testen van de implementatie van uw Audience Manager. Wijzigingen in bèta hebben geen invloed op de productiegegevens. Neem contact op met de vertegenwoordiger van de Partner Solutions van uw Audience Manager als u geïnteresseerd bent in het gebruik van de bètaomgeving.

## Overzicht

De functionaliteit in de omgeving van de bveta is een exacte replica van de productieomgeving, zonder experimentele of niet-uitgebrachte kenmerken. Uw aanmeldingsgegevens van de productieomgeving zijn geldig in de bètaomgeving.

**Plan bijwerken**

De bètaomgeving wordt aan het einde van elke maand bijgewerkt tijdens niet-piekuren.

>[!IMPORTANT]
>
>Merk op dat uw klantgegevens ([signalen, eigenschappen en segmenten](https://experienceleague.adobe.com/docs/audience-manager/user-guide/reference/signal-trait-segment.html?lang=nl-NL)) niet wordt gesynchroniseerd tussen de productie- en bètaomgevingen.

## Binnenkomend verkeer

De bètaomgeving ondersteunt alleen binnenkomend verkeer voor de validatie van de bestandsnaam en de inhoudsyntaxis. Aangezien er geen id-toewijzing plaatsvindt in de bètaomgeving, zullen klanten geen segmentpopulaties zien.

De [!UICONTROL Onboarding Status] pagina wordt altijd gerapporteerd [!UICONTROL No matching AAM ID] bij inname van bestanden in de bètaomgeving.

Wij adviseren alle klanten om het even welke binnenkomende tests op hun productiemilieu uit te voeren.

## Uitgaand Verkeer

Het uitgaande verkeer wordt niet toegelaten voor het bètamilieu.

## Eindpunten

| Service | URL/hostnaam | Hoe te om toegang te verkrijgen |
|--- |--- | --- |
| S3 | Neem contact op met uw Audience Manager Partner Solutions-vertegenwoordiger of klantenservice | Neem contact op met uw Audience Manager Partner Solutions-vertegenwoordiger of de klantenservice om een Amazon S3-emmertje voor uw bètainstantie in te stellen. Meer informatie over de [voordelen van het gebruik van Amazon S3](../reference/amazon-s3.md). |
| DCS | `https://dcs-beta.demdex.net/...` | Zie [De DCS openen in de bètomgeving](../reference/beta-environment.md#access-dcs-beta-environment). |
| UI | `https://bank-beta.demdex.com` | Uw referenties voor de productieomgeving zijn geldig voor de bètaomgeving. |
| API | `https://api-beta.demdex.com/...` | Uw referenties voor de productieomgeving zijn geldig voor de bètaomgeving. We raden u aan een algemene API-gebruiker te maken. [zie details](../api/rest-api-main/aam-api-getting-started.md#requirements). |

## De DCS openen in de bètomgeving {#access-dcs-beta-environment}

1. Maak een vraag DCS gebruikend de krulling [command](https://curl.haxx.se/docs/manpage.html). Curl is een hulpmiddel om gegevens van of naar een server over te brengen, gebruikend één van vele gesteunde protocollen.

   Bijvoorbeeld:

   `curl -v https://dcs-beta.demdex.net/event`

1. Controleer of uw verzoek door de bètaversie-DCS is verzonden door te zoeken naar &quot;sandbox&quot; in de DCS-antwoordheader.

   Bijvoorbeeld:

   ```
   curl -v http://dcs-beta.demdex.net/?event
   [...]
   < DCS: va6-sandbox-dcs-3.sandbox.demdex.com <release_number>
   [...]
   ```

<!--

1. Determine the load balancer's endpoint IP addresses.

   Run the `dig`  [command](https://en.wikipedia.org/wiki/Dig_(command)) to determine the IP address of the nearest load balancer. The `dig` command queries the Domain Name System and returns the name and IP addresses of the [!DNL Audience Manager] [!UICONTROL Data Collection Servers (DCS)].

   ```
   dig dcs-beta.demdex.net
   ...
   dcs-sandbox-1754093861.us-east-1.elb.amazonaws.com. 60 IN A 52.87.15.51
   dcs-sandbox-1754093861.us-east-1.elb.amazonaws.com. 60 IN A 50.16.150.8
   dcs-sandbox-1754093861.us-east-1.elb.amazonaws.com. 60 IN A 52.2.228.100
   ```

2. Using one of the addresses in the above table, add a static DNS entry in the [!DNL /etc/hosts] file.

   On Windows, modify [!DNL c:\WINDOWS\system32\drivers\etc\hosts].

   For example:

   [!DNL 52.87.15.51 *`samplepartner`*.demdex.net]

   >[!NOTE]
   >
   >The addresses change occasionally, so you must keep your [!DNL /etc/hosts] file up to date.

   Additionally, if you need to set up ID synchronization, you must add a similar entry for [!DNL dpm.demdex.net.]

   [!DNL 52.87.15.51 dpm.demdex.net]. 

3. Make a DCS call, using the `curl` [command](https://curl.haxx.se/docs/manpage.html). Curl is a tool to transfer data from or to a server, using one of many supported protocols.

   For example:

   [!DNL https://<domain>/event?product=camera] 

4. Verify that your request was served by the beta DCS by looking for "sandbox" in the DCS response header.

   For example:

   ```
   curl -v https://dcs-beta.demdex.net/?event
   [...]
   < DCS: va6-sandbox-dcs-3.sandbox.demdex.com <release_number>
   [...]
   ```

   -->
