---
layout: default
---

<!-- ================================================================== -->
<!-- NAGŁÓWEK                                                           -->
<!-- ================================================================== -->

<header>
  <div class="logo-mark" itemscope itemtype="https://schema.org/ImageObject">
    <img src="piotrek.jpg" alt="Smutny Pan — muzyk i animator z Krakowa, autor piosenek z rysunkami" width="90" height="90" loading="eager" itemprop="contentUrl"/>
    <meta itemprop="name" content="Smutny Pan — zdjęcie profilowe"/>
  </div>
  <h1 itemprop="name">Smutny Pan</h1>
  <p class="tagline">piosenki z rysunkami</p>
</header>

<nav aria-label="Nawigacja główna">
  <a href="#muzyka">Muzyka</a>
  <a href="#filmy">Filmy</a>
  <a href="#o-mnie">O mnie</a>
  <a href="#kontakt">Kontakt</a>
</nav>

<!-- ================================================================== -->
<!-- GŁÓWNY FILM (embed) — ustawiany w _data/videos.yml -> featured     -->
<!-- ================================================================== -->

{% assign featured = site.data.videos.featured %}

<article class="hero" aria-labelledby="hero-caption">
  <h2 class="hero-caption" id="hero-caption">{{ featured.caption }}</h2>
  <p class="hero-subcaption">{{ featured.subcaption }}</p>
  <div class="video-embed">
    <iframe src="https://www.youtube-nocookie.com/embed/{{ featured.id }}?rel=0" title="{{ featured.title }} — teledysk Smutny Pan" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen referrerpolicy="strict-origin-when-cross-origin" loading="eager"></iframe>
  </div>
</article>

<!-- ================================================================== -->
<!-- INNE / WCZEŚNIEJSZE FILMY — lista z _data/videos.yml -> others     -->
<!-- ================================================================== -->

<section id="filmy" aria-labelledby="filmy-label">
  <h2 class="section-label" id="filmy-label">Inne / wcześniejsze filmy</h2>
  <div class="video-grid">

    {% for video in site.data.videos.others %}
    <a class="video-card" href="https://www.youtube.com/watch?v={{ video.id }}" target="_blank" rel="noopener noreferrer" aria-label="{{ video.title }} — teledysk na YouTube">
      <figure class="video-thumb">
        <img src="https://img.youtube.com/vi/{{ video.id }}/maxresdefault.jpg" alt="Miniaturka teledysku {{ video.title }} — ręcznie rysowana animacja" width="480" height="270" loading="lazy"/>
      </figure>
      <h3 class="video-title">{{ video.title }}</h3>
      <p class="video-views">{{ video.views }} · {{ video.date }}</p>
    </a>
    {% endfor %}

  </div>
  <div class="yt-all">
    <a href="https://www.youtube.com/@{{ site.author.youtube }}" target="_blank" rel="noopener noreferrer">Wszystkie filmy na YouTube →</a>
  </div>
</section>

<!-- ================================================================== -->
<!-- SŁUCHAJ I OBSERWUJ                                                 -->
<!-- ================================================================== -->

