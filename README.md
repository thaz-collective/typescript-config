# [@thaz/typescript-config](https://github.com/thaz-collective/typescript-config)

The purpose of this project is to have a common starting point for TypeScript configs for various projects types that thaz-collective projects use out of the box.

---

## Usage

- Install TypeScript and config:

    ```bash
    vp add -D typescript @thaz/typescript-config 
    ```

- Create a `tsconfig.json` with the following content

    ```json
    {
        "extends": [
            // Always include
            "@thaz/typescript-config/bundler.json", 
            // Use by default
            "@thaz/typescript-config/lib.json", 
            // Use when library/application needs the DOM
            "@thaz/typescript-config/lib-dom.json", 
            // Include when application uses react
            "@thaz/typescript-config/react.json", 
            // Provides common paths in applications
            "@thaz/typescript-config/paths.json"
        ], 
        // Add any folders/files to be included
        "include": [
            "src",
            "test",
            "mock",
            "vite.config.ts"
        ],
        "compilerOptions": {
            // Need to include types by default now
            // https://www.typescriptlang.org/docs/handbook/release-notes/typescript-6-0.html#types-now-defaults-to-
            "types": [
                "vite-plus/client",
                "node"
            ]
        }
    }
    ```

- So a full react example would look like:
    ```json
    {
        "extends": [
            "@thaz/typescript-config/bundler.json", 
            "@thaz/typescript-config/lib-dom.json", 
            "@thaz/typescript-config/react.json", 
            "@thaz/typescript-config/paths.json"
        ], 
        "include": [
            "src",
            "test",
            "mock",
            "vite.config.ts"
        ],
        "compilerOptions": {
            "types": [
                "vite-plus/client",
                "node"
            ]
        }
    }
    ```

---

## Acknowledgements

- [total-typescript/tsconfig](https://github.com/total-typescript/tsconfig) - A reference for configuring typescript
