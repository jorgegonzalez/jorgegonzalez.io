# jorgegonzalez.io

Personal site for Jorge R. Gonzalez — engineering leader, builder of [Ginyu](https://www.ginyu.io) and [Probed](https://probed.chat).

Built with [Astro](https://astro.build) and deployed on [Vercel](https://vercel.com). Dark, minimal, single-page — a sibling to ginyu.io.

## Develop

```sh
bun install
bun dev          # http://localhost:4321
```

## Build

```sh
bun run build    # outputs to dist/
bun run preview
```

## Structure

```
public/                       static assets (favicon, manifest)
src/layouts/Base.astro        nav, footer, global styles, fonts
src/pages/index.astro         the whole site — content lives in the frontmatter arrays
```

Content (current work, experience, projects, skills) is plain data at the top of
`src/pages/index.astro`. Edit those arrays to update the site.
