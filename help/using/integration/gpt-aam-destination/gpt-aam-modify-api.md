---
description: Voeg een if-instructie toe om te controleren op cookies van Audience Manager voordat u de methode Google Publisher Tag.setTargeting aanroept.
seo-description: Voeg een if-instructie toe om te controleren op cookies van Audience Manager voordat u de methode Google Publisher Tag.setTargeting aanroept.
seo-title: Wijzig de GPT setTargeting API Vraag
solution: Audience Manager
title: Wijzig de GPT setTargeting API Vraag
uuid: 0cd38f30-5d29-4511-a779-d32587f1dafb
translation-type: tm+mt
source-git-commit: d6abb45fa8b88248920b64db3ac4e72c53ecee13

---


# De GPT `setTargeting` API-aanroep wijzigen {#modify-the-gpt-settargeting-api-call}

Voeg een if- verklaring toe om de koekjes van de Manager van de Publiek te controleren alvorens de [!DNL Google Publisher Tag] `.setTargeting` methode te roepen.

## Controleren op cookies van Audience Manager met een `IF` instructie

De `.setTargeting` methode krijgt gegevens van het bestemmingskoekje van de Manager van de Publiek en het unieke koekje van identiteitskaart van de gebruiker ( `aam_uuid`). Als deze cookies echter `.setTargeting` worden aangeroepen voordat deze worden [!UICONTROL DIL] geschreven of als de cookies leeg zijn, kunnen er fouten optreden wanneer de pagina wordt geladen. U kunt dit voorkomen door de `.setTargeting` methode op te nemen in een `if` instructie die op deze cookies controleert. Als ze niet zijn ingesteld, voorkomt deze instructie dat `.setTargeting` de `AamGpt` functie wordt aangeroepen.

### `IF` Voorbeeld van instructiecode

In dit voorbeeld is de naam van het doelcookie van Audience Manager `Sample`. U stelt deze naam in wanneer u het doelcookie maakt in de interface van Audience Manager. [!UICONTROL DIL] Hiermee stelt u de `aam_uuid` cookie in en de naam kan niet worden gewijzigd.

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
   <td colname="col3"> <p>Hiermee wordt de gebruikers-id van Audience Manager geretourneerd, bijvoorbeeld <code> 12345 </code>. </p> </td> 
  </tr>
 </tbody>
</table>

>[!MORELIKETHIS]
>
>* [Een GPT-doel maken](../../integration/gpt-aam-destination/gpt-aam-create-destination.md)
>* [Code Auditiemanager voor Google Publisher-tags](../../integration/gpt-aam-destination/gpt-aam-aamgpt-code.md)

