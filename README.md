# Meetly Clip (MR20) firmware feed

The Meetly app reads mr20/firmware.json on this branch (raw.githubusercontent.com) and lists every build under Settings › Meetly Clip › Firmware. Any build can be installed; an older one is the rollback.

Add a build: put the .bin in mr20/, append an entry (version, channel stable|experimental, file, sha256, bytes, frameBytes 244, numbered true, reportedAs, notes), push to firmware-mr20. No app build needed. Experimental builds show only in Debug and TestFlight.

Before sending, the app checks size, SHA-256, the AOTA magic and both CRC32s, and the board name in ota.xml. Rollback is an ordinary OTA: it works only while the installed firmware boots and accepts BLE&OTA.
