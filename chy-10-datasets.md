---
id: 1057
title: chy-10 Datasets
date: 2014-07-27T13:01:40+00:00
author: Adrian Corcoran
layout: page
guid: http://openknowledge.ie/?page_id=1057
infinite_meta_show_sidebar:
  - No
infinite_meta_show_flex_slideshow:
  - No
infinite_meta_show_title:
  - No
wpd3-1057-0:
  - |
    {"includes":["http://openknowledge.ie/wp-content/uploads/2014/07/tabulate.js","https://ajax.googleapis.com/ajax/libs/jquery/1.11.0/jquery.min.js","http://openknowledge.ie/wp-content/uploads/2014/07/jquery.tablesorter.min_.js","http://openknowledge.ie/wp-content/uploads/2014/08/jquery.formatCurrency-1.4.0.min_.js"],"code":"\tvar mydata; // store data globally\r\n\t\r\n\t//-----------------------------------------------------------\r\n\t// 1. Load external data and format into hierarchy\r\n\t// 1.1 load external data\r\n\td3.tsv(\"http://openknowledge.ie/wp-content/uploads/2014/11/dsdd.tsv\", function(error, data3) {\r\n\t\tdata3.forEach(function(d) {\r\n\t      d.RowID = parseInt(d.RowID);\r\n\t\t});\r\n\t\t\t\t\t\r\n\t\tmydata = data3.filter(function(d) { return 1 == 1; });\r\n//\t\talert(JSON.stringify(mydata.filter(function(d) { return 1 == 1 ; })));\r\n\t\t\t\r\n\t\tvar cols = [\"RowID\",\"Column\",\"Format\",\"Description\",\"ds01\",\"ds02\",\"ds03\"\r\n\t\t    ]; // build array of column\r\n\t\t$(tabulate(mydata.filter(function(d) { return 1 == 1; }),cols ,\"#tbl\"));\t//build table\r\n\t\t\r\n/*\r\n\t\t// build anchor element for title\r\n\t\t$('#tbl table tbody').children('tr').each(function() {\r\n\t\t\tvar a = $(this).children('td:nth-child(2)').html();\r\n\t\t\tvar h = $(this).children('td:nth-child(3)').html();\r\n\t\t\tvar s = \"<a target=\\\"_blank\\\" href=\\\"\"+h+\"\\\">\"+a+\"</a>\";\r\n//\t\t\talert(h);\r\n\t\t\tif ( h != '' ) { $(this).children('td:nth-child(2)').html(s); }\r\n\t\t});\r\n\t\t\r\n\t    // Format Currency\r\n\t\t$('#tbl table tbody').children('tr').each(function() {\r\n\t\t    $(this).children('td:nth-child(4)').formatCurrency({symbol:'€',roundToDecimalPlace:-1});\r\n//\t\t    $(this).children('td:nth-child(9)').formatCurrency({symbol:'€',roundToDecimalPlace:-1});\r\n//\t\t    $(this).children('td:nth-child(10)').formatCurrency({symbol:'€',roundToDecimalPlace:-1});\r\n\t\t    $(this).children('td:nth-child(4)').css('text-align','right');\r\n//\t\t    $(this).children('td:nth-child(9)').css('text-align','right');\r\n//\t\t    $(this).children('td:nth-child(10)').css('text-align','right');\r\n\t\t});\r\n\t\t\r\n\t    // Format Percentage\r\n\t\t$('#tbl table tbody').children('tr').each(function() {\r\n\t\t    $(this).children('td:nth-child(6)').append(' %');$(this).children('td:nth-child(6)').css('text-align','right');\r\n\t\t    $(this).children('td:nth-child(7)').append(' %');$(this).children('td:nth-child(7)').css('text-align','right');\r\n\t\t    $(this).children('td:nth-child(8)').append(' %');$(this).children('td:nth-child(8)').css('text-align','right');\r\n\t\t});\r\n\t\t\r\n*/\r\n        // hide columns\r\n//        $('#tbl table thead th:nth-child(3)').hide();$('#tbl table tbody td:nth-child(3)').hide();\r\n        $(\"#tbl table\").tablesorter();  // sort table\r\n  });"}
---
<ul id="menu">
  <li style="float: left; display: inline; padding-right: 20px;">
    <a href="chy-04">(1) Home</a>
  </li>
  <li style="float: left; display: inline; padding-right: 20px;">
    <a href="chy-12-2">(2) Income</a>
  </li>
  <li style="float: left; display: inline; padding-right: 20px;">
    <a href="chy-15">(3) Expenditure</a>
  </li>
  <li style="float: left; display: inline; padding-right: 20px; background-color: #ffffcc;">
    <a href="chy-10-datasets">(4) Datasets (Open Data)</a>
  </li>
  <li style="float: left; display: inline; padding-right: 20px;">
    <a href="openspending">(5) Openspending.org</a>
  </li>
  <li style="float: left; display: inline; padding-right: 20px;">
    <a href="chy-12">(6) Future Website</a>
  </li>
</ul>

* * *

## Datasets (Open Data)

A team of volunteers extracted data from the 2012 annual financial reports of 24 of the largest charities in Ireland (1Mil+€) and have made this data available as &#8220;Open Data&#8221;. While, these datasets may only represent a small sample of the thousands of charities in Ireland, they do however go some way towards demonstrating transparency, particularly in regard to  &#8220;How Charities are funded&#8221; and &#8220;Where the money is spent&#8221;.

We hope that these inputs can be built upon by other volunteers/groups thus helping us to achieve the aim of informing the public that there are well run Open & Transparent Charities, who need continued public support to provide vital services and simultaneously encourage the Charity Sector to become more transparent by publishing their reports in an open data format.

