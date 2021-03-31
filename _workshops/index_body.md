<p>I offer a variety of virtual, live workshops that will help you develop your reproducible research skills. Below is a listing of the upcoming workshops with links to details and information on costs and how to register.</p>

<ul>

{% for w in site.workshops %}

{% if w.layout == "workshop" and w.status == "live" %}
<li>
<p><a href="{{w.url}}">{{ w.topic }}</a> ({{w.dates}})</p>
</li>
{% endif %}

{% endfor %}
</ul>
