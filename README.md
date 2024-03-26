# `workers-types` `Env` POC

This POC shows a simple example on how an `Env` type could be defined in the `@cloudflare/workers-types` package and extended/used externally (one of the main use cases being `getPlatformProxy`).

In `src/index.ts` you can see the `Env` type being expanded:
```ts
declare module '@cloudflare/workers-types/base' {
	interface Env {
		MY_VAR: number;
	}
}
```

Such expansion could be also implemented opt-in by `wrangler types`.

___

As I mentioned one of the biggest benefits of this would be the possible customization of the `Env` interface externally in combination with `getPlatformProxy`.

For example frameworks/libraries using `getPlatformProxy` could, without any change on their part, allow developers to customize their `Env` type (similarly to this [example](https://github.com/dario-piotrowicz/nitro-generic-wrangler-env-type-example)).

Related discussion: https://github.com/pi0/nitro-cloudflare-dev/pull/13

