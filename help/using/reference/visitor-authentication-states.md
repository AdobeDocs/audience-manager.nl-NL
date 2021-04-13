---
description: De verificatiestatus van de bezoeker in Audience Manager bepaalt of de nieuwe informatie over de eigenschap wordt geschreven naar het geverifieerde profiel van de bezoeker of naar het apparaatprofiel, waar de gegevens zijn verzameld. De Audience Manager behandelt de de authentificatiestatus van bezoekersidentiteitskaart UNKNOWN en LOGGED_OUT in gebeurtenisvraag op de zelfde manier.
keywords: dpm.demdex.net
seo-description: De verificatiestatus van de bezoeker in Audience Manager bepaalt of de nieuwe informatie over de eigenschap wordt geschreven naar het geverifieerde profiel van de bezoeker of naar het apparaatprofiel, waar de gegevens zijn verzameld. De Audience Manager behandelt de de authentificatiestatus van bezoekersidentiteitskaart UNKNOWN en LOGGED_OUT in gebeurtenisvraag op de zelfde manier.
seo-title: Verificatiestatus van bezoekers in Audience Manager
solution: Audience Manager
title: Verificatiestatus van bezoekers in Audience Manager
uuid: d748c0c3-5833-4fb9-ab3e-793f5f252e47
feature: 'Referenties '
exl-id: 55aec28d-02f6-4e6d-9be1-4ce40deb8dc3
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '439'
ht-degree: 5%

---

# Verificatiestatus van bezoekers in Audience Manager{#visitor-authentication-states-in-audience-manager}

De verificatiestatus van de bezoeker in Audience Manager bepaalt of de nieuwe informatie over de eigenschap wordt geschreven naar het geverifieerde profiel van de bezoeker of naar het apparaatprofiel, waar de gegevens zijn verzameld. De Audience Manager behandelt de de authentificatiestatus van bezoekersidentiteitskaart UNKNOWN en LOGGED_OUT in gebeurtenisvraag op de zelfde manier.

Vanaf [!DNL Experience Cloud] ID service v1.5+ bevat de methode `setCustomerID` het optionele object `AuthState`. `AuthState` identificeert bezoekers volgens hun  [authentificatiestatus](https://docs.adobe.com/content/help/en/id-service/using/reference/authenticated-state.html). [!DNL Audience Manager] behandelt verschillend de gerealiseerde eigenschappen, afhankelijk van de authentificatiestatus die in de vraag en het  [Profiel wordt overgegaan ](../features/profile-merge-rules/merge-rules-dashboard.md) Ruleu van de Fusie van het Profiel gebruikt voor segmentatie.

## Verificatiestatus: ONBEKEND {#auth-status-unknown}

<table id="table_E1EA51533FAE4BBFB338D6F6116BC1F9"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Aanvraagwaarde </p> </th> 
   <th colname="col2" class="entry"> <p> <b>Informatie uit het geverifieerde profiel </b> lezen </p> </th> 
   <th colname="col3" class="entry"> <p> <b>Schrijven </b> karakteriseert het geverifieerde profiel </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1" morerows="1"> <p> <code> 0 </code> </p> </td> 
   <td colname="col2"> <p>Ja, als de voor authentiek verklaarde Optie Regel van de Fusie = "Laatste Voor authentiek verklaarde Profielen". </p> </td> 
   <td colname="col3" morerows="1"> <p>Nee, de gegevens over de eigenschap worden toegevoegd aan het apparaatprofiel. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Nee, als de regel Samenvoegen van geverifieerde optie = "Huidige geverifieerde profielen" of "Geen geverifieerd profiel" is. </p> </td> 
  </tr> 
 </tbody> 
</table>

Voorbeeldaanroep (de aanvraagwaarde die overeenkomt met de verificatiestatus wordt gemarkeerd):

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%010&d_sid=123456`

## Verificatiestatus: GEAUTHENTIFICEERD {#auth-status-authenticated}

<table id="table_956ABF96024744308F7773E1F96482B7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Aanvraagwaarde </p> </th> 
   <th colname="col2" class="entry"> <p> <b>Informatie uit het geverifieerde profiel </b> lezen </p> </th> 
   <th colname="col3" class="entry"> <p> <b>Schrijven </b> karakteriseert het geverifieerde profiel </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1" morerows="1"> <p> <code> 1 </code> </p> </td> 
   <td colname="col2"> <p>Ja, als de regel Samenvoegen van geverifieerde optie = "Huidige geverifieerde profielen" of "Laatste geverifieerde profielen" is. </p> </td> 
   <td colname="col3" morerows="1"> <p>Ja, de gegevens van de eigenschap worden toegevoegd aan het geverifieerde profiel. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Nr, als de Voor authentiek verklaarde Optie Regel van de Fusie = "Geen Voor authentiek verklaard Profiel". </p> </td> 
  </tr> 
 </tbody> 
</table>

Voorbeeldaanroep (de aanvraagwaarde die overeenkomt met de verificatiestatus wordt gemarkeerd):

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%011&d_sid=123456`

## Verificatiestatus: LOGGED_OUT {#auth-status-logged-out}

<table id="table_783F0CBB0431482AA49F41468FA65B19"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Aanvraagwaarde </p> </th> 
   <th colname="col2" class="entry"> <p> <b>Informatie uit het geverifieerde profiel </b> lezen </p> </th> 
   <th colname="col3" class="entry"> <p> <b>Schrijven </b> karakteriseert het geverifieerde profiel </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1" morerows="1"> <p> <code> 2 </code> </p> </td> 
   <td colname="col2"> Ja, als de voor authentiek verklaarde Optie Regel van de Fusie = "Laatste Voor authentiek verklaarde Profielen" </td> 
   <td colname="col3" morerows="1"> <p>Nee, de gegevens over de eigenschap worden naar het apparaatprofiel geschreven. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> Nee, als de regel voor het samenvoegen van geverifieerde opties = "Huidige geverifieerde profielen" of "Geen geverifieerd profiel" is </td> 
  </tr> 
 </tbody> 
</table>

Voorbeeldaanroep (de aanvraagwaarde die overeenkomt met de verificatiestatus wordt gemarkeerd):

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%012&d_sid=123456`

>[!NOTE]
>
>[!DNL Audience Manager] voert in alle drie gevallen een id-synchronisatie uit tussen  [CID en ](../reference/ids-in-aam.md) UUID.

>[!MORELIKETHIS]
>
>* [Klant-id&#39;s en verificatiestatussen](https://docs.adobe.com/content/help/en/id-service/using/reference/authenticated-state.html)

