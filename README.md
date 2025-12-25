# Whether Weather

Whether Weather is a static weather dashboard built using HTML, CSS (Bulma framework), vanilla JavaScript and Eleventy as a static site generator to build and deploy the site.

## Project Overview

Whether Weather allows users to view weather information for multiple cities, navigate from a dashboard to individual city focus pages, and select favourite cities via a user preferences UI.

## Features

- **Dashboard page**
  - Displays multiple cities using Bulma cards
  - Each city links to a detailed City Focus page

- **City Focus pages**
  - Separate page per city (Dublin, London, Paris, Berlin, Rome, Athens)
  - Displays:
    - Current weather
    - Temperature
    - Wind speed
    - Weekly forecast
  - Consistent layout using Eleventy templates

- **User Preferences page**
  - Allows users to select favourite cities via checkboxes
  - UI only (preferences are not saved, as required)

- **Reusable templates**
  - Layouts and partials used to avoid repeated markup
  - Shared navbar, footer, and city card components

- **Responsive UI**
  - Styled using the Bulma CSS framework
  - Works on mobile and desktop screen sizes

---

## Project Structure

```bash
├── _includes/
│   ├── layout.njk
│   ├── navbar.njk
│   ├── footer.njk
│   └── city-card-component.njk
├── city/
│   ├── dublin.njk
│   ├── london.njk
│   ├── paris.njk
│   ├── berlin.njk
│   ├── rome.njk
│   └── athens.njk
├── index.njk
├── dashboard.njk
├── preferences.njk
├── css/
│   └── styles.css
├── images/
├── .eleventy.js
├── package.json
├── package-lock.json
└── README.md
```

---

## Technologies Used

- [Eleventy (11ty)](https://www.11ty.dev/) – Static site generator
- [Nunjucks](https://mozilla.github.io/nunjucks/) – Templating language
- [Bulma](https://bulma.io/) – CSS framework
- HTML5 / CSS3
- JavaScript (minimal, for UI behaviour)
- GitHub – Version control
- Netlify – Deployment

---

## Getting Started

### Prerequisites

- **Node.js** (v18+ recommended)
- npm or yarn
- A modern web browser

### Installation

1. **Clone the repository**

    ```
    git clone https://github.com/sarahjameson/whether-weather.git
    cd city-explorer
    ```

2. **Install dependencies**

    ```
    npm install
    ```

3. **Run the development server**

   Using npx (recommended):

    ```
    npx @11ty/eleventy --serve
    ```

   Or if Eleventy is installed globally:

    ```
    eleventy --serve
    ```

4. **View the site**

   Open your browser and navigate to:

    http://localhost:8080

   Eleventy will:

- Watch for file changes
- Rebuild automatically
- Live reload the browser

## Development

### Eleventy Configuration

The `.eleventy.js` file defines how Eleventy processes the site:

    ```
    module.exports = function (eleventyConfig) {
      eleventyConfig.addPassthroughCopy("css");
      eleventyConfig.addPassthroughCopy("images");
    };
    ```

### Making Changes

- Edit `.njk` templates or components
- Update styles in `css/styles.css`
- Eleventy automatically rebuilds on save
- View updates instantly in the browser

> **Note:** Do not edit files inside the `_site/` directory. It is regenerated on every build.

### Useful Commands

    # Build the site once
    ```
    npx @11ty/eleventy
    ```

    # Build and serve with live reload
    ```
    npx @11ty/eleventy --serve
    ```

    # Debug build output
    ```
    npx @11ty/eleventy --quiet=false
    ```

## Build & Deployment

### Production Build

    ```
    npx @11ty/eleventy
    ```

The production-ready site will be generated in the `_site/` directory.

### Deployment Options

**Netlify (Recommended)**

- Build command: `npx @11ty/eleventy`
- Publish directory: `_site`
- Automatic deploys on every push

**Vercel**

- Import the GitHub repository
- Auto-detects Eleventy
- Zero-config deployment

**GitHub Pages**

    ```
    npx @11ty/eleventy
    npx gh-pages -d _site
    ```

**Manual Deployment**

- Build the site
- Upload the contents of `_site/` to your hosting provider

## Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/new-feature`)
3. Commit your changes (`git commit -m 'Add new feature'`)
4. Push to the branch
5. Open a Pull Request

## License

This project is open source and intended for educational and personal use.

## Author

- Sarah Jameson

## Acknowledgments

- [Eleventy](https://www.11ty.dev/) for the fast static site generator
- [Nunjucks](https://mozilla.github.io/nunjucks/templating.html) for flexible templating
- [Bulma](https://bulma.io/) for the responsive layout and clear design
- [Unsplash](https://unsplash.com/) for images
- Inspired by modern city guide, travel websites and [Dotify project website](https://github.com/johnrellis/dotify-html) built by John Rellis
