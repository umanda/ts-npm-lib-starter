## Developer's Guide: Building a TypeScript Package with Vite

### Introduction
Creating a TypeScript package can streamline the reuse of utility functions or complex code across multiple projects. This guide provides a step-by-step approach to building a TypeScript package using Vite, suitable for both frontend and backend applications.

### Prerequisites
   Ensure the following package versions or later:

- `typescript": "^5.2.2"`
- `"vite": "^5.0.8"`
- `"vue-tsc": "^1.8.25"`
- `"vite-plugin-dts": "^3.7.1"`
- `"vitest": "^0.28.5"`
- `"vitest: ^0.28.5"`

### Scaffolding the Project
1. **Create a New Vite Project:**
   ```bash
   npm create vite@latest
   ```
   Configure as follows:
   - Project name: `ts-npm-lib-starter`
   - Framework: `Vanilla`
   - Variant: `TypeScript`

   Initial folder structure:
   ```
   📦ts-npm-lib-starter
    ┣ 📂public
    ┣ 📂src
    ┣ 📜.gitignore
    ┣ 📜index.html
    ┣ 📜package.json
    ┗ 📜tsconfig.json
   ```

2. **Cleanup:**
   Delete `index.html`, `public` folder, and contents in `src`.

3. **Install Dependencies:**
   ```bash
   npm install
   ```

### Implementing Features
1. **Develop Utility Functions:**
   Create files `src/sum.ts`, `src/subtract.ts`, and implement functions.

2. **Export Functions:**
   Use `src/index.ts` to export all functions.

### Bundling the Package
1. **Install Development Dependencies:**
   ```bash
   npm install -D @types/node vite-plugin-dts
   ```

2. **Configure Vite:**
   Create `vite.config.ts` at the root with necessary configurations.

3. **Configure `package.json`:**
   Update fields like `main`, `module`, `types`, and `exports`.

### Versioning
1. **Semantic Versioning:**

   Use `npm version [patch/minor/major]` to update package version.
   ```
   npm version patch
   # Bumps the patch number like 0.0.0 -> 0.0.1

   npm version minor
   # Bumps the patch number like 0.0.x -> 0.1.0

   npm version major
   # Bumps the patch number like 0.x.y -> 1.0.0
   ```

### Setting Up Tests
1. **For Jest:**
   Install dependencies: `npm install -D jest @types/jest ts-jest`
   Configure Jest: `npx ts-jest config:init`
   Update `package.json` to add a test script.

2. **For Vitest:**
   Install Vitest: `npm install -D vitest`
   Configure in `vite.config.ts` and update `package.json`.

### Linting & Formatting
- Consider using ESLint and Prettier.
- Initialize ESLint: `npx eslint --init`
- Use `eslint-plugin-prettier` and `eslint-config-prettier` for integration.

### Publishing the Package

1. **Update `package.json`:**

   Add fields: `description`, `author`, `license`, `homepage`, `repository`, `bugs`, `keywords`.

2. **Publish:**
   ```bash
   npm publish
   ```

### Setting up the Local Development Environment

1. **Create vite project call "lib-testing-app" ( i.e. React)**
   ```bash
   npm create vite@latest
   ```

2. **Add ts-npm-lib-starter to global npm package folder :**
   ```bash
   cd ts-npm-lib-starter
   npm link
   ```
3. **Add ts-npm-lib-starter to global npm package folder :**
   ```bash
   cd lib-testing-app
   npm link ts-npm-lib-starter
   ```

### Additional Steps
- **Create `README.md`:** Describe usage and examples.
- **Add a `LICENSE` file:** Choose appropriate licensing.
- **Include `files` field in `package.json`:** Indicate what should be included in the final package.
- **Preview Package:** Use `npm pack --dry-run` to preview the package.

### Conclusion
This guide provides the essential steps for building and publishing a TypeScript package using Vite. Always refer to the official documentation for detailed instructions and best practices.