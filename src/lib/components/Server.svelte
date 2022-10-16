<script>
	export let name
	export let status
	export let online
	export let max
	export let version
	export let protocol

	import {config} from "../../config/config.js"
</script>

{#if status == "success"}
	<div class="server-container online">
		<svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor" class="bi bi-check-circle-fill" viewBox="0 0 16 16">
			<path d="M16 8A8 8 0 1 1 0 8a8 8 0 0 1 16 0zm-3.97-3.03a.75.75 0 0 0-1.08.022L7.477 9.417 5.384 7.323a.75.75 0 0 0-1.06 1.06L6.97 11.03a.75.75 0 0 0 1.079-.02l3.992-4.99a.75.75 0 0 0-.01-1.05z"/>
		</svg>
		<div class="spacer">
			<div>
				<h1 style="text-align: left;">{name}</h1>
				{#if config.showVersion == true}
					<p style="text-align: left; font-size: 1rem; font-weight: 400; color: lightgray;">{version}</p>
				{/if}
			</div>
			{#if config.showPlayerCount == true}
				<p>{online}/{max}</p>
			{/if}
		</div>
	</div>
{:else if status == "error"}
	<div class="server-container offline">
		<svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor" class="bi bi-exclamation-circle-fill" viewBox="0 0 16 16">
			<path d="M16 8A8 8 0 1 1 0 8a8 8 0 0 1 16 0zM8 4a.905.905 0 0 0-.9.995l.35 3.507a.552.552 0 0 0 1.1 0l.35-3.507A.905.905 0 0 0 8 4zm.002 6a1 1 0 1 0 0 2 1 1 0 0 0 0-2z"/>
		</svg>
		<div class="spacer">
			<h1>{name}</h1>
			<p>Offline</p>
		</div>
	</div>
{:else if status == "fail"}
	<div class="server-container offline">
		<svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="red" class="bi bi-exclamation-circle-fill" viewBox="0 0 16 16">
			<path d="M16 8A8 8 0 1 1 0 8a8 8 0 0 1 16 0zM8 4a.905.905 0 0 0-.9.995l.35 3.507a.552.552 0 0 0 1.1 0l.35-3.507A.905.905 0 0 0 8 4zm.002 6a1 1 0 1 0 0 2 1 1 0 0 0 0-2z"/>
		</svg>
		<div class="spacer">
			<h1>{name}</h1>
			<p>An Error Occured</p>
		</div>
	</div>
{:else}
	<div class="server-container">
		<svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor" class="bi bi-gear-fill" viewBox="0 0 16 16">
			<path d="M9.405 1.05c-.413-1.4-2.397-1.4-2.81 0l-.1.34a1.464 1.464 0 0 1-2.105.872l-.31-.17c-1.283-.698-2.686.705-1.987 1.987l.169.311c.446.82.023 1.841-.872 2.105l-.34.1c-1.4.413-1.4 2.397 0 2.81l.34.1a1.464 1.464 0 0 1 .872 2.105l-.17.31c-.698 1.283.705 2.686 1.987 1.987l.311-.169a1.464 1.464 0 0 1 2.105.872l.1.34c.413 1.4 2.397 1.4 2.81 0l.1-.34a1.464 1.464 0 0 1 2.105-.872l.31.17c1.283.698 2.686-.705 1.987-1.987l-.169-.311a1.464 1.464 0 0 1 .872-2.105l.34-.1c1.4-.413 1.4-2.397 0-2.81l-.34-.1a1.464 1.464 0 0 1-.872-2.105l.17-.31c.698-1.283-.705-2.686-1.987-1.987l-.311.169a1.464 1.464 0 0 1-2.105-.872l-.1-.34zM8 10.93a2.929 2.929 0 1 1 0-5.86 2.929 2.929 0 0 1 0 5.858z"/>
		</svg>
		<div class="spacer">
			<h1>{name}</h1>
		</div>
	</div>
{/if}

<style>
	.server-container {
		text-align: center;
		background-color: #181818;
		padding: 2vw;
		margin: 0;
		width: 50vw;
		display: flex;
		align-items: center;
	}

	.server-container h1 {
		padding: 0;
		margin: 0;
		font-size: 1.3rem;
	}

	.server-container p {
		padding: 0;
		margin: 0;
		text-align: right;
		font-size: 1.3rem;
		font-weight: 700;
	}

	.server-container svg {
		width: 2rem;
		height: 2rem;
		padding-right: 2vw;
	}

	.online svg {
		color: lime;
	}

	.offline svg {
		color: orange;
	}

	.offline p {
		padding: 0;
		margin: 0;
		text-align: right;
		font-size: 1rem;
		font-weight: 700;
		color: lightgray;
	}

	.online {
		background-color: #212121;
	}

	.offline {
		background-color: #181818;
	}

	.spacer {
		display: flex;
		justify-content: space-between;
		align-items: center;
		width: 100%;
	}

	@media (max-width: 1200px) {
		.server-container {
			width: 80vw;
			padding: 4vw;
		}
		.server-container svg {
			width: 2rem;
			height: 2rem;
			padding-right: 4vw;
		}

		.server-container h1 {
			font-size: 1.1rem;
		}

		.server-container p {
			font-size: 0.9rem;
			font-weight: 400;
		}

	}
</style>