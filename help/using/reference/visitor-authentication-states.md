---
description: De verificatiestatus van de bezoeker in Audience Manager bepaalt of de nieuwe informatie over de eigenschap wordt geschreven naar het geverifieerde profiel van de bezoeker of naar het apparaatprofiel, waar de gegevens zijn verzameld. De Audience Manager behandelt de de authentificatiestatus van bezoekersidentiteitskaart UNKNOWN en LOGGED_OUT in gebeurtenisvraag op de zelfde manier.
keywords: dpm.demdex.net
seo-description: De verificatiestatus van de bezoeker in Audience Manager bepaalt of de nieuwe informatie over de eigenschap wordt geschreven naar het geverifieerde profiel van de bezoeker of naar het apparaatprofiel, waar de gegevens zijn verzameld. De Audience Manager behandelt de de authentificatiestatus van bezoekersidentiteitskaart UNKNOWN en LOGGED_OUT in gebeurtenisvraag op de zelfde manier.
seo-title: Verificatiestatus van bezoekers in Audience Manager
solution: Audience Manager
title: Verificatiestatus van bezoekers in Audience Manager
uuid: d748c0c3-5833-4fb9-ab3e-793f5f252e47
feature: reference
translation-type: tm+mt
source-git-commit: a41f0beffba686f283a2933ad7066cb124e4d380
workflow-type: tm+mt
source-wordcount: '440'
ht-degree: 5%

---


# Verificatiestatus van bezoekers in Audience Manager{#visitor-authentication-states-in-audience-manager}

De verificatiestatus van de bezoeker in Audience Manager bepaalt of de nieuwe informatie over de eigenschap wordt geschreven naar het geverifieerde profiel van de bezoeker of naar het apparaatprofiel, waar de gegevens zijn verzameld. De Audience Manager behandelt de de authentificatiestatus van bezoekersidentiteitskaart UNKNOWN en LOGGED_OUT in gebeurtenisvraag op de zelfde manier.

Vanaf [!DNL Experience Cloud] ID service v1.5+ bevat de `setCustomerID` methode het optionele `AuthState` object. `AuthState` identificeert bezoekers volgens hun [authentificatiestatus](https://docs.adobe.com/content/help/en/id-service/using/reference/authenticated-state.html). [!DNL Audience Manager] behandelt de gerealiseerde eigenschappen verschillend, afhankelijk van de authentificatiestatus die in de vraag en de Regel [van de Fusie van het](../features/profile-merge-rules/merge-rules-dashboard.md) Profiel wordt overgegaan u voor segmentatie gebruikt.

## Verificatiestatus: ONBEKEND {#auth-status-unknown}

| Aanvraagwaarde | **Informatie uit het geverifieerde profiel lezen** | **Nieuwe kenmerken naar het geverifieerde profiel schrijven** |
---------|----------|---------
| 0 | <ul><li>Ja, als de voor authentiek verklaarde Optie Regel van de Fusie = &quot;Laatste Voor authentiek verklaarde Profielen&quot;.</li><li>Nee, als de regel Samenvoegen van geverifieerde optie = &quot;Huidige geverifieerde profielen&quot; of &quot;Geen geverifieerd profiel&quot; is.</li></ul> | Nee, de gegevens over de eigenschap worden toegevoegd aan het apparaatprofiel. |


Voorbeeldaanroep (de aanvraagwaarde die overeenkomt met de verificatiestatus wordt gemarkeerd):

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%010&d_sid=123456`

## Verificatiestatus: GEAUTHENTIFICEERD {#auth-status-authenticated}

| Aanvraagwaarde | **Informatie uit het geverifieerde profiel lezen** | **Nieuwe kenmerken naar het geverifieerde profiel schrijven** |
---------|----------|---------
| 1 | <ul><li>Ja, als de regel Samenvoegen van geverifieerde optie = &quot;Huidige geverifieerde profielen&quot; of &quot;Laatste geverifieerde profielen&quot; is.</li><li>Nr, als de Voor authentiek verklaarde Optie Regel van de Fusie = &quot;Geen Voor authentiek verklaard Profiel&quot;.</li></ul> | Ja, de gegevens van de eigenschap worden toegevoegd aan het geverifieerde profiel. |

Voorbeeldaanroep (de aanvraagwaarde die overeenkomt met de verificatiestatus wordt gemarkeerd):

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%011&d_sid=123456`

## Verificatiestatus: LOGGED_OUT {#auth-status-logged-out}

| Aanvraagwaarde | **Informatie uit het geverifieerde profiel lezen** | **Nieuwe kenmerken naar het geverifieerde profiel schrijven** |
---------|----------|---------
| 2 | <ul><li>Ja, als de voor authentiek verklaarde Optie Regel van de Fusie = &quot;Laatste Voor authentiek verklaarde Profielen&quot;</li><li>Nee, als de regel voor het samenvoegen van geverifieerde opties = &quot;Huidige geverifieerde profielen&quot; of &quot;Geen geverifieerd profiel&quot; is</li></ul> | Nee, de gegevens over de eigenschap worden naar het apparaatprofiel geschreven. |

Voorbeeldaanroep (de aanvraagwaarde die overeenkomt met de verificatiestatus wordt gemarkeerd):

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%012&d_sid=123456`

>[!NOTE]
>
>[!DNL Audience Manager] voert in alle drie gevallen een id-synchronisatie uit tussen [CID en UUID](../reference/ids-in-aam.md) .

>[!MORELIKETHIS]
>
>* [Klant-id&#39;s en verificatiestatussen](https://docs.adobe.com/content/help/en/id-service/using/reference/authenticated-state.html)

