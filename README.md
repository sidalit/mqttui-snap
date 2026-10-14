# mqttui snap

[![mqttui](https://snapcraft.io/mqttui/badge.svg)](https://snapcraft.io/mqttui)

Snap packaging for [mqttui](https://github.com/EdJoPaTo/mqttui), a terminal interface for browsing MQTT topics and publishing messages.

Unofficial build, not affiliated with or endorsed by the mqttui project.

## Build

```bash
snapcraft pack
```

## Install and try

<a href="https://snapcraft.io/mqttui"><img alt="Get it from the Snap Store" src="https://snapcraft.io/en/dark/install.svg" width="180"></a>

```bash
sudo snap install mqttui                   # or a local build: ./mqttui_0.24.0_*.snap --dangerous
mqttui --broker mqtt://test.mosquitto.org "hello/world"
mqttui publish "hello/world" "Hi"
mqttui read-one "hello/world"
```

## Known limitations

### Certificate files outside your home folder

`--ca-cert`, `--client-cert` and `--client-private-key` can only read files in your home folder. Hidden folders directly in it (such as `~/.mqtt`) and system paths (such as `/etc/mosquitto/certs`) are blocked by strict confinement. Copy the files to a normal folder in your home:

```bash
mkdir -p ~/mqtt-certs
cp /etc/mosquitto/certs/ca.crt ~/mqtt-certs/
mqttui --broker mqtts://broker.example --ca-cert ~/mqtt-certs/ca.crt
```

## Update to a new upstream release

Change `version` and `source-tag` in `snap/snapcraft.yaml`, then rebuild.

## License

The packaging is MIT-licensed (see `LICENSE`). mqttui is GPL-3.0-or-later; its dependencies carry their own licenses.
