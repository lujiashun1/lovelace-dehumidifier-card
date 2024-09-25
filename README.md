<!--
 * @Author        : fineemb
 * @Github        : https://github.com/fineemb
 * @Description   : 
 * @Date          : 2024-02-03 12:52:45
 * @LastEditors   : ljs
 * @LastEditTime  : 2024-09-25 11:11:26
 -->

# Dehumififier Card(Mijia Smart Dehumidifier 13L)

[![hacs_badge](https://img.shields.io/badge/HACS-Default-orange.svg)](https://github.com/custom-components/hacs)

A simple Dehumififier implemented in CSS and SVG based on <a href="https://codepen.io/dalhundal/pen/KpabZB/">Dehumififier Control</a> by Dal Hundal
 (<a href="https://codepen.io/dalhundal">@dalhundal</a>) on <a href="https://codepen.io">CodePen</a>

+  Supports [HACS](https://github.com/custom-components/hacs) installation
+  Allow changing of Opration mode
+  Allow avoid the card background

## Preview
![](https://bbs.hassbian.com/data/attachment/forum/202003/14/172544q3ajp7742cbo757h.gif)

## Update
## HACS Installation
Add https://github.com/lujiashun1/lovelace-dehumidifier-card to Custom repositories
Search for Dehumififier Card
## Manual Installation
1. Download `main.js` `thermostat_card.lib.js` `styles.js`
1. Copy to `www\community\lovelace-dehumififier-card`
1. Add the following to your Lovelace resources
    ``` yaml
    resources:
      - url: /hacsfiles/lovelace-dehumififier-card/main.js
        type: module
    ```
1. Add the following to your Lovelace config `views.cards` key
    ```yaml
    - type: custom:dehumififier-card
      entity: humififier.xiaomi_13l_xxxx_dehumidifier
      title: 工作间
    ```
    Replace `xiaomi_13l_xxxx_dehumidifier` with your dehumififier's entity_id and `工作间` with any name you'd like to name your dehumififier with

## Options

| Name | Type | Default | Description
| ---- | ---- | ------- | -----------
| type | string | **Required** | `custom:thermostat-card`
| entity | string | **Required** | The entity id of climate entity. Example: `climate.hvac`
| title | string | optional | Card title
| no_card | boolean | false | Set to true to avoid the card background and use the custom element in picture-elements.
| step | number | 1 | The step to use when increasing or decreasing humidity
| highlight_tap | boolean | false | Show the tap area highlight when changing humidity settings
| chevron_size | number | 50 | Size of chevrons for humidity adjutment
| pending | number | 3 | Seconds to wait in control mode until state changes are sent back to the server
| light_entity | string | optional | Backlight entity,when null then light.xiaomi_13l_`xxxx`_indicator_light
| lock_entity | string | optional | Child safety lock entity,when null then switch.xiaomi_13l_`xxxx`_physical_control_locked

## Credits
<a href="https://codepen.io/dalhundal">@dalhundal</a>
