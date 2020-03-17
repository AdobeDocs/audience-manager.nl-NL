---
description: Code die door de Onderneming van DART (en andere bestemmingstypes) wordt vereist om de waarde van de Gebruiker van de Manager van de Publiek unieke (UUID) te vangen.
seo-description: Code die door de Onderneming van DART (en andere bestemmingstypes) wordt vereist om de waarde van de Gebruiker van de Manager van de Publiek unieke (UUID) te vangen.
seo-title: get_aamCookie-code
solution: Audience Manager
title: get_aamCookie-code
uuid: 89c30fe3-dbe6-4d18-b161-104167d75bcd
translation-type: tm+mt
source-git-commit: abb66d75a0d47f5257ea8c63bdb59e604db801d3

---


# `get_aamCookie` Code {#get-aamcookie-code}

Code die door [!DNL DART Enterprise] (en andere bestemmingstypes) wordt vereist om de unieke gebruiker van de Manager van de Publiek - identiteitskaart ([!DNL UUID]) waarde te vangen.

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
