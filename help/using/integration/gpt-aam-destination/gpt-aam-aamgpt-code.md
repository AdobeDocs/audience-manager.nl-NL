---
description: AamGpt is een JavaScript-functie die Cookgegevens van Audience Manager leest en die informatie naar Google Publisher-tags verzendt.
seo-description: AamGpt is een JavaScript-functie die Cookgegevens van Audience Manager leest en die informatie naar Google Publisher-tags verzendt.
seo-title: Code Auditiemanager voor Google Publisher-tags
solution: Audience Manager
title: Code Auditiemanager voor Google Publisher-tags
uuid: 24ff5d16-b360-46cc-a4c6-6db34d7fda75
translation-type: tm+mt
source-git-commit: 6169e8aefc4c215c83d6229be7378f90453f19e9

---


# Code Auditiemanager voor Google Publisher-tags {#audience-manager-code-for-google-publisher-tags}

`AamGpt` is een [!DNL JavaScript] functie die de koekjesgegevens van de Manager van de Publiek leest en die informatie naar [!DNL Google Publisher Tags]. verzendt.

>[!NOTE]
>
>Deze functie is niet vereist als u uw eigen code hebt om de koekjesgegevens van de Manager van de Audience van de Manager van de Auditie van de [!UICONTROL UUID] en bestemmingskoekjes te lezen.

## Voorbeeldcode

Plaats de `AamGpt` code boven aan de pagina, idealiter binnen het `<head>` codeblok. De `AamGpt` code is hieronder beschikbaar:

```js
var AamGpt = {  
 strictEncode: function(str){ 
  return encodeURIComponent(str).replace(/[!'()]/g, escape).replace(/\*/g, "%2A"); 
 }, 
 getCookie: function(c_name) 
 { 
  var i,x,y,c=document.cookie.split(";"); 
  for (i=0;i<c.length;i++) 
  { 
   x=c[i].substr(0,c[i].indexOf("=")); 
   y=c[i].substr(c[i].indexOf("=")+1); 
   x=x.replace(/^\s+|\s+$/g,""); 
   if (x==c_name) 
   { 
    return unescape(y); 
   } 
  } 
 }, 
 getKey: function(c_name){ 
  var c=this.getCookie(c_name); 
  c=this.strictEncode(c); 
  if(typeof c != "undefined" && c.match(/\w+%3D/)){ 
   var cList=c.split("%3D"); 
   if(typeof cList[0] != "undefined" && cList[0].match(/\w+/)) 
   { 
    return cList[0]; 
   } 
  }  
 }, 
 getValues: function(c_name){ 
  var c=this.getCookie(c_name); 
  c=this.strictEncode(c); 
  if(typeof c != "undefined" && c.match(/\w+%3D\w+/)){ 
   var cList=c.split("%3D"); 
   if(typeof cList[1] != "undefined" && cList[1].match(/\w+/)) 
   { 
    var vList=cList[1].split("%2C"); 
    if(typeof vList[0] != "undefined") 
    { 
     return vList; 
    } else { 
     return null; 
    }    
   } else { 
    return null; 
   } 
  } else { 
   return null; 
  } 
 } 
};
```
