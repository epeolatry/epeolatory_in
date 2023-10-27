---
layout: page
title: Testimonials
menu: 
  header:
    weight: 8
---

{% assign testimonials = site.data.testimonials %}

{% for testimonial in testimonials %}
  <div class="testimonial">
    <img src="{{ testimonial.image }}" alt="{{ testimonial.author }}" width="100px"/>
    <p>
      "{{ testimonial.intro }}"
    </p>
    <div id="testimonial-details-{{ forloop.index }}" style="display: none;">
      <p>
        {{ testimonial.details }}
      </p>
      <p>
        - {{ testimonial.author }}
        ({{ testimonial.book }})
      </p>
    </div>
    <button id="read-more-btn-{{ forloop.index }}" onclick="toggleTestimonialDetails({{ forloop.index }})">Read more...</button>
  </div>
{% endfor %}

<script>
function toggleTestimonialDetails(id) {
  var details = document.getElementById("testimonial-details-" + id);
  var button = document.getElementById("read-more-btn-" + id);

  if (details.style.display === "none") {
    details.style display = "block";
    button.innerHTML = "Read less...";
  } else {
    details.style.display = "none";
    button.innerHTML = "Read more...";
  }
}
</script>
