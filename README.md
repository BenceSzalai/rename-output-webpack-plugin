# Rename Output Webpack Plugin
Webpack plugin to rename outfile files / chunks generated by Webpack.

[![npm](https://img.shields.io/npm/v/rename-output-webpack-plugin.svg)](https://www.npmjs.com/package/rename-output-webpack-plugin)
[![GitHub issues](https://img.shields.io/github/issues/sun1l/rename-output-webpack-plugin.svg)](https://github.com/sun1l/rename-output-webpack-plugin/issues)
[![GitHub license](https://img.shields.io/badge/license-MIT-blue.svg)](https://raw.githubusercontent.com/sun1l/rename-output-webpack-plugin/master/LICENSE)

[Installation](#Installation) |
[Usage](#usage) |
[License](#license)

## Installation

```bash
npm install rename-output-webpack-plugin
```

## Usage
```bash
const renameOutputPlugin = require('rename-output-webpack-plugin');

module.exports = {
    entry: {
        'core': './src/core.js',
        'app': './src/index.js',
        'jquery': ['jquery'],
        'angular-suite': ['angular', 'angular-ui-bootstrap', 'angular-ui-router'],
    },
    output: {
        'filename': '[name]-[id].js',
        'path': path.resolve(__dirname, 'dist')
    },
    plugins: [
        new renameOutputPlugin({
            'core': 'framework-[hash].js',
            'jquery': '[name]-[version].min.js',
            'angular-suite': '[name]-[version@angular].min.js'
        })
    ]
};
```

```bash
Hash: 7aa4bcb22d7fa4791dd8
Version: webpack 3.8.1
Time: 1812ms
                            Asset     Size  Chunks                    Chunk Names
                         app-0.js  2.08 MB       0  [emitted]  [big]  app
       angular-suite-1.6.6.min.js  1.73 MB       1  [emitted]  [big]  angular-suite
              jquery-3.2.1.min.js   271 kB       2  [emitted]  [big]  jquery
framework-7aa4bcb22d7fa4791dd8.js   271 kB       3  [emitted]  [big]  core
```
## Authors

*   **Sunil Kumar** - [@sun1lkumar](https://twitter.com/sun1lkumar)

See also the list of [contributors](https://github.com/sun1l/rename-output-webpack-plugin/graphs/contributors) who participated in this project.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details
