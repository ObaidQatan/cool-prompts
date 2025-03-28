# React + Vite + TS Prompts
Prompts in this document are specifically tailored for React + Vite + Typescript + Tailwind CSS projects. Feel free to adjust any instructions to fit your needs.

## Figma to Code
To convert a UI Figma design into code by providing the target Figma file URL or a node selection link (`CTRL/cmd + L` on a Figma frame to copy).

### Tested on: `claude sonnet 3.7`

### Prompt Starts
Convert this Figma design into code. Follow the instructions:

### Refs:

- Figma URL: `<figma_url>`
- Assets path: `<assets_path> (default: "@/assets/imgs/")`
- Components dir: `<components_dir> (default: "@/components")`
- Hooks dir: `<hooks_dir> (default: "@/hooks")`
- Class utility function: `<class_utility_fn> (default: "cn" from "@/lib/utils")`
- Image Placeholder: `<image_placeholder> (default: "Avatar component from "@/components/ui/avatar")`
- File naming: `<file_naming_convention> (default: kebab-cased, e.g., example-card.tsx)`
- Component naming: `<component_naming_convention> (default: PascalCase, e.g., ExampleCard)`
- Tailwind breakpoints: `<tailwind_breakpoints> (default: lg and max-lg)`
- Icons library: `<icons_lib> (default: Lucide, suffixed with Icon, e.g., PlusIcon)`
- Text content instructions: `<txt_guide> (default: "Hardcode all text content")`

---

- Optimize for both desktop and mobile (use Tailwind's <tailwind_breakpoints> breakpoints)
- Download required assets, and assets src should strictly be variables imported from <assets_path> directly, never use other directories like /public unless you're told to.
- Pay attention to places that require special hover behavior
- Code step by step and carefully pay attention to details
- Use Tailwind CSS, and use relative classes like start-/end- instead of left-/right- whenever possible to ensure responsiveness in both LTR and RTL directions
- Read the folder structure to get an idea what components we have
- The page works within a React Vite environment with proper TypeScript
- Use <icons_lib> for icons
- Use your deep thinking intelligence to ensure an accurately designed layout and style
- Text content instructions: <txt_inst>
- Pre-defined and commonly used components inside <components_dir> dir
- Pre-defined and commonly used hooks inside <hooks_dir> dir
- For conditional styles, use cn function imported from <class_utility_fn>
- For images that require a fallback placeholder, use the <image_placeholder>
- Don't create or modify any .md file
- Use <file_naming_convention> names for files and <component_naming_convention> for component names
- Follow the Figma design blindly, don't make things from your own, simply and strictly follow the Figma design
- Always revise what you have built at the end, if something is missing/broken, fix/download it

### Prompt Ends
---
