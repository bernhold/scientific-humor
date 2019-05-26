---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: home
---
This is a collection of humorous quotes from
scientific and technical talks, classes, etc. that I've attended.

*Note: One of the ground rules for this collection is that I had to
witness the event.  I'm not looking for outside sumbmissions.
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

And thanks to my colleague Sarat Sreepathi for motivating me to get
this back online, after a long hiatus.

So, enjoy...

<hr style="width:50%; margin-left:auto; margin-right:auto">

{% for quote in site.quotes reversed %}

<section style="margin-top:1em">

{{ quote.content | markdownify }}

<p style="margin-top:0; margin-left:33%;">
  <em>{{ quote.source }}{% if quote.context != nil %}, {{ quote.context }}{% endif %}{% if quote.date != nil %}, {{ quote.date | date: "%B %Y" }}{% elsif quote.quotedate != nil %}, {{ quote.quotedate }}{% endif %}
</em></p>

{% if forloop.last == false %}
  <hr style="width:50%; margin-left:auto; margin-right:auto">
{% endif %}

</section>

{% endfor %}
