---
description: Codevoorbeelden en beschrijvingen voor specifieke DIL-gebruiksgevallen.
seo-description: Code samples and descriptions for specific DIL use cases.
seo-title: DIL Use Cases and Code Samples
solution: Audience Manager
title: DIL Use cases and Code Samples
uuid: 27995c2d-6572-438e-af99-b5477f090ae9
feature: DIL Implementation
exl-id: 001710be-b377-460a-9e29-7268d25a6305
source-git-commit: cad38e2c523e9b762aa996c275daefa96c8e14b0
workflow-type: tm+mt
source-wordcount: '961'
ht-degree: 0%

---

# DIL Use cases and Code Samples{#dil-use-cases-and-code-samples}

>[!WARNING]
>
>Vanaf juli 2023 heeft Adobe de ontwikkeling van de extensie [!DNL Data Integration Library (DIL)] en [!DNL DIL] stopgezet.
>
>Bestaande klanten kunnen hun [!DNL DIL] -implementatie blijven gebruiken. Adobe ontwikkelt [!DNL DIL] echter niet verder dan dit punt. De klanten worden aangemoedigd om [ SDK van het Web van Experience Platform ](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) voor hun lange termijn strategie van de gegevensinzameling te evalueren.
>
>De klanten die nieuwe integratie van de gegevensinzameling na Juli 2023 willen uitvoeren zouden [ SDK van het Web van Experience Platform ](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) in plaats daarvan moeten gebruiken.

Codevoorbeelden en beschrijvingen voor specifieke DIL-gebruiksgevallen.

<!-- 

c_dil_use_case.xml

 -->

## Gegevenselementen naar Audience Manager verzenden met DIL {#send-data-elements-dil}

Maak een objectvariabele die informatie over pagina-elementen naar Audience Manager verzendt. Dit is nuttig voor algemene gegevensinzameling of als alternatief aan het verzamelen van gegevens met variabelen van de Analyse.

<!-- 

c_dil_send_page_objects.xml

 -->

**Beschrijving**

In de volgende code ziet u hoe u paginagegevens kunt verzamelen en naar Audience Manager kunt verzenden met [!UICONTROL DIL] . In deze voorbeelden wordt een variabele gebruikt om gegevenselementen op te nemen in een platte lijst of een array. Herinner me, ga in variabelen als [ zeer belangrijk-waardeparen ](../reference/key-value-pairs-explained.md) over. Noteer ook het voorvoegsel `c_` vóór de toets in het sleutelwaardepaar. Dit [ vereiste prefix ](../features/traits/trait-variable-prefixes.md) identificeert informatie als user-defined gegevens. In het eerste voorbeeld moet u `c_` handmatig aan de sleutel toevoegen. In het tweede voorbeeld doet [!UICONTROL DIL] dit automatisch voor u.

**houd de Eigenschappen van de Waarde verenigbaar**

Vergeet niet de eigenschappen van de waarde gelijk te houden wanneer u gegevens doorgeeft. Als u bijvoorbeeld twee identieke toetsen met verschillende waarden hebt, heeft de waarde van het laatste sleutelwaardepaar voorrang op de voorgaande waardeobjecten. Als u bijvoorbeeld `color:blue` en `color:red` opgeeft, wordt de geretourneerde waarde ingesteld op rood (overschrijft blauw).

**Voorbeeld 1: Verzend Gegevens als sleutel-Waarde paren**

In dit eenvoudige voorbeeld worden kleur- en prijsgegevens naar Audience Manager verzonden in de vorm van sleutelwaardeparen. De code kan er ongeveer als volgt uitzien:

<pre class="java"><code>
var sample_dil = DIL.create({partner:"<i>partner name</i>"}); 
sample_dil.api.signals(&lbrace; 
   c_color:"blue", 
   c_price:"900" 
&rbrace;); 
sample_dil.api.submit();
</code></pre>

**Voorbeeld 2: Verzend Gegevens in een Voorwerp**

In dit geavanceerde voorbeeld wordt getoond hoe gegevens in een object naar Audience Manager worden verzonden. Wanneer u met deze methode werkt, kunt u met [!UICONTROL DIL] een object als functieparameter doorgeven aan de methode [!DNL signals()] . [!UICONTROL DIL] De code kan er als volgt uitzien:

