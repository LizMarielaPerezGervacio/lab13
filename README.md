# Lab 13 Astro React and component quality

VolumeSlider built with Astro 7, React 19 and Material UI 9, documented in
Storybook 10 and tested with Vitest. The history preserves the initial failing
CI runs, their fixes and two merged token pull requests.

## Requirements

Use Node.js 24 and npm 10 or newer. The `.nvmrc` selects Node 24.

## Run locally

```sh
npm ci
npm run dev
```

Open the URL printed by Astro, normally `http://localhost:4321`.
The page hydrates the React slider using `client:load`.

## Component catalog

```sh
npm run storybook
```

Open `http://localhost:6006` and select `UI/VolumeSlider`. The catalog contains
Low, High, SinLabel, ConTextoPersonalizado and Secondary, plus automatic Docs.

## Validate changes

```sh
npm run format
npm run format:check
npm run lint
npm run test:run
npm run build
```

Ten tests cover the slider and the six shared color tokens. GitHub Actions runs
tests, formatting, lint and the Astro build on pushes and pull requests to main.
`npm run build-storybook` produces the static component catalog.

## Lab history

- Initial defects: inverted callback value and changed label casing.
- Test fix: emit the selected value and preserve the supplied label.
- Quality fix: format stories, use const and remove an unused React import.
- PR #1 adds secondary and accent brand tokens.
- PR #2 adds feedback tokens and resolves the conflict through rebase.

The default label is `Volume`. `SinLabel` deliberately supplies an empty label
for the exercise; production consumers should provide an accessible name.
