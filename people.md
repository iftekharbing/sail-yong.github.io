---
title: People
permalink: /people/
---

{% assign people_sorted = site.people | sort: 'joined' %}
{% assign role_array = "pi|postdoc|gradstudent|researchstaff|visiting|others|alumni" | split: "|" %}

{% for role in role_array %}

{% assign people_in_role = people_sorted | where: 'position', role %}

<!-- Skip section if there's nobody -->
{% if people_in_role.size == 0 %}
  {% continue %}
{% endif %}

<div class="pos_header">
{% if role == 'postdoc' %}
<h3>Postdoctoral Fellows</h3>
 {% elsif role == 'pi' %}
<h3>Principal Investigator</h3>
 {% elsif role == 'gradstudent' %}
<h3>Graduate Students</h3>
 {% elsif role == 'researchstaff' %}
<h3>Research Staff</h3>
 {% elsif role == 'visiting' %}
<h3>Visiting Scholars</h3>
 {% elsif role == 'others' %}
<h3>Honorary Members</h3>
 {% elsif role == 'alumni' %}
<h3>Alumni</h3>
{% endif %}
</div>

{% if role != 'alumni' %}
<div class="content list people">
  {% for profile in people_sorted %}
    {% if profile.position contains role %}
      <div class="list-item-people">
        <p class="list-post-title">
          {% if profile.avatar %}
            <a href="{{ site.baseurl }}{{ profile.url }}"><img class="profile-thumbnail" src="{{site.baseurl}}/images/people/{{profile.avatar}}"></a>
          {% else %}
            <a href="{{ site.baseurl }}{{ profile.url }}"><img class="profile-thumbnail" src="http://evansheline.com/wp-content/uploads/2011/02/facebook-Storm-Trooper.jpg"></a>
          {% endif %}
          <a class="name" href="{{ site.baseurl }}{{ profile.url }}">{{ profile.name }}</a>
        </p>
      </div>    
    {% endif %}
  {% endfor %}
</div>
<hr>

{% else %}

<br>

| Who are they | When were they here | Where they went |
| :------------- |:-------------| :-----------|
| Eric Cadalzo | MS student (2023-2024) |  |
| Priscilla Pomerantz | MS student (2023-2024) | |
| [Justin Reicher](https://www.linkedin.com/in/justin-reicher) | Undergraduate researcher (2023-2024) | Systems engineer at L3Harris |
| Javier Guadalupe | Undergraduate researcher (2023-2024) | Senior at Binghamton University |
| Kyra Cheung | Visiting high school researcher (2023-2024) | Freshman at Binghamton University |
| [Hasan Al Tarify](https://www.linkedin.com/in/hasan-al-tarify?trk=public_profile_browsemap) | MS thesis student (2022-2023) | PhD student at University of Minnesota |
| [Reza Goharimerh](https://www.linkedin.com/in/reza-goharimehr-b7383b258) | PhD student (2022-2023) | PhD position at Villanova University |
| [Gottlieb Teoli](https://www.linkedin.com/in/gottlieb-teoli) | Undergraduate reseacher (2023) | Product design engineer at ITT Inc. |
| Ryan Ginley | Undergraduate researcher (2023) | MS student at Binghamton University
| [Jonathan M. Blisko](https://www.linkedin.com/in/jonathan-blisko-8aa7a9180) | Undergraduate researcher, MS student, and post-bacc reseacher (2018-2023) | MS student at University of Padova |
| Mithila Farin | Undergraduate reseacher (2020-2021) | Undergraduate at Boston University
| [Shensheng Chen](https://scholar.google.com/citations?user=rODiYsoAAAAJ&hl=en) | PhD student (2016-2020) | Postdoc at Caltech |
| [Hussein N. Dalgamoni](https://scholar.google.com/citations?user=s6FGfz4AAAAJ&hl=en) | PhD Student (2016-2019) | Assistant Professor at Hashemite University, Jordan |
| [Ao Li](https://www.linkedin.com/in/ao-li-li-ao) | MS and PhD student (2015-2019) | Software engineer at Mathworks |
| [Shiyi Qin](https://scholar.google.com.hk/citations?user=CtIGZxEAAAAJ&hl=en) | PhD student (2015-2019) | Postdoc at Northwestern University |
| [Mingfei Zhao](https://mzhao.people.ua.edu/) | PhD student (2015-2019) | Postdoc at University of Chicago
| Andy Zou | Undergraduate researcher (2018-2019)
| [Tyler F. Moy](https://www.linkedin.com/in/tylermoy)| Undergraduate researcher (2019) | |
| Adrian J. Diaz | Undergraduate researcher (2019) | MS student at Binghamton University |
| [Joseph M. Prisaznuk](https://www.linkedin.com/in/joe-prisaznuk) | Undergraduate researcher (2019) | PhD student at Binghamton University |
| Pranshu Babber | Undergraduate researcher (2019) | |
| Rebecca E. Schneider | Undergraduate researcher (2019) | |
| Tanjil S. Uddin | Undergraduate researcher (2017-2019) | MD student at NJIT |
| [Wilson Luo](https://www.linkedin.com/in/wilson-luo-67654b100) | Undergraduate researcher (2017-2019) | Systems Engineer at Lockheed Martin |
| [Chunheng Zhao](https://www.linkedin.com/in/chunheng-zhao-76b609133) | MS thesis student (2017-2018) | PhD student at CCNY |
| [Junhyunk (Andrew) Kang](https://www.linkedin.com/in/andrew-j-kang) | Undergraduate researcher (2017-2018) | PhD student at Cornell University |
| Lawrence Zhang | Undergraduate researcher (2017) | MD student at Drexel University |
| Giomar I. Condori | CSTEP summer researcher (2017) | PharmD student at Binghamton University |
| Jiamin Li | Undergraduate researcher (2016-2017) | PhD student at UIC |
| Peijun Yu | MS thesis student (2015-2016) | PhD student at City University of Hong Kong |
| Juan C. Medina | Undergraduate Researcher (2015-2016) | Engineer at Pratt & Whitney |
| Sumiao Pang | Undergraduate researcher (2015) | MS student at Binghamton University |


{% endif %}
{% endfor %}
