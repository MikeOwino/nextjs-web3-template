# NextJS + Web3 + Zustand


The trick here for supporting universal Zustand is to separate the cases for the client and the server. When we are on the server we want to create a new store every time, otherwise different users data will be mixed up. If we are in the client we want to use always the same store. That's what we accomplish on `store.js`.

All components have access to the Zustand store using `useStore()` returned from zustand's `createContext()` function.

On the server side every request initializes a new store, because otherwise different user data can be mixed up. On the client side the same store is used, even between page changes.

## Preview

Preview the example live on [StackBlitz](http://stackblitz.com/):

[![Open in StackBlitz](https://developer.stackblitz.com/img/open_in_stackblitz.svg)](https://stackblitz.com/github/vercel/next.js/tree/canary/examples/with-zustand)

## Deploy your own

Deploy the example using [Vercel](https://vercel.com?utm_source=github&utm_medium=readme&utm_campaign=next-example):

[![Deploy with Vercel](https://vercel.com/button)](https://vercel.com/new/git/external?repository-url=https://github.com/vercel/next.js/tree/canary/examples/with-zustand&project-name=with-zustand&repository-name=with-zustand)

## How to use

Execute [`create-next-app`](https://github.com/vercel/next.js/tree/canary/packages/create-next-app) with [npm](https://docs.npmjs.com/cli/init) or [Yarn](https://yarnpkg.com/lang/en/docs/cli/create/) to bootstrap the example:

```bash
npx create-next-app --example with-zustand with-zustand-app
# or
yarn create next-app --example with-zustand with-zustand-app
```

Deploy it to the cloud with [Vercel](https://vercel.com/new) ([Documentation](https://nextjs.org/docs/deployment)).
