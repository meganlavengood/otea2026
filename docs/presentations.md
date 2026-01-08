---
layout: page
title: "Presentations"
menu: false
order: 5
permalink: /presentations/
---

In 2023, I started making my presentations using [Reveal.js](https://revealjs.com), so you can view the slides as a website. You can view more complete lists of my presentations on my [Research](/research) and [CV](/cv) pages.

<div class="row justify-content-around g-4 mb-3" id="presentations-list">

    {% assign talks = site.data.research | where: "type", "presentation" %}

    {% for item in talks %}
    <div class="col-md-6">
        <div class="card">
            <img src="{{site.baseurl}}/assets/{{ item.img }}" class="card-img-top" alt="{{ item.alt }}" />
            {% if item.credit %}
            <div class="text-secondary text-end img-att">{{ item.credit }}</div>
            {% endif %}
            <div class="card-body">

                <h3 class="card-title h5" id="{{ item.id }}">{{ item.title }}</h3>
                <div class="card-text">
                    {% if item.note %}

                    <p>{{ item.note }}</p>
                    {% endif %}

                    <p>Presented at {% if item.conf-link %}<a class="text-dark" href="{{ item.conf-link }}">{% endif %}{{ item.conf }}{% if item.conf-link %}</a>{% endif %}, {{ item.year }}.</p>
                    {% if item.link %}
                    <div class="text-center">
                        <a class="btn btn-primary" href="{{ item.link }}" target="_blank" rel="noopener noreferrer">
                            <i class="bi bi-unlock2-fill"></i> view presentation
                        </a>
                    </div>
                    {% endif %}

                </div>
            </div>
        </div>
    </div>

    {% endfor %}

</div>
