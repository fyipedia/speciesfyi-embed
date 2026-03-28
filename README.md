# speciesfyi-embed

[![npm](https://img.shields.io/npm/v/speciesfyi-embed)](https://www.npmjs.com/package/speciesfyi-embed)
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT)
[![Zero Dependencies](https://img.shields.io/badge/dependencies-0-brightgreen)](https://www.npmjs.com/package/speciesfyi-embed)

Embed **SpeciesFYI** widgets — species, glossary terms, interactive tools, and inline elements — on any website. **8 widget types**, zero dependencies, Shadow DOM style isolation, 4 built-in themes (light, dark, sepia, auto), 2 styles (modern, organic), and live data from the [SpeciesFYI](https://speciesfyi.com) database.

Every widget includes a "Powered by SpeciesFYI" backlink directing readers to the full reference.

> **Try the interactive widget builder at [widget.speciesfyi.com](https://widget.speciesfyi.com)**

## Quick Start

```html
<!-- Place widget div where you want it to appear -->
<div data-speciesfyi="entity" data-slug="species" data-theme="light"></div>

<!-- Load the embed script once, anywhere on the page -->
<script src="https://cdn.jsdelivr.net/npm/speciesfyi-embed@1/dist/embed.min.js"></script>
```

That's it. The widget fetches data from the SpeciesFYI API and renders with full style isolation.

## Widget Types

| Type | Usage | Description |
|------|-------|-------------|
| `entity` | `<div data-speciesfyi="entity" data-slug="..."></div>` | Entity detail card — species, bird, fish, plant, or dinosaur |
| `glossary` | `<div data-speciesfyi="glossary" data-slug="..."></div>` | Glossary term definition with cross-references |
| `guide` | `<div data-speciesfyi="guide" data-slug="..."></div>` | Guide summary card with key takeaways |
| `compare` | `<div data-speciesfyi="compare" data-slug="..."></div>` | Side-by-side entity comparison |
| `search` | `<div data-speciesfyi="search" data-slug="..."></div>` | Search box linking to the full database |
| `iucn-badge` | `<div data-speciesfyi="iucn-badge" data-slug="..."></div>` | IUCN conservation status badge with 9 status levels |
| `iucn-inline` | `<div data-speciesfyi="iucn-inline" data-slug="..."></div>` | Inline IUCN status colored pill |
| `taxonomy-inline` | `<div data-speciesfyi="taxonomy-inline" data-slug="..."></div>` | Italic scientific binomial name |

## Widget Options

| Attribute | Values | Default | Description |
|-----------|--------|---------|-------------|
| `data-speciesfyi` | entity, compare, glossary, guide, search, [tools] | required | Widget type |
| `data-slug` | e.g. "species" | — | Entity slug from the SpeciesFYI database |
| `data-theme` | light, dark, sepia, auto | light | Visual theme (`auto` follows OS preference) |
| `data-style` | modern, organic | modern | Widget design style |
| `data-size` | default, compact, large | default | Widget size |
| `data-placeholder` | any string | "Search Species..." | Search box placeholder |

## Themes

```html
<!-- Light (default) -->
<div data-speciesfyi="entity" data-slug="species" data-theme="light"></div>

<!-- Dark -->
<div data-speciesfyi="entity" data-slug="species" data-theme="dark"></div>

<!-- Sepia -->
<div data-speciesfyi="entity" data-slug="species" data-theme="sepia"></div>

<!-- Auto — follows OS dark/light preference -->
<div data-speciesfyi="entity" data-slug="species" data-theme="auto"></div>
```

## Styles

```html
<!-- Modern (default) — clean lines, rounded corners, accent gradients -->
<div data-speciesfyi="entity" data-slug="species" data-style="modern"></div>

<!-- Organic — natural curves, earth-tone aesthetics, field-guide look -->
<div data-speciesfyi="entity" data-slug="species" data-style="organic"></div>
```

## Web Components (Custom Elements)

As an alternative to `data-*` attributes, you can use native HTML custom elements:

```html
<!-- Custom element form -->
<speciesfyi-entity slug="species" theme="light"></speciesfyi-entity>
<speciesfyi-compare slugs="species,other-slug"></speciesfyi-compare>
<speciesfyi-search placeholder="Search Species..."></speciesfyi-search>

<script src="https://cdn.jsdelivr.net/npm/speciesfyi-embed@1/dist/embed.min.js"></script>
```

Use `style-variant` (not `style`) to avoid conflicts with the HTML reserved `style` attribute.

## Examples

### Entity Card

```html
<div data-speciesfyi="entity" data-slug="species" data-theme="light"></div>
<script src="https://cdn.jsdelivr.net/npm/speciesfyi-embed@1/dist/embed.min.js"></script>
```

### Side-by-Side Comparison

```html
<div data-speciesfyi="compare" data-slugs="species,other-slug"></div>
<script src="https://cdn.jsdelivr.net/npm/speciesfyi-embed@1/dist/embed.min.js"></script>
```

### Search Box

```html
<div data-speciesfyi="search" data-placeholder="Search Species..."></div>
<script src="https://cdn.jsdelivr.net/npm/speciesfyi-embed@1/dist/embed.min.js"></script>
```

### Glossary Term

```html
<div data-speciesfyi="glossary" data-slug="example-term" data-theme="light"></div>
<script src="https://cdn.jsdelivr.net/npm/speciesfyi-embed@1/dist/embed.min.js"></script>
```

## CDN Options

### jsDelivr (recommended — global CDN, auto-updates with npm)

```html
<script src="https://cdn.jsdelivr.net/npm/speciesfyi-embed@1/dist/embed.min.js"></script>
```

### Specific version (production stability)

```html
<script src="https://cdn.jsdelivr.net/npm/speciesfyi-embed@1.0.0/dist/embed.min.js"></script>
```

### npm (for bundlers)

```bash
npm install speciesfyi-embed
```

```javascript
import 'speciesfyi-embed';
```

## Technical Details

- **Shadow DOM**: Complete style isolation — no CSS conflicts with your site
- **Zero dependencies**: No jQuery, React, or any external library
- **2 styles**: Modern (accent gradients) and Organic (natural curves, field-guide aesthetic)
- **4 themes**: Light, Dark, Sepia, Auto (OS preference detection)
- **CORS**: SpeciesFYI API has CORS enabled for all origins
- **MutationObserver**: Works with dynamically added elements (SPAs)
- **IntersectionObserver**: Lazy loading — widgets only fetch when entering viewport (200px margin)
- **Rich Snippets**: DefinedTerm JSON-LD injected for glossary widgets
- **Bundle size**: Tree-shaken per site — only includes tools available on SpeciesFYI

## Learn More About Species

Visit [speciesfyi.com](https://speciesfyi.com) — SpeciesFYI is a comprehensive species reference with interactive tools, guides, and developer resources.

- **API docs**: [speciesfyi.com/developers/](https://speciesfyi.com/developers/)
- **Widget builder**: [widget.speciesfyi.com](https://widget.speciesfyi.com)
- **npm package**: [npmjs.com/package/speciesfyi-embed](https://www.npmjs.com/package/speciesfyi-embed)
- **GitHub**: [github.com/fyipedia/speciesfyi-embed](https://github.com/fyipedia/speciesfyi-embed)

## Nature FYI Family

Part of [FYIPedia](https://fyipedia.com) — open-source developer tools ecosystem. Nature FYI covers species taxonomy, ornithology, marine biology, botany, and paleontology. Hub: [naturefyi.com](https://naturefyi.com).

| Site | Domain | Focus | Package |
|------|--------|-------|---------|
| **SpeciesFYI** | [speciesfyi.com](https://speciesfyi.com) | Species taxonomy, biodiversity, IUCN conservation status | **[npm](https://www.npmjs.com/package/speciesfyi-embed)** |
| BirdFYI | [birdfyi.com](https://birdfyi.com) | 11,251 birds, biometrics, conservation, habitats | [npm](https://www.npmjs.com/package/birdfyi-embed) |
| FishFYI | [fishfyi.com](https://fishfyi.com) | 35,729 fish, game fishing, aquarium care, compatibility | [npm](https://www.npmjs.com/package/fishfyi-embed) |
| PlantFYI | [plantfyi.com](https://plantfyi.com) | 379,774 plants, hardiness zones, bloom seasons, gardening | [npm](https://www.npmjs.com/package/plantfyi-embed) |
| DinoFYI | [dinofyi.com](https://dinofyi.com) | 6,142 dinosaurs, geological periods, paleontology | [npm](https://www.npmjs.com/package/dinofyi-embed) |

## License

MIT — see [LICENSE](./LICENSE).

Built with care by [FYIPedia](https://fyipedia.com).
