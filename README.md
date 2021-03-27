# First-Yarn-Typescript
Built from scratch React frontend and Express backend with TypeScript following tutorial: [https://halftheopposite.dev/post/app-yarn-typescript-esbuild-part-1](https://halftheopposite.dev/post/app-yarn-typescript-esbuild-part-1)

## Packages
- `common` used by both `app` and `server` (provide shared logic and variables)
- `app` is the React frontend
- `server` is the Express backend

## Writing Steps
- No bootstrapper was used (eg: create-react-app, express-generator)
- Used one yarn.lock to manage dependencies in `app`, `common`, and `server` packages
  - can access workspaces via name (eg: add Express to server package.json: `yarn server add express`)
- Fixed tutorial path (change to import from common as opposed to @flapjack package - `import { APP_TITLE } from "../../common";`)
- Transpiled TypeScript with ESBuild (other bundlers: Webpack, Parcel, Rollup)
- Added building with Docker (see Dockerfile and .dockerignore)
- Used GitHub Actions to auto-publish Docker image to GitHub Packages every push (see docker-publish.yml)
  - checkouts master/main branch
  - builds Docker image & publishes to repository's packages (GitHub Packages)
- Used GitHub Actions to auto-deploy to Heroku given HEROKU_EMAIL, HEROKU_API_KEY, HEROKU_APP_NAME(see heroku-deploy.yml)
  - added Repo Secrets as outlined [here](https://docs.github.com/en/actions/reference/encrypted-secrets#creating-encrypted-secrets-for-a-repository) - HEROKU_EMAIL, HEROKU_API_KEY, HEROKU_APP_NAME
  - script replaces GitHub Secrets with values from project's settings at buildtime
  - script deploys master branch to Heroku (uses jctaveras's GitHub Action from Marketplace )