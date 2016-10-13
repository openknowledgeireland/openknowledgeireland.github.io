---
id: 800
title: d3 tree map
date: 2014-07-18T23:16:15+00:00
author: Adrian Corcoran
layout: page
guid: http://openknowledge.ie/?page_id=800
wpd3-800-0:
  - |
    {"includes":["/wp-content/uploads/2014/07/treemap.css"],"code":"var margin = {top: 40, right: 10, bottom: 10, left: 10},\r\n    width = 900 - margin.left - margin.right,\r\n    height = 500 - margin.top - margin.bottom;\r\n\r\nvar color = d3.scale.category20c();\r\n\r\nvar treemap = d3.layout.treemap()\r\n    .size([width, height])\r\n    .sticky(true)\r\n    .value(function(d) { return d.size; });\r\n\r\nvar div = d3.select(\".wpd3-800-0\").append(\"div\")\r\n    .style(\"position\", \"relative\")\r\n    .style(\"width\", (width + margin.left + margin.right) + \"px\")\r\n    .style(\"height\", (height + margin.top + margin.bottom) + \"px\")\r\n    .style(\"left\", margin.left + \"px\")\r\n    .style(\"top\", margin.top + \"px\");\r\n\r\n// Load the external data and transform\r\nd3.tsv(\"/wp-content/uploads/2014/07/tree.csv\", function(error, data) {\r\n\t// 1.2 create a name-based map for the nodes\r\n\t\tvar dataMap = data.reduce(function(map, node) {\r\n\t\t\t\tmap[node.name] = node;\r\n\t\t\t\treturn map;\r\n\t\t\t}, {});\r\n\t//\t\talert('name-based map'+JSON.stringify(dataMap));\r\n\t\t\t\r\n\t// 1.3 iteratively add each child to its parents, or to the root array if no parent is found\r\n\t\t\t\tvar treeData = [];\r\n\t\t\t\tdata.forEach(function(node) {\r\n\t\t\t\t // add to parent\r\n\t\t\t\t var parent = dataMap[node.parent];\r\n\t\t\t\t if (parent) {\r\n\t\t\t\t  // create child array if it doesn't exist\r\n\t\t\t\t  (parent.children || (parent.children = []))\r\n\t\t\t\t   // add node to child array\r\n\t\t\t\t   .push(node);\r\n\t\t\t\t } else {\r\n\t\t\t\t  // parent is null or missing\r\n\t\t\t\t  treeData.push(node);\r\n\t\t\t\t }\r\n\t\t\t\t});\r\n\t//  1.4 Confirm TreeData is in the correct format\r\n\t//\t\t\talert(JSON.stringify(treeData));\r\n//\t$(\"#ac\").html(JSON.stringify(treeData[0]));\r\n\t\r\n//d3.json(\"../json/flare.json\", function(error, root) {\r\n  var node = div.datum(treeData[0]).selectAll(\".node\")\r\n      .data(treemap.nodes)\r\n    .enter().append(\"div\")\r\n      .attr(\"class\", \"node\")\r\n      .call(position)\r\n      .style(\"background\", function(d) { return d.children ? color(d.name) : null; })\r\n      .text(function(d) { return d.children ? null : d.name; });\r\n\r\n  d3.selectAll(\"input\").on(\"change\", function change() {\r\n    var value = this.value === \"count\"\r\n        ? function() { return 1; }\r\n        : function(d) { return d.size; };\r\n\r\n    node\r\n        .data(treemap.value(value).nodes)\r\n      .transition()\r\n        .duration(1500)\r\n        .call(position);\r\n  });\r\n\r\n  function position() {\r\n  this.style(\"left\", function(d) { return d.x + \"px\"; })\r\n      .style(\"top\", function(d) { return d.y + \"px\"; })\r\n      .style(\"width\", function(d) { return Math.max(0, d.dx - 1) + \"px\"; })\r\n      .style(\"height\", function(d) { return Math.max(0, d.dy - 1) + \"px\"; });\r\n}\r\n\r\n  });\r\n"}
infinite_meta_show_sidebar:
  - No
infinite_meta_show_flex_slideshow:
  - No
infinite_meta_show_title:
  - No
---
<ul id="menu">
  <li style="float:left;display:inline;padding-right: 20px;">
    <a href="chy-04">Home</a>
  </li>
  <li style="float:left;display:inline;padding-right: 20px;">
    <a href="chy-02-test">Cause</a>
  </li>
  <li style="float:left;display:inline;padding-right: 20px;">
    <a href="chy-06">Bar Charts</a>
  </li>
  <li style="float:left;display:inline;padding-right: 20px;">
    <a href="d3-tree-chart">Tree Charts</a>
  </li>
  <li style="float:left;display:inline;padding-right: 20px;">
    <a href="d3-tree-map">Tree Map</a>
  </li>
  <li style="float:left;display:inline;padding-right: 20px;">
    <a href="chy-07">Map of Charities</a>
  </li>
  <li style="float:left;display:inline;padding-right: 20px;">
    <a href="chy-01-charity">Datasets (Open Data)</a>
  </li>
</ul>



### Tree Map

<link type="text/css" rel="Stylesheet" href='http://openknowledge.ie/wp-content/uploads/2014/07/treemap.css' />

<div class="wpd3-800-0">
</div>