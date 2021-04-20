---
description: Voeg een if-instructie toe om te controleren op cookies van Audience Managers voordat u de Google Publisher-tag .setTargeting-methode aanroept.
seo-description: Voeg een if-instructie toe om te controleren op cookies van Audience Managers voordat u de Google Publisher-tag .setTargeting-methode aanroept.
seo-title: De GPT setTargeting API-call wijzigen
solution: Audience Manager
title: De GPT setTargeting API-call wijzigen
uuid: 0cd38f30-5d29-4511-a779-d32587f1dafb
feature: Third-party Integration
exl-id: cc34b7e8-7bbd-463f-9378-9d3a40c49594
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '300'
ht-degree: 8%

---

# Wijzig GPT `setTargeting` API Vraag {#modify-the-gpt-settargeting-api-call}

Voeg een if verklaring toe om op de koekjes van de Audience Manager te controleren alvorens [!DNL Google Publisher Tag] `.setTargeting` methode te roepen.

## Controleren op Audience Manager Cookies met een instructie `IF`

De `.setTargeting` methode krijgt gegevens van het de bestemmingskoekje van de Audience Manager en het unieke koekje van identiteitskaart van de gebruiker ( `aam_uuid`). Als `.setTargeting` echter wordt aangeroepen voordat [!UICONTROL DIL] deze cookies schrijft of als de cookies leeg zijn, kunnen er fouten optreden wanneer de pagina wordt geladen. Om dit te helpen vermijden, verpakt de `.setTargeting` methode in een `if` verklaring die op deze koekjes controleert. Als ze niet zijn ingesteld, voorkomt deze instructie dat `.setTargeting` de functie `AamGpt` aanroept.

### `IF` Voorbeeld van instructiecode

In dit voorbeeld is de naam van het doelcookie van de Audience Manager `Sample`. U plaatst deze naam wanneer u het bestemmingskoekje in het gebruikersinterface van de Audience Manager creeert. [!UICONTROL DIL] Hiermee stelt u de  `aam_uuid` cookie in en de naam kan niet worden gewijzigd.

```js
if(typeof AamGpt.getCookie("Sample") != "undefined"){ 
  googletag.pubads().setTargeting(AamGpt.getKey("Sample"),AamGpt.getValues("Sample")); 
}; 
if(typeof AamGpt.getCookie("aam_uuid") != "undefined" ){ 
   googletag.pubads().setTargeting("aamId", AamGpt.getCookie("aam_uuid")); 
};
```

>[!IMPORTANT]
>
>Afhankelijk van hoe u met [!DNL Google Ad Manager] wilt integreren, hebt u slechts enkele lijnen in het bovenstaande codevoorbeeld nodig:
>
>* Integratie op de client: alleen regel 1-3 gebruiken.
>* Integratie op de server: geen van de regels is nodig .
>* Voeg [!DNL Google Ad Manager] logbestanden in voor rapportage in [!DNL Audience Manager]: alleen de regels 4-6 gebruiken. Deze code voegt de waarde van het `aam_uuid` koekje in de logboeken op zodat kunnen zij voor rapportering worden opgenomen.


### `AamGpt` Functies en gegevenstypen

Definieert de toetsvariabelen die worden gebruikt in de instructie `if`.

<table id="table_881391C9BDDF4FACAFC37A47B14B31A1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> -functie </th> 
   <th colname="col2" class="entry"> Type </th> 
   <th colname="col3" class="entry"> Beschrijving </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> AamGpt.getKey </code> </p> </td> 
   <td colname="col2"> <p>String </p> </td> 
   <td colname="col3"> <p>Retourneert de sleutel in het sleutelwaardensegment. Als uw sleutelwaardepaar bijvoorbeeld uit <code> color=blue </code> bestond, retourneert dit <code> color </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> AamGpt.getValues </code> </p> </td> 
   <td colname="col2"> <p>Array van tekenreeksen </p> </td> 
   <td colname="col3"> <p>Retourneert waarden in een array, bijvoorbeeld <code> ["value1","value2"] </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> AamGpt.getCookie </code> </p> </td> 
   <td colname="col2"> <p>Int </p> </td> 
   <td colname="col3"> <p>Retourneert de gebruikers-id van de Audience Manager, bijvoorbeeld <code> 12345 </code>. </p> </td> 
  </tr>
 </tbody>
</table>

>[!MORELIKETHIS]
>
>* [Een GPT-bestemming maken](../../integration/gpt-aam-destination/gpt-aam-create-destination.md)
>* [Audience Manager-code voor Google Publisher-tags](../../integration/gpt-aam-destination/gpt-aam-aamgpt-code.md)

