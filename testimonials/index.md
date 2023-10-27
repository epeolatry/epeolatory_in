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
        "{{ testimonial.intro }}"
      </p>
      <p class="testimonial-details">
        {{ testimonial.details }}
      </p>
      <a class="testimonial-author" href="#">Read more...</a>
    </div>
  {% endfor %}
</div>

<script>
  var readMoreLinks = document.querySelectorAll(".testimonial-author");

  readMoreLinks.forEach(function(link) {
    link.addEventListener("click", function(e) {
      e.preventDefault();
      var details = link.previousElementSibling.nextElementSibling;
      details.style.display = details.style.display === "block" || details.style.display === "" ? "none" : "block";
    });
  });
</script>
