# AGENTS.md

Guidance for AI agents working in this repo. Humans: see [README.md](README.md).

## What this is

`quotes-service` 0.0.0: a 2014 skeleton of an Express quote service for a Ripple gateway. Two commits, one day. Abandoned.

## Stack

- JavaScript, ES6 in `src/`, transpiled to `build/` by gulp 3 and `gulp-6to5`.
- Runtime dependency: express ^4.10.6. No tests and no test framework.
- Era-appropriate runtime is Node 0.10 **(inference)**. Gulp 3 and `gulp-6to5` are known not to work on current Node.js.

## Layout

- `src/index.js` Express app and routes
- `src/controller.js` quote handlers (stubbed)
- `gulpfile.js` build
- `docs/STATUS.md` current state of the repo

## Commands

- Install: `npm install`
- Build: `npm run build` (gulp)
- Test: `npm test` only runs the build. There are no tests.
- Run: `npm start` (build, then `node build`). `.gitignore` does not list `build/`, so do not commit build output.
- Not verified on a current toolchain.

## Rules

- Add tests with every change (there are none yet).
- Never commit secrets.
- Use Conventional Commits.
- Keep `docs/STATUS.md` current.

## Agents may and may not

- May: improve docs, add tests, open PRs on a branch.
- May not: archive the repo, publish to npm, or rewrite git history without Steven.
