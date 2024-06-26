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
      {% if testimonial.image %}
        <img src="{{ testimonial.image }}" alt="{{ testimonial.author }}" width="100px"/>
      {% endif %}
      <p>
        <em><strong>{{ testimonial.author }}</strong></em> <em>(<strong>{{ testimonial.book }}</strong>)</em>
        <br>
        "{{ testimonial.intro }}"
        {% if testimonial.details.size > 100 %}
          <a class="testimonial-author" href="javascript:void(0)">Read more...</a>
        {% endif %}
      </p>
      <p class="testimonial-details">
        {{ testimonial.details }}
        <a class="read-less" href="javascript:void(0)" style="display: none">Read less</a>
      </p>
    </div>
    <p></p> <!-- Add a paragraph space after each testimonial -->
  {% endfor %}
</div>

<script>
  var readMoreLinks = document.querySelectorAll(".testimonial-author");
  var readLessLinks = document.querySelectorAll(".read-less");

  readMoreLinks.forEach(function(link, index) {
    link.addEventListener("click", function(e) {
      e.preventDefault();
      var details = link.closest('.testimonial').querySelector('.testimonial-details');
      var readLessLink = readLessLinks[index];

      if (details.style.display === "block" || details.style.display === "") {
        details.style.display = "none";
        link.style.display = "inline"; // Show "Read more" again
        readLessLink.style.display = "none";
      } else {
        details.style.display = "block";
        link.style.display = "none"; // Hide "Read more"
        readLessLink.style.display = "inline"; // Show "Read less"
      }
    });
  });

  readLessLinks.forEach(function(link, index) {
    link.addEventListener("click", function(e) {
      e.preventDefault();
      var details = link.closest('.testimonial').querySelector('.testimonial-details');
      var readMoreLink = readMoreLinks[index];

      details.style.display = "none";
      link.style.display = "none"; // Hide "Read less"
      readMoreLink.style.display = "inline"; // Show "Read more"
    });
  });
</script>