<section id="muzyka" aria-labelledby="muzyka-label">
  <h2 class="section-label" id="muzyka-label">Słuchaj i obserwuj</h2>
  <div class="links-grid">
    <a class="link-btn" href="https://open.spotify.com/artist/{{ site.author.spotify }}" target="_blank" rel="noopener noreferrer nofollow" aria-label="Smutny Pan na Spotify">
      <svg width="20" height="20" viewBox="0 0 24 24" fill="currentColor" style="flex-shrink:0;opacity:0.6" aria-hidden="true"><path d="M12 2C6.477 2 2 6.477 2 12s4.477 10 10 10 10-4.477 10-10S17.523 2 12 2zm4.586 14.424a.622.622 0 01-.857.207c-2.348-1.435-5.304-1.76-8.785-.964a.622.622 0 11-.277-1.215c3.809-.87 7.077-.495 9.712 1.115a.623.623 0 01.207.857zm1.223-2.722a.78.78 0 01-1.072.257C14.1 12.14 10.64 11.74 7.4 12.66a.779.779 0 01-.972-.519.781.781 0 01.519-.972c3.665-1.113 7.56-.574 10.435 1.261a.782.782 0 01.427 1.272zm.105-2.835C15.91 9.087 11.8 8.95 9.124 9.763a.937.937 0 01-.574-1.787c3.11-.998 7.67-.806 10.7 1.106a.937.937 0 01-.435 1.785z"/></svg>
      <div><p class="platform">Spotify</p><p class="name">Smutny Pan</p></div>
    </a>
    <a class="link-btn" href="https://www.youtube.com/@{{ site.author.youtube }}" target="_blank" rel="noopener noreferrer" aria-label="Smutny Pan na YouTube">
      <svg width="20" height="20" viewBox="0 0 24 24" fill="currentColor" style="flex-shrink:0;opacity:0.6" aria-hidden="true"><path d="M23.498 6.186a3.016 3.016 0 00-2.122-2.136C19.505 3.545 12 3.545 12 3.545s-7.505 0-9.377.505A3.017 3.017 0 00.502 6.186C0 8.07 0 12 0 12s0 3.93.502 5.814a3.016 3.016 0 002.122 2.136c1.871.505 9.376.505 9.376.505s7.505 0 9.377-.505a3.015 3.015 0 002.122-2.136C24 15.93 24 12 24 12s0-3.93-.502-5.814zM9.545 15.568V8.432L15.818 12l-6.273 3.568z"/></svg>
      <div><p class="platform">YouTube</p><p class="name">@{{ site.author.youtube }}</p></div>
    </a>
    <a class="link-btn" href="https://www.instagram.com/{{ site.author.instagram }}" target="_blank" rel="noopener noreferrer" aria-label="Smutny Pan na Instagramie">
      <svg width="20" height="20" viewBox="0 0 24 24" fill="currentColor" style="flex-shrink:0;opacity:0.6" aria-hidden="true"><path d="M12 2.163c3.204 0 3.584.012 4.85.07 3.252.148 4.771 1.691 4.919 4.919.058 1.265.069 1.645.069 4.849 0 3.205-.012 3.584-.069 4.849-.149 3.225-1.664 4.771-4.919 4.919-1.266.058-1.644.07-4.85.07-3.204 0-3.584-.012-4.849-.07-3.26-.149-4.771-1.699-4.919-4.92-.058-1.265-.07-1.644-.07-4.849 0-3.204.013-3.583.07-4.849.149-3.227 1.664-4.771 4.919-4.919 1.266-.057 1.645-.069 4.849-.069zm0-2.163c-3.259 0-3.667.014-4.947.072-4.358.2-6.78 2.618-6.98 6.98-.059 1.281-.073 1.689-.073 4.948 0 3.259.014 3.668.072 4.948.2 4.358 2.618 6.78 6.98 6.98 1.281.058 1.689.072 4.948.072 3.259 0 3.668-.014 4.948-.072 4.354-.2 6.782-2.618 6.979-6.98.059-1.28.073-1.689.073-4.948 0-3.259-.014-3.667-.072-4.947-.196-4.354-2.617-6.78-6.979-6.98-1.281-.059-1.69-.073-4.949-.073zm0 5.838c-3.403 0-6.162 2.759-6.162 6.162s2.759 6.163 6.162 6.163 6.162-2.759 6.162-6.163c0-3.403-2.759-6.162-6.162-6.162zm0 10.162c-2.209 0-4-1.79-4-4 0-2.209 1.791-4 4-4s4 1.791 4 4c0 2.21-1.791 4-4 4zm6.406-11.845c-.796 0-1.441.645-1.441 1.44s.645 1.44 1.441 1.44c.795 0 1.439-.645 1.439-1.44s-.644-1.44-1.439-1.44z"/></svg>
      <div><p class="platform">Instagram</p><p class="name">@{{ site.author.instagram }}</p></div>
    </a>
  </div>
</section>

<!-- ================================================================== -->
<!-- O MNIE                                                              -->
<!-- ================================================================== -->

