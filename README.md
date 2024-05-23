<div align="center">
    <h1>McStatus</h1>
    <p>A minimal status page built for Minecraft servers.</p>
    <a href="https://github.com/baylorhenshaw/mcstatus/issues"><img src="https://img.shields.io/github/issues/baylorhenshaw/mcstatus"></a>
    <a href="https://github.com/baylorhenshaw/mcstatus/"><img src="https://img.shields.io/github/forks/baylorhenshaw/mcstatus"></a>
    <a href="https://github.com/baylorhenshaw/mcstatus/"><img src="https://img.shields.io/github/stars/baylorhenshaw/mcstatus"></a>
</div>


## What is McStatus?
McStatus is a minimal status page built for server owners. You can add your server domains/ips and McStatus will let you know if they are online! In the case of an outage, McStatus will allow your players to see which server is offline!

## Local Installation
1. Clone the repository on to your local machine.
2. Run the following commands.
```sh
npm i
npm run dev
```

## Deploying on Vercel
1. Fork this Repository
2. Create a new vercel project with your new forked repository.
3. Deploy!

## Configuration
All configuration files use JSON syntax.
### General Configuration
Configure servers in the `src/config/config.js` file.
```js
export const config = {
	"title": "McStatus",
	"description": "A minimal status page for your Minecraft server.",
	"showVersion": false,
	"showPlayerCount": true,
	"showTitle": true,
	"showFooter": true
}
```
### Server Configuration
Configure servers in the `src/config/servers.js` file.
```js
export const servers = [
	{
		"title": "Popular Servers",
		"servers": [
			{
				"name": "Hypixel",
				"host": "mc.hypixel.net",
				"port": 25565
			},
			{
				"name": "Minehut",
				"host": "minehut.com",
				"port": 25565
			},
			{
				"name": "Wynncraft",
				"host": "play.wynncraft.com",
				"port": 25565
			},
			{
				"name": "CubeCraft",
				"host": "play.cubecraft.net",
				"port": 25565
			}
		]
	}
]
```
