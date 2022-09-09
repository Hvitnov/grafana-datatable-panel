# Grafana Datatable Panel

[![Twitter Follow](https://img.shields.io/twitter/follow/jepetlefeu.svg?style=social)](https://twitter.com/jepetlefeu)
![Release](https://github.com/briangann/grafana-datatable-panel/workflows/Release/badge.svg)
[![David Dependancy Status](https://david-dm.org/briangann/grafana-datatable-panel.svg)](https://david-dm.org/briangann/grafana-datatable-panel)
[![David Dev Dependency Status](https://david-dm.org/briangann/grafana-datatable-panel/dev-status.svg)](https://david-dm.org/briangann/grafana-datatable-panel?type=dev)
[![Known Vulnerabilities](https://snyk.io/test/github/briangann/grafana-datatable-panel/badge.svg)](https://snyk.io/test/github/briangann/grafana-datatable-panel)
[![Maintainability](https://api.codeclimate.com/v1/badges/7b3cb7018973e4ddfdac/maintainability)](https://codeclimate.com/github/briangann/grafana-datatable-panel/maintainability)
[![Test Coverage](https://api.codeclimate.com/v1/badges/7b3cb7018973e4ddfdac/test_coverage)](https://codeclimate.com/github/briangann/grafana-datatable-panel/test_coverage)

This panel plugin provides a [Datatables.net](http://www.datatables.net) table panel for [Grafana](http://www.grafana.com) 6.x/7.x

## Screenshots

### Paging enabled

![Default Paging](https://raw.githubusercontent.com/briangann/grafana-datatable-panel/master/src/screenshots/datatable-basic-dark.png)

### Scrolling enabled

![Scrolling](https://raw.githubusercontent.com/briangann/grafana-datatable-panel/master/src/screenshots/datatable-dark-scrolling.png)

### Light Theme with Paging

![Light Theme with Paging](https://raw.githubusercontent.com/briangann/grafana-datatable-panel/master/src/screenshots/datatable-basic-light.png)

### Numbered Rows and Compact Style

![Numbered and Compact Rows](https://raw.githubusercontent.com/briangann/grafana-datatable-panel/master/src/screenshots/datatable-dark-numbered-compact.png)

## Options

### Options Tab

![Options](https://raw.githubusercontent.com/briangann/grafana-datatable-panel/master/src/screenshots/datatable-options.png)

Same options as built-in table panel

### Datatable Options Tab

![Datatable Options](https://raw.githubusercontent.com/briangann/grafana-datatable-panel/master/src/screenshots/datatable-dt-options.png)

Table Display Options

* Font Size - set font size of table content
* Scroll - toggle for scrolling vs Paging
* Paging Options
  * Rows Per Page - number of rows to display when paging is enabled
  * Paging type - multiple navigation options

Column Aliasing

* Override the name displayed for a column

Column Width Hints

* Provide a width "hint" in percentage or pixels ( 100px or 10% ). Note: The table will autosize as needed, but will use the hints provided.

Column Sorting

* Sort table by any number of columns in ascending/descending order.

Table Options

* Row Numbers - toggle to show row numbers
* Length Change Enabled - top left dropdown for showing alternate page sizes
* Search Enabled - toggle to allow searching table content (regex is enabled)
* Info - Displays the "Show N of X entries" on bottom left of table
* Cell Borders - show borders around each Cell (cannot be enabled with Row Borders)
* Row Borders - show border between rows
* Compact Rows - uses less padding for denser data display
* Striped Rows - non-colored rows will be "striped" odd/even
* Order Column - Highlights the column used for sorting
* Hover - Highlights row on mouse hover

Theme Settings

* Basic theme is currently the only option, more to be added

## Thresholding

### Row-based threshold coloring

![Thresholding with Row Coloring](https://raw.githubusercontent.com/briangann/grafana-datatable-panel/master/src/screenshots/datatable-threshold-row.png)

### Cell based threshold coloring

![Thresholding with Cell Coloring](https://raw.githubusercontent.com/briangann/grafana-datatable-panel/master/src/screenshots/datatable-threshold-cell.png)

### Cell based threshold value coloring

![Thresholding with Value Coloring](https://raw.githubusercontent.com/briangann/grafana-datatable-panel/master/src/screenshots/datatable-threshold-value.png)

### RowColumn threshold coloring

This option sets the row color to the "highest" threshold found for all cells in row.

It also sets the color for each cell according to the threshold (you can tell which columns actually exceeded the threshold).

This means - a row can have an overall color, with each cell indicating it's real threshold color.

![Thresholding with RowColumn1](https://raw.githubusercontent.com/briangann/grafana-datatable-panel/master/src/screenshots/datatable-threshold-rowcolumn1.png)

![Thresholding with RowColumn2](https://raw.githubusercontent.com/briangann/grafana-datatable-panel/master/src/screenshots/datatable-threshold-rowcolumn2.png)

### RowColumn threshold coloring including row counter

Same as above, but with row counter included

![Thresholding with RowColumn including row count](https://raw.githubusercontent.com/briangann/grafana-datatable-panel/master/src/screenshots/datatable-threshold-rowcolumn-rownumbers.png)

## Features

* Feature parity with built-in Grafana Table Panel
* Row coloring uses the "highest" threshold color of all columns
* New "RowColumn" threshold color option:
   Sets color to "highest" threshold found for all cells in row.
   Also sets color for each cell according to the threshold.
   This means - a row can have an overall color, with each cell indicating it's real threshold color.
* Set font size for rows
* Scrolling
* Paging
  * Preset page sizes
  * Multiple paging types
  * Dropdown for page size
* Row Numbers reactive to filtering
* Searchable table content (filtering), regex enabled
* Columns names can be aliased
* URLs inside row text can be "clicked"
* Rows can have a click-through URL
* Multi-Column Sorting
* Horizontal scrolling enabled when columns are wider than panel

## TODO

* [+] Column is not working

## Building

This plugin relies on Yarn, typical build sequence:

```BASH
yarn install
yarn build
```

For development, you can run:

```BASH
yarn install
yarn watch
```

The code will be parsed then copied into "dist" if the build passes without errors.

## Docker Support

A docker-compose.yml file is include for easy development and testing, just run

```BASH
docker-compose up
```

Then browse to (<http://localhost:3000>)

## RPM

A spec file is included to facilitate RPM based deployments, to generate run

```BASH
make rpm
```

## External Dependencies

* Grafana 6.x/7.x

## Build Dependencies

* yarn

## Acknowledgements

This panel is based on the "Table" panel by GrafanaLabs

## Grafana development on Watch Mode using Yarn:

This is a guide on how to run changes for Grafana plugins in Watch Mode without signing the plugins – using the datatable panel plugin from: https://github.com/Hvitnov/grafana-datatable-panel/tree/master/src

Prerequisites:
- Install Yarn and Nodes.js
- Copy make a new copy of the default.ini and name it custom.ini. This new file will override default.ini. 
- Clone plugin and make sure to place the plugin in the plugin directory: 
- [paths]
plugins = "/path/to/grafana-plugins"
- In the custom.ini config-file set the property 'app_mode = development' 
- In the plugin folder, check if the package.json file is restricted to a specific engine – if so, remove it otherwise we won't be able to install yarn   
"engines": {
  "node": ">=12 <13"
}
- Open terminal and move to the plugin folder in your plugin directory. 

- Write 'yarn add @grafana/toolkit' to install yarn 

- Write 'yarn watch' to compile the plugin live (of course you have to refresh the browser to see the changes) 
Note when you run it in watch mode it will probably prompt error messages, and it's usually nothing that important. Just try to change up the code and you will see the terminal compile automatically. 

 
