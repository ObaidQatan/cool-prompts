# Node.js + TS + Prisma ORM Prompts

## Database Model + Zod schema + Example CRUD

To create Prisma schemas with relevant zod schemas and example CRUD operations from specifications.
<b>NOTE:</b> Defining model fields wouldn't make sense in prompts, list required fields after running the prompt.

### Tested on: `claude sonnet 3.7`

### Prompt Starts

Generate this database model. Follow the instructions:

### Refs:

- Model name: `<model_name> (required, PascalCase, e.g., "UserAccount")`
- Suggets relevant fields: `<suggest_field> (default: No)`
- Relations: `<relations> (format: "RelatedModel:relationType", e.g., "Profile:oneToOne")`
- Indexes: `<indexes> (default: "id,createdAt", use "none" to disable)`
- Schema path: `<prisma_schema> (default: "@/prisma/schema.prisma")`
- Types dir: `<types_dir> (default: "@/types/db.ts")`
- Zod schema dir: `<schemas_dir> (default: "@/lib/schemas.ts")`
- Seed: `<seed_dir> (default: "@/prisma/seed.ts")`

---

- Read and analyze the current prisma schema in <prisma_schema> (if exists)
- Generate complete model definition in <prisma_schema>
- Use camelCase for field names (e.g., "userName")
- Include @@index([<indexes>]) (if <indexes> is not "none")
- Add relations according to the overall schema
- Mandatory fields: id (String @id @default(uuid())), createdAt (DateTime @default(now())), updatedAt (DateTime @updatedAt)
- Suggest fields relevant to the model according to what you see fit (if <suggest_field> is not "No")

- Create CRUD operations: findMany, create, update, delete
- Generate input/output zod schemas in <schemas_dir> for the created CRUD operations
- Generate corresponding z.inferred TypeScript types in <types_dir>, along with any other relevant types that might be required, except of prisma types that can be imported from @prisma/client
- Add JSDoc comments for all fields

- Distinguish between null (explicit empty) and undefined (not provided)
- Generate sample seed data in <seed_dir>
- Include 3 realistic seed examples per model, if possible

- Never use snake_case or PascalCase for field names
- Don't create duplicate relations
- Avoid any database vendor-specific syntax
- No arbitrary indexes beyond <indexes>

- List created/modified files
- Show model statistics (fields/relations/indexes count)
- Include seed data preview
- Verify schema relations diagram
- Always revise what you have built at the end, if something is missing/broken, fix/complete it

### Prompt Ends

---
