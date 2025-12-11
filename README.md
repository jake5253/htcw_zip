# zip

A set of zip classes in C++

Updated to work on ESP32-C3.
The hex literal 0x06054B50 is typed as int by default in C++, and the compiler sees 8 possible from_le() overloads that could accept it (through implicit conversions).
I had to explicitly cast to uint32_t:
```cpp
if (signature == bits::from_le(static_cast<uint32_t>(0x06054B50)))
```

```ini
[env:airm2m_core_esp32c3]
platform = espressif32
board = airm2m_core_esp32c3
framework = arduino
build_flags = 
    -DARDUINO_USB_MODE=1
    -DARDUINO_USB_CDC_ON_BOOT=1
lib_deps =
    mathieucarbou/ESP Async WebServer @ 3.0.6
    ArduinoJson
    WebSockets
    https://github.com/jake5253/htcw_zip
```
