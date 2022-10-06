---
layout: section
title: eCSE Reports - Mathematics and Computer Science 
banner: web_banners_10.jpg
tags: [Earth Sciences and Environment, Engineering and Energy, Chemistry and Materials, Mathematics and Computer Science]
---

  
<div>
Subject Areas:
{% for tag in page.tags %}
<a href="/ecse/reports/{{ tag }}" ><code  style="font-size:15px;"><nobr>{{ tag }}</nobr></code>&nbsp;</a>
{% endfor %} 
<a href="/ecse/reports/" ><code  style="font-size:15px;"><nobr>All</nobr></code>&nbsp;</a>   
</div>


{% assign current_ecse = site.ecse | where_exp: "ecse", "ecse.status != 'hidden'" %}
{% assign mcs_ecse = current_ecse | where_exp: "ecse", "ecse.subject == 'Mathematics and Computer Science'" %}

{% for ecse in mcs_ecse reversed %}



<div class="casestudy">

	<div class="csimage">
		<a href="{{ ecse.ecse }}"><img
			src="{{ ecse.image_src }}" alt="{{ ecse.image_alt }}" title="{{ ecse.image_alt }}" style="width: 200px;" /></a>
	</div>

	<div class="cstext">

		<h3>
			<a href="{{ ecse.ecse }}">{{ ecse.title }}</a>
		</h3>

		<b>
			ARCHER2-{{ ecse.ecse }} 
		</b>

 		&colon; {{ ecse.pi }} <br><br>

		Subject Area: <a href="/ecse/reports/{{ ecse.subject }}"><code class="highligher-rouge"><nobr>{{ ecse.subject }}</nobr></code>&nbsp;</a>
        {% assign pd = ecse.pub_date | date: "%Y-%m-%d" %}
		&nbsp; &nbsp; &nbsp; &nbsp;
		Published &colon; {{ pd }}    <br><br>	

		<p>
          {{ ecse.summary }}
		 
			<a href="{{ ecse.ecse }}"> Read more...</a>
		</p>

	</div>
</div>






{% endfor %}






