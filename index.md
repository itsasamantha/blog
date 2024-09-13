# Samantha's Blog

My name is Samantha and I'm a senior in highschool. I currently attend [Medgar Evers College Preparatory School](https://www.mecps.org/) with a dual enrollment at the [Brooklyn STEAM Center](https://brooklynsteamcenter.org/). 

This is a blog dedicated to my coding projects.

<ul>
  {% for post in site.posts %}
    <li>
      <a href="{{ post.url | relative_url }}"> {{ post.title }} </a>
    </li>
  {% endfor %}
</ul>