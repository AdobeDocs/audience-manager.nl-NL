---
description: Voeg een if-instructie toe om te controleren op cookies van de Audience Manager voordat u de methode Google Publisher Tag.setTargeting aanroept.
seo-description: Add an if statement to check for Audience Manager cookies before calling the Google Publisher Tag .setTargeting method.
seo-title: Modify the GPT setTargeting API Call
solution: Audience Manager
title: De GPT setTargeting API-call wijzigen
uuid: 0cd38f30-5d29-4511-a779-d32587f1dafb
feature: Third-party Integration
exl-id: cc34b7e8-7bbd-463f-9378-9d3a40c49594
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '274'
ht-degree: 6%

---

# De GPT wijzigen `setTargeting` API-aanroep {#modify-the-gpt-settargeting-api-call}

Voeg een if-instructie toe om te controleren op cookies van Audience Managers voordat u de instructie [!DNL Google Publisher Tag] `.setTargeting` methode.

## Controleren op Audience Manager cookies met een `IF` Instructie

De `.setTargeting` methode krijgt gegevens van de bestemmingskoekje van de Audience Manager en het unieke koekje van identiteitskaart ( `aam_uuid`). Als `.setTargeting` wordt aangeroepen vóór [!UICONTROL DIL] Deze cookies worden weggeschreven, anders zijn de cookies leeg. Er kunnen fouten optreden wanneer de pagina wordt geladen. Om dit te helpen voorkomen, plaatst u de `.setTargeting` in een `if` die deze cookies controleert. Als ze niet zijn ingesteld, voorkomt deze instructie `.setTargeting` vanaf het aanroepen van `AamGpt` functie.

### `IF` Voorbeeld van instructiecode

In dit voorbeeld is de naam van het doelcookie van de Audience Manager `Sample`. U plaatst deze naam wanneer u het bestemmingskoekje in het gebruikersinterface van de Audience Manager creeert. [!UICONTROL DIL] stelt de `aam_uuid` cookie en de naam kunnen niet worden gewijzigd.

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
>Afhankelijk van de manier waarop u wilt integreren [!DNL Google Ad Manager]U hebt slechts enkele regels in het bovenstaande codevoorbeeld nodig:
>
>* Integratie op de client: alleen regel 1-3 gebruiken.
>* Integratie op de server: geen van de regels is nodig .
>* Ingest [!DNL Google Ad Manager] logbestanden voor rapportage in [!DNL Audience Manager]: alleen de regels 4-6 gebruiken. Deze code voegt de waarde van de `aam_uuid` koekje in de logboeken zodat kunnen zij voor rapportering worden opgenomen.


### `AamGpt` Functies en gegevenstypen

Definieert de sleutelvariabelen die worden gebruikt in het dialoogvenster `if` instructie.

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
   <td colname="col3"> <p>Retourneert de sleutel in het sleutelwaardensegment. Bijvoorbeeld, als uw sleutel-waarde paar bestond uit <code> color=blue </code>, retourneert <code> color </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> AamGpt.getValues </code> </p> </td> 
   <td colname="col2"> <p>Array van tekenreeksen </p> </td> 
   <td colname="col3"> <p>Geeft waarden in een array terug, bijvoorbeeld <code> ["value1","value2"] </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> AamGpt.getCookie </code> </p> </td> 
   <td colname="col2"> <p>Int </p> </td> 
   <td colname="col3"> <p>Hiermee wordt de gebruikers-id van de Audience Manager geretourneerd, bijvoorbeeld <code> 12345 </code>. </p> </td> 
  </tr>
 </tbody>
</table>

>[!MORELIKETHIS]
>
>* [Een GPT-bestemming maken](../../integration/gpt-aam-destination/gpt-aam-create-destination.md)
>* [Audience Manager-code voor Google Publisher-tags](../../integration/gpt-aam-destination/gpt-aam-aamgpt-code.md)

