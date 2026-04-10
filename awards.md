---
layout: default
title: Awards
permalink: /awards/
---

<div class="awards-page">
    <h1>Awards & Recognition</h1>

    <div class="awards-list" style="margin-top: 2rem;">
        {% if site.awards %}
            {% assign awards = site.awards | sort: "year" | reverse %}
            {% for award in awards %}
            <article class="award-card" style="margin-bottom: 2rem; padding: 1.5rem; border: 1px solid #ddd; border-radius: 4px;">
                <h3 style="margin-bottom: 0.5rem;">
                    <a href="{{ award.url | relative_url }}">{{ award.title }}</a>
                </h3>
                {% if award.year %}
                    <p style="margin: 0.25rem 0; color: #666;">
                        <strong>Year:</strong> {{ award.year }}
                    </p>
                {% endif %}
                {% if award.category %}
                    <p style="margin: 0.25rem 0; color: #666;">
                        <strong>Category:</strong> {{ award.category }}
                    </p>
                {% endif %}
                
                {% assign award_pubs = site.publications | where_exp: "pub", "pub.awards contains award.award_id" %}
                {% if award_pubs.size > 0 %}
                    <p style="margin-top: 0.75rem; color: #555;">
                        <strong>Recipient Publications:</strong>
                        <ul style="margin: 0.5rem 0 0 0;">
                            {% for pub in award_pubs %}
                                <li><a href="{{ pub.url | relative_url }}">{{ pub.title }}</a></li>
                            {% endfor %}
                        </ul>
                    </p>
                {% endif %}
            </article>
        {% endfor %}
        {% else %}
            <p style="color: #666; font-style: italic;">No awards to display yet.</p>
        {% endif %}
    </div>
</div>
