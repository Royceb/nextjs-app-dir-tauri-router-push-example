This is a [Next.js](https://nextjs.org/) project bootstrapped with [`create-next-app`](https://github.com/vercel/next.js/tree/canary/packages/create-next-app).

This app is a simple reproduction of an issue using router.push from next/navigation inside a tauri app.

## Steps to reproduce

1. Ran `npx create-next-app@latest --experimental-app`
2. Set up Tauri

   2.1: Ran `pnpm add -D @tauri-apps/cli`

   2.2: Added `tauri` to package.json scripts. Ran `pnpm tauri init`.

3. Updated next.config.js to use `output: "export"`.
4. Made a simple page at `app/examplePage/page.tsx`
5. Imported `next/navigation` in `app/page.tsx` and added a button that calls `router.push('/examplePage')`.
6. Ran `pnpm tauri dev` and clicked the button. The app navigated to the example page as expected and rendered it properly.
7. Ran `pnpm tauri build` and opened the app. Clicked the button. The app did naviate to the example page, but it did not render it properly. The page rendered code as text instead of rendering the page.

## Getting Started

Install

```
pnpm install
```

Run the development server for tauri:

```bash
pnpm tauri dev
```

The desktop app will open.

Run the development server for web:

```bash
pnpm dev
```

## Build

Build the desktop app to reproduce the issue

```bash
pnpm tauri build
```

Find and open the app.
