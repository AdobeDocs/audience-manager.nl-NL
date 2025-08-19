---
description: Voeg een if-instructie toe om op Audience Manager-cookies te controleren voordat u de methode Google Publisher Tag.setTargeting aanroept.
seo-description: Add an if statement to check for Audience Manager cookies before calling the Google Publisher Tag .setTargeting method.
seo-title: Modify the GPT setTargeting API Call
solution: Audience Manager
title: Wijzig de GPT setTargeting API Vraag
uuid: 0cd38f30-5d29-4511-a779-d32587f1dafb
feature: Third-party Integration
exl-id: cc34b7e8-7bbd-463f-9378-9d3a40c49594
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '278'
ht-degree: 4%

---

# De GPT `setTargeting` API-aanroep wijzigen {#modify-the-gpt-settargeting-api-call}

Voeg een if-instructie toe om op Audience Manager-cookies te controleren voordat u de methode [!DNL Google Publisher Tag] `.setTargeting` aanroept.

## Controleren op Audience Manager-cookies met een instructie `IF`

De methode `.setTargeting` haalt gegevens op uit de Audience Manager-doelcookie en het unieke gebruikers-id-cookie ( `aam_uuid` ). Als `.setTargeting` echter wordt aangeroepen voordat [!UICONTROL DIL] deze cookies schrijft of als de cookies leeg zijn, kunnen er fouten optreden wanneer de pagina wordt geladen. Om dit te voorkomen, plaatst u de methode `.setTargeting` in een instructie `if` die op deze cookies controleert. Als deze niet zijn ingesteld, voorkomt deze instructie dat `.setTargeting` de functie `AamGpt` aanroept.

### `IF` Code-voorbeeld voor instructie

In dit voorbeeld is de naam van de Audience Manager-doelcookie `Sample` . U stelt deze naam in wanneer u de doelcookie maakt in de Audience Manager-gebruikersinterface. [!UICONTROL DIL] stelt het `aam_uuid` -cookie in en de naam kan niet worden gewijzigd.

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
>* Integratie aan de clientzijde: alleen regel 1-3 gebruiken.
>* Integratie op de server: geen van de regels is nodig.
>* Samenvatting [!DNL Google Ad Manager] van logbestanden voor rapportage in [!DNL Audience Manager] : gebruik alleen de regels 4-6. Deze code voegt de waarde van het `aam_uuid` cookie in de logbestanden in, zodat deze kunnen worden ingepakt voor rapportage.

### `AamGpt` Functies en gegevenstypen

Definieert de toetsvariabelen die worden gebruikt in de instructie `if` .

<table id="table_881391C9BDDF4FACAFC37A47B14B31A1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Functie </th> 
   <th colname="col2" class="entry"> Type </th> 
   <th colname="col3" class="entry"> Beschrijving </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> AamGpt.getKey </code> </p> </td> 
   <td colname="col2"> <p>String </p> </td> 
   <td colname="col3"> <p>Retourneert de sleutel in het sleutelwaardensegment. Als uw sleutelwaardepaar bijvoorbeeld uit <code> color=blue </code> bestaat, wordt <code> color </code> geretourneerd. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> AamGpt.getValues </code> </p> </td> 
   <td colname="col2"> <p>Array van tekenreeksen </p> </td> 
   <td colname="col3"> <p>Retourneert waarden in een array, bijvoorbeeld <code> ["value1","value2"] </code> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> AamGpt.getCookie </code> </p> </td> 
   <td colname="col2"> <p>Int </p> </td> 
   <td colname="col3"> <p>Retourneert de Audience Manager-gebruikersnaam, bijvoorbeeld <code> 12345 </code> . </p> </td> 
  </tr>
 </tbody>
</table>

>[!MORELIKETHIS]
>
>* [Een GPT-bestemming maken](../../integration/gpt-aam-destination/gpt-aam-create-destination.md)
>* [Audience Manager-code voor Google Publisher-tags](../../integration/gpt-aam-destination/gpt-aam-aamgpt-code.md)
