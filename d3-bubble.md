---
id: 796
title: d3 bubble
date: 2014-07-18T23:00:58+00:00
author: Adrian Corcoran
layout: page
guid: http://openknowledge.ie/?page_id=796
wpd3-796-0:
  - |
    {"includes":["/wp-content/uploads/2014/07/bubble.css"],"code":"var diameter = 800,\n    format = d3.format(\",d\");\n\nvar pack = d3.layout.pack()\n    .size([diameter - 4, diameter - 4])\n    .value(function(d) { return d.size; });\n\nvar svg = d3.select(\".wpd3-796-0\").append(\"svg\")\n    .attr(\"width\", diameter)\n    .attr(\"height\", diameter)\n  .append(\"g\")\n    .attr(\"transform\", \"translate(2,2)\");\n//----------------------------------\nd3.tsv(\"/wp-content/uploads/2014/07/tree.csv\", function(error, data) {\n\t// 1.2 create a name-based map for the nodes\n\t\tvar dataMap = data.reduce(function(map, node) {\n\t\t\t\tmap[node.name] = node;\n\t\t\t\treturn map;\n\t\t\t}, {});\n//\t\t\talert('name-based map'+JSON.stringify(dataMap));\n\t\t\t\n\t// 1.3 iteratively add each child to its parents, or to the root array if no parent is found\n\t\t\t\tvar treeData = [];\n\t\t\t\tdata.forEach(function(node) {\n\t\t\t\t // add to parent\n\t\t\t\t var parent = dataMap[node.parent];\n\t\t\t\t if (parent) {\n\t\t\t\t  // create child array if it doesn't exist\n\t\t\t\t  (parent.children || (parent.children = []))\n\t\t\t\t   // add node to child array\n\t\t\t\t   .push(node);\n\t\t\t\t } else {\n\t\t\t\t  // parent is null or missing\n\t\t\t\t  treeData.push(node);\n\t\t\t\t }\n\t\t\t\t});\n\t//  1.4 Confirm TreeData is in the correct format\n\t//\t\t\talert(JSON.stringify(treeData));\n//\t$(\"#ac\").html(JSON.stringify(treeData[0]));\n\n  var node = svg.datum(treeData[0]).selectAll(\".node\")\n      .data(pack.nodes)\n    .enter().append(\"g\")\n      .attr(\"class\", function(d) { return d.children ? \"node\" : \"leaf node\"; })\n      .attr(\"transform\", function(d) { return \"translate(\" + d.x + \",\" + d.y + \")\"; });\n  node.append(\"title\")\n      .text(function(d) { return d.name + (d.children ? \"\" : \": \" + format(d.size)); });\n  node.append(\"circle\")\n      .attr(\"r\", function(d) { return d.r; });\n  node.filter(function(d) { return !d.children; }).append(\"text\")\n      .attr(\"dy\", \".3em\")\n      .style(\"text-anchor\", \"middle\")\n      .text(function(d) { return d.name.substring(0, d.r / 3); });\n//});\n\nd3.select(self.frameElement).style(\"height\", diameter + \"px\");\n\n});\n\n"}
infinite_meta_show_sidebar:
  - Yes
infinite_meta_show_flex_slideshow:
  - Yes
infinite_meta_show_title:
  - Yes
---
### Bubble Chart

<link type="text/css" rel="Stylesheet" href='http://openknowledge.ie/wp-content/uploads/2014/07/bubble.css' />

<div class="wpd3-796-0">
</div>

###