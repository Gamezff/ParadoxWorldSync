# ParadoxWorldSync
QBCore based world syncing and weather system with bucket support.

#### FiveM Topic: https://forum.cfx.re/t/free-qb-paradox-world-sync-smooth-time-and-weather-sync/4970361

### What makes this different than other scripts?
What I am calling "smooth sync", no longer will you ever (hopefully) see the sky jitter at all. By variaing the time per minute to match near the server time (so if we are behind we speed up time slightly) we can maintain fully synced time (or within a minute) while keeping it optimized with statebags.

### Note!
This script is in BETA and it basically is fully functioning minus some things like making sure the config option for time per minute will replicate correctly so I would not mess with `Config.TimeScaler` unless you want to toy around with the timer loop on the server side. Its also kinda jank sometimes with the weather systems and I have rewritten it a few times but I haven't found a flow I like that allows overridding so any PRs are appreciated!

## Commands

### Weather
> `weather <system/weather?` - Overrides current weather to this weather system or GTA default weather type

> `freezeweather` - Toggles freezing of weather

> `skipweather` - Trigger a new random weather change

> `enablesnow <true/false>` - Enables/disables snow

### Time
> `time <hours> <minutes>` - Set time to specified hour and minute

> `freezetime <true/false>` - Freeze the time

### Extras
> `blackout <true/false>` - Enables blackout (does not affect car lights)


## Events

### Server
> `ParadoxWorld:server:setBlackout` `bool BlackoutState` - Set blackout from another script

### Client
> `ParadoxWeather:client:snowToggled` `bool Enabled` - Emitted when snow is enabled from client

## Extras
This has a snow plow effect built in. Whenever it snows it will reset the snowplowed variable. If you call this from another script (say a snowplowing script) then it will disable the snow traction (the slippery effect) while keeping snow on the ground. 


Credit:

Vespura - vSync for the shift to hours,minutes functions on serverside: https://github.com/DevTestingPizza/vSync
