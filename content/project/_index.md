---
title: Research
type: landing
sections:
  - block: portfolio
    content:
      title: Research Projects
      subtitle: view by theme
      text: |
        <center>We are broadly interested in the interactions among <strong>water, ecosystems, and people</strong>.</center>.
        
        <div style="display: flex; gap: 2rem;">
        <div style="flex: 1;">
        Our core <strong>research themes</strong> include:
        <ul>
        <li>Safeguarding Natural Ecosystems</li>
        <li>Sustainably Managing Urban Stormwater</li>
        <li>Increasing Resilience to Hydrologic Hazards</li>
        </ul>
        </div>

        <div style="flex: 1;">
        The <strong>tools and approaches</strong> we use include:
        <ul>
        <li>Hydrologic Modeling</li>
        <li>Empirical Data (including field and lab data collection)</li>
        <li>Stakeholder Engagement</li>
        </ul>
        </div>
        </div>
        
                
      filters:
        folders:
          - project
      buttons:
        - name: All
          tag: '*'
        - name: Safeguarding Natural Ecosystems
          tag: ecosystems
        - name: Sustainably Managing Urban Stormwater
          tag: stormwater
        - name: Increasing Resilience to Hydrologic Hazards
          tag: resilience
        - name: Hydrologic Modeling
          tag: modeling
        - name: Empirical Data
          tag: data
        - name: Stakeholder Engagement
          tag: engagement
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