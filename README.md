# Munin plugin for the DHT22 temperature and humidity sensor

Munin Plugin for monitoring the DHT22 temperature and humidity sensor
on a Raspberry Pi

## Dependencies

The `Adafruit CircuitPython DHT` library is required:

```
pip3 install adafruit-circuitpython-dht
```

## Installation

Copy the `dht22` file somewhere:

```
cp dht22 /usr/local/share/munin/plugins/
```

## Enablement

### Enable plugin
Link the plugin to `/etc/munin/plugins/dht22` to enable the plugin:

```
ln -s /usr/local/share/munin/plugins/dht22 /etc/munin/plugins/dht22
```

Possibly you have to change the connected pins. For this, adjust the
source code. The plugin expectes two sensors: one on GPIO4, one on GPIO22.

### Create configuration file

Create the `/etc/munin/plugin-conf.d/dht` configuration file:

```
[dht22]
user root
```

### Restart munin

```
systemctl restart munin-node.service
```