**Datasets:**
  
**** 2012 &#8211; Data scraped by volunteers from Annual Reports**

<a href="https://docs.google.com/document/d/14rmhlEgdfolXyJASAe-X-mg8Tr4LMrhyUHH5M-kBjOU/pub" target="_blank">Methodology</a>

  1. ds01\_charity\_2012_summary             <a href="https://docs.google.com/spreadsheets/d/1R0QgwdpDK6_KZLz2i20zc-EwSo4OgBiI0nCRQawixI0/export?gid=1237917342&format=tsv" target="_blank">TSV</a> , <a href="https://docs.google.com/spreadsheets/d/1R0QgwdpDK6_KZLz2i20zc-EwSo4OgBiI0nCRQawixI0/export?gid=1237917342&format=csv" target="_blank">CSV</a>, <a href="https://docs.google.com/spreadsheets/d/1R0QgwdpDK6_KZLz2i20zc-EwSo4OgBiI0nCRQawixI0/export?gid=1237917342&format=xlsx" target="_blank">EXCEL</a>
  2. ds02\_charity\_2012_expenditure      <a href="https://docs.google.com/spreadsheets/d/1R0QgwdpDK6_KZLz2i20zc-EwSo4OgBiI0nCRQawixI0/export?gid=931706284&format=tsv" target="_blank">TSV</a> , <a href="https://docs.google.com/spreadsheets/d/1R0QgwdpDK6_KZLz2i20zc-EwSo4OgBiI0nCRQawixI0/export?gid=931706284&format=csv" target="_blank">CSV</a>, <a href="https://docs.google.com/spreadsheets/d/1R0QgwdpDK6_KZLz2i20zc-EwSo4OgBiI0nCRQawixI0/export?gid=931706284&format=xlsx" target="_blank">EXCEL</a>
  3. ds03\_charity\_2012_income                 <a href="https://docs.google.com/spreadsheets/d/1R0QgwdpDK6_KZLz2i20zc-EwSo4OgBiI0nCRQawixI0/export?gid=349511916&format=tsv" target="_blank">TSV</a> , <a href="https://docs.google.com/spreadsheets/d/1R0QgwdpDK6_KZLz2i20zc-EwSo4OgBiI0nCRQawixI0/export?gid=349511916&format=csv" target="_blank">CSV</a>, <a href="https://docs.google.com/spreadsheets/d/1R0QgwdpDK6_KZLz2i20zc-EwSo4OgBiI0nCRQawixI0/export?gid=349511916&format=xlsx" target="_blank">EXCEL</a>

**** 2013 &#8211; Only one charity has volunteered its financial information in Open Data Format**

  1. ds01\_charity\_2013_summary         <a href="https://docs.google.com/spreadsheets/d/1R0QgwdpDK6_KZLz2i20zc-EwSo4OgBiI0nCRQawixI0/export?gid=1334509422&format=tsv" target="_blank">TSV</a> , <a href="https://docs.google.com/spreadsheets/d/1R0QgwdpDK6_KZLz2i20zc-EwSo4OgBiI0nCRQawixI0/export?gid=1334509422&format=csv" target="_blank">CSV</a>, <a href="https://docs.google.com/spreadsheets/d/1R0QgwdpDK6_KZLz2i20zc-EwSo4OgBiI0nCRQawixI0/export?gid=1334509422&format=xlsx" target="_blank">EXCEL</a>
  2. ds02\_charity\_2013_expenditure   <a href="https://docs.google.com/spreadsheets/d/1R0QgwdpDK6_KZLz2i20zc-EwSo4OgBiI0nCRQawixI0/export?gid=1997554011&format=tsv" target="_blank">TSV</a> , <a href="https://docs.google.com/spreadsheets/d/1R0QgwdpDK6_KZLz2i20zc-EwSo4OgBiI0nCRQawixI0/export?gid=1997554011&format=csv" target="_blank">CSV</a>, <a href="https://docs.google.com/spreadsheets/d/1R0QgwdpDK6_KZLz2i20zc-EwSo4OgBiI0nCRQawixI0/export?gid=1997554011&format=xlsx" target="_blank">EXCEL</a>
  3. ds03\_charity\_2013_income               <a href="https://docs.google.com/spreadsheets/d/1R0QgwdpDK6_KZLz2i20zc-EwSo4OgBiI0nCRQawixI0/export?gid=128675537&format=tsv" target="_blank">TSV</a> , <a href="https://docs.google.com/spreadsheets/d/1R0QgwdpDK6_KZLz2i20zc-EwSo4OgBiI0nCRQawixI0/export?gid=128675537&format=csv" target="_blank">CSV</a>, <a href="https://docs.google.com/spreadsheets/d/1R0QgwdpDK6_KZLz2i20zc-EwSo4OgBiI0nCRQawixI0/export?gid=128675537&format=xlsx" target="_blank">EXCEL</a>

### Data Dictionary

<div id="tbl">
</div>


  

  

  


<div class="wpd3-1057-0">
</div>

  * <a href="http://openknowledge.ie/wp-content/uploads/2014/10/Benefits-Map-Charity-2-2-2.pdf" target="_blank">Charity Open Data Concept</a>
  * <a href="http://www.dochas.ie/pages/resources/documents/sorp05.pdf#page=21" target="_blank">SORP Standard</a>
  * <a href="http://openknowledge.ie/wp-content/uploads/2014/10/Charity_SORP_v2.pdf" target="_blank">SORP v2 (OK Ireland)</a>