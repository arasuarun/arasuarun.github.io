---
layout: default
title: Home
---

I recently finished my PhD at New York University, where I was 
fortunate to be advised by [Joseph Bonneau](https://jbonneau.com/). 

My PhD work focused on building efficient zero-knowledge proofs to verify real-world systems.
My most notable project is the [Jolt](https://github.com/a16z/jolt) zero-knowledge virtual machine.

I now research verifiable computing and its applications to machine learning at Gensyn AI. 

# Publications

{% for publication in site.data.publications %}
  <p class="publication">
    <a href="{{ publication.link }}" class="publication-title">{{ publication.title }}</a><br>
    {% assign authors = publication.authors | split: ', ' %}
    {% for author in authors %}
      {% if author == "Arasu Arun" %}
        <u>{{ author }}</u>{% if forloop.last == false %},{% endif %}
      {% else %}
        {{ author }}{% if forloop.last == false %},{% endif %}
      {% endif %}
    {% endfor %}<br>
    <em>{{ publication.venue }}</em>
    {% if publication.code %}
      <br><a href="{{ publication.code }}">Code</a>
    {% endif %}
    {% if publication.talks %}
      {% for talk in publication.talks %}
        <br><a href="{{ talk }}">Talk </a>
      {% endfor %}
    {% endif %}
    {% if publication.special_description %}
      <div class="special-description">
        <p>{{ publication.special_description | markdownify }}</p>
      </div>
    {% endif %}
  </p>
{% endfor %}

# Talks

{% for talk in site.data.talks %}
  <div class="talk">
    <strong>{{ talk.title }}</strong>
    <ul>
      {% for detail in talk.talks %}
        <li>{{ detail.venue }}, {{ detail.date }} - <a href="{{ detail.link }}">Link</a></li>
      {% endfor %}
    </ul>
  </div>
{% endfor %}


# Internships

{% for internship in site.data.internships %}
  <p class="internship">
    {{ internship.institution }}, {{ internship.term }}<br>
  </p>
{% endfor %}
