---
description: Code die door DART Enterprise (en andere bestemmingstypes) wordt vereist om de Audience Manager unieke gebruiker - identiteitskaart (UUID) waarde te vangen.
seo-description: Code die door DART Enterprise (en andere bestemmingstypes) wordt vereist om de Audience Manager unieke gebruiker - identiteitskaart (UUID) waarde te vangen.
seo-title: get_aamCookie-code
solution: Audience Manager
title: get_aamCookie-code
uuid: 89c30fe3-dbe6-4d18-b161-104167d75bcd
feature: Destination Basics
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '75'
ht-degree: 0%

---


# `get_aamCookie` Code {#get-aamcookie-code}

Code die door [!DNL DART Enterprise] (en andere bestemmingstypes) wordt vereist om de Audience Manager unieke gebruiker - identiteitskaart ([!DNL UUID]) waarde te vangen.

Definieer deze functie boven aan de pagina, idealiter binnen het `<head>` codeblok.

<!-- r_aam_de_cookie.xml -->

```js
<script type="text/javascript">
function get_aamCookie (c_name)
{
var i,x,y,ARRcookies=document.cookie.split(";");
for (i=0;i<ARRcookies.length;i++)
   {
   x=ARRcookies[i].substr(0,ARRcookies[i].indexOf("="));
   y=ARRcookies[i].substr(ARRcookies[i].indexOf("=")+1);
   x=x.replace(/^\s+|\s+$/g,"");
   if (x==c_name)
      { 
      return unescape(y);
      }
   }
}
</script>
```