<pre class="java"><code>
var my_object = &lbrace; 
   color : "blue", 
   price : "900" 
&rbrace;; 
 
var sample_dil = DIL.create({ partner : "<i>partner name</i>" }); 
//Load the object and append "c_" to all keys in the key-value pairs and send data to AudienceManager. 
sample_dil.api.signals(my_object,"c_").submit();
</code></pre>

**Voorbeeld 3: Verzend de Gegevens van de Pagina in een Serie**

In dit geval gebruikt de variabele `my_object` een array om gegevens op te slaan. Dit voorbeeld bouwt op de informatie voort die door de geadviseerde methode hierboven wordt overgegaan, maar voegt een extra laag toe om een producttype en een model aan te passen. De code kan er ongeveer als volgt uitzien:

<pre class="java"><code>
var my_objects = &lbrack;&lbrace; 
   color : "blue", 
   price : "900" 
&rbrace;, &lbrace; 
   type : "acura", 
   model : "tl" 
&rbrace;&rbrack;; 
 
var sample_dil = DIL.create({ partner : "<i>partner name</i>" }); 
 
for (var i = 0; i < my_objects.length; i++) 
//Load the object and append "c_" to all the keys in the key-value pairs.  
&lbrace; 
    sample_dil.api.signals(my_objects[i], "c_"); 
&rbrace; 
sample_dil.api.submit();
</code></pre>

## URL van vastlegverwijzing {#capture-referring-url}

Leg een referentie-URL vast en verzend deze naar Audience Manager.

<!-- 

c_dil_hrefer_over_https.xml

 -->

>[!NOTE]
>
>Deze methode werkt alleen wanneer gebruikers schakelen tussen pagina&#39;s met vergelijkbare protocollen (HTTP versus HTTPS). De browser behoudt bijvoorbeeld een verwijzende URL wanneer u van een beveiligde site naar een andere beveiligde site navigeert. Browsers behouden de referentie-URL niet wanneer u gaat schakelen tussen beveiligde en onveilige sites. Dit gedrag is de normale browserfunctionaliteit en kan niet worden omzeild door [!UICONTROL DIL] .

**Steekproef van de Code**

De code kan er ongeveer als volgt uitzien:

<pre class="java"><code>
var adobe_dil = DIL.create({ partner : "<i>partner name</i>" }); 
adobe_dil.api.signals({ d_referer : document.referrer }).submit();
</code></pre>

## Typen zoekmachines vastleggen en zoektermen vastleggen {#capture-search-engine-types}

Stuur informatie over zoekmachinetypen en trefwoordzoekopdrachten naar Audience Manager.

>[!IMPORTANT]
>
>In deze sectie wordt de oude functionaliteit beschreven die niet wordt ondersteund in de nieuwste versies van DIL.

**Ondersteunde Motoren van het Onderzoek**

Standaard herkent `DIL.getSearchReferrer` zoekopdrachten vanuit deze zoekmachines (inclusief internationale variaties):

* [!DNL AOL]
* [!DNL Ask]
* [!DNL Bing]
* [!DNL Google]
* [!DNL Yahoo!]

**Beschrijving**

In de volgende code ziet u hoe u de zoekreferentie ophaalt voor een van de ondersteunde zoekprogramma&#39;s. In dit geval, veronderstellen wij een gebruiker die op de term &quot;huizen&quot;van [!DNL Google] Canada ( `www.google.ca`) wordt gezocht. Met deze code kunt u deze zoektermen vastleggen en naar Audience Manager verzenden.

**Basiscode**

De basiscode voor het ophalen van de zoekreferentie (bijvoorbeeld uit `google.com` ) ziet er als volgt uit:

```java
var search_referrer = DIL.tools.getSearchReferrer();
```

**Lijst van de Code van de Motor van het Onderzoek Code van de Motor**

Laten we er in dit geval van uitgaan dat een gebruiker de term &quot;huizen&quot; heeft gezocht vanuit [!DNL Google] Canada ( `www.google.ca` ). Let op hoe de code de vereiste parameter `c_` vooraf bepaalt in de zoekmachine ( `c_se` ) en de zoekterm ( `c_st` ). `c_` is a [ vereiste prefix ](../features/traits/trait-variable-prefixes.md) die deze als klant-bepaalde variabelen aan Audience Manager identificeert.

