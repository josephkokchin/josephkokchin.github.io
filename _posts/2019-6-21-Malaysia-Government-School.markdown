---
layout: post
title: "Data Viz: Malaysia Government School"
date: 2019-06-21 19:50
published: true
image: 
headerImage: false
tag:
- Tableau
- Data Viz
- Python
- Notebook
category: blog
author: josephkchin
description: "A Quick Look at the School Distribution across States in Malaysia"
---

![]({{ site.baseurl }}/images/sekolahmalaysia-min.jpg)

The purpose of this dashboard is to discover the density and proximity of government schools across different states in Malaysia.The data is sourced from the Malaysian government website which was last updated in June 2019.


I have carried out the data cleaning part using Python and the you can referred to the detail walkthrough in the following notebook.


<script src="https://gist.github.com/josephkokchin/edcdbec18206406af7bb3ea814a68edf.js"></script>


Now you have finish reading the data cleaning section, you can play around with the interactive dashboard.


<!-- Tableau embeded -->

<div class='tableauPlaceholder' id='viz1562653717005' style='position: relative'><noscript><a href='https:&#47;&#47;github.com&#47;josephkokchin&#47;Malaysia-Schools-Dashboard'><img alt=' '
        src='https:&#47;&#47;public.tableau.com&#47;static&#47;images&#47;Ma&#47;MalaysiaGovernmentSchool&#47;Dashboard1&#47;1_rss.png' style='border: none' /></a></noscript><object class='tableauViz' style='display:none;'>
    <param name='host_url' value='https%3A%2F%2Fpublic.tableau.com%2F' />
    <param name='embed_code_version' value='3' />
    <param name='path' value='views&#47;MalaysiaGovernmentSchool&#47;Dashboard1?:embed=y&amp;:display_count=y' />
    <param name='toolbar' value='yes' />
    <param name='static_image' value='https:&#47;&#47;public.tableau.com&#47;static&#47;images&#47;Ma&#47;MalaysiaGovernmentSchool&#47;Dashboard1&#47;1.png' />
    <param name='animate_transition' value='yes' />
    <param name='display_static_image' value='yes' />
    <param name='display_spinner' value='yes' />
    <param name='display_overlay' value='yes' />
    <param name='display_count' value='yes' /></object></div>
<script type='text/javascript'>
  var divElement = document.getElementById('viz1562653717005');
  var vizElement = divElement.getElementsByTagName('object')[0];
  if (divElement.offsetWidth > 800) {
    vizElement.style.width = '1000px';
    vizElement.style.height = '827px';
  } else if (divElement.offsetWidth > 500) {
    vizElement.style.width = '1000px';
    vizElement.style.height = '827px';
  } else {
    vizElement.style.width = '100%';
    vizElement.style.height = '1127px';
  }
  var scriptElement = document.createElement('script');
  scriptElement.src = 'https://public.tableau.com/javascripts/api/viz_v1.js';
  vizElement.parentNode.insertBefore(scriptElement, vizElement);
</script>

<!-- Tableau End -->

Lastly, happy crunching data ! Feel free to get in touch with me if you have any questions or interesting projects to discuss.
