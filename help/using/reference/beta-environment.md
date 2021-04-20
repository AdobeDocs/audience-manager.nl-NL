---
description: De bètaomgeving is bedoeld voor het testen van de implementatie van uw Audience Manager. Wijzigingen in bèta hebben geen invloed op de productiegegevens. Neem contact op met de vertegenwoordiger van de Partner Solutions van uw Audience Manager als u geïnteresseerd bent in het gebruik van de bètaomgeving.
keywords: sandbox
seo-description: De bètaomgeving is bedoeld voor het testen van de implementatie van uw Audience Manager. Wijzigingen in bèta hebben geen invloed op de productiegegevens. Neem contact op met de vertegenwoordiger van de Partner Solutions van uw Audience Manager als u geïnteresseerd bent in het gebruik van de bètaomgeving.
seo-title: Bètaomgeving
solution: Audience Manager
title: Bètaomgeving
uuid: de4a1a46-cfa4-4f64-8569-48a7650fd8cf
feature: Reference
exl-id: a6a5e1c2-29a2-40bf-972c-87fb8716a394
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '318'
ht-degree: 4%

---

# Bètaomgeving {#beta-environment}

De bètaomgeving is bedoeld voor het testen van de implementatie van uw Audience Manager. Wijzigingen in bèta hebben geen invloed op de productiegegevens. Neem contact op met de vertegenwoordiger van de Partner Solutions van uw Audience Manager als u geïnteresseerd bent in het gebruik van de bètaomgeving.

## Overzicht

De bètaomgeving is een exacte replica van de productieomgeving, zonder experimentele of niet-vrijgegeven functies. Uw aanmeldingsgegevens van de productieomgeving zijn geldig in de bètaomgeving.

**Plan bijwerken**

De bètaomgeving wordt aan het einde van elke maand tijdens niet-piekuren bijgewerkt.

**Uitgaand Verkeer**

Het uitgaande verkeer wordt niet toegelaten voor het bètamilieu.

<!-- 

Added re: AAM-30826.

 -->

## Eindpunten



| Service | URL/hostnaam | Hoe te om toegang te verkrijgen |
|--- |--- | --- |
| S3 | Neem contact op met uw Audience Manager Partner Solutions-vertegenwoordiger of klantenservice | Neem contact op met uw Audience Manager Partner Solutions-vertegenwoordiger of de klantenservice om een Amazon S3-emmertje voor uw bètainstantie in te stellen. Lees meer over de [voordelen van het gebruik van Amazon S3](../reference/amazon-s3.md). |
| DCS | `https://dcs-beta.demdex.net/...` | Zie [Toegang tot DCS in het Bètamilieu](../reference/beta-environment.md#access-dcs-beta-environment). |
| UI | `https://bank-beta.demdex.com` | Uw referenties voor de productieomgeving zijn geldig voor de bètaomgeving. |
| API | `https://api-beta.demdex.com/...` | Uw referenties voor de productieomgeving zijn geldig voor de bètaomgeving. Wij adviseren dat u een generische gebruiker API creeert, [zie details](../api/rest-api-main/aam-api-getting-started.md#requirements). |

## Toegang tot DCS in het milieu van Beta {#access-dcs-beta-environment}

1. Maak een vraag DCS, gebruikend de krullende [command](https://curl.haxx.se/docs/manpage.html). Curl is een hulpmiddel om gegevens van of naar een server over te brengen, gebruikend één van vele gesteunde protocollen.

   Bijvoorbeeld:

   `curl -v https://dcs-beta.demdex.net/event`

1. Verifieer dat uw verzoek door bèta DCS door &quot;zandbak&quot;in de DCS reactiekop te zoeken werd gediend.

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
