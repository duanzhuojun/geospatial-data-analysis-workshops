---
layout: default
title: Home
---

<style>
  .content-wrapper {
    display: flex;
    max-width: 1400px;
    margin: 0 auto;
    padding: 2rem;
    gap: 2rem;
  }
  
  .nav-links {
    display: flex;
    flex-direction: column;
    gap: 0.5rem;
    width: 200px;
    flex-shrink: 0;
    padding: 1.5rem;
    background: #f6f8fa;
    border-radius: 8px;
    height: fit-content;
    position: sticky;
    top: 2rem;
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
    text-align: center;
  }
  
  .nav-links a:hover {
    background: #3498db;
    color: white;
    text-decoration: none;
    border-color: #3498db;
  }
  
  .nav-links .spacer {
    height: 1rem;
  }
  
  .main-content {
    flex: 1;
    min-width: 0;
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

<div class="content-wrapper">

<nav class="nav-links">
  <a href="{{ site.baseurl }}/" style="background: #3498db; color: white; border-color: #3498db;">🏠 Home</a>
  <a href="{{ site.baseurl }}/setup.html">⚙️ Setup</a>
  <a href="{{ site.baseurl }}/materials.html">📚 Materials</a>
  <a href="{{ site.baseurl }}/about.html">ℹ️ About</a>
  <div class="spacer"></div>
  <a href="{{ site.baseurl }}/workshops/workshop-1.html">Workshop 1</a>
  <a href="{{ site.baseurl }}/workshops/workshop-2.html">Workshop 2</a>
  <a href="{{ site.baseurl }}/workshops/workshop-3.html">Workshop 3</a>
</nav>

<div class="main-content" markdown="1">

<div class="section" markdown="1">

<h2>Welcome</h2>

Welcome to the Geospatial Data Analysis Workshops series! These workshops introduce participants to data mining and geospatial analysis techniques applied to thunderstorm and severe weather studies.

Our workshops focus on:

<ul>
  <li><strong>Thunderstorm and Lightning Data Analysis</strong>: Working with real-world meteorological datasets</li>
  <li><strong>Geospatial Analysis</strong>: Spatial clustering, pattern recognition, and mapping techniques</li>
  <li><strong>Data Mining</strong>: Extracting insights from large-scale environmental datasets</li>
  <li><strong>Reproducible Workflows</strong>: Using modern tools and best practices for data science</li>
</ul>

<h2>Acknowledgement</h2>
<p>The datasets used in this workshop series are from the NSF-funded research project: <em>RUI: Characterization of Aerosol Effects within an Urban Lightning Climatology across a North American Climatic Gradient</em> (Award Abstract #2104299), supported by the National Science Foundation (NSF), USA.</p>

</div>

<div class="section" markdown="1">

<h2>Learning Objectives</h2>

Participants will:
<ul>
  <li>Understand the structure of geospatial and meteorological datasets</li>
  <li>Apply data mining techniques to thunderstorm-related data</li>
  <li>Explore spatial and temporal patterns in lightning and weather events</li>
  <li>Gain hands-on experience with reproducible data analysis workflows</li>
</ul>

</div>

<div class="section" markdown="1">

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

<div class="section" markdown="1">

<h2>Enrollment Details</h2>

<ul>
  <li>Basic knowledge of Python, Java, C, or R is recommended</li>
  <li>Please bring a laptop; if you are unable to do so, contact us in advance</li>
  <li>Open to students from all majors</li>
  <li>You may enroll in one, two, or all three workshops</li>
</ul>

<div style="text-align: center;">
  <a href="https://docs.google.com/forms/d/1M06EsLJa7SuCjiA_yNynPSFug94BY_q-A-C73cp0YdI/edit" style="display: inline-block; margin-top: 1.5rem; padding: 0.8rem 1.5rem; background: #3498db; color: white; text-decoration: none; border-radius: 6px; font-weight: 500; transition: background 0.2s;" onmouseover="this.style.background='#2980b9'" onmouseout="this.style.background='#3498db'">📝 Enroll Now</a>
</div>

</div>


<div class="section" markdown="1">

<h2>Contact</h2>

For questions or more information, please contact: [gs1@jmu.edu]

</div>

</div>

</div>

