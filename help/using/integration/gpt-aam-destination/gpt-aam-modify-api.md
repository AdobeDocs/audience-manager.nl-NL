---
description: Voeg een if-instructie toe om te controleren op cookies van Audience Managers voordat u de Google Publisher-tag .setTargeting-methode aanroept.
seo-description: Voeg een if-instructie toe om te controleren op cookies van Audience Managers voordat u de Google Publisher-tag .setTargeting-methode aanroept.
seo-title: Wijzig de GPT setTargeting API Vraag
solution: Audience Manager
title: Wijzig de GPT setTargeting API Vraag
uuid: 0cd38f30-5d29-4511-a779-d32587f1dafb
feature: Third Party Integrations
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '298'
ht-degree: 0%

---


# De GPT `setTargeting` API-aanroep wijzigen {#modify-the-gpt-settargeting-api-call}

Voeg een if-instructie toe om te controleren op cookies van de Audience Manager voordat u de [!DNL Google Publisher Tag] `.setTargeting` methode aanroept.

## Controleren op Audience Manager Cookies met een `IF` instructie

De `.setTargeting` methode krijgt gegevens van het de bestemmingskoekje van de Audience Manager en het unieke koekje van identiteitskaart van de gebruiker ( `aam_uuid`). Als deze cookies echter `.setTargeting` worden aangeroepen voordat deze worden [!UICONTROL DIL] geschreven of als de cookies leeg zijn, kunnen er fouten optreden wanneer de pagina wordt geladen. U kunt dit voorkomen door de `.setTargeting` methode op te nemen in een `if` instructie die op deze cookies controleert. Als ze niet zijn ingesteld, voorkomt deze instructie dat `.setTargeting` de `AamGpt` functie wordt aangeroepen.

### `IF` Voorbeeld van instructiecode

In dit voorbeeld is de naam van het doelcookie van de Audience Manager `Sample`. U plaatst deze naam wanneer u het bestemmingskoekje in het gebruikersinterface van de Audience Manager creeert. [!UICONTROL DIL] Hiermee stelt u de `aam_uuid` cookie in en de naam kan niet worden gewijzigd.

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
>Afhankelijk van hoe u wilt integreren met [!DNL DFP], hebt u slechts enkele lijnen in het bovenstaande codevoorbeeld nodig:
>
>* Integratie op de client: alleen regel 1-3 gebruiken.
>* Integratie op de server: geen van de regels is nodig .
>* Logbestanden [!DNL DFP] samenvoegen voor rapportage in [!DNL Audience Manager]: alleen de regels 4-6 gebruiken. Deze code voegt de waarde van het `aam_uuid` cookie in de logboeken in zodat deze kunnen worden ingepakt voor rapportage.


### `AamGpt` Functies en gegevenstypen

Definieert de toetsvariabelen die in de `if` instructie worden gebruikt.

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
   <td colname="col3"> <p>Retourneert de sleutel in het sleutelwaardensegment. Bijvoorbeeld, als uw sleutel-waarde paar van bestond <code> color=blue </code>, keert dit terug <code> color </code>. </p> </td> 
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
>* [Een GPT-doel maken](../../integration/gpt-aam-destination/gpt-aam-create-destination.md)
>* [Audience Manager Code voor Google Publisher-tags](../../integration/gpt-aam-destination/gpt-aam-aamgpt-code.md)

