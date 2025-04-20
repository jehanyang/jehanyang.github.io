---
layout: default
title: Home
---
<h1 id="home" style="margin-block-start:0">Home</h1>

<!-- <h3 class="message" style="line-height: 1.5; font-weight: normal"> </h3> -->
<!--Feel free to check out my blog too. It will be mostly about graduate school and some content I think will be relevant for students studying engineering and computer science. 
## Recent News -->
<ul style="margin-bottom:0px">
<li><em>January 2025</em>&mdash;<a href="https://www.nature.com/articles/s44182-025-00018-3">My work</a> in HDEMG for assistive robot control has just been published in Nature Partner Journals in Robotics! </li>
<li><em>December 2024</em>&mdash;I will present <a href="https://emgbench.github.io">my work</a> at NeurIPS 2024 involving open-source EMG gesture recognition for generalization and adaptation across people! </li>
<li><em>March 2024</em>&mdash;<a href="https://dl.acm.org/doi/10.1145/3610977.3634964">Our work</a> involving the control of a mobile manipulator robot to perform various home tasks in the home of a person with quadriplegia won Best Paper at HRI 2024! See link. </li>
</ul>
<details class="toggle-details">
  <summary class="toggle-summary"><strong>More</strong></summary>
  <div class="toggle-content">
    <ul>
      <li><em>August 2022</em>&mdash;I begin my PhD at CMU!</li>
      <li><em>June 2022</em>&mdash;I begin working full-time as a software intern at fast-food robotics startup, <a href="https://misorobotics.com">Miso Robotics</a>.</li>
      <li><em>April 2022</em>&mdash;I committed to my PhD at <a href="https://cmu.edu">Carnegie Mellon University</a> with advisors Zackory Erickson and Doug Weber! I received a 2-year fully-funded departmental fellowship.</li>
      <li><em>June 2020</em>&mdash;I start my internship with the self-driving car startup, <a href="https://nuro.ai">Nuro</a>.</li>
      <li><em>May 2020</em>&mdash;I committed to starting my MS in Electrical Engineering at <a href="https://ee.caltech.edu">Caltech</a> with a 2-year fully-funded departmental fellowship.</li>
      <li><em>April 2020</em>&mdash;I received the <a href="https://nsfgrfp.org">NSF GRFP</a>! I am indescribably grateful for my mentors' and friends' help.</li>
      <li><em>Sep. 2019</em>&mdash;I started working with <a href="https://covariant.ai">Covariant</a> as an intern.</li>
      <li><em>May 2019</em>&mdash;I received funding from the <a href="https://hsp.berkeley.edu">Haas Scholars Fellowship</a>, the largest research award for undergraduates at UC Berkeley.</li>
    </ul>
    <p class="toggle-less"><strong>Less</strong></p>
  </div>
</details>

<script>
  document.addEventListener("DOMContentLoaded", function() {
    const details = document.querySelector(".toggle-details");
    const summary = details.querySelector(".toggle-summary");
    const lessText = details.querySelector(".toggle-less");

    lessText.style.display = "none"; // Hide "Less" initially

    details.addEventListener("toggle", function() {
      if (details.open) {
        summary.style.display = "none"; // Completely remove "More" when expanded
        lessText.style.display = "block"; // Show "Less" at the bottom
      } else {
        summary.style.display = "list-item"; // Restore "More" with the triangle
        lessText.style.display = "none"; // Hide "Less"
      }
    });

    lessText.addEventListener("click", function() {
      details.open = false; // Close the <details> element when "Less" is clicked
      summary.style.display = "list-item"; // Restore "More" and triangle
      lessText.style.display = "none"; // Hide "Less"
    });
  });
</script>

<h1>Publications</h1>

