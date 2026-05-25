# Project Conventions Discovery

**Question:** What conventions are used in this project for naming, component architecture, key files, and code patterns?

---

## 1. Naming Conventions

- **Files:**
  - PascalCase for components ([codebase/src/App.js](codebase/src/App.js))
  - Lower-case for entry points ([codebase/src/index.js](codebase/src/index.js))
  - Lower-case with hyphens for public assets ([codebase/public/manifest.json](codebase/public/manifest.json))
- **Variables/Constants:**
  - camelCase ([preferredColorScheme](codebase/src/App.js), [colorScheme](codebase/src/App.js), [setColorScheme](codebase/src/App.js), [toggleColorScheme](codebase/src/App.js))
- **Functions/Methods:**
  - camelCase ([toggleColorScheme](codebase/src/App.js), [useHotkeys](codebase/src/App.js), [useColorScheme](codebase/src/App.js))
- **Components:**
  - PascalCase ([App](codebase/src/App.js))
- **Directories:**
  - lower-case, no separators ([codebase/src](codebase/src), [codebase/public](codebase/public))

## 2. Component Architecture

- **Framework:** React ([codebase/src/App.js](codebase/src/App.js))
- **Style:** Function components with hooks ([useState](codebase/src/App.js), [useEffect](codebase/src/App.js), [useRef](codebase/src/App.js))
- **Class Components:** never use
- **Example:** [codebase/src/App.js](codebase/src/App.js)

## 3. Key Files

- **Entry Points:**
  - [codebase/src/index.js](codebase/src/index.js) (main JS entry)
  - [codebase/src/App.js](codebase/src/App.js) (main app component)
  - [codebase/public/index.html](codebase/public/index.html)
- **Config:**
  - [codebase/package.json](codebase/package.json)
  - [codebase/public/manifest.json](codebase/public/manifest.json)
  - [codebase/public/robots.txt](codebase/public/robots.txt)
- **Documentation:**
  - [README.md](README.md) (root)
  - [codebase/README.md](codebase/README.md)
  - [AGENTS.md](AGENTS.md)

## 4. Code Patterns

- **State Management:** React hooks ([useState](codebase/src/App.js), [useRef](codebase/src/App.js), [useEffect](codebase/src/App.js)); no Redux/Context found
- **Import/Export:** ES6 modules with grouped imports ([codebase/src/App.js](codebase/src/App.js))
- **UI Library:** Mantine UI components and theming ([MantineProvider](codebase/src/App.js), [ColorSchemeProvider](codebase/src/App.js))
- **Folder Organization:** Type-based ([codebase/src](codebase/src) for source, [codebase/public](codebase/public) for static)
- **Error Handling:** Minimal; no try/catch or error boundaries found
- **Testing:** No test files or patterns found (unknown)

---

**Gaps/Unknowns:**
- No global state management (Redux/Context) found
- No test files or testing patterns found
- Error handling approach is minimal/unclear

---

**Evidence links:** All claims are linked to specific files using workspace-relative paths.
