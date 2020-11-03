# MQTT Recorder

Simple tool to record/replay MQTT data written in Python3.

## Installation
Requires the `hbmqtt` library
```
pip3 install hbmqtt
```

## Usage

```
usage: mqtt_recorder.py [-h] [--server URL] [--mode mode]
                        [--input filename] [--output filename] [--append]
                        [--realtime] [--speed factor]
                        [--delay milliseconds] [--debug]

MQTT recorder for all topics of a broker

optional arguments:
  -h, --help            show this help message and exit
  --server URL          MQTT broker e.g. mqtt://127.0.0.1/
  --mode mode           Mode of operation (record/replay)
  --input filename      Input file
  --output filename     Output file
  --append              Append output file
  --realtime            Enable realtime replay
  --speed factor        Realtime speed factor for replay (10=10x)
  --delay milliseconds  Delay between replayed events
  --repeat              Restart playback after end of file
  --debug               Enable debugging
```

### Example
```
# To record a broker's messages to a new file, over-writing if a file already exists
$ python3 mqtt_recorder.py --server mqtt://127.0.0.1/ --mode record --output testrecord.mqtt

# To play back a previously recorded file in realtime
$ python3 mqtt_recorder.py --server mqtt://127.0.0.1/ --mode replay --realtime --input testrecord.mqtt

```