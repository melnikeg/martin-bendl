## Development

When starting the dev server, use background mode:

```
astro dev --background
```

Manage the background server with `astro dev stop`, `astro dev status`, and `astro dev logs`.

## Project Conventions

- This is a static Astro site using Tailwind CSS 4 through `@tailwindcss/vite`. Keep pages and reusable UI in `.astro` files unless a feature genuinely needs a client-side framework.
- Prefer semantic HTML, accessible labels and controls, and Astro's server-rendered output. Add client-side JavaScript only for interactions that need it; do not add framework hydration by default.
- Define component data and typed props in Astro frontmatter. Keep components focused and reuse existing components for shared site elements.
- Preserve the configured `site` and `base` in `astro.config.mjs`. Build links to local assets and pages so they continue to work when deployed under `/martin-bendl`.
- For Astro-specific APIs, configuration, or framework behavior, consult the Astro Docs MCP server configured in `.vscode/mcp.json` when the answer may depend on current Astro guidance. Prefer official Astro documentation over assumptions based on older versions.

## Styling

- Use Tailwind utility classes directly in markup as the default. Follow Tailwind CSS 4 conventions and reuse the theme tokens in `src/styles/global.css` (for example, `text-[var(--color-text-primary)]` and `bg-[var(--color-olive)]`).
- Keep `src/styles/global.css` for the Tailwind import, shared theme tokens, and truly site-wide rules. Do not move component styles into global CSS or create custom CSS classes as substitutes for ordinary Tailwind utilities.
- Use responsive, state, and accessibility variants (such as `md:`, `hover:`, `focus-visible:`, and `motion-reduce:`) where appropriate. Reserve arbitrary values for one-off designs not covered by the theme or standard utilities.
- Use component-scoped CSS only when a design cannot be expressed clearly with Tailwind utilities, such as complex selectors or animations. Keep such styles local to the component.
- Oсновной контейнер для всех новых страниц на эранах 1920px должен составлять 1280px.
- Все новые страницы и блоки пиши в лучших практиках SEO оптимизации. Максиально ориентируйся на такие поисковые запросы "Martin Bendl"

## Validation

- Run `npm run build` after code changes to verify Astro rendering and the production bundle.
- There is currently no test or lint script in `package.json`; do not assume one exists.

## Documentation

Full documentation: https://docs.astro.build

Consult these guides before working on related tasks:

- [Adding pages, dynamic routes, or middleware](https://docs.astro.build/en/guides/routing/)
- [Working with Astro components](https://docs.astro.build/en/basics/astro-components/)
- [Adding styles or using Tailwind](https://docs.astro.build/en/guides/styling/)
