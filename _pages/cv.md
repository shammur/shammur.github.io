---
layout: page
permalink: /cv/
title: CV
# nav: true
nav_order: 5
cv_pdf: SAC_CV_format2.pdf
# description: This is a description of the page. You can modify it in '_pages/cv.md'. You can also change or remove the top pdf download button.
# toc:
  # sidebar: left
---

{% assign cv_path = '/assets/pdf/SAC_CV_format2.pdf' | relative_url %}

<div class="cv-pdf-page">
  <p>
    <a class="primary-link" href="{{ cv_path }}" target="_blank" rel="noopener">Open PDF CV</a>
  </p>
  <iframe class="cv-pdf-viewer" src="{{ cv_path }}" title="Shammur Absar Chowdhury CV"></iframe>
</div>
