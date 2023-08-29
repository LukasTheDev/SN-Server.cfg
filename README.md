# Server.cfg Template 

This docker image allows you to run a server for FiveM, a modded GTA multiplayer program.
Upon first run, the configuration is generated in the host mount for the `/config` directory.
The container should be stopped so fivem can be configured to the user requirements in the `server.cfg`.

## License Key

A freely obtained license key is required to use this server, which should be declared as `$LICENSE_KEY`. A tutorial on how to obtain a license key can be found [here](https://forum.fivem.net/t/explained-how-to-make-add-a-server-key/56120).

### Web UI (txAdmin)

The web UI can be enabled by not passing any `+exec` config to the FXServer binary. This can be achieved by setting the `NO_DEFAULT_CONFIG` environment variable (see below).

`txAdmin` stores it's configuration and database data in `/txData`, so a volume can be set up to persist this data:

### Environment Variables

- `LICENSE_KEY` - This is a required variable for the license key needed to start the server.
- `RCON_PASSWORD` - A password to use for the RCON functionality of the fxserver. If not specified, a random 16 character password is assigned. This is only used upon creation of the default configs
- `NO_DEFAULT_CONFIG` - Optional. Set to any non-zero value to disable the default exec config. This is required for txAdmin.
- `NO_LICENSE_KEY` - Optional. Set to any non-zero length value to disable specifying the license key in the environment. Useful if your license key is in a config file.
- `NO_ONESYNC` - Optional. Set to any non-zero value to disable OneSync being added to the default configs.

## Check the discord
--https://discord.gg/WrQmADK3
