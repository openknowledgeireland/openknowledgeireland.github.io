---
id: 830
title: chy-02 test
date: 2014-07-19T23:50:31+00:00
author: Adrian Corcoran
layout: page
guid: http://openknowledge.ie/?page_id=830
wpd3-830-0:
  - |
    {"includes":["http://openknowledge.ie/wp-content/uploads/2014/07/list.css","https://ajax.googleapis.com/ajax/libs/jquery/1.11.0/jquery.min.js","http://openknowledge.ie/wp-content/uploads/2014/07/chy02.js"],"code":"\t\tvar mydata; // store data globally\r\n//\t\tvar alldata; // store data globally\r\n\r\n\t//-----------------------------------------------------------\r\n\t// 1. Load external data and format into hierarchy\r\n\t// 1.1 load external data\r\n\td3.tsv(\"http://openknowledge.ie/wp-content/uploads/2014/07/ds01_Charity_Summary.tsv\", function(error, data3) {\r\n\t\tdata3.forEach(function(d) {\r\n\t      d.CharityRegNo = parseInt(d.CharityRegNo);\r\n//\t\t  d.Seq = parseInt(d.Seq);\r\n//          d.Outline = parseInt(d.Outline);\r\n\t\t\t//        d.date = parseDate(d['Date Purchased']);\r\n\t\t});\r\n\t\t\t\t\t\r\n\t\tmydata = data3.filter(function(d) { return 2 == 2; });\r\n\t//\talert(JSON.stringify(mydata));\r\n\t//\t$(\"#ac\").html(JSON.stringify(mydata));\r\n\r\n\t\t\t\t// Nest the data\t\t\r\n\t\t\tvar data=d3.nest()\r\n\t\t\t\t.key(function(d) {return d.Cause;}).sortKeys(d3.Charity).sortKeys(d3.CharityRegNo)\r\n\t\t\t\t.entries(mydata);\r\n\t//\t\t\talert(JSON.stringify(data));\r\n\t//\t\t\t$(\"#ac\").html(JSON.stringify(data));\r\n\r\n\t\t\t// build level 1 menu\r\n\t\t\tvar m1 = d3.select(\".wpd3-830-0\").selectAll(\"div\").data(data).enter().append(\"div\")\r\n\t\t\t\t.html(function(d,i){return d.key+\"   (\"+d.values.length+\")\";})\r\n\t\t\t\t.attr(\"data-ID\",function(d,i){return i;})\r\n\t\t\t\t.style(\"background-color\",\"lightgray\");\r\n\r\n\t\t\t// Build level 2 menu\t\r\n\t\t\tvar m2 = m1.selectAll(\"div\").data(function(d1){return d1.values;}).enter().append(\"div\")\r\n\t\t\t\t.html(function(d){return \"<span>\"+\"\"+d.Charity+\"</span>\";})\r\n\t\t\t\t.attr(\"class\",\"off\")\r\n\t\t\t\t.style(\"text-indent\",\"25px\")\r\n\t\t\t\t.attr(\"data-ID\",function(d,i){return d.CharityRegNo;})\t\t\t\t\r\n\t\t\t\t.on(\"click\", function(d,i) {  \r\n\t//\t\t\t\t\talert('hi'+d3.select(this).attr(\"data-ID\"));\r\n\t\t\t\t\t\tmyFunction(parseInt(d3.select(this).attr(\"data-ID\")));    \r\n\t\t\t\t})\r\n\t\t\t\t.on(\"mouseover\", function(d,i) { d3.select(this).attr(\"class\", \"on\");})\r\n\t\t\t\t.on(\"mouseout\", function(d,i) { d3.select(this).attr(\"class\", \"off\");});\r\n\t\t\t\t\r\n\t\t\t\t\t\r\n  }); // Close d3.csv\t\r\n\r\n\t\tfunction myFunction(id) {\r\n//\t\t\talert('in myfunction'+JSON.stringify(mydata.filter(function(d) { return d.ID == id ; })));\r\n//\t\t\t$(\"#tbl\").html('in myfunction'+JSON.stringify(mydata.filter(function(d) { return d.ID == id ; })));\r\n\t\t\t$(\"#tbl\").html(buildCommit(mydata.filter(function(d) { return d.CharityRegNo == id ; }))); \r\n//\t\t\t$('#tbl table').addClass('table table-hover table-condensed');  // format table\t\r\n\t\t\t};\r\n"}
infinite_meta_show_sidebar:
  - No
infinite_meta_show_flex_slideshow:
  - No
infinite_meta_show_title:
  - No
---
<ul id="menu">
  <li style="float: left; display: inline; padding-right: 20px;">
    <a href="chy-04">(1) Home</a>
  </li>
  <li style="float: left; display: inline; padding-right: 20px;background-color:#FFFFCC">
    <a href="chy-02-test">(2) Browse by Category</a>
  </li>
  <li style="float: left; display: inline; padding-right: 20px;">
    <a href="chy-07">(3) Charities HQ</a>
  </li>
  <li style="float: left; display: inline; padding-right: 20px;">
    <a href="chy-01-charity">(4) Datasets (Open Data)</a>
  </li>
  <li style="float: left; display: inline; padding-right: 20px;">
    <a href="sample-visualisations">(5) Sample Visualisations</a>
  </li>
  <li style="float: left; display: inline; padding-right: 20px;">
    <a href="chy-12">(6) Future Website</a>
  </li>
</ul>



### Review the list of charities by cause.

<div>
  <div id="menu" style="width300px;float: left;">
    <b>Menu</b> 
    
    <link type="text/css" rel="Stylesheet" href='http://openknowledge.ie/wp-content/uploads/2014/07/list.css' />
    
    <br /> </p> 
    
    <div class="wpd3-830-0">
    </div>
  </div>
  
  <div id="tbl">
  </div>
</div>