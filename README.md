# nifi-websockets-bundle

A NiFi ListenWebSocket processor

## Basic Setup

### Installation

```sh
$ mvn clean compile package -DskipTests
$ cp nifi-websockets-nar/target/nifi-websockets-nar-0.0.1.nar $NIFI_HOME/lib/
$ nifi start
```

### Dataflow Setup

Make sure the ListenWebSocket NAR has been installed on your NiFi instance [as described above](#installation).

1. Start a WebSocket server.
2. Add the ListenWebSocket processor to your canvas and configure the server property so it's pointing to your WebSocket server ([ws://localhost:8025/websockets/test](ws://localhost:8025/websockets/test) using the example server below).

## WebSocket Server

This bundle includes an example websocket server. You can test it out and connect the NiFi ListenWebSocket processor to it along with WebSocket.org's echo example. First:

```sh
$ java -jar nifi-websockets-bundle/WebSocketServer/target/WebSocketServer-0.0.1.jar
$ open http://www.websocket.org/echo.html
```

Then, enter [ws://localhost:8025/websockets/test](ws://localhost:8025/websockets/test) into the location form field, click connect and start sending messages.

## Todo

1. WSS SSL support
2. Option for batching websocket events into batch messages

![ScreenShot](https://raw.github.com/acesir/nifi-websockets-bundle/master/NiFiExample.png)

## License

Copyright (c) 2016. nifi-put-site-to-site-bundle is released under the Apache License Version 2.0.
