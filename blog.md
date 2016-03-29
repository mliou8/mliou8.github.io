---
layout: page
permalink: /blog
---

<div class="posts">
{% for post in site.posts limit:10 %}
	<div class="post-preview">
		<h2><a href="{{ site.baseurl }}{{ post.url }}">{{ post.title }}</a></h2>
		<div class="post-date">{{ post.date | date: "%B %d, %Y" }}</div>
		{{ post.content | split:'<!--break-->' | first }}
		{% if post.content contains '<!--break-->' %}
			<a href="{{ site.baseurl }}{{ post.url }}">read more</a>
		{% endif %}
	</div>
	<hr>
	{% endfor %}
</div>

