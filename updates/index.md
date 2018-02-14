---
layout: default
category: posts
title: Updates
---
<div class="index">

	<h2>{{ page.title }}</h2>

	<p>Data science, reproducible research, omics are all hot areas in science and microbiology right now. We'll do our best to flag articles and opportunities that touch on these areas and provide some color commentary about the issues they raise.</p>

	<ul>
	  {% for post in site.posts %}
			<li>
				<div class="title">{{ post.title }}</div>
				<p class="meta">{{ post.date | date: "%b %-d, %Y" }}{% if post.author %} • {{ post.author }}{% endif %}</p>
				<div class="content">
						{{ post.excerpt | remove: '</p>' }}
						<a class="read-more" href="{{ post.url | prepend: site.baseurl }}">Read more...</a></p>
				</div>
			</li>
	  {% endfor %}
	</ul>


</div>
