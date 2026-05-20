# tv-extension-template
A template to create and register your own extensions for Geomatic

## How to set up
1. Copy/clone/fork this repo.
  - Make sure Github actions are enabled in the fork.
2. Set up Github pages (`repo` -> `Settings` -> `Pages` -> `Build and deployment` -> Choose `Github Actions`).
3. Set the `name` and `description` properties in `package.json`.
4. Modify the properties in `manifest.json`.
5. Run `npm install` to install dependencies.
6. Run `npm run build` and check the newly created `dist` folder - it should have the `.mjs` file and `manifest.json` with details fetched from `src/index.ts`.
7. Start implementing your own extension functions in `src/my-function.ts`.
  - You can, and should, rename `my-function` to something more suitable.
  - You can also create more files in `src`, with each implementing functions.
  - Remember to add these files from `src/index.ts` to export them.

Every time `main` branch is updated, it will trigger the Github action defined in `.github/workflows/deploy.yml`. 

> Once the action is complete, the manifest file should be available at `https://username.github.io/extension-name/manifest.json`. You can use this link to load the extension after which the functions implemented will be available to use as commands in [Geomatic](https://www.tinyvolt.com/geomatic).