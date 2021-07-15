# docsify-lang-test

Experimental [Docsify.js](https://github.com/docsifyjs/docsify) project exploring
different ways to enable multilingual documentation.

## Notes

- Docsify does not provide localization out-of-the-box.

- Docsify's own [homepage](https://docsify.js.org) handles multi-language content
by aliasing URLs to separate GitHub repos:

```js
window.$docsify = {
  alias: {
    // ...
    "/zh-cn/(.*)": "https://cdn.jsdelivr.net/gh/docsifyjs/docs-zh@master/$1",
    "/de-de/(.*)": "https://raw.githubusercontent.com/docsifyjs/docs-de/master/$1",
    "/ru-ru/(.*)": "https://raw.githubusercontent.com/docsifyjs/docs-ru/master/$1",
    "/es/(.*)": "https://raw.githubusercontent.com/docsifyjs/docs-es/master/$1",
    // ...
  },
};
```

- Not sure if we want to do the same; we can probably just keep all languages
in the same repo, as demonstrated in this experimental project.

- There seems to be a problem with path resolution for embedded images or code snippets,
see issues [#850](https://github.com/docsifyjs/docsify/issues/850),
[#877](https://github.com/docsifyjs/docsify/issues/877), and pull request
[#1339](https://github.com/docsifyjs/docsify/pull/1339). For now, paths to shared images
and code snippets must be relative, e.g., `[hello.js](../../../_snippets/hello.js ':include :type=code')`.
