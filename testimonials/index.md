---
layout: page
title: Testimonials
menu: 
  header:
    weight: 8
---

<style>
  .testimonial-details {
    display: none;
  }

  .testimonial-author:hover + .testimonial-details {
    display: block;
  }
</style>

{% assign testimonials = site.data.testimonials %}

{% for testimonial in testimonials %}
  <div class="testimonial">
    <img src="{{ testimonial.image }}" alt="{{ testimonial.author }}" width="100px"/>
    <p>
      {{ testimonial.author }} ({{ testimonial.book }})      
      <br>
      "{{ testimonial.intro }}" <a class="testimonial-author" href="#">Read more...</a>
    </p>
    <p class="testimonial-details">
      {{ testimonial.details }}
    </p>
  </div>
{% endfor %}
