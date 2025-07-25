---
title: Research
type: landing
sections:
  - block: portfolio
    content:
      title: Research Projects
      subtitle: view by theme
      text: |
        <center>We are broadly interested in the interactions among <strong>water, ecosystems, and people</strong>.</center><br>
        
        In terms of *Hydrologic Processes*, we currently have a strong focus on:
        - **Urban (Eco-)Hydrology**, with a number of projects focusing specifically on **Green Stormwater Infrastructure**
        - Hydrologic feedbacks, including **Surface Water-Groundwater** interactions and **Land-Atmosphere** interactions
        
        Our core *Approaches* included:
        - Developing novel **Integrated Modeling** tools to capture hydrologic processes
        - Incorporating **Community Engagement**
        <br><br>        
      filters:
        folders:
          - project
      buttons:
        - name: All
          tag: '*'
        - name: Urban (Eco-)Hydrology
          tag: urban-hydro
        - name: Green Stormwater Infrastructure
          tag: gsi
        - name: Surface Water-Groundwater
          tag: sw-gw
        - name: Land-Atmosphere
          tag: land-atmos
        - name: Integrated Modeling
          tag: modeling-tools
        - name: Community Engagement
          tag: community-engagement
      filter_default: 0
    design:
      view: compact
      columns: '1'
  - block: markdown
    content:
      title: ''
      subtitle: ''
      text: ''
    design:
      background:
        image:
          filename: conceptual_fig_updated_website.png
          filters:
              brightness: 1
          parallax: true
          position: center
          placement: 1
          size: contain
          text_color_light: true
      columns: "1"
      css_class: fullscreen
---