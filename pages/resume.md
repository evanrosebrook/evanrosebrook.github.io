---
layout: page
title: Resume
permalink: /resume/
---

{% assign basics = site.data.resume.basics %}


## {{ basics.name }}
[{{ basics.website }}](https://{{ basics.website }})  
![email address]({{site.baseurl}}/assets/images/email.png)

{{ basics.summary }}

---
## Skills
{% for section in site.data.resume.skills %}
**{{ section.name }}:**
{{ section.keywords | array_to_sentence_string: "" }}
{% endfor %}
---
## Experience

{% for job in site.data.resume.work %}

**{{ job.position }}**, {{ job.company }}  
*{{ job.startDate | date: '%m/%Y' }} - {{ job.endDate | date: '%m/%Y' | default: "Present" }}*  
{{job.summary}}
{% for item in job.highlights %}
* {{ item }}
{% endfor %}
{% endfor %}
---
## Education
{% for edu in site.data.resume.education %}
**{{ edu.area }}**, {{ edu.institution }}, {{ edu.endDate | date: '%Y' }}
{% endfor %}
