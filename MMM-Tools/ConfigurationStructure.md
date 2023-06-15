---
title: Configuration Structure
description: 
published: true
date: 2022-04-20T17:27:06.749Z
tags: 
editor: markdown
dateCreated: 2021-07-14T11:50:13.512Z
---

# Field in `root`
> |field | default | description
> |--- |--- |---
> |debug| `false` | enable or not debug mode
> |refresh| `5000` | Milliseconds for refreshing status information on `MagicMirror`
> |containerSize| `null` | Force to define the container size in px. With `null` it's automaticaly calculated
> |itemSize| `null` | Force to define the item size in px. With `null` it's automaticaly calculated

# Field `MM: {...}`
> |field | default | description
> |--- |--- |---
> |displayMM| `true` | Display version of MagicMirror
> |orderOs| `0` | Number of order in the array

# Field `NODE: {...}`
> |field | default | description
> |--- |--- |---
> |displayNode| `true` | Display version of node
> |orderNode| `1` | Number of order in the array

# Field `NPM: {...}`
> |field | default | description
> |--- |--- |---
> |displayNpm| `true` | Display version of npm
> |orderNpm| `2` | Number of order in the array

# Field `OS: {...}`
> |field | default | description
> |--- |--- |---
> |displayOs| `true` | Display the name of the OS
> |displayArch| `true` | Display the operating system CPU architecture (`arm`, `arm64`, `ia32`, `mips`, `mipsel`, `ppc`, `ppc64`, `s390`, `s390x` or `x64`)
> |orderOs| `3` | Number of order in the array

# Field `CPU: {...}`
> |field | default | description
> |--- |--- |---
> |displayUsage| `true` | Display usage of the CPU in %
> |orderUsage| `8` | Order number in the array for displaying CPU usage
> |displaySpeed| `true` | Display current CPU Speed
> |orderSpeed| `5` | Order number in the array for displaying CPU Speed
> |displayGovernor| `true` | Display current Governor
> |orderGovernor| `6` | Order number in the array for displaying CPU Governor
> |displayTemp| `true` | Display temperature of the CPU
> |celciusTemp| `true` | true: Display temperature in celcius, false: in fahrenheit
> |orderTemp| `11` | Order number in the array for displaying CPU Temp.
> |displayType| `true` | Display type of the RPI or CPU
> |orderType| `4` | Order number in the array for displaying CPU/RPI Type

# Field `RAM: {...}`
> |field | default | description
> |--- |--- |---
> |displayRam| `true` | Display RAM usage
> |orderRam| `9` | Order number in the array for RAM usage

# Field `STORAGE: {...}`
> |field | default | description
> |--- |--- |---
> |displayStorage| `true` | Display storage informations
> |orderStorage| `10` | Order number in the array for storage informations
> |partitionExclude| `[]` | Exclude some partition informations

Samples:

`PartitionExclude: [ "/boot" ]`

`PartitionExclude: [ "/boot", "/media/Data" ]`

# Field `NETWORK: {...}`
> |field | default | description
> |--- |--- |---
> |displayNetwork| `true` | Display network informations
> |orderNetwork| `7` | Order number in the array for network informations
> |nativeNetwork| `true` | If you activate this feature, the real name of the interface will be displayed else it's display LAN/WLAN
> |displayDefaultNetwork| `true` | Localize the default network with a `*` (only on multi-network)

# Field `UPTIME: {...}`
> |field | default | description
> |--- |--- |---
> |displayUptime| `true` | Display uptime informations
> |useMagicMirror| `true` | if `true` MagicMirror uptime is used, `false` is system uptime (since boot)
> |orderUptime| `12` | Order number in the array for uptime informations
> |displayRecord| `true` | Display record uptime informations
> |orderRecord| `13` | Order number in the array for record uptime informations

# Field `WARNING: {...}`
> |field | default | description
> |--- |--- |---
> |enableWarning| `false` | Enable TelegramBot warning
> |interval| `300000`| check warning interval (in ms)
> |check| `{...}` | values to check, if defined value is over, it display a TelegramBot warning

## Field `check: {...}` in the Field `WARNING: {...}`
> |check field | default | description
> |--- |--- |---
> |CPU_TEMP| `65` | check CPU Temp (in °C)
> |CPU_USAGE| `75` | check CPU average usage (in %)
> |STORAGE_USED| `80` | check Storage use (in %)
> |MEMORY_USED| `80` | check Memory use (in %)

> You can disable your desire check item by setting check value to `0`
{.is-warning}
