---
description: De verificatiestatus van de bezoeker in Audience Manager bepaalt of de nieuwe informatie over de eigenschap wordt geschreven naar het geverifieerde profiel van de bezoeker of naar het apparaatprofiel, waar de gegevens zijn verzameld. De Audience Manager behandelt de de authentificatiestatus van bezoekersidentiteitskaart UNKNOWN en LOGGED_OUT in gebeurtenisvraag op de zelfde manier.
keywords: dpm.demdex.net
seo-description: The visitor authentication status in Audience Manager determines if the new trait information is written to the visitor's authenticated profile or to the device profile, where the data was collected from. Audience Manager handles the visitor ID authentication statuses UNKNOWN and LOGGED_OUT in event calls in the same way.
seo-title: Visitor Authentication States in Audience Manager
solution: Audience Manager
title: Verificatiestatus van bezoekers in Audience Manager
uuid: d748c0c3-5833-4fb9-ab3e-793f5f252e47
feature: Reference
exl-id: 55aec28d-02f6-4e6d-9be1-4ce40deb8dc3
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '330'
ht-degree: 6%

---

# Verificatiestatus van bezoekers in Audience Manager{#visitor-authentication-states-in-audience-manager}

De verificatiestatus van de bezoeker in Audience Manager bepaalt of de nieuwe informatie over de eigenschap wordt geschreven naar het geverifieerde profiel van de bezoeker of naar het apparaatprofiel, waar de gegevens zijn verzameld. De Audience Manager behandelt de de authentificatiestatus van bezoekersidentiteitskaart UNKNOWN en LOGGED_OUT in gebeurtenisvraag op de zelfde manier.

Beginnen met [!DNL Experience Cloud] De dienst van identiteitskaart v1.5+, `setCustomerID` bevat de optionele `AuthState` object. `AuthState` identificeert bezoekers volgens hun [verificatiestatus](https://experienceleague.adobe.com/docs/id-service/using/reference/authenticated-state.html). [!DNL Audience Manager] behandelt verschillend de gerealiseerde eigenschappen, afhankelijk van de authentificatiestatus die in de vraag en wordt overgegaan [Regel voor samenvoegen van profiel](../features/profile-merge-rules/merge-rules-dashboard.md) u gebruikt voor segmentatie.

## Verificatiestatus: ONBEKEND {#auth-status-unknown}

| Aanvraagwaarde | Informatie lezen uit het geverifieerde profiel | Nieuwe kenmerken naar het geverifieerde profiel schrijven |
|---|---|---|
| 0 | <ul><li>Ja, als de [!UICONTROL Authenticated Option Merge Rule] = [!UICONTROL Last Authenticated Profiles].</li><li>Nee, als de [!UICONTROL Authenticated Option Merge Rule] = [!UICONTROL Current Authenticated Profiles] of [!UICONTROL No Authenticated Profile].</li></ul> | Nee, de gegevens over de eigenschap worden toegevoegd aan het apparaatprofiel. |

Voorbeeldaanroep (de aanvraagwaarde die overeenkomt met de verificatiestatus wordt gemarkeerd):

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%010&d_sid=123456`

## Verificatiestatus: GEAUTHENTIFICEERD {#auth-status-authenticated}

| Aanvraagwaarde | Informatie lezen uit het geverifieerde profiel | Nieuwe kenmerken naar het geverifieerde profiel schrijven |
|---|---|---|
| 1 | <ul><li>Ja, als de [!UICONTROL Authenticated Option Merge Rule] = [!UICONTROL Current Authenticated Profiles] of [!UICONTROL Last Authenticated Profiles].</li><li>Nee, als de [!UICONTROL Authenticated Option Merge Rule] = [!UICONTROL No Authenticated Profile].</li></ul> | Ja, de gegevens van de eigenschap worden toegevoegd aan het geverifieerde profiel. |

Voorbeeldaanroep (de aanvraagwaarde die overeenkomt met de verificatiestatus wordt gemarkeerd):

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%011&d_sid=123456`

## Verificatiestatus: LOGGED_OUT {#auth-status-logged-out}

| Aanvraagwaarde | Informatie lezen uit het geverifieerde profiel | Nieuwe kenmerken naar het geverifieerde profiel schrijven |
|---|---|---|
| 2 | <ul><li>Ja, als de [!UICONTROL Authenticated Option Merge Rule] = [!UICONTROL Last Authenticated Profiles].</li><li>Nee, als de [!UICONTROL Authenticated Option Merge Rule] = [!UICONTROL Current Authenticated Profiles] of [!UICONTROL No Authenticated Profile].</li></ul> | Nee, de gegevens over de eigenschap worden naar het apparaatprofiel geschreven. |

Voorbeeldaanroep (de aanvraagwaarde die overeenkomt met de verificatiestatus wordt gemarkeerd):

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%012&d_sid=123456`

>[!NOTE]
>
>[!DNL Audience Manager] voert een synchronisatie van identiteitskaart tussen uit [CID en UUID](../reference/ids-in-aam.md) in alle drie gevallen.

>[!MORELIKETHIS]
>
>* [Klant-id&#39;s en verificatiestatussen](https://experienceleague.adobe.com/docs/id-service/using/reference/authenticated-state.html)