<div class="publications">
  {% for pub in site.data.publications %}
  <div class="publication-entry">
    <div class="publication-image">
      <a href="{{ pub.website | default: pub.pdf }}">
        <img src="{{ pub.image }}" alt="{{ pub.title }}">
      </a>
    </div>
    <div class="publication-details">
      <h2><a href="{{ pub.website | default: pub.pdf }}">{{ pub.title }}</a></h2>
      <p>{{ pub.authors | replace: "Jehan Yang", "<strong>Jehan Yang</strong>" }}</p>
      <p><em>{{ pub.venue }}, {{ pub.year }} </em> {% if pub.awards %} <strong>{{ pub.awards }}</strong>{% endif %}</p>


      <p>
        {% if pub.abstract %}
          <a href="#" class="toggle" data-target="abstract-{{ pub.id }}">Abstract</a> /
        {% endif %}
        {% if pub.pdf %}
          <a href="{{ pub.pdf }}">PDF</a> /
        {% endif %}
        {% if pub.video %}
          <a href="{{ pub.video }}">Video</a> /
        {% endif %}
        {% if pub.projectpage %}
          <a href="{{ pub.projectpage }}">Project Page</a> /
        {% endif %}
        {% if pub.news %}
          <a href="{{ pub.news }}">Article 1</a>{% if pub.news2 %} / <a href="{{ pub.news2 }}">Article 2</a>{% endif %}
          /
        {% endif %}
        {% if pub.bibtex %}
          <a href="#" class="toggle" data-target="bibtex-{{ pub.id }}">BibTeX</a>
        {% endif %}
      </p>

      {% if pub.abstract %}
      <div class="toggle-content" id="abstract-{{ pub.id }}" style="display:none;">
        <p class="abstract">{{ pub.abstract }}</p>
      </div>
      {% endif %}

      {% if pub.bibtex %}
      <div class="toggle-content" id="bibtex-{{ pub.id }}" style="display:none;">
        <pre>{{ pub.bibtex }}</pre>
      </div>
      {% endif %}
    </div>
  </div>
  {% endfor %}
</div>

<script>
  document.addEventListener("DOMContentLoaded", function() {
    document.querySelectorAll(".toggle").forEach(function(element) {
      element.addEventListener("click", function(event) {
        event.preventDefault(); // Prevents default anchor behavior
        event.stopPropagation(); // Stops event from bubbling

        let targetId = this.getAttribute("data-target");
        let target = document.getElementById(targetId);
        if (target.style.display === "none" || target.style.display === "") {
          target.style.display = "block";
        } else {
          target.style.display = "none";
        }
      });
    });
  });
</script>

<details style="padding-top:10px;"><summary style="padding-left: 20px; padding-bottom: 0px; margin-bottom:0px; font-size:20px"><strong>Projects</strong></summary><p style="padding-left: 20px" >

<div class="row">
  <div class="column" style="width:100%"> 
  <a class="nochangelink" href="portfolio/leg">
  <div class="card">
    <img src="/images/prosthLeg.jpg" alt="Caltech AMBER Lab Prosthetic Leg" style="width:100%;border-radius: 5px 5px 0 0;">
  <div class="container">
    <strong>Prosthetic Leg Pressure Sensing</strong>
    <p>Software</p>
  </div>
  </div>
  </a>
  </div>
</div>

<div class="row">
  <div class="column">
  <a class="nochangelink" href="/portfolio/pie">
  <div class="card">
   <img src="/images/PiE.jpg" alt="Pioneers in Engineering robot maintenance" style="width:100%;border-radius: 5px 5px 0 0;">
  <div class="container">
   <strong>Pioneers in Engineering</strong>
   <p>Team Leader, Treasurer</p> 
  </div>
  </div>
  </a>
  </div>     

  <div class="column">
  <a class="nochangelink" href="/portfolio/biomfing">
  <div class="card">
  <img src="/images/biomFing.png" alt="Biomimetic Finger Projects" style="width:100%;border-radius: 5px 5px 0 0;">
  <div class="container">
   <strong>Biomimetic Finger</strong>
   <p>Undergraduate Researcher, Haas Scholar</p> 

  </div>
  </div>
  </a>
  </div>
