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
  <span style="flex-grow: 1;"></span>
  <a href="{{ site.baseurl }}/workshops/workshop-1.html" style="background: #3498db; color: white; border-color: #3498db;">Workshop 1</a>
  <a href="{{ site.baseurl }}/workshops/workshop-2.html">Workshop 2</a>
  <a href="{{ site.baseurl }}/workshops/workshop-3.html">Workshop 3</a>
</nav>



## Welcome

Welcome to the Geospatial Data Analysis Workshops series! These workshops introduce participants to data mining and geospatial analysis techniques applied to thunderstorm and severe weather studies.





## About the Workshops

Our workshops focus on:
- **Thunderstorm and Lightning Data Analysis**: Working with real-world meteorological datasets
- **Geospatial Analysis**: Spatial clustering, pattern recognition, and mapping techniques
- **Data Mining**: Extracting insights from large-scale environmental datasets
- **Reproducible Workflows**: Using modern tools and best practices for data science





## Learning Objectives

Participants will:
- Understand the structure of geospatial and meteorological datasets
- Apply data mining techniques to thunderstorm-related data
- Explore spatial and temporal patterns in lightning and weather events
- Gain hands-on experience with reproducible data analysis workflows





## Available Workshops

<div class="workshop-card">
  <h3>📍 <a href="workshops/workshop-1.html" style="color: #2c3e50; text-decoration: none;">Workshop 1: Introduction to Geospatial Data Analysis</a></h3>
  <p>Get started with fundamental concepts in geospatial data handling, coordinate systems, and basic lightning data analysis.</p>
  <p><strong>Duration:</strong> 3 hours | <strong>Level:</strong> Beginner</p>
</div>

<div class="workshop-card">
  <h3>🔬 <a href="workshops/workshop-2.html" style="color: #2c3e50; text-decoration: none;">Workshop 2: Advanced Spatial Analysis</a></h3>
  <p>Deep dive into spatial clustering algorithms, kernel density estimation, and pattern detection in severe weather data.</p>
  <p><strong>Duration:</strong> 3 hours | <strong>Level:</strong> Intermediate</p>
</div>

<div class="workshop-card">
  <h3>📈 <a href="workshops/workshop-3.html" style="color: #2c3e50; text-decoration: none;">Workshop 3: Time Series and Forecasting</a></h3>
  <p>Learn techniques for analyzing temporal patterns in thunderstorm data and building predictive models.</p>
  <p><strong>Duration:</strong> 3 hours | <strong>Level:</strong> Advanced</p>
</div>

</div>



## Prerequisites

- Basic knowledge of Python or R
- Familiarity with data analysis concepts
- Laptop with required software installed (see Setup Guide)


## Getting Started

1. Review the [Setup Guide](setup.html) to prepare your environment
2. Download the [workshop materials](materials.html)
3. Join our community discussion forum


## Contact

For questions or more information, please contact: [zhuoj.duan@gmail.com](mailto:zhuoj.duan@gmail.com)

