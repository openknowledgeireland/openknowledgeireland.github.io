---
id: 805
title: Outcomes from Charity Data hackDay 26-7-2014
date: 2014-07-19T14:27:06+00:00
author: Adrian Corcoran
layout: page
guid: http://openknowledge.ie/?page_id=805
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
  <li style="float: left; display: inline; padding-right: 20px;">
    <a href="chy-12-2">(2) Income</a>
  </li>
  <li style="float: left; display: inline; padding-right: 20px;">
    <a href="chy-15">(3) Expenditure</a>
  </li>
  <li style="float: left; display: inline; padding-right: 20px; background-color: #ffffcc;">
    <a href="chy-01-charity">(4) Datasets (Open Data)</a>
  </li>
  <li style="float: left; display: inline; padding-right: 20px;">
    <a href="sample-visualisations">(5) Sample Visualisations</a>
  </li>
  <li style="float: left; display: inline; padding-right: 20px;">
    <a href="chy-12">(6) Future Website</a>
  </li>
</ul>

* * *

## Welcome to the Charity Open Data Page

# Charity Datasets

The following  &#8220;_Open Data_&#8221; compliant datasets are proposed.

**Datasets:**

  1. ds01\_charity\_summary                   :  <a href="https://docs.google.com/document/d/14rmhlEgdfolXyJASAe-X-mg8Tr4LMrhyUHH5M-kBjOU/pub" target="_blank">Methodology</a>,             Links to Data  <a href="https://docs.google.com/spreadsheets/d/1R0QgwdpDK6_KZLz2i20zc-EwSo4OgBiI0nCRQawixI0/export?gid=1237917342&format=tsv" target="_blank">TSV</a> , <a href="https://docs.google.com/spreadsheets/d/1R0QgwdpDK6_KZLz2i20zc-EwSo4OgBiI0nCRQawixI0/export?gid=1237917342&format=csv" target="_blank">CSV</a>, <a href="https://docs.google.com/spreadsheets/d/1R0QgwdpDK6_KZLz2i20zc-EwSo4OgBiI0nCRQawixI0/export?gid=1237917342&format=xlsx" target="_blank">EXCEL</a>
  2. ds02\_charity\_2012_expenditure :  <a href="https://docs.google.com/document/d/14rmhlEgdfolXyJASAe-X-mg8Tr4LMrhyUHH5M-kBjOU/pub" target="_blank">Methodology</a>,              Links to Data  <a href="https://docs.google.com/spreadsheets/d/1R0QgwdpDK6_KZLz2i20zc-EwSo4OgBiI0nCRQawixI0/export?gid=931706284&format=tsv" target="_blank">TSV</a> , <a href="https://docs.google.com/spreadsheets/d/1R0QgwdpDK6_KZLz2i20zc-EwSo4OgBiI0nCRQawixI0/export?gid=931706284&format=csv" target="_blank">CSV</a>, <a href="https://docs.google.com/spreadsheets/d/1R0QgwdpDK6_KZLz2i20zc-EwSo4OgBiI0nCRQawixI0/export?gid=931706284&format=xlsx" target="_blank">EXCEL</a>

&nbsp;

You can download these Datasets directly into Excel/Google Fusion Tables and being exploring the information.

External Datasets which may be relevant include:

  1. <a href="http://www.revenue.ie/en/about/publications/charities_alpha.xls" target="_blank">Revenue &#8211; Register of Charities</a> (format Excel, contains charity number, official name and address)

* * *

&nbsp;

##  Appendix A. Data Extraction,Transformation and Load

### A.1 Dimensions

Tables that are used to  filter queries and to select data.

  * <a href="https://docs.google.com/spreadsheets/d/1sIH9NKBkpQMFMnt_0sYW9B8DSyv839EbbtLmibdml1s/pubhtml" target="_blank">Charity</a> :  &#8211; charity register & categorization
  * <a href="https://docs.google.com/spreadsheets/d/1sIH9NKBkpQMFMnt_0sYW9B8DSyv839EbbtLmibdml1s/edit#gid=861039018" target="_blank">Expenditure Codes </a>: &#8211; chart of accounts for expenditure.

### A.2 Measures

Tables  that list things we want to measure about the charity.

  *  things that we can compare charities across, forms the basis for rating.

### A.3 Facts ( <span style="text-decoration: underline;">This is where we need your help  !!</span>)

**Instructions**

  1. Please download the following Excel file to your computer  <a href="https://drive.google.com/?tab=wo&authuser=0#folders/0BwvqlbZTmJr6T2FOdWpFRzBUeVE" target="_blank">CharityFinancialData.xsln</a>
  2. Look at the example on the &#8220;Concern&#8221; sheet. &#8211; notice how the data is aligned in a highlighted table.
  3. Adopt your charity &#8211; select from Red/Green/Blue
  4. Format your sheets data
  5. Copy the table of data to a new excel file.
  6. Email it as an attachment to openknowledgeireland@gmail.com

All of your data will be loaded into the Charity_Fact table and processed to build our datasets.