# karlberg.io

Professional portfolio website for Rickard Karlberg - Infrastructure Engineer

## 🚀 Overview

A modern, responsive portfolio website showcasing infrastructure engineering expertise, technical skills, and professional projects. Built with clean HTML, CSS, and vanilla JavaScript for optimal performance.

## ✨ Features

- **Responsive Design** - Mobile-first approach with seamless experience across all devices
- **Interactive Terminal** - Live Terraform code demonstration with typing animation
- **Modern UI/UX** - Clean, professional design with smooth animations and transitions
- **SEO Optimized** - Comprehensive meta tags for better search engine visibility
- **Performance Focused** - Lightweight, fast-loading static site
- **Accessibility** - ARIA labels and semantic HTML for better accessibility

## 🛠️ Tech Stack

- HTML5
- CSS3 (Custom properties, Grid, Flexbox)
- Vanilla JavaScript
- Font Awesome Icons
- Google Fonts (Inter, JetBrains Mono)

## 📋 Sections

- **Hero** - Introduction with interactive Terraform terminal demo
- **About** - Professional background and expertise
- **Skills** - Technical competencies organized by category:
  - Container Orchestration (Kubernetes, Docker)
  - Cloud Platforms (Azure, AWS, GCP)
  - Infrastructure as Code (Terraform, Ansible)
  - CI/CD & Automation
  - Monitoring & Observability
  - Security & Compliance
- **Projects** - Featured infrastructure projects with tech stacks
- **Contact** - Professional links and social profiles

## 🚀 Development

This is a static website deployed on Azure Static Web Apps. No build process required.

### Local Development

Simply open `src/index.html` in your browser or use a local server:

```bash
# Using Python
python -m http.server 8000

# Using Node.js http-server
npx http-server src/

# Then open http://localhost:8000
```

## 📁 Project Structure

```
karlberg-io/
├── src/
│   ├── index.html           # Main page
│   ├── 404.html             # Custom 404 page
│   ├── styles.css           # Stylesheet
│   ├── favicon.png          # Site icon
│   ├── routes.json          # Routing config
│   └── staticwebapp.config.json  # Azure SWA config
├── staticwebapp.config.json # Root SWA config
└── README.md
```

## 🌐 Deployment

Deployed to Azure Static Web Apps with automatic CI/CD via GitHub Actions.

## 📄 License

© 2026 Rickard Karlberg. All rights reserved.

## 🔗 Links

- Website: [karlberg.io](https://karlberg.io)
- GitHub: [@klbrg](https://github.com/klbrg)
- LinkedIn: [rickard-karlberg](https://www.linkedin.com/in/rickard-karlberg)