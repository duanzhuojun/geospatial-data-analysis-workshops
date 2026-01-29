---
layout: default
title: Workshop 1 - Getting Started with Thunderstorm datasets & Jupyter Notebook
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
  
  .schedule-section { 
    background: #f8f9fa; 
    padding: 1.2rem; 
    margin: 1rem 0; 
    border-radius: 5px; 
    border-left: 4px solid #3498db;
  }
  
  .code-example { 
    background: #f4f4f4; 
    padding: 1rem; 
    border-radius: 5px; 
    margin: 1rem 0;
  }
  
  .section {
    margin-bottom: 3rem;
  }
  
  .section h2 {
    color: #2c3e50;
    border-bottom: 2px solid #3498db;
    padding-bottom: 0.5rem;
    margin-bottom: 1.5rem;
  }
</style>

<div class="content-wrapper">

<nav class="nav-links">
  <a href="{{ site.baseurl }}/">🏠 Home</a>
  <a href="{{ site.baseurl }}/setup.html">⚙️ Setup</a>
  <a href="{{ site.baseurl }}/materials.html">📚 Materials</a>
  <a href="{{ site.baseurl }}/about.html">ℹ️ About</a>
  <div class="spacer"></div>
  <a href="{{ site.baseurl }}/workshops/workshop-1.html" style="background: #3498db; color: white; border-color: #3498db;">Workshop 1</a>
  <a href="{{ site.baseurl }}/workshops/workshop-2.html">Workshop 2</a>
  <a href="{{ site.baseurl }}/workshops/workshop-3.html">Workshop 3</a>
</nav>

<div class="main-content">

<div class="section">

<h1>Workshop 1: Getting Started with Thunderstorm Datasets & Jupyter Notebook</h1>

<p><strong>Duration:</strong> 1 hour | <strong>Level:</strong> Beginner</p>

<h2>Overview</h2>

<p>Set up your environment using Jupyter Notebook and explore real-world meteorological datasets to see what storm data looks like in practice.</p>

</div>

<div class="section">

<h2>Learning Objectives</h2>

<p>By the end of this workshop, you will be able to:</p>

<ul>
  <li>Understand the basics of Jupyter Notebook environment</li>
  <li>Work with Python libraries for data analysis (pandas, numpy)</li>
  <li>Load and explore real-world lightning and thunderstorm datasets</li>
  <li>Perform basic data manipulation and cleaning operations</li>
  <li>Create simple visualizations of meteorological data</li>
</ul>

</div>

<div class="section">

<h2>Prerequisites</h2>

<ul>
  <li>Basic Python knowledge</li>
  <li>Completed <a href="../setup.html">Setup Guide</a></li>
  <li>Downloaded <a href="../materials.html">Workshop Materials</a></li>
</ul>

</div>

<div class="section">

<h2>Instructions</h2>

<div class="schedule-section">

<h3>Preparation</h3>

<ol>
  <li>Set up your computer with Python interpreter and VS Code installed</li>
  <li>In VS Code, install the <strong>Jupyter extension</strong> from the Extensions Marketplace</li>
</ol>

</div>

<div class="schedule-section">

<h3>Jupyter Introduction</h3>

<ol>
  <li>Download the first notebook file: <a href="workshop1-code/intro-jupyter.ipynb" download><code>intro-jupyter.ipynb</code></a></li>
  <li>Read through the provided notes and run the code cells</li>
  <li>Complete the exercises at the end of the notebook</li>
</ol>

</div>

<div class="schedule-section">

<h3>Jupyter Activity: Work with a Real-World Lightning Dataset</h3>

<ol>
  <li>Download the starter notebook file: <a href="workshop1-code/jupyter_exercise.ipynb" download><code>jupyter_exercise.ipynb</code></a></li>
  <li>Download the dataset: <a href="workshop1-code/Salt_Lake_2020.csv" download><code>Salt_Lake_2020.csv</code></a></li>
  <li>Use Python to load, explore, and process the dataset in a Jupyter Notebook</li>
</ol>

</div>

</div>

</div>

</div>
