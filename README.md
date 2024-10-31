# stella-implementation-in-typescript

Template for an implementation of Stella in TypeScript (with ANTLRv4).

## Getting started

### Generating the parser

> Note: the generated parser is checked into git so that you don't have to run these commands yourself.
> The instructions are left here just for reference.

First, make sure you have `antlr4` installed using `pip install antlr4-tools`.
Then, you must generate the Stella parser and lexer using `npm run antlr4`.
This script adds a `// @ts-nocheck` preamble to the generated files so they don't bother you with false positives.

### Running the code

You can use any number of modules you want, but the main driver code should be in [`index.ts`](./src/index.ts).
Run `npm run build` to bundle it into 1 JS file under `build`, or use `npm run watch`
to run it in watch mode during development.

To run the built code, use `node build [path/to/file.stella]`.

Your code will be tested by running the following commands:
```sh
npm install
npm run build
npm start -- <path/to/test.stella>
```

### AST

For your convenience, a hand-written AST is written in [`ast.ts`](./src/ast.ts)
to make it easier to work with the parser generated by ANTLR.
If you prefer using the Visitor pattern with the Concrete Syntax Tree, see the
code in [`visitors.ts`](./src/visitors.ts) that transforms the CST to AST.
