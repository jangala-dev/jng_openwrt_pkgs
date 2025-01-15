This repo contains packages we wan't to install on our openwrt system that don't exist on openwrt.

### atinout
Allows us to run at commands to communicate with modems.

### jng-device-specific
Prevents getbox from rebooting.

### libubootenv
Library to access uboot firmware environment variables (currently outdated now on 0.3.6).

### lua-http
Http server. Needs following dependencies to work:
* lpeg_patterns
* lua-basexx
* lua-binaryheap
* lua-bit32
* lua-compat53
* lua-cqueues
* lua-fifo

### lua-lumen
Lumen is a very simple environment for coroutine based multitasking

### lua-popen3
The lua-popen3 library provides a Lua interface for executing external commands with full control over their standard input, output, and error streams (stdin, stdout, stderr). It enables bi-directional communication with processes.

### luamqtt
The luamqtt library is a pure Lua implementation of the MQTT protocol, enabling clients to publish and subscribe to MQTT topics for messaging in IoT and real-time applications.

### luaossl
The luaossl library provides a comprehensive Lua binding to OpenSSL, enabling cryptographic operations such as encryption, decryption, signing, certificate handling, and secure network communication.

### swupdate
swupdate is a flexible and powerful software update framework for embedded Linux systems. It supports OTA (Over-the-Air) and local updates, handling firmware, bootloader, and application updates. It provides features like update validation, rollback mechanisms, and support for various formats (e.g., raw binaries, compressed files, and container formats).