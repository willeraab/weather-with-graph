# Weather card

![Example from Stockholm/Sweden](https://user-images.githubusercontent.com/1109836/60332830-e6096e80-9997-11e9-9527-16b424e1984c.png)

## About

This repository was initially a fork of [a nice weather card](https://github.com/sgttrs/lovelace-weather-card-chart) that I wanted to tweak and adapt quite a lot. For various reasons I've turned this into its own project, but please do visit the original to see if it better suits your needs.

## Configuration

Copy `weather-with-graph.js` from this repository into your `config/www` directory first.

Add a reference to the copied file:
```yaml
# Example Lovelace UI config entry
resources:
- type: module
  url: /local/weather-with-graph.js
```
Then you can add the card to the view:
```yaml
# Example Lovelace UI config entry
  - type: 'custom:weather-with-graph'
    title: Weather
    weather: weather.openweathermap
```
You can update this card using [custom updater](https://github.com/custom-components/custom_updater). To do this, add these lines to `custom_updater` configuration in `configuration.yaml`:
```yaml
# Example configuration.yaml entry
custom_updater:
  card_urls:
    - https://github.com/willeraab/weather-with-graph/blob/master/custom-updater.json
```

#### Configuration variables:

| Name    | Optional | Description                                                                                        |
| ------- | -------- | -------------------------------------------------------------------------------------------------- |
| type    | **No**   | Should be `'custom:weather-with-graph'`. |
| weather | **No**   | An entity_id with the `weather` domain. |
| title   | Yes      | Card title, defaults to friendly_name if no title is set. |
| temp    | Yes      | Entity_id of the temperature sensor. Show temperature value from sensor instead. |
| mode    | Yes      | Default value: `daily`. Set mode to `hourly` to display hours instead weekdays on the chart. |
| number_of_forecasts | Yes | Number of forecast recordings to show, min 3 max 9. |
| chart_only | Yes | Display the chart without displaying the header information. Boolean. |
