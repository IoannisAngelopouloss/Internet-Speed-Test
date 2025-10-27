# Internet-Speed-Test
Python script to measure internet speed (download, upload, ping) using speedtest-cli.
## Features
- Measure download and upload speed in Mbps
- Measure ping in ms
- Uses the best server automatically
- Lightweight and easy to use

## Installation
1. Install Python 3.6+
2. Install the required package:
   ```bash
   python -m pip install --user speedtest-cli

import speedtest  

def check_internet_speed():
    st = speedtest.Speedtest()   
    st.get_best_server()      
    
    print("...Testing speed, please wait...\n")

    download = st.download() / 1_000_000  # Μετατροπή σε Mbps
    upload = st.upload() / 1_000_000      # Μετατροπή σε Mbps
    ping = st.results.ping                # Ping σε ms

    return {
        "download_mbps": round(download, 2),
        "upload_mbps": round(upload, 2),
        "ping_ms": round(ping, 2)
    }

# Κλήση της συνάρτησης
speed = check_internet_speed()

# Εμφάνιση αποτελεσμάτων
print(f"Download Speed: {speed['download_mbps']} Mbps")
print(f"Upload Speed: {speed['upload_mbps']} Mbps")
print(f"Ping: {speed['ping_ms']} ms")


