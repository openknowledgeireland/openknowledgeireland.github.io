---
id: 875
title: HackDay WebPages
date: 2014-07-22T20:54:55+00:00
author: Adrian Corcoran
layout: page
guid: http://openknowledge.ie/?page_id=875
wpd3-875-0:
  - |
    {"includes":["http://openknowledge.ie/wp-content/uploads/2014/07/tabulate.js","https://ajax.googleapis.com/ajax/libs/jquery/1.11.0/jquery.min.js","http://openknowledge.ie/wp-content/uploads/2014/07/jquery.tablesorter.min_.js","http://openknowledge.ie/wp-content/uploads/2014/08/jquery.formatCurrency-1.4.0.min_.js"],"code":"\tvar mydata; // store data globally\r\n\t\r\n\t//-----------------------------------------------------------\r\n\t// 1. Load external data and format into hierarchy\r\n\t// 1.1 load external data\r\n\td3.tsv(\"http://openknowledge.ie/wp-content/uploads/2014/08/ds01_charity_2012_summary.tsv\", function(error, data3) {\r\n\t\tdata3.forEach(function(d) {\r\n\t      d.CharityRegNo = parseInt(d.CharityRegNo);\r\n\t      d.TotalExp = parseFloat(d.TotalExp);\r\n\t      d.Pct_Charity = parseFloat(d.Pct_Charity);\r\n\t\t});\r\n\t\t\t\t\t\r\n\t\tmydata = data3.filter(function(d) { return 1 == 1; });\r\n//\t\talert(JSON.stringify(mydata.filter(function(d) { return 1 == 1 ; })));\r\n\t\t\t\r\n\t\tvar cols = [\"CHY\",\"Charity\",\"Website\",\"B_Expended\",\"ExpBarChart\",\"Cause\",\"Pct_B2\",\r\n\t\t    \"A1a_Voluntary\",\"2012_Rpt\",\"CRO\",\"OpenCorporates\"]; // build array of column\r\n\t\t$(tabulate(mydata.filter(function(d) { return 1 == 1; }),cols ,\"#tbl\"));\t//build table\r\n\t\t\r\n\t\t// build anchor element for title\r\n\t\t$('#tbl table tbody').children('tr').each(function() {\r\n\t\t\tvar a = $(this).children('td:nth-child(2)').html();\r\n\t\t\tvar h = $(this).children('td:nth-child(3)').html();\r\n\t\t\tvar s = \"<a target=\\\"_blank\\\" href=\\\"\"+h+\"\\\">\"+a+\"</a>\";\r\n//\t\t\talert(h);\r\n\t\t\tif ( h != '' ) { $(this).children('td:nth-child(2)').html(s); }\r\n\t\t});\r\n\t\t\r\n\t\t// build anchor element for opencorporates\r\n\t\t$('#tbl table tbody').children('tr').each(function() {\r\n\t\t\tvar a = $(this).children('td:nth-child(10)').html();\r\n\t\t\tvar h = $(this).children('td:nth-child(11)').html();\r\n\t\t\tvar s = \"<a target=\\\"_blank\\\" href=\\\"\"+h+\"\\\">\"+a+\"</a>\";\r\n//\t\t\talert(h);\r\n\t\t\tif ( h != '' ) { $(this).children('td:nth-child(10)').html(s); }\r\n\t\t});\r\n\t\t\r\n\t\t\t\t// build anchor element for 2012 report\r\n\t\t$('#tbl table tbody').children('tr').each(function() {\r\n//\t\t\tvar a = $(this).children('td:nth-child(9)').html();\r\n\t\t\tvar h = $(this).children('td:nth-child(9)').html();\r\n\t\t\tvar s = \"<a target=\\\"_blank\\\" href=\\\"\"+h+\"\\\">\"+\"2012 Rpt.\"+\"</a>\";\r\n//\t\t\talert(h);\r\n\t\t\tif ( h != '' ) { $(this).children('td:nth-child(9)').html(s); }\r\n\t\t});\r\n\t\t\r\n\t    // Format Currency\r\n\t\t$('#tbl table tbody').children('tr').each(function() {\r\n\t\t    $(this).children('td:nth-child(4)').formatCurrency({symbol:'€',roundToDecimalPlace:-1});\r\n\t\t    $(this).children('td:nth-child(8)').formatCurrency({symbol:'€',roundToDecimalPlace:-1});\r\n//\t\t    $(this).children('td:nth-child(10)').formatCurrency({symbol:'€',roundToDecimalPlace:-1});\r\n\t\t    $(this).children('td:nth-child(4)').css('text-align','right');\r\n\t\t    $(this).children('td:nth-child(8)').css('text-align','right');\r\n//\t\t    $(this).children('td:nth-child(10)').css('text-align','right');\r\n\t\t});\r\n\t\t\r\n\t    // Format Percentage\r\n\t\t$('#tbl table tbody').children('tr').each(function() {\r\n\t\t    $(this).children('td:nth-child(7)').append(' %');$(this).children('td:nth-child(7)').css('text-align','right');\r\n//\t\t    $(this).children('td:nth-child(7)').append(' %');$(this).children('td:nth-child(7)').css('text-align','right');\r\n//\t\t    $(this).children('td:nth-child(8)').append(' %');$(this).children('td:nth-child(8)').css('text-align','right');\r\n\t\t});\r\n\r\n        // rename columns\t\t\r\n        $('#tbl table thead tr').find('th:nth-child(7)').text('Pct_B2_Charity');\r\n\r\n        // hide columns\r\n        $('#tbl table thead th:nth-child(3)').hide();$('#tbl table tbody td:nth-child(3)').hide();\r\n        $('#tbl table thead th:nth-child(11)').hide();$('#tbl table tbody td:nth-child(11)').hide();\r\n        $(\"#tbl table\").tablesorter();  // sort table\r\n  });"}
infinite_meta_show_sidebar:
  - No
infinite_meta_show_flex_slideshow:
  - No
infinite_meta_show_title:
  - No
---
<ul id="menu">
  <li style="float: left; display: inline; padding-right: 20px; background-color: #ffffcc;">
    <a href="chy-04">(1) Home</a>
  </li>
  <li style="float: left; display: inline; padding-right: 20px;">
    <a href="chy-12-2">(2) Income</a>
  </li>
  <li style="float: left; display: inline; padding-right: 20px;">
    <a href="chy-15">(3) Expenditure</a>
  </li>
  <li style="float: left; display: inline; padding-right: 20px;">
    <a href="chy-10-datasets">(4) Datasets (Open Data)</a>
  </li>
  <li style="float: left; display: inline; padding-right: 20px;">
    <a href="http://www.openspending.org">(5) Openspending.org</a>
  </li>
  <li style="float: left; display: inline; padding-right: 20px;">
    <a href="chy-12">(6) Future Website</a>
  </li>
</ul>

* * *

### Charity 2012 Summary

This table represents just a few of the columns from the Charity Summary dataset. We hope you will be interested to visit our [Datasets (Open Data)](http://openknowledge.ie/chy-10-datasets/) page, download the datasets, build improved visualizations and help us to extract more data from the Annual Reports.

<div id="tbl">
</div>


  

  

  


<div class="wpd3-875-0">
</div>