
# Raspberry Pi Setup for Multiple Services

This repository contains scripts to set up various services on a Raspberry Pi, particularly using Pi OS Lite. It is designed to facilitate a quick deployment of common services for personal use or small-scale server setups.

## Services Included

- **Home Assistant**: An open-source home automation platform that puts local control and privacy first.
- **ESPHome**: Helps in creating custom firmware for ESP8266/ESP32 devices.
- **Pi-hole**: A network-wide ad blocking service that acts as a DNS sinkhole.
- **Plex Media Server**: For organizing and streaming your media on any device.
- **Mumble Server (Murmur)**: A low-latency, high-quality voice chat software primarily intended for use while gaming.
- **Deluge**: A lightweight, Free Software, cross-platform BitTorrent client with a Web UI.

## Installation Script

The main script, `install_services.sh`, automates the installation of the above services. It sets up everything from user permissions to service daemons, ensuring each component is ready to use right after the script finishes.

### Running the Script

To run the installation script, clone the repository and execute the following command:

```bash
sudo ./install_services.sh
```

Ensure that you have sufficient permissions and your Raspberry Pi is connected to the internet before running the script.

## Maintenance Script

To ensure all services remain updated and operational, a maintenance script, `maintain_services.sh`, is included. It performs system updates, updates services, and ensures all services are running correctly.

### Setting Up the Maintenance Script

To automatically run this maintenance script, add it to your crontab:

```bash
(crontab -l 2>/dev/null; echo "0 * * * * /path/to/maintain_services.sh >> /path/to/logfile.log 2>&1") | crontab -
```

Replace `/path/to/maintain_services.sh` with the actual path where the script is stored.

## Additional Setup for Plex on Separate Subdomains

If you're running Plex on a different subdomain and using Pi OS Lite without the Pi OS desktop interface, you need to configure XRDP for remote desktop access. Run the `rdp.sh` script provided in this repository to set up XRDP with XFCE, which allows for a graphical interface over remote connections.

### Running the RDP Setup Script

```bash
sudo ./rdp.sh
```

This script will prompt for the creation of a new user dedicated to XRDP, install necessary packages, and configure the system for remote access.

## Notes

- Before running the installation scripts, ensure your system is up-to-date and has internet access.
- Modifications might be required based on your specific hardware or network configuration.

For detailed information about configuring and using each service, refer to their respective official documentation or community forums.

---

For issues, suggestions, or contributions, please [file an issue](https://github.com/battlefeel1942/raspberry-pi_a-few-things/issues) on this repository.