<section id="o-mnie" aria-labelledby="o-mnie-label">
  <h2 class="section-label" id="o-mnie-label">O mnie</h2>
  <p style="font-family:'Playfair Display',Georgia,serif;font-size:1.05rem;line-height:1.75;max-width:520px;" itemprop="description">
    Muzyka dzieje się nocą. I to nocą powstają piosenki, a później nocami powstają do nich animacje, kreska po kresce i kartka po kartce. Nie jestem taki smutny, jak się może wydawać.
  </p>
</section>

<!-- ================================================================== -->
<!-- KONTAKT / NEWSLETTER                                                -->
<!-- ================================================================== -->

<section id="kontakt" aria-labelledby="kontakt-label">
  <a href="https://instagram.com/smutnypan.art" target="_blank" rel="noopener noreferrer" style="display: inline-flex; align-items: center; gap: 6px; color: #E1306C; text-decoration: none; font-weight: 500;">
    <svg width="20" height="20" viewBox="0 0 24 24" fill="currentColor"><path d="M12 2.163c3.204 0 3.584.012 4.85.07 3.252.148 4.771 1.691 4.919 4.919.058 1.265.069 1.645.069 4.849 0 3.205-.012 3.584-.069 4.849-.149 3.225-1.664 4.771-4.919 4.919-1.266.058-1.644.07-4.85.07-3.204 0-3.584-.012-4.849-.07-3.26-.149-4.771-1.699-4.919-4.92-.058-1.265-.07-1.644-.07-4.849 0-3.204.013-3.583.07-4.849.149-3.227 1.664-4.771 4.919-4.919 1.266-.057 1.645-.069 4.849-.069zm0-2.163c-3.259 0-3.667.014-4.947.072-4.358.2-6.78 2.618-6.98 6.98-.059 1.281-.073 1.689-.073 4.948 0 3.259.014 3.668.072 4.948.2 4.358 2.618 6.78 6.98 6.98 1.281.058 1.689.072 4.948.072 3.259 0 3.668-.014 4.948-.072 4.354-.2 6.782-2.618 6.979-6.98.059-1.28.073-1.689.073-4.948 0-3.259-.014-3.667-.072-4.947-.196-4.354-2.617-6.78-6.979-6.98-1.281-.059-1.69-.073-4.949-.073zm0 5.838c-3.403 0-6.162 2.759-6.162 6.162s2.759 6.163 6.162 6.163 6.162-2.759 6.162-6.163c0-3.403-2.759-6.162-6.162-6.162zm0 10.162c-2.209 0-4-1.79-4-4 0-2.209 1.791-4 4-4s4 1.791 4 4c0 2.21-1.791 4-4 4zm6.406-11.845c-.796 0-1.441.645-1.441 1.44s.645 1.44 1.441 1.44c.795 0 1.439-.645 1.439-1.44s-.644-1.44-1.439-1.44z"/></svg>
    @smutnypan.art
  </a>
  <!--h2 class="sr-only" id="kontakt-label">Kontakt — newsletter</h2>
  <div class="newsletter">
    <h3>Zostań na bieżąco</h3>
    <p>Nowy utwór, nowa animacja — co jakiś czas, kiedy coś wychodzi.<br>Bez spamu. Bez algorytmu. Tylko e-mail.</p>
    <div class="email-row">
      <label for="email-input" class="sr-only">Twój adres e-mail</label>
      <input type="email" id="email-input" name="email" placeholder="twój@email.pl" autocomplete="email" required aria-required="true"/>
      <button type="button" onclick="handleSubscribe()">Zapisz się</button>
    </div>
    <div id="sub-msg" role="status" aria-live="polite"></div>
  </div-->
</section>

<!-- ================================================================== -->
<!-- STOPKA                                                              -->
<!-- ================================================================== -->

<footer>
  <p style="font-family:'Playfair Display',Georgia,serif;font-style:italic;">Smutny Pan, 2026</p>
  <nav class="footer-links" aria-label="Linki do social media">
    <a href="https://www.youtube.com/@{{ site.author.youtube }}" target="_blank" rel="noopener noreferrer">YouTube</a>
    <a href="https://www.instagram.com/{{ site.author.instagram }}" target="_blank" rel="noopener noreferrer">Instagram</a>
  </nav>
</footer>
