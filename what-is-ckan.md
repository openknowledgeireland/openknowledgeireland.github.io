---
id: 44
title: What is CKAN?
date: 2013-10-09T14:23:58+00:00
author: Eugene Eichelberger
layout: page
guid: http://www.opendata.ie/?page_id=44
layout_key:
  - 
post_slider_check_key:
  - 0
---
CKAN — an abbreviation for “Comprehensive Knowledge Archive Network”, which does not exactly describe its actual use-cases today — is an open-source (_check_) web platform for publishing and sharing data. Written in Python, it offers a simple, nice looking, and very friendly user interface (_check_) and provides by default a RDF metadata representation for each dataset (_check_). The feature that, in our view, makes CKAN really outstanding is its API, which allows access to nearly every function of the system including writing and deleting of datasets (_check_; more on that later).

CKAN has [many, many more features](http://ckan.org/features/) that could be listed here, including harvesting, data visualisation and preview, full-text and fuzzy search, and faceting. It is widely used, mainly in the field of open government data, where it has become a de facto standard software package. CKAN powers the national open data portals of the [UK](http://data.gov.uk/), the [USA](http://www.data.gov/), [Australia,](http://data.gov.au/) the [EU](http://open-data.europa.eu/), or [Ireland](http://data.gov.ie), to name only a few well-known examples. The CKAN website has an [impressive list with all known production instances](http://ckan.org/instances/).

The very active development of CKAN is led and organised by the [Open Knowledge Foundation (OKF](http://okfn.org/)). There are around ten people at OKF who are mainly [working on CKAN](http://okfn.org/about/team/), most of them developers, and in addition at least 30-40 developers are [contributing actively](https://github.com/okfn/ckan/graphs/contributors).

If you want to contribute to CKAN or develop an extension you should subscribe to the [developer mailing list](http://lists.okfn.org/mailman/listinfo/ckan-dev). There’s also a [general discussion list](http://lists.okfn.org/mailman/listinfo/ckan-discuss), and if you want to use CKAN for research data management (and in the end that’s what this article is all about) please immediately subscribe to the quite newly established and already mentioned list [ckan4rdm](http://lists.okfn.org/mailman/listinfo/ckan4rdm).

CKAN’s source code can be found at [github](http://https//github.com/okfn/ckan). It is written very cleanly (forced by clear [coding standards](http://docs.ckan.org/en/latest/contributing.html#coding-standards)). As a reasonably experienced Python developer you won’t have major difficulties in understanding the code.

If you just want to test the front end, i.e. the user interface of CKAN, you don’t have to install it yourself. OKF is running the public open data portal [datahub.io](http://datahub.io/), where you can register and upload data. The portal is not only for testing purposes. For example, all the [RDF data of the Linked Data cloud](http://datahub.io/group/lld) is registered there. There’s also a ‘pure’ [demo site](http://demo.ckan.org/) that gives you a first impression.

However, if you’re really considering CKAN to power your open data portal you should of course install it yourself.

&#8211; See more at: http://ckan.org/2013/09/25/edawax/#sthash.Uc8w6Pds.dpuf

&nbsp;

EXCERPT FROM: <http://ckan.org/2013/09/25/edawax/>