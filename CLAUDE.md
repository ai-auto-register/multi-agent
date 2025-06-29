# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Development Commands

**Package Management & Development:**
- `bun dev` - Start development server
- `bun run build` - Production build with type checking  
- `bun lint` - Run ESLint with auto-fix
- `bun run format` - Format code with Prettier

## Architecture Overview

This is a Vue 3 + TypeScript multi-agent system interface built with modern tooling:

**Core Stack:**
- Vue 3.5+ with Composition API (script setup syntax)
- TypeScript with strict configuration
- Vite 7.0+ for build tooling
- Bun as package manager

**UI Architecture:**
- Tailwind CSS 4.1+ for styling
- Naive UI component library for Vue 3
- Lucide Vue Next for icons

**State & Routing:**
- Pinia stores using Composition API style
- Vue Router 4.5+ for client-side routing
- Path aliases: `@/` maps to `./src/`

## Component Patterns

**UI Components:**
- Use Naive UI components with on-demand imports
- TypeScript interfaces for all props
- Follow Vue 3 Composition API patterns

**Styling Conventions:**
- Use Tailwind utility classes
- Naive UI theme customization when needed
- Dark mode support through Naive UI's built-in theme system

## Key Application Features

**TopBar Navigation:**
- Multi-agent system branding with Bot icon
- Three main action buttons: 会话管理 (Session Management), AI角色 (AI Roles), 设置 (Settings)
- Uses Naive UI NButton components with ghost variant and icons
- Responsive flex layout with proper spacing

**Planned Feature Areas:**
- Session management functionality
- AI role configuration
- System settings interface

## Development Notes

**TypeScript Configuration:**
- Split config: app (`tsconfig.app.json`) and node (`tsconfig.node.json`)
- Strict type checking enabled
- Path mapping configured for clean imports

**Code Quality:**
- ESLint with Vue + TypeScript rules
- Prettier for consistent formatting
- Vue DevTools available in development

**Component Development:**
- Use Composition API throughout
- Define TypeScript interfaces for props
- Import Naive UI components on-demand for better performance
- Leverage path aliases for imports (`@/components`, `@/lib`, etc.)