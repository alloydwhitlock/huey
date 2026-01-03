# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Type
Huey is a minimal Hugo blog theme that uses the Bulma CSS framework.

## Commands
- Run local server: `hugo server -D`
- Build site: `hugo`
- Create new content: `hugo new content/posts/my-post/index.md`
- Create new page: `hugo new content/about.md`

## Code Style Guidelines
- HTML: Follow semantic HTML5 conventions in layout files
- SCSS: Use Bulma variables and mixins when possible
- Markdown: Use standard markdown for content
- TOML: Use for configuration (config.toml, theme.toml)

## Structure Conventions
- Use page bundles for content organization
- Follow Hugo's naming conventions for layouts
- Place custom CSS in assets/css/extra/
- Image assets should be placed in content post bundles

## Best Practices
- Keep theme minimal and lightweight
- Maintain compatibility with Hugo version >= 0.154.2
- Follow Bulma documentation for CSS framework usage
- Ensure responsive design principles are followed