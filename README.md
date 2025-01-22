# VoidTogether-Server (NodeJS)
[![NodeJS](https://img.shields.io/badge/Node.js-6DA55F?logo=node.js&logoColor=white)](#)‎ ‎ '‎ ‎ [![GitHub license](https://img.shields.io/github/license/VoidTogether/VoidTogether-Server?label=License&labelColor=ff903b&color=c9783a)](https://github.com/VoidTogether/VoidTogether-Server/blob/main/LICENSE) ‎ '‎ ‎ [![Discord](https://img.shields.io/discord/1291130292425195570?logo=discord&label=Discord&logoColor=white&labelColor=7674FA&color=9092E7)](https://discord.gg/voidtogether)  ‎ '‎ ‎ [![KoFi](https://img.shields.io/badge/Ko--fi-F16061?logo=ko-fi&logoColor=white)](https://ko-fi.com/gatodev)

Simple, Semi-RPC-Based Multiplayer Mod Server Handler, responsible for Networking Players, Props, and more.

Oh, yeah, and its written in NodeJS, using Websockets.

**WARNING: THIS IS UNFINISHED, AND ONLY FOR THE VOIDTOGETHER SANDBOX CONCEPT DEMO**

## Pre-Requisites:
- Knowing Port Forwarding
- Having a Machine that can reasonably run NodeJS
- Any Relatively New Installation of NodeJS, [you can download it here](https://nodejs.org/en/download)
- Strong Ethernet Connection

## Installing the Server
1. At the top of this Github page, click the "Code" button, and select "Download Zip" at the bottom of the dropdown.

2. Make a folder where you want your installation to be placed, and extract the contents of the Zip file you downloaded into it.

3. Shift + Right Click on the empty space below the extracted files in your file browser and click "Open Powershell window here"

4. In the Powershell Terminal that has opened, type in the command `npm i`. This is required to install all the NodeJS Modules required by the server.

5. Now, whenever you want to Run your Server, open the Powershell Window and run `npm start`.
  
If you have any issues, reinstall your Server, and try deleting the `consoleModule.js` in `./modules/console/` if a Docker container refuses to load beyond the Commands Module.

You can type `help` into the console to see a few available commands that can be run administratively.

## Installing the Server on Pterodactyl
You can use the egg from this [repository](https://github.com/xela-the-proto/Xela-s-pterodactyl-eggs) and install it on the panel

## Configuring a Server
Configuring a server is quite similar to games like SCP: Secret Laboratory and Minecraft. 

While your server is off, open `serverconf.yml`. This is where you can change most of the server settings, such as the Name, MOTD, Discord Tools, and Gameplay Variables.

Everything is mostly explained in the file, so I won't cover too much. Reinstall it from the Github if you have issues after changing yours.

## Permissions
Permissions are handled similarly to SCP: Secret Laboratory and Minecraft, although the main difference is that permissions are stored in a JSON file.

Open up the `permissions.json`, You should see something like this:
```json
{
    "users": {
        "default": [
            "VoidTogether.User"
        ]
    }
}
```
By default, any player that joins will get the perms in the square brackets where "default" is. This is normally used to give your players the basic permissions they need to play the game.

However, if you want control and moderation for your server, you don't want a ton of people running every command all at once. Permissions are handed out based on Machine ID Hash (the big, 64-ish character string attached to the username).

If you want to give yourself every permission you would use the wildcard (aka "I have all permissions under this group of permissions"), symbolized by the `*`. This means if you want all VoidTogether permissions only, you do `VoidTogether.*`.

Here is an example where I give a Reserved Slot (The ability to join when the server is full) to a player.
```json
{
    "users": {
        "default": [
            "VoidTogether.User"
        ],
        "7018CF0D3D5388B800411B39BD933A6103BD68BA8E6CE9571EDDAAFE97F0372C": [
            "VoidTogether.User",
            "VoidTogether.ReservedSlot"
        ]
    }
}
```

Here is a list of the VoidTogether permissions
```
VoidTogether.Admin.Ban
VoidTogether.Admin.Kick
VoidTogether.Admin.Props
VoidTogether.Admin.Server
VoidTogether.Admin.Size
VoidTogether.Admin.Teleport
VoidTogether.Ambient.Time
VoidTogether.ReservedSlot
VoidTogether.User
```
