---
description: Codevoorbeelden en beschrijvingen voor specifieke gevallen waarin DIL wordt gebruikt.
seo-description: Code samples and descriptions for specific DIL use cases.
seo-title: DIL Use Cases and Code Samples
solution: Audience Manager
title: DIL-gebruiksscenario’s en codevoorbeelden
uuid: 27995c2d-6572-438e-af99-b5477f090ae9
feature: DIL Implementation
exl-id: 001710be-b377-460a-9e29-7268d25a6305
source-git-commit: cad38e2c523e9b762aa996c275daefa96c8e14b0
workflow-type: tm+mt
source-wordcount: '981'
ht-degree: 2%

---

# DIL-gebruiksscenario’s en codevoorbeelden{#dil-use-cases-and-code-samples}

>[!WARNING]
>
>Vanaf juli 2023 heeft Adobe de ontwikkeling van de [!DNL Data Integration Library (DIL)] en de [!DNL DIL] extensie.
>
>Bestaande klanten kunnen hun [!DNL DIL] uitvoering. Adobe zal zich echter niet ontwikkelen [!DNL DIL] verder dan dit punt. Klanten worden aangemoedigd om te evalueren [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) voor hun strategie voor het verzamelen van gegevens op lange termijn.
>
>Klanten die na juli 2023 nieuwe integratie voor gegevensverzameling willen implementeren, moeten [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) in plaats daarvan.

Codevoorbeelden en beschrijvingen voor specifieke gevallen waarin DIL wordt gebruikt.

<!-- 

c_dil_use_case.xml

 -->

## Gegevenselementen naar Audience Manager verzenden met DIL {#send-data-elements-dil}

Maak een objectvariabele die informatie over pagina-elementen naar de Audience Manager verzendt. Dit is nuttig voor algemene gegevensinzameling of als alternatief aan het verzamelen van gegevens met variabelen van de Analyse.

<!-- 

c_dil_send_page_objects.xml

 -->

**Beschrijving**

De volgende code laat zien hoe u paginagegevens kunt verzamelen en naar de Audience Manager kunt verzenden met [!UICONTROL DIL]. In deze voorbeelden wordt een variabele gebruikt om gegevenselementen op te nemen in een platte lijst of een array. Onthoud, variabelen doorgeven als [sleutelwaardeparen](../reference/key-value-pairs-explained.md). Let ook op de `c_` voor de toets in het sleutelwaardepaar. Dit [vereist voorvoegsel](../features/traits/trait-variable-prefixes.md) identificeert informatie als user-defined gegevens. In het eerste voorbeeld moet u handmatig toevoegen `c_` op de toets. In het tweede voorbeeld: [!UICONTROL DIL] doet dit automatisch voor u.

**Waardeeigenschappen consistent houden**

Vergeet niet de eigenschappen van de waarde gelijk te houden wanneer u gegevens doorgeeft. Als u bijvoorbeeld twee identieke toetsen met verschillende waarden hebt, heeft de waarde van het laatste sleutelwaardepaar voorrang op de voorgaande waardeobjecten. Bijvoorbeeld, doorgeven `color:blue` en `color:red` Hiermee stelt u de geretourneerde waarde in op rood (overschrijft u blauw).

**Voorbeeld 1: Gegevens verzenden als sleutel-waardeparen**

In dit eenvoudige voorbeeld worden kleur- en prijsgegevens naar de Audience Manager verzonden in de vorm van sleutelwaardeparen. De code kan er ongeveer als volgt uitzien:

<pre class="java"><code>
var sample_dil = DIL.create({partner:"<i>partner name</i>"}); 
sample_dil.api.signals({ 
   c_color:"blue", 
   c_price:"900" 
}); 
sample_dil.api.submit();
</code></pre>

**Voorbeeld 2: Gegevens verzenden in een object**

In dit geavanceerde voorbeeld wordt getoond hoe gegevens in een object naar Audience Manager worden verzonden. Wanneer u met deze methode werkt, [!UICONTROL DIL] Hiermee kunt u een object als functieparameter doorgeven aan [!DNL signals()] methode. [!UICONTROL DIL] De code kan er ongeveer als volgt uitzien:

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

In dit geval wordt de variabele `my_object` gebruikt een array om gegevens op te slaan. Dit voorbeeld bouwt op de informatie voort die door de geadviseerde methode hierboven wordt overgegaan, maar voegt een extra laag toe om een producttype en een model aan te passen. De code kan er ongeveer als volgt uitzien:

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

Leg een referentie-URL vast en verzend deze naar de Audience Manager.

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

