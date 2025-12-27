---
layout: default
title: Home
---

<style>
  .content-wrapper {
    max-width: 1200px;
    margin: 0 auto;
    padding: 2rem;
  }
  
  .nav-links {
    display: flex;
    flex-wrap: wrap;
    gap: 1rem;
    margin-bottom: 3rem;
    padding: 1.5rem;
    background: #f6f8fa;
    border-radius: 8px;
  }
  
  .nav-links a {
    padding: 0.6rem 1.2rem;
    background: white;
    border: 1px solid #e1e4e8;
    border-radius: 6px;
    text-decoration: none;
    color: #24292e;
    font-weight: 500;
    transition: all 0.2s;
  }
  
  .nav-links a:hover {
    background: #3498db;
    color: white;
    text-decoration: none;
    border-color: #3498db;
  }
  
  .workshop-card { 
    background: #f8f9fa; 
    padding: 1.5rem; 
    margin-bottom: 1.5rem; 
    border-radius: 8px; 
    border-left: 4px solid #3498db;
    transition: transform 0.2s, box-shadow 0.2s;
  }
  
  .workshop-card:hover {
    transform: translateY(-2px);
    box-shadow: 0 4px 12px rgba(0,0,0,0.1);
  }
  
  .workshop-card h3 { 
    margin-top: 0; 
    color: #2c3e50; 
  }
  
  .section {
    margin-bottom: 3rem;
    padding: 1.5rem 0;
  }
  
  .section h2 {
    color: #2c3e50;
    border-bottom: 2px solid #3498db;
    padding-bottom: 0.5rem;
    margin-bottom: 1.5rem;
    margin-top: 0;
  }
  
  .section p, .section ul {
    margin-bottom: 1rem;
  }
  
  ul {
    line-height: 1.8;
  }
  
  strong {
    color: #2c3e50;
  }
</style>

<div class="content-wrapper" markdown="1">

<nav class="nav-links">
  <a href="{{ site.baseurl }}/" style="background: #3498db; color: white; border-color: #3498db;">🏠 Home</a>
  <a href="{{ site.baseurl }}/setup.html">⚙️ Setup</a>
  <a href="{{ site.baseurl }}/materials.html">📚 Materials</a>
  <a href="{{ site.baseurl }}/about.html">ℹ️ About</a>
  <span style="flex-grow: 1;"></span>
  <a href="{{ site.baseurl }}/workshops/workshop-1.html">Workshop 1</a>
  <a href="{{ site.baseurl }}/workshops/workshop-2.html">Workshop 2</a>
  <a href="{{ site.baseurl }}/workshops/workshop-3.html">Workshop 3</a>
</nav>

<div class="section">

<h2>Welcome</h2>

Welcome to the Geospatial Data Analysis Workshops series! These workshops introduce participants to data mining and geospatial analysis techniques applied to thunderstorm and severe weather studies.


Our workshops focus on:
- **Thunderstorm and Lightning Data Analysis**: Working with real-world meteorological datasets
- **Geospatial Analysis**: Spatial clustering, pattern recognition, and mapping techniques
- **Data Mining**: Extracting insights from large-scale environmental datasets
- **Reproducible Workflows**: Using modern tools and best practices for data science

</div>

<div class="section">

<h2>Learning Objectives</h2>

Participants will:
- Understand the structure of geospatial and meteorological datasets
- Apply data mining techniques to thunderstorm-related data
- Explore spatial and temporal patterns in lightning and weather events
- Gain hands-on experience with reproducible data analysis workflows

</div>

<div class="section">

<h2>Available Workshops</h2>

<div class="workshop-card">
  <h3>📍 <a href="workshops/workshop-1.html" style="color: #2c3e50; text-decoration: none;">Workshop 1: Getting Started with Thunderstorm datasets & Jupyter Notebook</a></h3>
  <p>Set up your environment using Jupyter Notebook and explore real-world meteorological datasets to see what storm data looks like in practice.</p>
  <p><strong>Duration:</strong> 1 hours | <strong>Level:</strong> Beginner</p>
</div>

<div class="workshop-card">
  <h3>🔬 <a href="workshops/workshop-2.html" style="color: #2c3e50; text-decoration: none;">Workshop 2: Finding Patterns in Thunderstorm datasets</a></h3>
  <p>Use pandas to clean and organize data, then apply spatiotemporal clustering techniques to uncover patterns in thunderstorm activity.</p>
  <p><strong>Duration:</strong> 1 hours | <strong>Level:</strong> Intermediate</p>
</div>

<div class="workshop-card">
  <h3>📈 <a href="workshops/workshop-3.html" style="color: #2c3e50; text-decoration: none;">Workshop 3: Visualization</a></h3>
  <p>Create visualizations that help you understand the results and communicate Thunderstorm patterns clearly and effectively.</p>
  <p><strong>Duration:</strong> 1 hours | <strong>Level:</strong> Intermediate</p>
</div>

</div>

<div class="section">

<h2>Enrollment Details</h2>

- Basic knowledge of Python, Java, C, or R is recommended
- Please bring a laptop; if you are unable to do so, contact us in advance
- Open to students from all majors
- You may enroll in one, two, or all three workshops
</div>

<div class="section">

<h2>Getting Started</h2>

1. Review the [Setup Guide](setup.html) to prepare your environment
2. Download the [workshop materials](materials.html)
3. Join our community discussion forum

</div>

<div class="section">

<h2>Contact</h2>

For questions or more information, please contact: [gs1@jmu.edu]

</div>

</div>

