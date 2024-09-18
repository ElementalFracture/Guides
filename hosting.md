# Spellbreak Community: How to Host a Server

This guide explains how to host your own match on a server you control. If you're looking to play in someone else’s match, check out the [setup guide](guide.md). **While Elemental Fracture doesn't provide explicit support in hosting your own servers, such as assistance with setting up portforwarding, we are happy to assist by providing the general steps to get set up.**

## Clients and Servers

Spellbreak Community Edition is divided into two components:

- **Client**: This includes all the graphics and menus. Each player needs their own copy.
- **Server**: This runs without graphics or menus and is used to host matches. You’ll need access to the server to host a game.

To host a match, the server must be accessible to the players who want to join. The guide below will help you set up your own server.

## Table of Contents

- [Player Location Matters](#player-location-matters)
  - [Local Players](#local-players)
  - [Internet Players](#internet-players)
- [Running the Server](#running-the-server)
  - [Prerequisites](#prerequisites)
  - [Choose a Game Mode and Run](#choose-a-game-mode-and-run)
- [Additional Notes and Troubleshooting](#additional-notes-and-troubleshooting)

---

## Player Location Matters

Players need the server’s **IP address** and **Port number** to connect. The default port for Spellbreak is `7777`. 

- If you’re hosting for players on the same local network, check the [Local Players](#local-players) section.
- If you’re hosting for players over the internet, check the [Internet Players](#internet-players) section.

### Local Players

If players are on the same local network (e.g., in the same house or office), finding the server's IP is simple. Follow these steps:

1. Open the command prompt and enter:
   ```bash
   ipconfig
   ```
   This will give you an IP address, such as:
   ```
   192.168.1.41:7777
   ```

2. Share the IP:Port combo with players on the local network so they can connect.

---

### Internet Players

If players are not on the same local network, they will need the public IP of your server.

1. To find your public IP, open a browser and search for "What is my IP?". Use the IP address displayed, like this:
   ```
   203.0.113.5:7777
   ```

2. If your local and public IPs differ, your server may be behind a **NAT Gateway**, and you will need to configure **port forwarding**.

---

### NAT Gateways and Port Forwarding

In most cases, NAT Gateways block incoming connections from the internet. You’ll need to set up **port forwarding** to allow players to connect.

1. **Access the configuration page** for your router/modem.
   - This could be an app or a web page with an address like `http://192.168.1.1`.
   
2. **Log in** to the configuration page. If you don’t know the login credentials, search for the default password or contact your ISP.

3. **Find the Port Forwarding settings**, often under menus like "Firewall" or "NAT".

4. **Add a port forwarding rule**:
   - **Protocol**: UDP (or TCP/UDP).
   - **Device IP**: The local IP of your server.
   - **Port**: 7777 (or a range from 7777 to 7778).

---

## Running the Server

To host a server, you need to download [the server files](https://cdn.elefrac.com/server/server.zip)`, then extract it to a folder of your choice.

### Prerequisites

Before running the server for the first time, install the **Unreal Engine 4 Prerequisites**:

- For 64-bit Windows: `UE4PrereqSetup_x64.exe`
- For 32-bit Windows: `UE4PrereqSetup_x86.exe`

**NOTE: If you've already installed these for the client, you don’t need to install them again.**

---

### Installing the Balance Patch

Much like the manual setup in our [setup guide](guide.md), you'll need to install the balance patch manually.
1. Download the latest balance patch from [here](https://cdn.elefrac.com/patch/latest.zip).
2. Extract the ZIP file and place the contents into the following directory within your game folder: `g3/Content/Paks`.

### Choose a Game Mode and Run

The server can be started by running one of the included batch files, such as `Start_a_Duos_server.bat`. This will open a terminal window, and you’ll see text scrolling by. Some lines may include "Warning," which is normal.

1. If a **Windows Security Alert** appears, make sure both checkboxes are checked and click "Allow access".
2. Players can now join by entering the IP:Port combo for the server.

---

## Additional Notes and Troubleshooting

- The server may take 1-2 minutes to load the world. Players will be able to join once the scrolling text stops.
- **Avoid running multiple servers** on the same machine, as they can conflict over port numbers.
  - Check Task Manager for any instances of `g3Server-Win64-Test.exe`. There should only be one per server.
- If a client cannot connect or remains on "connecting" for too long, check the server status and port forwarding.
- Check out the [FAQ](faq.md) which has some additional troubleshooting steps.
