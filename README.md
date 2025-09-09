# Tekion IT Status Page

A Hugo-based status page for monitoring Tekion's IT infrastructure and services.

## Overview

This is a static status page built with [Hugo](https://gohugo.io/) using the [cState theme](https://github.com/cstate/cstate). It provides real-time status information for various IT services and infrastructure components across Tekion's global offices.

## Features

- **Service Status Monitoring**: Track operational status of offices, infrastructure, and applications
- **Incident Management**: Display and manage service incidents with detailed timelines
- **Responsive Design**: Mobile-friendly interface with dark mode support
- **Static Site Generation**: Fast, secure, and reliable using Hugo
- **Multiple Categories**: Organized by Offices, IT Infrastructure, URLs/Websites, and Corporate Apps

## Quick Start

### Prerequisites

- [Hugo](https://gohugo.io/installation/) (Extended version recommended)
- Git

### Local Development

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd AzurePagePOC
   ```

2. **Start the Hugo development server**
   ```bash
   hugo server
   ```

3. **Access the status page**
   Open your browser to: http://localhost:1313

## Project Structure

```
├── config.yml              # Main Hugo configuration
├── content/
│   ├── issues/             # Incident markdown files
│   ├── it-internal/        # Internal IT documentation
│   ├── pages/              # Additional pages
│   ├── security/           # Security-related content
│   └── sla/                # SLA documentation
├── data/
│   └── services.json       # Service status data
├── layouts/                # Custom Hugo templates
├── static/                 # Static assets (images, CSS, etc.)
├── themes/cstate/          # cState theme
└── public/                 # Generated site (auto-created)
```

## Configuration

### Services

Services are defined in `data/services.json`. Each service has:
- `name`: Display name
- `status`: Current status (operational, disrupted, down)
- `category`: Service category
- `lastUpdated`: Last update timestamp (optional)

### Categories

Service categories are configured in `config.yml` under `params.categories`:
- **Offices**: Physical office locations
- **IT Cloud Infrastructure**: Servers and cloud services
- **IT Internal**: Internal tools and systems
- **URLs/Websites**: Public-facing websites
- **Corp Apps Services**: Corporate applications

### Systems

Individual systems/services are listed in `config.yml` under `params.systems`.

## Managing Content

### Creating Incidents

Create new incident files in `content/issues/` with the following frontmatter:

```yaml
---
title: "Incident Title"
date: 2025-09-01T10:00:00+05:30
resolved: false
severity: disrupted  # notice, disrupted, down
affected:
  - Service Name 1
  - Service Name 2
section: issue
resolvedWhen: ""  # Set when resolved
---

Incident description and updates go here.
```

### Updating Service Status

Edit `data/services.json` to update service statuses:

```json
{
  "services": [
    {
      "name": "Service Name",
      "status": "operational",
      "category": "IT Cloud Infrastructure",
      "lastUpdated": "2025-09-01T10:00:00.000Z"
    }
  ]
}
```

## Deployment

### Netlify

The project includes `netlify.toml` for easy Netlify deployment:

1. Connect your repository to Netlify
2. Build command: `hugo`
3. Publish directory: `public`

### Vercel

The project includes `vercel.json` for Vercel deployment:

1. Connect your repository to Vercel
2. Framework preset: Hugo
3. Build command: `hugo`
4. Output directory: `public`

### Manual Build

```bash
hugo --minify
```

The generated site will be in the `public/` directory.

## Customization

### Branding

- Update `config.yml` with your organization details
- Replace `tekionlogo.png` with your logo
- Modify colors in `config.yml` under `params`

### Theme

This project uses the cState theme. For advanced customization:
- Override theme templates in `layouts/`
- Add custom CSS in `static/`
- Modify theme configuration in `config.yml`

## Support

For issues related to:
- **Hugo**: [Hugo Documentation](https://gohugo.io/documentation/)
- **cState Theme**: [cState GitHub](https://github.com/cstate/cstate)
- **This Implementation**: Create an issue in this repository

## License

This project uses the cState theme which is licensed under the MIT License.
