# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

**Quartz v4** is a static site generator (SSG) for publishing digital gardens and notes as websites. It features a plugin-based architecture with a content processing pipeline: parse → filter → emit.

**Key tech stack**: TypeScript, Node.js (v22+), esbuild, Preact, unified/remark/rehype ecosystem for markdown processing.

## Development Commands

### Building and Serving
- `npm run docs` - Build and serve the docs site for testing
- `npm run quartz build` - Build the site once
- `npm run quartz build --serve` - Build and serve the site (watch mode)
- `npm run quartz create [path]` - Create a new note

### Code Quality
- `npm run check` - Type check (tsc) and prettier format check (run before committing)
- `npm run format` - Format all code with prettier
- `npm run test` - Run all tests (tsx test runner)
- `npm run test [file]` - Run tests in a specific file (e.g., `npm run test quartz/util/path.test.ts`)

### Performance
- `npm run profile` - Profile build performance with 0x

### Requirements
- Node.js v22+
- npm v10.9.2+

## Architecture Overview

### High-Level Pipeline

The core content processing happens in three stages:

1. **Parse** (`quartz/processors/parse.ts`): Convert markdown files to AST using remark
2. **Filter** (`quartz/processors/filter.ts`): Remove content based on filters (e.g., RemoveDrafts)
3. **Emit** (`quartz/processors/emit.ts`): Generate HTML pages using emitters

### Key Directories

- **`quartz/build.ts`** - Main build orchestration with watch mode support (see `startWatching()`)
- **`quartz/plugins/`** - Plugin system with three categories:
  - `transformers/` - Process markdown (e.g., FrontMatter, SyntaxHighlighting, GitHubFlavoredMarkdown)
  - `filters/` - Filter content (e.g., RemoveDrafts)
  - `emitters/` - Generate output (e.g., ContentPage, Static, Favicon)
- **`quartz/components/`** - Preact UI components (renderPage.tsx is the main layout)
- **`quartz/util/`** - Utilities (path.ts, fileTrie.ts for file operations; ctx.ts for build context)
- **`quartz/cli/`** - CLI handlers (args parsing, command implementations)
- **`quartz.config.ts`** - User-facing configuration file (plugins, theme, locale, etc.)

### Configuration System

- Users configure Quartz in `quartz.config.ts` following the `QuartzConfig` type (in `quartz/cfg.ts`)
- Plugins are instantiated from the config during build
- Theme colors and typography are defined in `configuration.theme`

### Testing

- Tests use tsx's built-in test runner (`node --test`)
- Test files: `quartz/util/path.test.ts`, `quartz/util/fileTrie.test.ts`
- Run single test file: `npm run test quartz/util/path.test.ts`

## Common Patterns and Notes

### Plugin Development
Plugins implement one of three interfaces from `quartz/plugins/types.ts`:
- **Transformer**: Modifies files in the processing pipeline
- **Filter**: Controls which files make it to emitters
- **Emitter**: Generates output files

### Markdown Processing
The remark/rehype ecosystem handles markdown:
- **Transformers** use remark (AST) for markdown-level modifications
- **Emitters** convert to HTML via rehype pipeline

### File Path Handling
Use utilities from `quartz/util/path.ts`:
- `FilePath` - Branded type for normalized paths
- `slugifyFilePath()` - Convert file paths to URL slugs
- `joinSegments()` - Join path segments safely

### Build Context
The `BuildCtx` type (in `quartz/util/ctx.ts`) is passed through the pipeline and contains:
- `allSlugs`, `allFiles` - Metadata about all content
- `cfg` - The configuration
- `argv` - CLI arguments

### Incremental Builds
In watch mode, the build tracks changes via `ContentMap` in build.ts. The `ChangeEvent` type tracks file add/modify/delete operations.

## Important Notes

- Always run `npm run check` before committing to catch type errors and formatting issues
- The build is multi-threaded (see `workerpool` in dependencies) for performance
- Custom OG image generation is enabled in the config but can be commented out to speed up builds
- The project uses esbuild's SASS plugin for styling
