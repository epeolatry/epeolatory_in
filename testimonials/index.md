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

{% for testimonial in testimonials %}
  <div class="testimonial">
    <img src="{{ testimonial.image }}" alt="{{ testimonial.author }}" width="100px"/>
    <p>
      {{ testimonial.author }} ({{ testimonial.book }})      
      <br>
      "{{ testimonial.intro }}" <a class="testimonial-author" href="#">Read more...</a>
    </p>
    <p class="testimonial-details" style="display: none;">
      {{ testimonial.details }}
    </p>
  </div>
{% endfor %}

<script>
  var readMoreLinks = document.querySelectorAll(".testimonial-author");

  readMoreLinks.forEach(function(link) {
    link.addEventListener("click", function(e) {
      e.preventDefault();
      // Toggle the visibility of the next element (the details)
      var details = link.nextElementSibling;
      details.style.display = details.style.display === "block" ? "none" : "block";
    });
  });
</script>