</div>

<div class="row">
  <div class="column">
  <a class="nochangelink" href="/portfolio/nerf">
  <div class="card">
  <img src="/images/Nerf3.jpg" alt="Nerf Prosthetic picture of product" style="width:100%;border-radius: 5px 5px 0 0;">
  <div class="container">
   <strong>Nerf Prosthetic</strong>
   <p>Voted Best Project, Technical Lead</p> 
  
  </div>
  </div>
  </a>
  </div>

  <div class="column">
  <a class="nochangelink" href="/portfolio/claw">
<div class="card">
   <img src="/images/TOM.jpg" alt="Tikka Olam Makers Makerthon products: Claw and Plug" style="width:100%;border-radius: 5px 5px 0 0;">
  <div class="container">
   <strong>Household Claw for Disabled Client</strong>
   <p>Manufacturing and Design</p> 
  </div>
  </div>
  </a>
  </div>     
 </div>

<details style="padding-top:10px;"><summary style="padding-left: 20px; padding-bottom: 0px; margin-bottom:0px; font-size:20px"><strong>More</strong></summary><p style="padding-left: 20px" >

<div class="row">
  <div class="column">
  <a class="nochangelink" href="/portfolio/joint">
  <div class="card">
   <img src="/images/Joint.png" alt="Soft Robotic Joint" style="width:100%;border-radius: 5px 5px 0 0;">
  <div class="container">
   <strong>Soft Robotic Joint</strong>
   <p>Force and Displacement Tester, Designer</p> 
  </div>
  </div>
  </a>
  </div>

  <div class="column">
  <a class="nochangelink" href="/portfolio/bopit">
  <div class="card">
   <img src="/images/BopIt.jpg" alt="Bop It! Rhythm Game Implemented in Hardware" style="width:100%;border-radius: 5px 5px 0 0;">
  <div class="container">
   <strong>Bop It! Rhythm Game</strong>
   <p>Mechanical Designer, Programmer</p> 
  </div>
  </div>
  </a>
  </div>
</div>


<div class="row">
  <div class="column">
  <a class="nochangelink" href="/portfolio/roach">
  <div class="card">
   <img src="/images/VelociRoACH.png" alt="VelociRoACH Profile View before Run" style="width:100%;border-radius: 5px 5px 0 0;">
  <div class="container">
   <strong>VelociRoACH Step Climbing</strong>
   <p>Lead Designer and Fabricator</p>
  </div>
  </div>
  </a>
  </div>


  <div class="column">
  <a class="nochangelink" href="/portfolio/salto">
  <div class="card">
   <img src="/images/SaltoFoot.jpg" alt="Salto Gripper" style="width:100%;border-radius: 5px 5px 0 0;">
  <div class="container">
   <strong>Salto Gripper</strong>
   <p>Jump Test and Foot Design</p> 
  </div>
  </div>
  </a>
  </div>
</div>

<div class="row">

  <div class="column">
  <a class="nochangelink" href="/portfolio/led">
  <div class="card">
   <img src="/images/arraypcb.jpg" alt="LED Array printed circuit board" style="width:100%;border-radius: 5px 5px 0 0;">
  <div class="container">
   <strong>LED Array PCB</strong>
   <p>PCB Designer</p> 
  </div>
  </div>
  </a>
  </div>

  <div class="column">
  <a class="nochangelink" href="/portfolio/turbine">
  <div class="card">
   <img src="/images/blades.png" alt="Milliscale Wind Turbine Blades" style="width:100%;border-radius: 5px 5px 0 0;">
  <div class="container">
   <strong>Milliscale Wind Turbine</strong>
   <p>CFD Analyst</p> 
  </div>
  </div>
  </a>
  </div>

</div>

</p></details>

</p></details>


<span></span>

