---
id: 1577
title: 'Ireland&#8217;s Hospital Waiting List'
date: 2015-09-04T11:01:38+00:00
author: Dan Alexandru Bujoreanu
layout: post
guid: http://openknowledge.ie/?p=1577
permalink: /irelands-hospital-waiting-list/
categories:
  - Uncategorized
tags:
  - '#OpenDataIRL'
  - Adrian Corcoran
  - Dan Alexandru Bujoreanu
  - healthcare
  - hospital waiting list
  - Ireland
  - Leo Varadkar
  - Linked Data
  - Richard Corbridge
---
Here is the live interactive <a href="https://public.tableau.com/views/OpenHospitalWaitingList/HospitalsWaitingList?:embed=y&:display_count=yes&:showTabs=y" target="_blank" rel="nofollow">Dashboard</a> showing the Patients Waiting times per Specialties for each Hospital in Ireland. It gives a better understanding over the Irish Health system and can definitely help patient management before and after enrolling for their procedure. Imagine having this overview when booking the appointment with your GP/ Consultant. With most procedures related to Outpatients, this means you can walk out of the Hospital same day. It could potentially save you important months of waiting.

To mention first, this is an ongoing dashboard I&#8217;ve created part of a bigger project led by <a href="https://www.linkedin.com/company/5205156?trk=tyah&trkInfo=clickedVertical%3Acompany%2CclickedEntityId%3A5205156%2Cidx%3A2-3-4%2CtarId%3A1441218625442%2Ctas%3Aopen%20knowledg" target="_blank">Open Knowledge Ireland</a> which consists in gathering all data from <a href="http://www.ntpf.ie/home/home.htm" target="_blank" rel="nofollow">National Treatment Purchase Fund (NTPF)</a> website (currently stored as .pdfs), and converting it to readable and open format.

Back to the dashboard. The story is organized in 3 tabs:

### **1.   Overview of Inpatients and Outpatients across all Hospitals/ Specialties:**

<a href="https://public.tableau.com/views/OpenHospitalWaitingList/HospitalsWaitingList?:embed=y&:display_count=yes&:showTabs=y" target="_blank" rel="nofollow"><img class="center" src="https://media.licdn.com/mpr/mpr/shrinknp_800_800/AAEAAQAAAAAAAAXcAAAAJGE4YzQ1YzQ3LWQ1N2YtNDEzYi04NGRhLWRlMzgyNDA1MWIxYg.jpg" alt="" width="640" height="553" data-loading-tracked="true" /></a>

  * There are 4 charts showing: Specialties by waiting times, Patient type (In/Out) for each specialty, Hospitals breakdown and overall waiting times.
  * By default report will load with Top 10 records but you can extend this up to Top 30 (recommended is maximum top 20 records). If you&#8217;re interested in a particular Hospital/ Specialty overview, you can use the dropdowns on the right side.
  * You can click on any charts and data will be displayed accordingly across the dashboard.

### **2.   Hospital Group Status:**

<a href="https://public.tableau.com/shared/R26X6K6T7?:display_count=yes" target="_blank" rel="nofollow"><img class="center" src="https://media.licdn.com/mpr/mpr/shrinknp_800_800/AAEAAQAAAAAAAAU3AAAAJDU3NWExMDFjLWMzNzQtNDY1Yi04ZTZiLWYwMTk4YzBkY2E1Mw.jpg" alt="" width="640" height="567" data-loading-tracked="true" /></a>

  * **Group Status** chart displays the trend for last 13 weeks for different Hospitals Groups and Metrics. You will notice some of the selections return no data, as there is no information available.
  * **Bed capacity** shows only Group/ Hospitals with available info. Data is retrieved from Wikipedia and links are clickable if you need to find more info.
  * **Map overview **&#8211; a quick visualization of all Hospitals color grouped by Hospital Group.
  * All charts are connected

### 3.   **Specialties &#8211; in-depth overview:**

<a href="https://public.tableau.com/shared/CBR2MGT5Q?:display_count=yes" target="_blank" rel="nofollow"><strong><img class="center" src="https://media.licdn.com/mpr/mpr/shrinknp_800_800/AAEAAQAAAAAAAAZEAAAAJDg4NjdlNjk4LTcyYzctNDRlMy05MjEwLTlhYjM4M2NmMzZhNA.jpg" alt="" width="640" height="568" data-loading-tracked="true" /></strong></a>

  * **Specialty% of Total **&#8211; the percentage of patients across all waiting periods
  * **#Patients per Wait period **&#8211; a similar view but showing the number of patients instead of %.

&nbsp;

While this is the first draft, it gives you a glimpse at the Hospital Waiting lists and answers few questions around waiting times. However, there is a lot more work to be done in promoting open data that could potentially impact patient lives. You can share the attached dashboard by using the following link:

<a href="https://public.tableau.com/views/OpenHospitalWaitingList/HospitalsWaitingList?:embed=y&:display_count=yes&:showTabs=y" target="_blank" rel="nofollow">https://public.tableau.com/views/OpenHospitalWaitingList/HospitalsWaitingList?:embed=y&:display_count=yes&:showTabs=y</a>

Thanks to <a href="http://openknowledge.ie/projects/open-hospital-waiting-list/" target="_blank" rel="nofollow">Open Knowledge Ireland</a> team and to Adrian Corcoran for making this data available.

Author: <a href="https://ie.linkedin.com/in/danbujoreanu" target="_blank">Dan Alexandru Bujoreanu</a>

Hospital Waiting List Project page: <a href="http://openknowledge.ie/projects/open-hospital-waiting-list/" target="_blank">http://openknowledge.ie/projects/open-hospital-waiting-list/</a>

Linked Hospital Waiting List Data: <a href="https://github.com/openknowledgeireland/DataStore/blob/master/HospitalWaitingList/NTPF_Datasets%20-%20Linked_Hospital.csv" target="_blank">https://github.com/openknowledgeireland/DataStore/blob/master/HospitalWaitingList/NTPF_Datasets%20-%20Linked_Hospital.csv</a>