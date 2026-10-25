<div align="center">

# mqttui

**Explore MQTT from your terminal**

[![mqttui](https://snapcraft.io/mqttui/badge.svg)](https://snapcraft.io/mqttui)
[![Base: core26](https://img.shields.io/badge/Base-core26-2C8C3C?logo=canonical&logoColor=white)](https://snapcraft.io/core26)
![Confinement: strict](https://img.shields.io/badge/Confinement-strict-2C8C3C)
[![Maintainer: sidaliteir](https://img.shields.io/badge/Maintainer-sidaliteir-2C8C3C?logo=snapcraft&logoColor=white)](https://snapcraft.io/publisher/sidaliteir)
![Architectures: amd64 and arm64](https://img.shields.io/badge/Architectures-amd64%20%7C%20arm64-2C8C3C?logo=linux&logoColor=white)

[Getting Started](#getting-started) · [Configure](#configure) · [Limitations](#limitations) · [Build](#build) · [Support](#support) · [License](#license)

Unofficial snap packaging for [mqttui](https://github.com/EdJoPaTo/mqttui), a terminal interface for browsing MQTT topics and publishing messages.

</div>

---

## Getting Started

<a href="https://snapcraft.io/mqttui"><img alt="Get it from the Snap Store" src="https://snapcraft.io/en/dark/install.svg" width="180"></a>

```bash
sudo snap install mqttui
mqttui --broker mqtt://test.mosquitto.org "hello/world"
```

The example connects to a public test broker. Use your own broker for private messages.

## Configure

There are no `snap set` options. Supply connection settings as command-line options; run `mqttui --help` for the complete list.

| Option | Accepted value |
| --- | --- |
| `--broker` | Broker URL, such as `mqtt://broker.example` or `mqtts://broker.example` |
| `--ca-cert` | Path to a CA certificate |
| `--client-cert` | Path to a client certificate |
| `--client-private-key` | Path to the client private key |

Keep certificate files in an accessible folder, such as `~/mqtt-certs`:

```bash
mqttui --broker mqtts://broker.example --ca-cert ~/mqtt-certs/ca.crt
```

## Limitations

- Hidden folders directly under your normal home directory, such as `~/.mqtt`, and system paths such as `/etc/mosquitto/certs` are inaccessible.
- Copy certificates and keys to a normal folder in your home directory before using them. This snap does not expose removable storage.

## Build

```bash
git clone https://github.com/sidalit/mqttui-snap.git
cd mqttui-snap
sudo snap install snapcraft --classic
snapcraft pack
```

## Support

- **Installation or snap issues:** [open a packaging issue](https://github.com/sidalit/mqttui-snap/issues).
- **Application bugs:** [report them upstream](https://github.com/EdJoPaTo/mqttui/issues).

## License

Snap packaging: [MIT](https://github.com/sidalit/mqttui-snap/blob/main/LICENSE).
