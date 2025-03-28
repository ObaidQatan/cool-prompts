# Common Prompts

## Informative Code Comments

To analyze and add clear inline comments to uncommented code within a specified directory.

### Tested on: `claude sonnet 3.7 , gpt-4o , cusror-small`

### Prompt Starts

Add developer comments to this codebase. Follow the instructions:

### Refs:

- Target directory: `<target_dir> (required)`
- Readme path: `<readme_path> (default: "<target_dir>/README.md")`
- Max line length: `<max_length> (default: 120 characters)`

---

- Focus exclusively on uncommented code sections
- Keep comments brief (1-2 lines max per function/block)
- For functions: describe purpose and parameters
- For components: explain props and usage
- For complex logic: summarize the approach
- Update/create <readme_path> with comment notice
- Strictly no code modifications - only comments
- Cover all code types (functions, components, logic blocks)
- Never assume functionality beyond visible code
- Respect the maximum length of around <max_length> (if specified) for line breaks
- Always revise work and ensure consistent style
- Output list of touched files with change summary (e.g., X functions commented, Readme updated, etc.)

### Prompt Ends

---
