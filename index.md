---
layout: default
---
<script src="assets/global/anchor.min.js"></script>
<script src="assets/global/jquery-3.6.4.min.js"></script>

<script>
  $(function() {
	anchors.options.icon = '🔗';
	anchors.options.placement = 'left';
	anchors.options.visible = 'hover';
	anchors.add('section');
});
</script>

This is a collection of humorous quotes from
scientific and technical talks, classes, etc. that I've attended.

*Note: One of the ground rules for this collection is that I had to
witness the event.  I'm not looking for outside submissions.
Consider starting your own list.*

As you may infer from the significant number of quotes from a single
source, this collection started with a professor from my undergraduate
days, who had a penchant for quotable comments in his lectures. We
students started writing down these quotes, and at the end of the
semester, we typed them up and gave him a copy.  He seemed to enjoy it
(he put it on his office door), and so did we.  

Ever since then, I've been trying to take note of the humor in things
that can often be rather dry.  And now, I'm posting it on the virtual
equivalent of my office door. (The real thing is too covered with
cartoons to have room for all of this anyway.)

Note that every quote has an HTML id attribute, allowing you to link
directly to a specific quote if you want to.  Just hover your mouse
over the beginning of the quote and a link symbol (🔗) should appear.
You can copy the link address, or you can click on it to jump to the
particular link in your browser.

And thanks to my colleague Sarat Sreepathi for motivating me to get
this back online, after a long hiatus.

So, enjoy...

<hr style="width:50%; margin-left:auto; margin-right:auto">

{% for quote in site.quotes reversed %}

{% capture seqnum %}{{ quote.path | remove: "_quotes/" | remove: ".md" }}{% endcapture %}

<section id="{{ seqnum }}" style="margin-top:1em">
{{ quote.content | markdownify }}

<p style="margin-top:0; margin-left:33%;">
  <em>{{ quote.source }}{% if quote.context != nil %}, {{ quote.context }}{% endif %}{% if quote.quotedate != nil %}, {{quote.quotedate }}{% elsif quote.date != nil %}, {{ quote.date | date: "%B %Y" }}{% endif %}
</em></p>

{% if forloop.last == false %}
  <hr style="width:50%; margin-left:auto; margin-right:auto">
{% endif %}

</section>

{% endfor %}
