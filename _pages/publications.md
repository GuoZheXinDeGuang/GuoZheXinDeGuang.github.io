---
layout: page
permalink: /publications/
title: publications
description: publications.
nav: true
nav_order: 2
---

<!-- _pages/publications.md -->

<!-- Bibsearch Feature -->

{% include bib_search.liquid %}

<style>
  .publications .abbr img.preview {
    width: 100%;
    max-height: 95px;
    object-fit: contain;
  }

  .publications .author em {
    font-style: normal;
    font-weight: 700;
  }
</style>

<script>
  document.addEventListener("DOMContentLoaded", function () {
    document.querySelectorAll(".publications .more-authors").forEach(function (element) {
      var handler = element.getAttribute("onclick") || "";
      var match = handler.match(/\? '([^']*)' : '([^']*)'/);

      if (!match) return;

      var fullText = match[1];
      var shortText = match[2];

      element.removeAttribute("onclick");
      element.setAttribute("role", "button");
      element.setAttribute("tabindex", "0");

      var toggle = function () {
        var isCollapsed = element.textContent.trim() === shortText;
        var nextText = isCollapsed ? fullText : shortText;
        element.innerHTML = nextText.replace("Zihan Liu", "<strong>Zihan Liu</strong>");
      };

      element.addEventListener("click", toggle);
      element.addEventListener("keydown", function (event) {
        if (event.key === "Enter" || event.key === " ") {
          event.preventDefault();
          toggle();
        }
      });
    });
  });
</script>

<div class="publications">

{% bibliography %}

</div>
