# DaisyUI CSS Optimization Issue

## The Problem

When building this Nuxt project for production, we're encountering an issue with CSS optimization. Specifically:

1. The built pages are unnecessarily large (~43kb) due to included unused CSS classes
2. CSS purging doesn't seem to be working as expected
3. Many unused DaisyUI classes are being included in the final build

### What We've Tried

- Following the official [DaisyUI installation guide](https://daisyui.com/docs/install/)
- Comparing our setup with the [official Nuxt3 DaisyUI example](https://stackblitz.com/edit/daisyui-nuxt3?file=package.json)
- Building and previewing the project:
  ```bash
  npx nuxi build
  npx nuxi preview
  ```

### Current Behavior

When building the project:
- The index page is ~43kb (much larger than expected)
- The built output includes many unused CSS classes
- These unused classes don't appear anywhere in our source code

### What We Need

We need to find a way to ensure unused CSS classes are properly removed during the build process to optimize our bundle size.

---

## Standard Project Commands

### Setup

```bash
# npm
npm install

# pnpm
pnpm install

# yarn
yarn install

# bun
bun install
```

### Development

```bash
# npm
npm run dev

# pnpm
pnpm dev

# yarn
yarn dev

# bun
bun run dev
```

### Production

```bash
# npm
npm run build

# pnpm
pnpm build

# yarn
yarn build

# bun
bun run build
```

### Preview

```bash
# npm
npm run preview

# pnpm
pnpm preview

# yarn
yarn preview

# bun
bun run preview
```

## Additional Resources
- [Nuxt Documentation](https://nuxt.com/docs/getting-started/introduction)
- [Deployment Documentation](https://nuxt.com/docs/getting-started/deployment)
