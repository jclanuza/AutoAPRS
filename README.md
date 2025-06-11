🛰️ AutoAPRS Beaconing System

AutoAPRS is a lightweight, standalone C# console application designed to send APRS (Automatic Packet Reporting System) beacons automatically over the APRS-IS network. It is ideal for unattended stations, fixed-location nodes, or experimental setups running on Windows.

The software operates via TCP, following the APRS protocol specifications, and can be fully configured using a plain-text config.txt file. It features a simple user interface with real-time status, transmission counters, visual progress bars, and optional audio feedback.

✨ Features
🔁 Automatic beacon transmission at configurable intervals (in minutes)

🌍 Custom coordinates, callsign, comments, and symbols

🖥️ Console-based UI with ASCII banners, timers, and rotating loading animations

📶 TCP connection to APRS-IS servers (rotate.aprs2.net or custom)

🔊 Optional roger beep (Quindar tone) after each transmission

🎨 Real-time progress bar with time countdown to the next beacon

🔐 APRS passcode automatically generated from your callsign (no need to input manually)

🧠 Built-in validation for common misconfigurations and security against malformed inputs

⚙️ Example Configuration (config.txt)
ini
Copy
Edit
# General AutoAPRS Configuration | YN1JLX
# Do NOT write inline comments on config lines.

# Callsign with SSID
callsign=YN1XXX-1

# Latitude and longitude (no leading dot, use N/S and E/W)
latitude=1214.38N
longitude=08600.08W

# APRS comment (e.g. location or purpose)
comment=AutoAPRS Beaconing System

# Station status or additional text
state=AutoAPRS Software System

# Symbol table selection (primary) and icon (secondary)
symbol_primary=/
symbol_secondary=n

# APRS-IS server and port
server_host=rotate.aprs2.net
server_port=14580

# Time between beacons, in minutes
every=10
For help choosing the correct APRS symbols and table codes, refer to:
📚 https://blog.thelifeofkenneth.com/2017/01/aprs-symbol-look-up-table.html

🛠 Requirements
Windows OS (Console)

.NET Framework 4.6+ or .NET 5/6/7 if compiled with Core

Internet access to connect to APRS-IS

📡 How It Works
Upon launch, the program:

Loads and validates the config.txt file.

Generates the APRS passcode using your callsign.

Connects to the APRS server and sends:

A status/info packet

A position beacon with your defined coordinates and symbol

Waits the configured interval with a live progress bar and rotating indicator.

Repeats the process indefinitely.

Each beacon sent is logged to the console with timestamps and server information.

🔐 Disclaimer
This software is provided in binary form only under a custom license. You may use it freely for personal, educational, and experimental use, but redistribution, reverse engineering, and unauthorized modification are strictly prohibited. See the LICENSE file for full terms.
