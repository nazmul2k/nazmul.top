---
title: "How to fix org.xml.sax.SAXParseException lineNumber * columnNumber * The reference to entity “l” must end with the * delimiter while adding Google Tag Manager"
date: 2025-02-08T17:26:50+06:00
draft: false
tags: ['google tag manager', 'tag manager error', 'google tag manager error', 'error fixing', 'error handling']
---

While we are adding Google Tag Manager into our site, sometimes we may face an error like below. (For security purposes I will not share any screenshot in this article.)


> org.xml.sax.SAXParseException; lineNumber: 9; columnNumber: 43; The reference to entity “l” must end with the ‘;’ delimiter.

To fix this watch the error carefully. Find the lineNumber of this error. In my case the lineNumber is 9. So, in lineNumber 9 seach for `&l=` and replace this with `&amp;=`

Now save this. Insha-Allah now your Google Tag Manager will be successfully added.
