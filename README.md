# Weather card

![Example from Stockholm/Sweden](https://user-images.githubusercontent.com/1109836/60332830-e6096e80-9997-11e9-9527-16b424e1984c.png)

## About

This repository was initially a fork of [a nice weather card](https://github.com/sgttrs/lovelace-weather-card-chart) that I wanted to tweak and adapt quite a lot. For various reasons I've turned this into its own project, but please do visit the original to see if it better suits your needs.

## Installation

### HACS - preferred method

If you don't know about HACS (Home Assistant Community Store), you should [check it out](https://github.com/custom-components/hacs). It is by far the best current method of finding, installing and maintaining plugins. Presently this repository is not in HACS (I do plan to add it when I have time), but you can add this repository manually.

1. In HASS, navigate to Community -> Settings.
2. Add [this repository](https://github.com/willeraab/weather-with-graph) to the custom repositories, as a plugin.
3. Navigate to Community -> Store.
4. Find the `weather with graph` card in the plugins section. Install.
5. In Lovelace UI config:
```resources:
 - url: /local/weather-with-graph.js
   type: module
```

### Manual

1. Copy [dist/weather-with-graph.js](https://raw.githubusercontent.com/willeraab/weather-with-graph/master/dist/weather-with-graph.js) into HASS `config/www` folder.
2. In Lovelace UI config:
```resources:
 - url: /local/weather-with-graph.js
   type: module
```

## Configuring the card

### Minimal installation

``` # Example Lovelace UI config entry
 - type: 'custom:weather-with-graph'
   weather: weather.openweathermap
```


#### Configuration variables:

| Name                | Optional | Description                                                                                        |
| ------------------- | -------- | -------------------------------------------------------------------------------------------------- |
| type                | **No**   | Should be `'custom:weather-with-graph'`.                                                           |
| weather             | **No**   | An entity_id with the `weather` domain.                                                            |
| title               | Yes      | Card title, defaults to friendly_name if no title is set.                                          |
| temp                | Yes      | Entity_id of the temperature sensor. Show temperature value from sensor instead.                   |
| mode                | Yes      | Default value: `daily`. Set mode to `hourly` to display hours instead weekdays on the chart.       |
| number_of_forecasts | Yes      | Number of forecast recordings to show, min 3 max 9.                                                |
| chart_only          | Yes      | Display the chart without displaying the header information. Boolean.                              |
