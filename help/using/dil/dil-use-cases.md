---
description: Codevoorbeelden en beschrijvingen voor specifieke gevallen van DIL-gebruik.
seo-description: Codevoorbeelden en beschrijvingen voor specifieke gevallen van DIL-gebruik.
seo-title: DIL-gebruik van tassen en codevoorbeelden
solution: Audience Manager
title: DIL-gebruik van tassen en codevoorbeelden
uuid: 27995c2d-6572-438e-af99-b5477f090ae9
translation-type: tm+mt
source-git-commit: d6abb45fa8b88248920b64db3ac4e72c53ecee13

---


# DIL-gebruik van tassen en codevoorbeelden{#dil-use-cases-and-code-samples}

Codevoorbeelden en beschrijvingen voor specifieke gevallen van DIL-gebruik.

<!-- 

c_dil_use_case.xml

 -->

## Gegevenselementen naar Auditiebeheer verzenden met DIL {#send-data-elements-dil}

Maak een objectvariabele die informatie over pagina-elementen naar Audience Manager verzendt. Dit is nuttig voor algemene gegevensinzameling of als alternatief aan het verzamelen van gegevens met variabelen van de Analyse.

<!-- 

c_dil_send_page_objects.xml

 -->

**Beschrijving**

In de volgende code ziet u hoe u paginagegevens kunt verzamelen en naar Audience Manager kunt verzenden met [!UICONTROL DIL]. In deze voorbeelden wordt een variabele gebruikt om gegevenselementen op te nemen in een platte lijst of een array. Denk eraan dat u variabelen doorgeeft als [sleutel-waardeparen](../reference/key-value-pairs-explained.md). Noteer ook het `c_` voorvoegsel vóór de toets in het sleutelwaardepaar. Dit [vereiste voorvoegsel](../features/traits/trait-variable-prefixes.md) identificeert informatie als user-defined gegevens. In het eerste voorbeeld moet u handmatig aan de toets toevoegen. `c_` In het tweede voorbeeld [!UICONTROL DIL] doet u dit automatisch.

**Waardeeigenschappen consistent houden**

Vergeet niet de eigenschappen van de waarde gelijk te houden wanneer u gegevens doorgeeft. Als u bijvoorbeeld twee identieke toetsen met verschillende waarden hebt, heeft de waarde van het laatste sleutelwaardepaar voorrang op de voorgaande waardeobjecten. Als u bijvoorbeeld de waarde doorgeeft `color:blue` en `color:red` instelt op rood (overschrijft blauw).

**Voorbeeld 1: Gegevens verzenden als sleutelwaardeparen**

In dit eenvoudige voorbeeld worden kleur- en prijsgegevens naar Audience Manager verzonden in de vorm van sleutelwaardeparen. De code kan er ongeveer als volgt uitzien:

<pre class="&ldquo;java&rdquo;"><code>
var sample_dil = DIL.create({partner:"<i>partner name</i>"}); 
sample_dil.api.signals({ 
   c_color:"blue", 
   c_price:"900" 
}); 
sample_dil.api.submit();
</code></pre>

**Voorbeeld 2: Gegevens verzenden in een object**

In dit geavanceerde voorbeeld wordt getoond hoe gegevens in een object naar Audience Manager worden verzonden. Wanneer u met deze methode werkt, [!UICONTROL DIL] kunt u een object als functieparameter doorgeven aan de [!DNL signals()] methode. [!UICONTROL DIL] De code kan er ongeveer als volgt uitzien:

<pre class="java"><code>
var my_object = { 
   color : "blue", 
   price : "900" 
}; 
 
var sample_dil = DIL.create({ partner : "<i>partner name</i>" }); 
//Load the object and append "c_" to all keys in the key-value pairs and send data to AudienceManager. 
sample_dil.api.signals(my_object,"c_").submit();
</code></pre>

**Voorbeeld 3: Paginagegevens verzenden in een array**

In dit geval `my_object` gebruikt de variabele een array om gegevens op te slaan. Dit voorbeeld bouwt op de informatie voort die door de geadviseerde methode hierboven wordt overgegaan, maar voegt een extra laag toe om een producttype en een model aan te passen. De code kan er ongeveer als volgt uitzien:

