# karma-firefox-launcher

[![npm version](https://img.shields.io/npm/v/%40wikimedia%2Fkarma-firefox-launcher.svg?style=flat-square)](https://www.npmjs.com/package/@wikimedia/karma-firefox-launcher)


> Launcher for Mozilla Firefox.

## Installation

The easiest way is to keep `karma-firefox-launcher` as a devDependency in your `package.json`.

You can simple do it by:

```bash
npm install karma-firefox-launcher --save-dev
```

## Configuration

```js
// karma.conf.js
module.exports = function (config) {
  config.set({
    plugins: [require("karma-firefox-launcher")],
    browsers: [
      "Firefox",
      "FirefoxDeveloper",
      "FirefoxAurora",
      "FirefoxNightly",
    ],
  });
};
```

You can pass list of browsers as a CLI argument too:

```bash
karma start --browsers Firefox,Chrome
```

To run Firefox in headless mode, append `Headless` to the version name, e.g. `FirefoxHeadless`, `FirefoxNightlyHeadless`.

### Environment variables

You can specify the location of the Firefox executable using the following
environment variables:

- `FIREFOX_BIN` (for browser `Firefox` or `FirefoxHeadless`)
- `FIREFOX_DEVELOPER_BIN` (for browser `FirefoxDeveloper` or
  `FirefoxDeveloperHeadless`)
- `FIREFOX_AURORA_BIN` (for browser `FirefoxAurora` or `FirefoxAuroraHeadless`)
- `FIREFOX_NIGHTLY_BIN` (for browser `FirefoxNightly` or
  `FirefoxNightlyHeadless`)

### Custom Firefox location

In addition to Environment variables you can specify location of the Firefox executable in a custom launcher:

```js
browsers: ['Firefox68', 'Firefox78'],

customLaunchers: {
    Firefox68: {
        base: 'Firefox',
        name: 'Firefox68',
        command: '<path to FF68>/firefox.exe'
    },
    Firefox78: {
        base: 'Firefox',
        name: 'Firefox78',
        command: '<path to FF78>/firefox.exe'
    }
}
```

---

For more information on Karma see the [homepage].

[homepage]: https://karma-runner.github.io
