# First-Yarn-Typescript
Built from scratch React frontend and Express backend with TypeScript following tutorial: [https://halftheopposite.dev/post/app-yarn-typescript-esbuild-part-1](https://halftheopposite.dev/post/app-yarn-typescript-esbuild-part-1)

## Packages
- `common` used by both `app` and `server` (provide shared logic and variables)
- `app` is the React frontend
- `server` is the Express backend

## Steps
- No bootstrapper was used (eg: create-react-app, express-generator)
- Used one yarn.lock to manage dependencies in `app`, `common`, and `server` packages
  - can access workspaces via name (eg: add Express to server package.json: `yarn server add express`)
- Transpiled TypeScript with ESBuild (other bundlers: Webpack, Parcel, Rollup)
- Fixed tutorial path (change to import from common as opposed to @flapjack package - `import { APP_TITLE } from "../../common";`)