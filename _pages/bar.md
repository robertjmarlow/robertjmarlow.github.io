---
permalink: /bar/
---

|Body Type|Color|Twanginess|Heaviness|Best For...|
|---------|-----|----------|---------|-----------|
{% for guitar in site.data.guitars %}{{ guitar.body }}|{{ guitar.color }}|{{ guitar.twanginess }}|{{ guitar.heaviness }}|{{ guitar.best-for }}
{% endfor %}
