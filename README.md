# Home Assistant Configuration
This repository contains my Home Assistant Configuration created for use with the Home Assistant OS version of Home Assistant. My current hardware set up includes:
* Raspberry Pi 4.
* [Cooler Master Pi Case 40](https://www.coolermaster.com/catalog/cases/raspberry-pi/pi-case-40/)
* [Samsung Micro-SDHC Pro Endurance AD 32GB](https://www.power.dk/mobil-og-foto/mobiltilbehoer/hukommelseskort/samsung-micro-sdhc-pro-endurance-ad-32gb/p-953915/store/3807/?gclid=Cj0KCQjwppSEBhCGARIsANIs4p5UoO-Hjgiy4fPPxC3hvTa_XAihavxcjS-GhrzCyoI2nVR2JNmjxkMaAoiWEALw_wcB&gclsrc=aw.ds)

## Smart devices in my home

* Philips Hue Bulbs
* IKEA Trådfri Bulbs
* Google Home Devices
* Samsung Smart TV
* Philiphs Smart TV
* Netatmo Healthy Home Coach
* Tapo Smart Plugs
* Xiaomi Roborock S5 Max

## Integrations
For my Home Assistant configuration I use the following integrations
* Google Cast
* HACS - Home Assistant Community Store
* Life360 - The Life360 integration is used to enable device tracking
* Mobile App - The Mobile App integration allows Home Assistant mobile apps to easily integrate with Home Assistant
* Netatmo
* Phillips Hue 

## Lovelace Dashboard
THIS SECTION IS A WORK IN PROGRESS (well, isn't the dashbord always a work in progress .. )


### Acknowledgements
This lovelace dashboard draws inspiration from [Lukevink's dashboard](https://github.com/lukevink/hass-config-lajv) and [Mattias Persson's dashboard](https://github.com/matt8707/hass-config).


Furthermore, for this dashboard I use several custom components, some of which are included in the list below. Later, I describe how they integrate in my implementation.
* [Sidebar Card](https://github.com/DBuit/sidebar-card)
* [Mini Graph Card](https://github.com/kalkih/mini-graph-card)
* [Mini Media Player](https://github.com/kalkih/mini-media-player)
* [Spotify Card](https://github.com/custom-cards/spotify-card)
* [Weather Card](https://github.com/bramkragten/weather-card)
* [Simple Weather Card](https://github.com/kalkih/simple-weather-card)
* [Light Pop-up Card](https://github.com/DBuit/light-popup-card)
* [Browser Mod](https://github.com/thomasloven/hass-browser_mod#popup)

Lastly, on the *floorplan* view all icons are downloaded [Flaticon.com]([flaticon.com](https://www.flaticon.com/)) and I attribute [Freepik](https://www.flaticon.com/authors/freepik) for their creation.

### Features

* 3D Floorplan to control: lights, music entities, and smart plugs and to view indoor climate data
  * Includes popup controls for each entity
* Dynamic floorplan view, adjusts brightness based on calculated brightness of the sun

### Approach
The general outline of the UI is made up of the [sidebar](https://github.com/DBuit/sidebar-card) panel to the left and the main view to the right. The implementation of all elements are found in the *ui-elements* folder. All views are in *panel* mode.

**Sidebar**

The sidebar consists of menu buttons that direct the user between the different views. The sidebar is created using the [sidebar](https://github.com/DBuit/sidebar-card) custom component. The different views are
* Hjem (home): shows the weather forecast, my calender, and recent news.
* Styr hejm (Control home): shows a 3D floorplan, and lets the user control all smart devices from there, such as toggleing lights, control media players etc
* Støvsuger (Vacuum Cleaner): Will eventually control my robot vacuum cleaner when implemented

The bottom card of the sidebar is a vertical stack consisting of
* *Horizontal stack* containing two *picture-entities* showing the users of the smart home. The pictures become greyscale when away and are in color when home.
* [Multiple entity row]() to show the current temperature indoor and outdoor and the CO2 level indoor. The inside readings are provided by the Netatmo Healty Home Coach
* [Mini Graph Card](https://github.com/kalkih/mini-graph-card) to show the indoor temperature the last 24 hours.

**Home View**

The Home view consists of a grid containing a weather card, a calender card and a RSS feed card. The weather data is provide by the *weather.home* sensor. The calender shows my calander as a month view and lastly the RSS feed shows news from [DR](https://www.dr.dk/nyheder/dr-nyheder-som-rss-feed).

**Floorplan View**

Needs documentation

## Automations
Write about my automations