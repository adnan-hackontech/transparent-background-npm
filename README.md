# Transparent Background (npm)

[![](https://img.shields.io/npm/v/transparent-background)](https://www.npmjs.com/package/transparent-background)

`transparent-background` lets you **easily remove backgrounds** from images powered by [InSPyReNet (ACCV 2022)](https://github.com/xuebinqin/U-2-Net)

This package **requires Python installed system-wide** and will install and run the tool locally.

Thanks to @plemeri for creating [transparent-background](https://github.com/plemeri/transparent-background)

```bash
pnpm install transparent-background
yarn add transparent-background
npm install transparent-background
```

## Example

```ts
import * as fs from "fs/promises";
import { transparentBackground } from "transparent-background";

// const fs = require("fs/promises");
// const { transparentBackground } = require("transparent-background");

(async () => {
	const input = await fs.readFile("test-input.png");

	const output = await transparentBackground(input, "png", {
		// uses a 1024x1024 model by default
		// enabling fast uses a 384x384 model instead
		fast: false,
	});

	await fs.writeFile("test-output.png", output);
})();
```