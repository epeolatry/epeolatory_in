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
</style>

{% assign testimonials = site.data.testimonials %}

<div class="testimonials-container">
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
</div>

<script>
  var readMoreLinks = document.querySelectorAll(".testimonial-author");

  readMoreLinks.forEach(function(link) {
    link.addEventListener("click", function(e) {
      e.preventDefault();
      var details = link.nextElementSibling;
      if (details.style.display === "block" || details.style.display === "")
        details.style.display = "none";
      else
        details.style.display = "block";
    });
  });
</script>
