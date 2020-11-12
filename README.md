<!-- Autogenerated from composer.json - All changes will be overridden if generated again! -->

# srag/generateplugininfoshelper Library

Generate plugin infos helper

This is an OpenSource project by studer + raimann ag, CH-Burgdorf (https://studer-raimann.ch)

This project is licensed under the GPL-3.0-only license

## Usage

### Composer

First add the following to your `composer.json` file:

```json
"require": {
  "srag/generateplugininfoshelper": ">=1.0.0"
},
```

And run a `composer install`.

If you deliver your plugin, the plugin has it's own copy of this library and the user doesn't need to install the library.

Tip: Because of multiple autoloaders of plugins, it could be, that different versions of this library exists and suddenly your plugin use an older or a newer version of an other plugin!

So I recommand to use [srag/librariesnamespacechanger](https://packagist.org/packages/srag/librariesnamespacechanger) in your plugin.

## GeneratePluginPhpAndXml

Generate `plugin.php` and `plugin.xml` and `LuceneObjectDefinition.xml` for ILIAS plugins from `composer.json`

Complete your `composer.json` with

```json
  ...
  "version": "x.y.z",
  ...
  "extra": {
    "ilias_plugin": {
      "id": "x",
      "name" => "X",
      "ilias_min_version": "x.y.z",
      "ilias_max_version": "x.y.z",
      "learning_progress": true | false,
      "lucene_search": true | false,
      "supports_export": true | false,
      "slot": "x/y/z"
      "events": [
        {
          "id": "X/Y",
          "type": "listen|raise"
        }
      ]
    }
  },
  ...
  "authors": [
    {
      "name": "...",
      "email": "...",
      "homepage": "...",
      "role": "Developer"
    }
  ],
  ...
```

### Composer script

#### Automatic

```json
  ...
  "pre-autoload-dump": [
    ...,
      "srag\\GeneratePluginInfosHelper\\x\\GeneratePluginPhpAndXml::generatePluginPhpAndXml"
    ]
  ...
```

```bash
composer du
```

#### Manual

```json
  ...
  "generate-plugin-php-and-xml": [
    ...,
     "srag\\GeneratePluginInfosHelper\\x\\GeneratePluginPhpAndXml::generatePluginPhpAndXml"
    ]
  ...
```

```bash
composer run generate-plugin-php-and-xml
```

### In code

```php
...
use srag\GeneratePluginInfosHelper\x\GeneratePluginPhpAndXml; 
...
GeneratePluginPhpAndXml::getInstance()->doGeneratePluginPhpAndXml($plugin_root, $log = false);
...
```

## GeneratePluginReadme

Auto generate `README.md`

Complete your `composer.json` with

```json
  ...
  "extra": {
    ...
    "generate_plugin_readme_template": "..."
    ...
  }
  ...
```

### Composer script

#### Automatic

```json
  ...
  "pre-autoload-dump": [
    ...,
     "srag\\GeneratePluginInfosHelper\\x\\GeneratePluginReadme::generatePluginReadme"
    ]
  ...
```

```bash
composer du
```

#### Manual

```json
  ...
  "generate-plugin-readme": [
    ...,
     "srag\\GeneratePluginInfosHelper\\x\\GeneratePluginReadme::generatePluginReadme"
    ]
  ...
```

```bash
composer run generate-plugin-readme
```

### In code

```php
...
use srag\GeneratePluginInfosHelper\x\GeneratePluginReadme; 
...
GeneratePluginReadme::getInstance()->doGeneratePluginReadme($project_root, $template = null, $log = false);
...
```

## Requirements

* PHP >=7.0

## Adjustment suggestions

* External users can report suggestions and bugs at https://plugins.studer-raimann.ch/goto.php?target=uihk_srsu_LGENPLUGINFHELP
* Adjustment suggestions by pull requests via github
