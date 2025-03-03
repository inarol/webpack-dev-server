<div align="center">
  <a href="https://github.com/webpack/webpack">
    <img width="200" height="200" src="https://webpack.js.org/assets/icon-square-big.svg">
  </a>
</div>

[![npm][npm]][npm-url]
[![node][node]][node-url]
[![tests][tests]][tests-url]
[![coverage][cover]][cover-url]
[![chat][chat]][chat-url]
[![downloads][downloads]][npm-url]
[![contributors][contributors]][contributors-url]

# webpack-dev-server

Use [webpack](https://webpack.js.org) with a development server that provides
live reloading. This should be used for **development only**.

It uses [webpack-dev-middleware][middleware-url] under the hood, which provides
fast in-memory access to the webpack assets.

## Table of Contents

- [Getting Started](#getting-started)
- [Usage](#usage)
  - [With the CLI](#with-the-cli)
  - [With NPM Scripts](#with-npm-scripts)
  - [The Result](#the-result)
- [Browser Support](#browser-support)
- [Support](#support)
- [Contributing](#contributing)
- [Attribution](#attribution)
- [License](#license)

## Getting Started

First things first, install the module:

```console
npm install webpack-dev-server --save-dev
```

_Note: While you can install and run webpack-dev-server globally, we recommend
installing it locally. webpack-dev-server will always use a local installation
over a global one._

## Usage

There are two main, recommended methods of using the module:

### With the CLI

The easiest way to use it is with the [webpack CLI](https://webpack.js.org/api/cli/). In the directory where your
`webpack.config.js` is, run:

```console
node_modules/.bin/webpack serve
```

Following options are available with `webpack serve`:

```
Usage: webpack serve|s [entries...] [options]

Options:
  -c, --config <value...>    Provide path to a webpack configuration file e.g. ./webpack.config.js.
  --config-name <value...>   Name of the configuration to use.
  -m, --merge                Merge two or more configurations using 'webpack-merge'.
  --env <value...>           Environment passed to the configuration when it is a function.
  --progress [value]         Print compilation progress during build.
  -j, --json [value]         Prints result as JSON or store it in a file.
  -d, --devtool <value>      Determine source maps to use.
  --no-devtool               Do not generate source maps.
  --entry <value...>         The entry point(s) of your application e.g. ./src/main.js.
  --mode <value>             Defines the mode to pass to webpack.
  --name <value>             Name of the configuration. Used when loading multiple configurations.
  -o, --output-path <value>  Output location of the file generated by webpack e.g. ./dist/.
  --stats [value]            It instructs webpack on how to treat the stats e.g. verbose.
  --no-stats                 Disable stats output.
  -t, --target <value...>    Sets the build target e.g. node.
  --watch-options-stdin      Stop watching when stdin stream has ended.
  --no-watch-options-stdin   Do not stop watching when stdin stream has ended.
  --host <value>             The hostname/ip address the server will bind to.
  --port <value>             The port server will listen to.
  --static [value...]        A directory to serve static content from.
  --no-static                Negative 'static' option.
  --live-reload              Enables live reloading on changing files.
  --no-live-reload           Disables live reloading on changing files.
  --https                    Use HTTPS protocol.
  --no-https                 Do not use HTTPS protocol.
  --http2                    Use HTTP/2, must be used with HTTPS.
  --no-http2                 Do not use HTTP/2.
  --bonjour                  Broadcasts the server via ZeroConf networking on start.
  --client-progress          Print compilation progress in percentage in the browser.
  --hot-only                 Do not refresh page if HMR fails.
  --setup-exit-signals       Close and exit the process on SIGINT and SIGTERM.
  --no-setup-exit-signals    Do not close and exit the process on SIGNIT and SIGTERM.
  --stdin                    Close when stdin ends.
  --open [value]             Open the default browser, or optionally specify a browser name.
  --use-local-ip             Open default browser with local IP.
  --open-page <value...>     Open default browser with the specified page.
  --client-logging <value>   Log level in the browser (none, error, warn, info, log, verbose).
  --history-api-fallback     Fallback to /index.html for Single Page Applications.
  --no-history-api-fallback  Do not fallback to /index.html for Single Page Applications.
  --compress                 Enable gzip compression.
  --no-compress              Disable gzip compression.
  --public <value>           The public hostname/ip address of the server.
  --firewall [value...]      Enable firewall or set hosts that are allowed to access the dev server.
  --no-firewall              Disable firewall.

Global options:
  --color                    Enable colors on console.
  --no-color                 Disable colors on console.
  -v, --version              Output the version number of 'webpack', 'webpack-cli' and 'webpack-dev-server' and commands.
  -h, --help [verbose]       Display help for commands and options.
```

_**Note**: For more information on above options explore this [link](https://webpack.js.org/configuration/dev-server/)._

### With NPM Scripts

NPM package.json scripts are a convenient and useful means to run locally installed
binaries without having to be concerned about their full paths. Simply define a
script as such:

```json
"scripts": {
  "start:dev": "webpack serve"
}
```

And run the following in your terminal/console:

```console
npm run start:dev
```

NPM will automagically reference the binary in `node_modules` for you, and
execute the file or command.

### The Result

Either method will start a server instance and begin listening for connections
from `localhost` on port `8080`.

webpack-dev-server is configured by default to support live-reload of files as
you edit your assets while the server is running.

See [**the documentation**][docs-url] for more use cases and options.

## Browser Support

While `webpack-dev-server` transpiles the client (browser) scripts to an ES5
state, the project only officially supports the _last two versions of major
browsers_. We simply don't have the resources to support every whacky
browser out there.

If you find a bug with an obscure / old browser, we would actively welcome a
Pull Request to resolve the bug.

## Support

We do our best to keep Issues in the repository focused on bugs, features, and
needed modifications to the code for the module. Because of that, we ask users
with general support, "how-to", or "why isn't this working" questions to try one
of the other support channels that are available.

Your first-stop-shop for support for webpack-dev-server should be the excellent
[documentation][docs-url] for the module. If you see an opportunity for improvement
of those docs, please head over to the [webpack.js.org repo][wjo-url] and open a
pull request.

From there, we encourage users to visit the [webpack Gitter chat][chat-url] and
talk to the fine folks there. If your quest for answers comes up dry in chat,
head over to [StackOverflow][stack-url] and do a quick search or open a new
question. Remember; It's always much easier to answer questions that include your
`webpack.config.js` and relevant files!

If you're twitter-savvy you can tweet [#webpack][hash-url] with your question
and someone should be able to reach out and lend a hand.

If you have discovered a :bug:, have a feature suggestion, or would like to see
a modification, please feel free to create an issue on Github. _Note: The issue
template isn't optional, so please be sure not to remove it, and please fill it
out completely._

## Contributing

We welcome your contributions! Please have a read of [CONTRIBUTING.md](CONTRIBUTING.md) for more information on how to get involved.

## Attribution

This project is heavily inspired by [peerigon/nof5](https://github.com/peerigon/nof5).

## License

#### [MIT](./LICENSE)

[npm]: https://img.shields.io/npm/v/webpack-dev-server.svg
[npm-url]: https://npmjs.com/package/webpack-dev-server
[node]: https://img.shields.io/node/v/webpack-dev-server.svg
[node-url]: https://nodejs.org
[tests]: https://github.com/webpack/webpack-dev-server/workflows/webpack-dev-server/badge.svg
[tests-url]: https://github.com/webpack/webpack-dev-server/actions?query=workflow%3Awebpack-dev-server
[cover]: https://codecov.io/gh/webpack/webpack-dev-server/branch/master/graph/badge.svg
[cover-url]: https://codecov.io/gh/webpack/webpack-dev-server
[chat]: https://badges.gitter.im/webpack/webpack.svg
[chat-url]: https://gitter.im/webpack/webpack
[docs-url]: https://webpack.js.org/configuration/dev-server/#devserver
[hash-url]: https://twitter.com/search?q=webpack
[middleware-url]: https://github.com/webpack/webpack-dev-middleware
[stack-url]: https://stackoverflow.com/questions/tagged/webpack-dev-server
[uglify-url]: https://github.com/webpack-contrib/uglifyjs-webpack-plugin
[wjo-url]: https://github.com/webpack/webpack.js.org
[downloads]: https://img.shields.io/npm/dm/webpack-dev-server.svg
[contributors-url]: https://github.com/webpack/webpack-dev-server/graphs/contributors
[contributors]: https://img.shields.io/github/contributors/webpack/webpack-dev-server.svg
