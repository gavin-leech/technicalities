---
layout: 	page
title: 		Posts by importance
permalink: 	/importance/

visible:  false
---

{% 		assign endow = "https://arbital.com/p/cosmic_endowment"			%}
{% 		assign g = "https://www.gwern.net/About#importance-tags"	%}


<br>I put an "importance" score on my posts: this weights the _topic_ of the post.<a href="#fn:1" id="fnref:1">1</a> The scale goes from 1 ("_applies only to Gavin's life_") to 10 ("_<a href="{{endow}}">applies to the entire possible future of all life</a>_"). So it's superexponential: a "10" is on a topic much more than a trillion times more important than a "2". 

Anything "4" or above _could_ affect your life, might be something you should know, as a generally optimising or curious or altruistic person.

It is an enduring mystery to me why my interest in a topic is not more correlated with my own estimate of its importance. ¯\\\_(ツ)\_/¯
<br><br>

<div class="home">
	{% for importance in (1..10) reversed %}
		<hr /><br>
		<h1 class="spaced">{{ importance }}</h1>
	    <table class="post-list">
			{% for post in site.posts %}
	  			<!-- % unless forloop.first %}</table>% endunless %} -->
	  			{% if importance == post.importance %}
					<!--  -->
					<tr class="spaced">
	          			<td style="width:55%;">
	          				<a class="archive-link" href="{{ post.url | prepend: site.baseurl }}"> 
	          					> {{ post.title }}
	          				</a>
	          			</td>
	          		</tr>
					<!--  -->
	  			{% 	endif 	%}
	  			{% if forloop.last %}</table>{% endif %}
			{% endfor %}
	{% endfor %}
</div>

<br><br>




<div class="footnotes">
<ol>
	<li class="footnote" id="fn:1">
		I stole the idea from <a href="{{g}}">Gwern</a>.
	</li>
</ol>
</div>