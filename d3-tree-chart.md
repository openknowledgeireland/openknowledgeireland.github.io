---
id: 782
title: d3 tree chart
date: 2014-07-18T22:14:18+00:00
author: Adrian Corcoran
layout: page
guid: http://openknowledge.ie/?page_id=782
infinite_meta_show_sidebar:
  - No
infinite_meta_show_flex_slideshow:
  - No
infinite_meta_show_title:
  - No
wpd3-782-0:
  - |
    {"includes":["/wp-content/uploads/2014/07/tree.css"],"code":"\t// 1. Load external data and format into hierarchy\r\n\t// 1.1 load external data\r\n\td3.tsv(\"/wp-content/uploads/2014/07/tree.csv\", function(error, data) {\r\n\t\tdata.forEach(function(d) {\r\n\t      d.PID = parseInt(d.PID);\r\n\t\t\t//        d.date = parseDate(d['Date Purchased']);\r\n\t\t});\r\n\t//\talert(JSON.stringify(data));\r\n\t\r\n\t// 1.2 create a name-based map for the nodes\r\n\t\tvar dataMap = data.reduce(function(map, node) {\r\n\t\t\t\tmap[node.name] = node;\r\n\t\t\t\treturn map;\r\n\t\t\t}, {});\r\n\t//\t\talert('name-based map'+JSON.stringify(dataMap));\r\n\r\n\t// 1.3 iteratively add each child to its parents, or to the root array if no parent is found\r\n\t\t\t\tvar treeData = [];\r\n\t\t\t\tdata.forEach(function(node) {\r\n\t\t\t\t // add to parent\r\n\t\t\t\t var parent = dataMap[node.parent];\r\n\t\t\t\t if (parent) {\r\n\t\t\t\t  // create child array if it doesn't exist\r\n\t\t\t\t  (parent.children || (parent.children = []))\r\n\t\t\t\t   // add node to child array\r\n\t\t\t\t   .push(node);\r\n\t\t\t\t } else {\r\n\t\t\t\t  // parent is null or missing\r\n\t\t\t\t  treeData.push(node);\r\n\t\t\t\t }\r\n\t\t\t\t});\r\n\t\t\t\t\r\n\t//  1.4 Confirm TreeData is in the correct format\r\n\t//\t\t\talert(JSON.stringify(treeData))\r\n\t//\t\t\talert(treeData[0].children[2].name);\t\r\n\t\t\t\t\r\n\t//-------------------------------------------------------------------\r\n\t// 2.0 ************** Generate the tree diagram  *****************\r\n\t\t\t\tvar margin = {top: 5, right: 10, bottom: 5, left: 150},\r\n\t\t\t\t width = 1000 - margin.right - margin.left,\r\n\t\t\t\t height = 500 - margin.top - margin.bottom;\r\n\t\t\t\t \r\n\t\t\t\tvar i = 0;\r\n\r\n\t\t\t\tvar tree = d3.layout.cluster()\r\n//\t\t\t\tvar tree = d3.layout.tree()\r\n\t\t\t\t .size([height, width]);\r\n\r\n\t\t\t\tvar diagonal = d3.svg.diagonal()\r\n\t\t\t\t .projection(function(d) { return [d.y, d.x]; });\r\n\r\n\t\t\t\tvar svg = d3.select(\".wpd3-782-0\").append(\"svg\")\r\n\t\t\t\t .attr(\"width\", width + margin.right + margin.left)\r\n\t\t\t\t .attr(\"height\", height + margin.top + margin.bottom)\r\n\t\t\t\t  .append(\"g\")\r\n\t\t\t\t .attr(\"transform\", \"translate(\" + margin.left + \",\" + margin.top + \")\");\r\n\r\n\t\t\t\t//root = treeData[0].children[2];\r\n\t\t\t\troot = treeData[0];\r\n\t\t\t\t  \r\n\t\t\t\tupdate(root);\r\n\t\t\t\t\r\n\t// 3.0 Draw Functions\r\n\t// --------------------------------------------------------------------------------------------------------------\r\n\t\t\t\tfunction update(source) {\r\n\r\n\t\t\t\t  // Compute the new tree layout.\r\n\t\t\t\t  var nodes = tree.nodes(root).reverse(),\r\n\t\t\t\t   links = tree.links(nodes);\r\n\r\n\t\t\t\t  // Normalize for fixed-depth.\r\n\t\t\t\t  nodes.forEach(function(d) { d.y = d.depth * 180; });\r\n\r\n\t\t\t\t  // Declare the nodes\r\n\t\t\t\t  var node = svg.selectAll(\"g.node\")\r\n\t\t\t\t   .data(nodes, function(d) { return d.id || (d.id = ++i); });\r\n\r\n\t\t\t\t  // Enter the nodes.\r\n\t\t\t\t  var nodeEnter = node.enter().append(\"g\")\r\n\t\t\t\t   .attr(\"class\", \"node\")\r\n\t\t\t\t   .attr(\"transform\", function(d) { \r\n\t\t\t\t\treturn \"translate(\" + d.y + \",\" + d.x + \")\"; });\r\n\t\t\t\t  \r\n\t\t\t\t\tnodeEnter.append(\"circle\")\r\n\t\t\t\t\t\t.attr(\"r\", function(d) { return d.value; })\r\n\t\t\t\t\t\t.style(\"stroke\", function(d) { return d.type; })\r\n\t\t\t\t\t\t.style(\"fill\", function(d) { return d.level; });\r\n\r\n\r\n\t\t\t\t  nodeEnter.append(\"text\")\r\n\t\t\t\t\t.attr(\"x\", function(d) { \r\n\t\t\t\t\treturn d.children || d._children ? (d.value + 4) * -1 : d.value + 4 })\r\n\t\t\t\t   .attr(\"dy\", \".35em\")\r\n\t\t\t\t   .attr(\"text-anchor\", function(d) { \r\n\t\t\t\t\treturn d.children || d._children ? \"end\" : \"start\"; })\r\n\t\t\t\t   .text(function(d) { return d.name; })\r\n\t\t\t\t   .style(\"fill-opacity\", 1);\r\n\r\n\t\t\t\t  // Declare the links\r\n\t\t\t\t  var link = svg.selectAll(\"path.link\")\r\n\t\t\t\t   .data(links, function(d) { return d.target.id; });\r\n\r\n\t\t\t\t  // Enter the links.  \r\n\t\t\t\t   link.enter().insert(\"path\", \"g\")\r\n\t\t\t\t   .attr(\"class\", \"link\")\r\n\t\t\t\t   .style(\"stroke\", function(d) { return d.target.level; })\r\n\t\t\t\t   .attr(\"d\", diagonal);\r\n\r\n\t\t\t\t};\t\t\t\t\r\n\t\r\n  }); // Close d3.csv"}
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



### Tree Chart

<span style="color: #ff0000;"><em><strong>Tree Chart ( Red format is not shown)</strong></em></span> header 

<link type="text/css" rel="Stylesheet" href='http://openknowledge.ie/wp-content/uploads/2014/07/tree.css' />

<div class="wpd3-782-0">
</div>