<pre class="java"><code>
var my_objects = [{ 
   color : "blue", 
   price : "900" 
}, { 
   type : "acura", 
   model : "tl" 
}]; 
 
var sample_dil = DIL.create({ partner : "<i>partner name</i>" }); 
 
for (var i = 0; i < my_objects.length; i++) 
//Load the object and append "c_" to all the keys in the key-value pairs.  
{ 
    sample_dil.api.signals(my_objects[i], "c_"); 
} 
sample_dil.api.submit();
</code></pre>

## URL van vastlegverwijzing {#capture-referring-url}

Leg een referentie-URL vast en verstuur deze naar Audience Manager.

<!-- 

c_dil_hrefer_over_https.xml

 -->

>[!NOTE]
>
>Deze methode werkt alleen wanneer gebruikers schakelen tussen pagina&#39;s met vergelijkbare protocollen (HTTP versus HTTPS). De browser behoudt bijvoorbeeld een verwijzende URL wanneer u van een beveiligde site naar een andere beveiligde site navigeert. Browsers behouden de referentie-URL niet wanneer u gaat schakelen tussen beveiligde en onveilige sites. Dit gedrag is de normale browserfunctionaliteit en kan niet worden omzeild door [!UICONTROL DIL].

**Codevoorbeeld**

De code kan er ongeveer als volgt uitzien:

<pre class="java"><code>
var adobe_dil = DIL.create({ partner : "<i>partner name</i>" }); 
adobe_dil.api.signals({ d_referer : document.referrer }).submit();
</code></pre>

## Typen zoekmachines vastleggen en zoektermen vastleggen {#capture-search-engine-types}

Verzend informatie over het type zoekmachine en trefwoordzoekopdrachten naar Audience Manager.

>[!IMPORTANT]
>
>In deze sectie wordt de oudere functionaliteit beschreven. Deze wordt niet ondersteund in de nieuwste versies van DIL.

**Ondersteunde zoekmachines**

Hiermee herkent u standaard zoekopdrachten van deze zoekmachines (inclusief internationale variaties): `DIL.getSearchReferrer`

* [!DNL AOL]
* [!DNL Ask]
* [!DNL Bing]
* [!DNL Google]
* [!DNL Yahoo!]

**Beschrijving**

In de volgende code ziet u hoe u de zoekreferentie ophaalt voor een van de ondersteunde zoekprogramma&#39;s. In dit geval, veronderstellen wij een gebruiker die op de term &quot;huizen&quot;van [!DNL Google] Canada ( `www.google.ca`) wordt gezocht. Met deze code kunt u deze zoektermen vastleggen en naar Audience Manager verzenden.

**Basiscode**

De basiscode voor het ophalen van de zoekverwijzer (bijvoorbeeld van `google.com`) ziet er als volgt uit:

```java
var search_referrer = DIL.tools.getSearchReferrer();
```

**Voorbeeld code van vermelde zoekmachine**

In dit geval, veronderstellen wij dat een gebruiker naar de term &quot;huizen&quot;van [!DNL Google] Canada ( `www.google.ca`) zocht. Let op hoe de code de vereiste `c_` parameter vooraf vastlegt aan zoekmachine ( `c_se`) en zoekterm ( `c_st`). `c_` is een [vereist voorvoegsel](../features/traits/trait-variable-prefixes.md) dat deze als door de klant gedefinieerde variabelen aan Audience Manager identificeert.

<pre class="java"><code>
var adobe_dil = DIL.create({partner:"<i>partner name</i>"}); 
var search_referrer = DIL.tools.getSearchReferrer(); 
 
if (search_referrer && search_referrer.valid) { 
  adobe_dil.api.signals({ 
    c_se : se.name, 
    c_st : se.keywords 
  }).submit(); 
}
</code></pre>

**Voorbeeld van code van niet-vermelde zoekmachine**