Gegevens over zoekmachinetypen en trefwoordzoekopdrachten naar Audience Manager verzenden.

>[!IMPORTANT]
>
>In deze sectie wordt de oudere functionaliteit beschreven. Deze wordt niet ondersteund in de nieuwste versies van DIL.

**Ondersteunde zoekmachines**

Standaard, `DIL.getSearchReferrer` erkent zoekopdrachten van deze zoekmachines ( inclusief internationale variaties ) :

* [!DNL AOL]
* [!DNL Ask]
* [!DNL Bing]
* [!DNL Google]
* [!DNL Yahoo!]

**Beschrijving**

In de volgende code ziet u hoe u de zoekreferentie ophaalt voor een van de ondersteunde zoekprogramma&#39;s. In dit geval, veronderstellen wij een gebruiker die op de term &quot;huizen&quot;van wordt gezocht [!DNL Google] Canada ( `www.google.ca`). Met deze code kunt u deze zoektermen vastleggen en naar de Audience Manager verzenden.

**Basiscode**

Basiscode voor het ophalen van de zoekreferentie (van `google.com`Bijvoorbeeld) ziet er als volgt uit:

```java
var search_referrer = DIL.tools.getSearchReferrer();
```

**Voorbeeld code van vermelde zoekmachine**

In dit geval, veronderstellen wij dat een gebruiker naar de term &quot;huizen&quot;van zocht [!DNL Google] Canada ( `www.google.ca`). Let op hoe de code de vereiste voorvoegsels bevat `c_` parameter voor zoekmachine ( `c_se`) en zoekterm ( `c_st`). `c_` is een [vereist voorvoegsel](../features/traits/trait-variable-prefixes.md) die deze als klant-bepaalde variabelen aan Audience Manager identificeert.

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

In dit geval, veronderstellen wij dat een gebruiker naar de term &quot;huizen&quot;van zocht `dogpile.com`. Omdat [!DNL Dogpile] wordt niet door gebrek gesteund, kunt u DIL vormen om dit onderzoeksmotor te erkennen en de onderzoekstermijnen aan Audience Manager terug te keren. De code kan er ongeveer als volgt uitzien:

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

In een sleutelwaardepaar, `c_` Het voorvoegsel dat aan de sleutel is toegevoegd, identificeert het signaal als door de klant gedefinieerde gegevens. Door de klant gedefinieerde gegevens worden gebruikt om zich te richten op de specifieke site die gegevens heeft doorgegeven bij een gebeurtenisaanroep. Soms wilt u deze informatie echter wel beschikbaar stellen voor alle eigenschappen in uw Audience Manager-account. Wijs de waarde in een `c_` sleutel-waarde paar aan een sleutel van het platformniveau. Een toets op platformniveau is vooraf ingesteld op `d_` en stelt het signaal beschikbaar voor het richten over alle eigenschappen in uw rekening.

Als voorbeeld verzamelt u ZIP-codegegevens van een bepaalde site, maar wilt u deze als doel instellen voor al uw Audience Manager-eigenschappen. Als u de ZIP-code beschikbaar wilt maken op platformniveau, kunt u de door de klant gedefinieerde ZIP-codesleutel toewijzen (bijvoorbeeld `c_zip`) naar een door het platform gedefinieerde sleutel, zoals hieronder wordt weergegeven.

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

Stel DIL in en bedien deze met een GTM-tag.

<!-- 

t_dil_google_tagmanager.xml

 -->

Deze procedure veronderstelt u hebt [!DNL Google Tag Manager] -account, enige praktische kennis van dat product en uw Audience Manager `dil.js` bestand.

Om het `dil.js` bestand in GTM:

1. Maak een nieuwe container of open een bestaande container.
1. Voeg een nieuwe tag toe aan de container.
1. Open de tag om deze te bewerken en:

   * Geef de tag een naam.
   * Selecteren **[!UICONTROL Custom HTML Tag]** van de **[!UICONTROL Tag Type]** vervolgkeuzelijst.
   * Plaats in het veld HTML de knop [!UICONTROL DIL] code (bibliotheek + aangepaste code) binnen scripttags `<script>DIL code</script>`.
   * Klik op **[!UICONTROL Save]**.

1. Publiceer de container.
1. Genereer de code van de containertag en plaats deze op uw voorraad.

>[!MORELIKETHIS]
>
>* [Google Tag Manager Help Center](https://support.google.com/tagmanager#topic=3441530)
>* [Signalen](../dil/dil-instance-methods.md#signals)
>* [Voorvoegselvereisten voor belangrijke variabelen](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/traits/trait-variable-prefixes.html#prefix-requirements-for-key-variables)
