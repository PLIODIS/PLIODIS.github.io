---
title: "Outreach"
layout: splash
classes: wide
permalink: /outreach/
header:
  overlay_image: /assets/images/Ngonye.jpg
  overlay_filter: 0.3
---

<div class="outreach-intro">
  <h2>Sharing the science</h2>
  <p>PLIODIS is committed to communicating science to the general public and to building a scientific community that shares knowledge across disciplines. Our work brings together geomorphology, palaeoclimate, and palaeoanthropology, and we believe the questions we ask, about how landscapes, climate, and early humans shaped one another, are ones everyone can engage with.</p>
  <p>Through school visits, public lectures, museum partnerships, and fieldwork open to local communities, we aim to make our research accessible, spark curiosity about deep human history, and encourage dialogue between researchers, students, and the wider public.</p>
</div>

<div class="outreach-events">

  <div class="outreach-event">
    <div class="outreach-text">
      <h2>Research seminar in Lusaka</h2>
      <p>At the end of the Zambia fieldtrip in August 2026, a short research seminar was held at the University of Zambia, under the umbrella of the Integrated Water Resources Management Centre of Excellence (IWRM-CoE).</p>
      <p>Researchers involved in the fieldwork presented their work on tectonics, climate change, erosion, river-system processes, human evolution, and sustainable water-resource management in southern Africa. More information is available on the official <a href="/assets/images/outreach/Lusaka/Research_Seminar.pdf">seminar leaflet</a>.</p>
    </div>
    <div class="outreach-slideshow" aria-label="University seminar photos">
      <figure class="outreach-slide is-active">
        <img src="/assets/images/outreach/Lusaka/lusaka-1.jpeg" alt="Pieter Vermeesch presenting">
        <figcaption>Pieter Vermeesch (UCL)</figcaption>
      </figure>
      <figure class="outreach-slide">
        <img src="/assets/images/outreach/Lusaka/lusaka-2.jpeg" alt="Eduardo Garzanti presenting">
        <figcaption>Eduardo Garzanti (UNIMIB)</figcaption>
      </figure>
      <figure class="outreach-slide">
        <img src="/assets/images/outreach/Lusaka/lusaka-3.jpeg" alt="K. Banda presenting">
        <figcaption>K. Banda (UNZA)</figcaption>
      </figure>
      <figure class="outreach-slide">
        <img src="/assets/images/outreach/Lusaka/lusaka-4.jpeg" alt="Matthew Fox presenting">
        <figcaption>Matthew Fox (UCL)</figcaption>
      </figure>
      <figure class="outreach-slide">
        <img src="/assets/images/outreach/Lusaka/lusaka-5.jpeg" alt="Guido Pastore presenting">
        <figcaption>Guido Pastore (UCL)</figcaption>
      </figure>
      <figure class="outreach-slide">
        <img src="/assets/images/outreach/Lusaka/lusaka-6.jpeg" alt="Group photo">
        <figcaption>Group photo</figcaption>
      </figure>
      <button class="outreach-nav outreach-prev" aria-label="Previous photo">&#8249;</button>
      <button class="outreach-nav outreach-next" aria-label="Next photo">&#8250;</button>
      <div class="outreach-dots"></div>
    </div>
  </div>

</div>

<script>
(function () {
  var shows = document.querySelectorAll('.outreach-slideshow');
  shows.forEach(function (show) {
    var slides = show.querySelectorAll('.outreach-slide');
    if (slides.length === 0) return;
    var dotsWrap = show.querySelector('.outreach-dots');
    var i = 0, timer, activeFound = false;

    slides.forEach(function (s, idx) {
      if (s.classList.contains('is-active')) { i = idx; activeFound = true; }
    });
    if (!activeFound) { slides[0].classList.add('is-active'); i = 0; }

    var dots = [];
    if (dotsWrap) {
      slides.forEach(function (s, idx) {
        var d = document.createElement('button');
        d.className = 'outreach-dot' + (idx === i ? ' is-active' : '');
        d.setAttribute('aria-label', 'Go to photo ' + (idx + 1));
        d.addEventListener('click', function () { go(idx); reset(); });
        dotsWrap.appendChild(d);
      });
      dots = dotsWrap.querySelectorAll('.outreach-dot');
    }

    function go(n) {
      slides[i].classList.remove('is-active');
      if (dots[i]) dots[i].classList.remove('is-active');
      i = (n + slides.length) % slides.length;
      slides[i].classList.add('is-active');
      if (dots[i]) dots[i].classList.add('is-active');
    }
    function next() { go(i + 1); }
    function prev() { go(i - 1); }
    function start() { if (slides.length > 1) timer = setInterval(next, 4500); }
    function reset() { clearInterval(timer); start(); }

    var nextBtn = show.querySelector('.outreach-next');
    var prevBtn = show.querySelector('.outreach-prev');
    if (nextBtn) nextBtn.addEventListener('click', function () { next(); reset(); });
    if (prevBtn) prevBtn.addEventListener('click', function () { prev(); reset(); });

    if (slides.length <= 1) {
      if (nextBtn) nextBtn.style.display = 'none';
      if (prevBtn) prevBtn.style.display = 'none';
      if (dotsWrap) dotsWrap.style.display = 'none';
    }

    show.addEventListener('mouseenter', function () { clearInterval(timer); });
    show.addEventListener('mouseleave', start);
    start();
  });
})();
</script>
