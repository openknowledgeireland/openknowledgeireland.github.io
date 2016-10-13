---
id: 852
title: chy03-test2
date: 2014-07-20T01:17:13+00:00
author: Adrian Corcoran
layout: page
guid: http://openknowledge.ie/?page_id=852
wpd3-852-0:
  - '{"includes":["http://openknowledge.ie/wp-content/uploads/2014/07/tabulate.js","https://ajax.googleapis.com/ajax/libs/jquery/1.11.0/jquery.min.js"],"code":"\tvar mydata; // store data globally\r\n\t\r\n\t//-----------------------------------------------------------\r\n\t// 1. Load external data and format into hierarchy\r\n\t// 1.1 load external data\r\n\td3.tsv(\"http://openknowledge.ie/wp-content/uploads/2014/07/ds_chy_dashboard.tsv\", function(error, data3) {\r\n\t\tdata3.forEach(function(d) {\r\n\t      d.CharityRegNo = parseInt(d.CharityRegNo);\r\n\t\t});\r\n\t\t\t\t\t\r\n\t\tmydata = data3.filter(function(d) { return 1 == 1; });\r\n\t\talert(JSON.stringify(mydata.filter(function(d) { return 1 == 1 ; })));\r\n\t\t\t\r\n\t\tvar cols = [\"CharityRegNo\",\"Charity\",\"Cause\",\"Category\",\"Website2\",\"WhatCharityDoes\",\"CompanyRegNo\"]; // build array of column\r\n\t\t$(tabulate(mydata.filter(function(d) { return 1 == 1; }),cols ,\"#tbl\"));\t//build table\r\n\r\n  }); "}'
infinite_meta_show_sidebar:
  - No
infinite_meta_show_flex_slideshow:
  - No
infinite_meta_show_title:
  - No
---

  


<div class="wpd3-852-0">
</div>

Click on the Charity name to open their website in a new tab.

&nbsp;