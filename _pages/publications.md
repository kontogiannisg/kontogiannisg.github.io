---
layout: page
permalink: /publications/
title: publications
description:
nav: true
nav_order: 1
---

<!-- _pages/publications.md -->

<!-- Bibsearch Feature -->

{% include bib_search.liquid %}

<div class="publications">

{% bibliography %}

</div>

<!-- Colour each publication card's left bar to match its venue badge. -->
<script>
  document.addEventListener("DOMContentLoaded", function () {
    document.querySelectorAll(".publications ol.bibliography > li").forEach(function (li) {
      var badge = li.querySelector(".abbr abbr");
      if (!badge) return;
      var color = getComputedStyle(badge).backgroundColor;
      if (color && color !== "rgba(0, 0, 0, 0)" && color !== "transparent") {
        li.style.setProperty("--venue-color", color);
      }
    });
  });
</script>
