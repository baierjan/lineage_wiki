---
sidebar: home_sidebar
title: Devices
permalink: devices.html
---
{% assign devices = "" |split: " " %}
{% for device in site.data.devices %}
{% assign devices = devices | push: device[1] %}
{% endfor %}

{% assign sorted = devices|sort:'name'|sort:'vendor' %}
| **device** | **codename** | **type** |{% for device in sorted %}
| [ {{ device.vendor }} {{ device.name }} ]({{ device.codename }}_info.html) |  [{{ device.codename }}]({{ device.codename }}_info.html) | {{ device.type }} |{% endfor %}
