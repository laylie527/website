---
layout: default
title: Download
css_class: install
platform_names:
  - windows
  - unix
---

<h1 class="text-centered page-title main-heading">Install Nim</h1>

<div class="slim content">
  <div class="pure-g center os-pickers">
    <div class="pure-u pure-u-md-1-3">
      <a href="{{ site.baseurl }}/install_windows.html">
        <div class="os-picker-box center">
          <i class="fab fa-windows" aria-hidden="true"></i>
        </div>
        <h2>Windows</h2>
      </a>
    </div>

    <div class="pure-u pure-u-md-1-3">
      <a href="{{ site.baseurl }}/install_unix.html">
        <div class="os-picker-box center">
          <i class="fab fa-apple" aria-hidden="true"></i>
          <i class="fab fa-linux" aria-hidden="true"></i>
        </div>
        <h2>Unix</h2>
      </a>
    </div>
  </div>
</div>

<section class="background-faded call-to-action">
  <section class="content text-centered center-banner">
    <h1 class="section-heading">
      <i class="far fa-moon fa-2x" aria-hidden="true"></i>
      Want a nightly build?
    </h1>
    <div class="pure-g center">
      <div class="pure-u-1-2">
        <p>
          We offer nightly builds both for the cutting-edge devel branch and
          for backports to our stable branch.
        </p>
      </div>
      <div class="pure-u-1 center">
        <a class="pure-button" href="https://github.com/nim-lang/nightlies/releases">Get nightlies</a>
      </div>
    </div>
  </section>
</section>


<h1 class="text-centered page-title main-heading">Install previous versions</h1>

<div class="slim content center">
  {% for platform_name in page.platform_names %}
  <div class="pure-u pure-u-md-1-3">
    <h2>{{ platform_name | capitalize }}</h2>
    {% for version in site.data.versions %}
    Nim {{ version.name }}:
    <ul>
    {% for release in version.releases %}
      <li>Nim {{ release.name }}:
      {% assign platform = release.platforms | where: 'name', platform_name | first %}
      {% for download in platform.downloads %}
      <a href="{{ site.baseurl }}{{ download.url }}">{{ download.name }}</a>{% unless forloop.last %},{% endunless %}
      {% endfor %}
      </li>
    {% endfor %}
    </ul>
    {% endfor %}
  </div>

  {% unless forloop.last %}
  <div class="pure-u pure-u-md-1-8"></div>
  {% endunless %}
  {% endfor %}
</div>
