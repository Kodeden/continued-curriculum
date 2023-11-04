# TypeScript (TS) Intro and Overview

## What is TypeScript?

TypeScript is a superset of JavaScript. This means that it wraps around JavaScript and adds additional features to the language. It is a language that is compiled into JavaScript. This means that TypeScript code is not run directly in the browser/Node. Instead it is compiled into JavaScript code that is run in the browser/Node.

Above all, it adds type annotations to the language. It is a statically typed language, meaning that the types are checked at compile time, not at runtime. This is in contrast to JavaScript, which is dynamically typed, meaning that the types are checked at runtime.

The primary motivation behind using TS is overall developer 👨🏾‍💻 experience. When properly integrated into VS Code, we get _real-time_ feedback on some common mistakes that we might make in our code. This goes above and beyond linting, which is a static analysis tool that checks for syntax errors and style issues. TS can catch errors that would otherwise be caught at runtime, which is a huge win for developers.

By runtime, we mean that with plain JS, we would have to run the code and wait it for it to crash (think 💭 `undefined.`) - _runtime errors._ JS lets us do pretty much whatever we want. It's very loose, which makes it easy to get started with but opens up the possibility for a lot of errors. TS helps us catch these errors before we run the code. With anything, there are pros and cons. Naturally, TS takes effort to learn and use, but it can save us time in the long run, especially on larger projects and/or when working with a team where not everyone can be intimately familiar with every part of the codebase.

Be warned ⚠️, TS can also be frustrating at times and difficult. But, usually anything worth doing is! It's a tool that can help us write better code, but it's not a silver bullet. It's not a replacement for writing good tests, for example. It's also not a replacement for writing good documentation. It's just another tool that we must understand to use properly. Of course, whenever in doubt, consult the docs 📝 and/or use ChatGPT, etc.

---

<div style="position: relative; padding-bottom: 56.25%; height: 0;"><iframe src="https://www.loom.com/embed/0b64f8bfec7c410eacde56fd09c72a83?sid=6ea9b0ab-0bbf-4f87-a12e-99ae40fb50b9" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;"></iframe></div>

In the video, I also show the use of `gh`. Unlike most of the other content, you _don't_ need to actually follow along. I will be creating the template repo that we will be using for actually working with TS! Of course, you can follow along if you'd like, but it's about actually applying TS and a lot of this other stuff is just boilerplate.

Also, even though I created the repo on `KodeDen`, I forgot to add the `--clone` or `-c` _flag_ to simultaneously clone it! See [docs](https://cli.github.com/manual/gh_repo_create).
