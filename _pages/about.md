---
permalink: /
title: "About me"
author_profile: true
header:
  image: /DSCN4513.jpg
redirect_from: 
  - /about/
  - /about.html

---





I am a postdoctoral scientist in the [Department of River-Coastal Science and Engineering at the School of Science and Engineering](https://sse.tulane.edu/river), Tulane University, at [Soenke Dangendorf's sea-level change team](https://sse.tulane.edu/sonke-dangendorf), since January 2025. 
I hold a doctoral degree in Geodesy and Oceanography from the [Deutsches Geodätisches Forschungsinstitut](https://www.dgfi.tum.de/en/) at the Technical University of Munich and a master’s degree from the [University of Hamburg](https://mpimet.mpg.de/en/homepage). My research focuses on disentangling the individual components of regional coastal sea-level change. In addition to climate-induced sea-level rise, a significant portion of relative sea-level change at the coast results from vertical land motion, including subsidence and uplift driven by various geophysical processes. To quantify these contributions, I integrates multiple observational techniques—including coastal altimetry, tide gauges, GNSS, and InSAR—with models of ocean and solid Earth dynamics. Using these constraints, I develop and apply statistical frameworks to assess the drivers and impacts of past and future sea-level changes.

 


## Research Interests

Oceanography, Sea-level Change, Climate Science, Remote Sensing, Statistics, Software Engineering

 
## Current Project

[Disentangling Vertical Land Motion Processes for Future Sea Level Change Projections (VLM-SLC)]({% include base_path %}/portfolio/portfolio-1/)

Marie-Curie Postdoctoral GF @Tulane University and @TUM



{% include base_path %}



  <link
    href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/css/bootstrap.min.css"
    rel="stylesheet"
    integrity="sha384-QWTKZyjpPEjISv5WaRU9OFeRpok6YctnYmDr5pNlyT2bRjXh0JMhjY6hW+ALEwIH"
    crossorigin="anonymous"
  >

  <script
    src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/js/bootstrap.bundle.min.js"
    integrity="sha384-YvpcrYf0tY3lHB60NNkmXc5s9fDVZLESaAA55NDzOxhy9GkcIdslK1eN7N6jIeHz"
    crossorigin="anonymous"
  ></script>

<style>

  .transition-shadow {
  transition: box-shadow 0.3s ease;
}
</style>

## More Projects

<div class="row mt-4">
{% for post in site.portfolio %}
  {% include archive-single_card_small.html %}
{% endfor %}
</div>





## GitHub Projects

<div class="container mx-0 px-0">
  <div class="row" id="github-repos"></div>
</div>
{% raw %}
<script>
document.addEventListener("DOMContentLoaded", () => {
  const username = "oelsmann";
  const targetRepos = ['sealeveltools', 'bpca', 'discotimes'];
  const container = document.getElementById("github-repos");

  fetch(`https://api.github.com/users/${username}/repos?per_page=100`, {
    headers: { "Accept": "application/vnd.github+json" }
  })
    .then(res => res.json())
    .then(async repos => {
      if (repos.message) throw new Error(repos.message); // handle API error
      const selected = repos.filter(r => targetRepos.includes(r.name));

      for (const repo of selected) {
        let hasNotebook = false;
        try {
          const contentsRes = await fetch(repo.contents_url.replace('{+path}', ''), {
            headers: { "Accept": "application/vnd.github+json" }
          });
          if (contentsRes.ok) {
            const contents = await contentsRes.json();
            hasNotebook = Array.isArray(contents) &&
                          contents.some(file => file.name.endsWith('.ipynb'));
          }
        } catch {}

        const notebookIcon = hasNotebook || repo.language === "Jupyter Notebook" ? "🟠" : "";
        const languageBadge = repo.language ? `<span class="badge bg-secondary">${repo.language}</span>` : "";

        const card = document.createElement("div");
        card.className = "col-md-4 mb-4 px-1";
        card.innerHTML = `
          <div class="card h-100 shadow-sm">
            <div class="card-body d-flex flex-column">
              <h5 class="card-title">
                <a href="${repo.html_url}" target="_blank" rel="noopener">${repo.name}</a>
              </h5>
              <p class="card-text" style="color: gray;">${repo.description || "No description provided."}</p>
              <div class="mt-auto d-flex justify-content-between align-items-center">
                <div>${notebookIcon} ${languageBadge}</div>
                <div style="color: gray; font-size: 1.2em;">☆ ${repo.stargazers_count}</div>
              </div>
            </div>
          </div>`;
        container.appendChild(card);
      }
    })
    .catch(err => {
      console.error("GitHub API error:", err);
      container.innerHTML = "<p>Failed to load repositories.</p>";
    });
});
</script>
{% endraw %}


## Recent Service Roles


Convener AGU25: Coastal Subsidence and Relative Sea-Level Rise: Assessments, Processes, Projections, and Mitigation in Natural and Urban Environments

Co-convener: Understanding sea level changes: global to local, from past to future, 2023, EGU23, Vienna, Austria

Convener: Coastal Altimetry Workshop, 2023, Cadiz, Spain

 

## Teaching


Contributions to teaching the ‘Sea-Level Change’ course at Tulane

Contributions to teaching the ‘Oceanography and Satellite Altimetry’ course at TUM

Organisation of Summer school on Earth System Modeling (EaSyMS Summer School), Hamburg, 2018




## Discover how sea levels are changing and the work of ESA’s SL_cci+ team in this brief, insightful video:

<video controls autoplay muted playsinline style="width: 100%; height: auto;">
  <source src="https://storage.googleapis.com/esa-cfs-storage/2.0.2/stories/story-42/assets/coastalsealevel-HD1080.mp4" type="video/mp4">
  Your browser does not support the video tag.
</video>