<pre class="java"><code>
var adobe_dil = DIL.create({partner:"<i>partner name</i>"}); 
var search_referrer = DIL.tools.getSearchReferrer(); 
 
if (search_referrer && search_referrer.valid) &lbrace; 
  adobe_dil.api.signals(&lbrace; 
    c_se : se.name, 
    c_st : se.keywords 
  &rbrace;).submit(); 
&rbrace;
</code></pre>

**Niet-vermelde de Codesteekproef van de Motor van het Onderzoek**

In dit geval, veronderstellen wij dat een gebruiker naar de term &quot;huizen&quot;van `dogpile.com` zocht. Omdat [!DNL Dogpile] niet standaard wordt ondersteund, kunt u DIL zo configureren dat dit zoekprogramma wordt herkend en de zoektermen worden teruggestuurd naar Audience Manager. De code kan er ongeveer als volgt uitzien:

<pre class="java"><code>
var adobe_dil = DIL.create({partner:"<i>partner name</i>"}); 
var search_referrer = DIL.tools.getSearchReferrer(document.referrer, &lbrace;  
    hostPattern:/dogpile\./, 
    queryParam:"q" 
&rbrace;); 
 
if (search_referrer && search_referrer.valid) &lbrace; 
  adobe_dil.api.signals(&lbrace; 
    c_se : se.name, 
    c_st : se.keywords 
  &rbrace;).submit(); 
&rbrace;
</code></pre>

## Sleutelwaarden toewijzen aan andere toetsen {#map-key-values}

Koppel de waarde van een sleutelwaardepaar aan een andere sleutel.

<!-- 

c_dil_map_keys.xml

 -->

**Beschrijving**

In een sleutelwaardepaar identificeert het voorvoegsel `c_` dat aan de sleutel is toegevoegd het signaal als door de klant gedefinieerde gegevens. Door de klant gedefinieerde gegevens worden gebruikt om zich te richten op de specifieke site die gegevens heeft doorgegeven bij een gebeurtenisaanroep. Soms wilt u deze informatie echter wel beschikbaar stellen voor alle eigenschappen in uw Audience Manager-account. Hiervoor wijst u de waarde in een `c_` sleutelwaardepaar toe aan een platformniveausleutel. Een sleutel op platformniveau wordt vooraf ingesteld met `d_` en maakt het signaal beschikbaar voor alle eigenschappen in uw account.

Als voorbeeld verzamelt u ZIP-codegegevens van een bepaalde site, maar wilt u deze als doel instellen voor al uw Audience Manager-eigenschappen. Als u de ZIP-code op platformniveau beschikbaar wilt maken, kunt u de door de klant gedefinieerde ZIP-codesleutel (bijvoorbeeld `c_zip` ) toewijzen aan een platformgedefinieerde sleutel, zoals hieronder wordt weergegeven.

**Steekproef van de Code**

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

## Verkeer DIL in Google Tag Manager (GTM) {#traffic-dil-gtm}

DIL instellen en bedienen met een GTM-tag.

<!-- 

t_dil_google_tagmanager.xml

 -->

Bij deze procedure wordt ervan uitgegaan dat u een [!DNL Google Tag Manager] -account, enige praktische kennis van dat product en uw Audience Manager `dil.js` -bestand hebt.

U kunt als volgt het `dil.js` -bestand verzenden in GTM:

1. Maak een nieuwe container of open een bestaande container.
1. Voeg een nieuwe tag toe aan de container.
1. Open de tag om deze te bewerken en:

   * Geef de tag een naam.
   * Selecteer **[!UICONTROL Custom HTML Tag]** in de vervolgkeuzelijst **[!UICONTROL Tag Type]** .
   * Plaats in het HTML-veld de [!UICONTROL DIL] -code (bibliotheek + de aangepaste code) binnen scripttags `<script>DIL code</script>` .
   * Klik op **[!UICONTROL Save]**.

1. Publiceer de container.
1. Genereer de code van de containertag en plaats deze op uw voorraad.

>[!MORELIKETHIS]
>
>* [ het Centrum van de Hulp van de Manager van de Markering van Google ](https://support.google.com/tagmanager#topic=3441530)
>* [ Signalen ](../dil/dil-instance-methods.md#signals)
>* [Voorvoegselvereisten voor belangrijke variabelen](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/traits/trait-variable-prefixes.html#prefix-requirements-for-key-variables)
