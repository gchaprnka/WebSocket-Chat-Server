# WebSocket-Chat-Server

A simple chat server based on the WebSocket protocol. Uses C# 4.0 and external libs [Fleck](http://github.com/statianzo/Fleck) and [Newtonsoft.Json] (http://github.com/JamesNK/Newtonsoft.Json).

See [FlorianWolters/WebSocket-Chat-Client](http://github.com/FlorianWolters/WebSocket-Chat-Client) for an example WebSocket chat client using HTML5, jQuery and CSS.

## Usage

Start the WebSocket chat server with the two arguments `<hostname>` and `<port>`. To start it with the standard configuration (which is also used in the [WebSocket-Chat-Client](http://github.com/FlorianWolters/WebSocket-Chat-Client)) use:
```cmd
WebSocketServer.exe localhost 80
```

# Chat Protocol

A sample chat client implementing the following "protocol" can be found at [FlorianWolters/WebSocket-Chat-Client](http://github.com/FlorianWolters/WebSocket-Chat-Client).

  ```json
  {
      "ts" : "2012-07-05 19:04:00",
      "uid": "Steffen Schuette",
      "msg": "hello, world"
  }
  ```

You expect a JSON object that contains three elements (`ts`, `uid`, `msg`). After the processing of the incoming message you have to send a multicast (or broadcast) to all connected chat clients (including the one that has send the message).

**NOTE:** The message sent, has to be identical to the JSON object described above.

## Used Technologies

* [Microsoft .NET Framework 4 Client Profile](http://microsoft.com/downloads/details.aspx?familyid=5765d7a8-7722-4888-a970-ac39b33fd8ab).
* [Fleck](http://github.com/statianzo/Fleck) v0.9.5-2
* [Newtonsoft.Json](http://github.com/JamesNK/Newtonsoft.Json) v4.5.7
* [StyleCop] (http://stylecop.codeplex.com/) v4.7.34.0 
* [NUnit] (http://nunit.org) v2.6.0.12051 (February 20, 2012)

## TODO

* Write test methods.
* Optimise source code.

## License

This program is free software: you can redistribute it and/or modify it under the terms of the GNU Lesser General Public License as published by the Free Software Foundation, either version 3 of the License, or (at your option) any later version.

This program is distributed in the hope that it will be useful, but WITHOUT ANY WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the GNU Lesser General Public License for more details.

You should have received a copy of the GNU Lesser General Public License along with this program. If not, see http://gnu.org/licenses/lgpl.txt.
