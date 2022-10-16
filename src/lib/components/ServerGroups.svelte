<script>
	import Server from "./Server.svelte"
	import TotalServers from "./TotalServers.svelte"
	import {servers} from "../../config/servers.js"
	import {config} from "../../config/config.js"

	let offline = 0

	async function getServer(host, port) {
		const res = await fetch("https://mcapi.us/server/status?ip="+ host + ":" + port);
		const json = await res.json();

		console.log(host + ":" + port + " - " + json.status)
		if (json.status) {
			if (json.status == "error") {
				offline++
			}
			return json;
		} else {
			throw new Error(json);
		}
	}
</script>

<TotalServers offline={offline}/>
<div class="group-container">
	{#each servers as group}
		<div class="server-group-container">
			<h1>{group.title}</h1>
		</div>
		<div class="server-group-container">
			{#each group.servers as server}
				{#await getServer(server.host, server.port)}
					<Server
						name="{server.name}"
						status="loading"
						online=0
						max=0
						version="Unknown"
						protocol="Unknown"
					/>
				{:then json}
					<Server
						name="{server.name}"
						status="{json.status}"
						online="{json.players.now}"
						max="{json.players.max}"
						version="{json.server.name}"
						protocol="{json.server.protocol}"
					/>
				{:catch error}
					<Server
						name="{server.name}"
						status="fail"
						online=0
						max=0
						version="Unknown"
						protocol="Unknown"
					/>
				{/await}

			{/each}
		</div>
	{/each}
</div>

<style>
	
	.group-container {
		display: flex;
		justify-content: center;
		width: 100vw;
		flex-direction: column;
	}

	.server-group-container {
		border-radius: 12px;
		overflow: hidden;
		width: 54vw;
		margin-top: 0vw;
		margin-bottom: 0vw;
		margin-left: 22.5vw;
		flex-direction: column;
	}

	.total-container {
		border-radius: 12px;
		overflow: hidden;
		width: 54vw;
		margin-top: 0vw;
		margin-bottom: 0vw;
		margin-left: 22.5vw;
		flex-direction: column;
	}

	@media (max-width: 1200px) {
		.server-group-container {
			width: 88vw;
			margin-left: 6vw;
		}
	}

</style>