In dit geval, veronderstellen wij dat een gebruiker naar de term &quot;huizen&quot;van `dogpile.com`zocht. Omdat [!DNL Dogpile] standaard geen ondersteuning wordt geboden, kunt u DIL zo configureren dat deze zoekfunctie wordt herkend en de zoektermen worden geretourneerd naar Audience Manager. De code kan er ongeveer als volgt uitzien:

<pre class="java"><code>
var adobe_dil = DIL.create({partner:"<i>partner name</i>"}); 
var search_referrer = DIL.tools.getSearchReferrer(document.referrer, {  
    hostPattern:/dogpile\./, 
    queryParam:"q" 
}); 
 
if (search_referrer && search_referrer.valid) { 
  adobe_dil.api.signals({ 
    c_se : se.name, 
    c_st : se.keywords 
  }).submit(); 
}
</code></pre>

## Sleutelwaarden toewijzen aan andere toetsen {#map-key-values}

Koppel de waarde van een sleutelwaardepaar aan een andere sleutel.

<!-- 

c_dil_map_keys.xml

 -->

**Beschrijving**

In een zeer belangrijk-waardepaar, identificeert het `c_` voorvoegsel dat aan de sleutel wordt toegevoegd het signaal als klant-bepaalde gegevens. Door de klant gedefinieerde gegevens worden gebruikt om zich te richten op de specifieke site die gegevens heeft doorgegeven bij een gebeurtenisaanroep. Soms wilt u deze informatie echter wel beschikbaar stellen voor alle eigenschappen in uw account Audience Manager. Hiervoor wijst u de waarde in een sleutelwaardepaar toe aan een sleutel op platformniveau. `c_` Een sleutel op platformniveau is vooraf ingesteld `d_` en maakt het signaal beschikbaar voor alle eigenschappen in uw account.

Als voorbeeld verzamelt u ZIP-codegegevens van een bepaalde site, maar wilt u deze als doel instellen voor alle eigenschappen van Audience Manager. Als u de ZIP-code beschikbaar wilt maken op platformniveau, kunt u de door de klant gedefinieerde ZIP-codesleutel toewijzen (bijvoorbeeld `c_zip`) aan een platform bepaalde sleutel zoals hieronder getoond.

**Codevoorbeeld**

De code kan er ongeveer als volgt uitzien:

```java
var adobe_dil = DIL.create({ 
    partner : "adobe", 
    mappings : { 
        c_zip : 'd_zip', 
        d_key2 : 'h_dil_key2' 
    } 
}); 
adobe_dil.api.signals({c_zip : '10010'}).submit(); 
// Request will look like /event?c_zip=10010&d_zip=10010
```

## Traffic DIL in Google Tag Manager (GTM) {#traffic-dil-gtm}

DIL instellen en bedienen met een GTM-tag.

<!-- 

t_dil_google_tagmanager.xml

 -->

Deze procedure veronderstelt u een [!DNL Google Tag Manager] rekening, wat werkende kennis van dat product, en uw `dil.js` dossier van de Manager van de Publiek hebt.

U kunt als volgt het `dil.js` bestand verzenden in GTM:

1. Maak een nieuwe container of open een bestaande container.
1. Voeg een nieuwe tag toe aan de container.
1. Open de tag om deze te bewerken en:

   * Geef de tag een naam.
   * Selecteer een optie **[!UICONTROL Custom HTML Tag]** in de **[!UICONTROL Tag Type]** vervolgkeuzelijst.
   * Plaats de [!UICONTROL DIL] code (bibliotheek + aangepaste code) in het HTML-veld binnen scripttags `<script>DIL code</script>`.
   * Klik op **[!UICONTROL Save]**.

1. Publiceer de container.
1. Genereer de code van de containertag en plaats deze op uw voorraad.

>[!MORELIKETHIS]
>
>* [Google Tag Manager Help Center](https://support.google.com/tagmanager#topic=3441530)
>* [Signalen](../dil/dil-instance-methods.md#signals)
>* [Voorvoegselvereisten voor belangrijkste variabelen](https://marketing.adobe.com/resources/help/en_US/aam/r_tb_variable_prefixes.html)

