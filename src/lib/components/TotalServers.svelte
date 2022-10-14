<script>
	export let offline
</script>

<div class="total-servers">
	{#if offline > 0}
		<svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="orange" class="bi bi-exclamation-circle-fill" viewBox="0 0 16 16">
			<path d="M16 8A8 8 0 1 1 0 8a8 8 0 0 1 16 0zM8 4a.905.905 0 0 0-.9.995l.35 3.507a.552.552 0 0 0 1.1 0l.35-3.507A.905.905 0 0 0 8 4zm.002 6a1 1 0 1 0 0 2 1 1 0 0 0 0-2z"/>
		</svg>
		<h1>{offline} Detected Outage</h1>
	{:else}
		<svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="lime" class="bi bi-check-circle-fill" viewBox="0 0 16 16">
			<path d="M16 8A8 8 0 1 1 0 8a8 8 0 0 1 16 0zm-3.97-3.03a.75.75 0 0 0-1.08.022L7.477 9.417 5.384 7.323a.75.75 0 0 0-1.06 1.06L6.97 11.03a.75.75 0 0 0 1.079-.02l3.992-4.99a.75.75 0 0 0-.01-1.05z"/>
		</svg>
		<h1>All systems are alive!</h1>
	{/if}
</div>

<style>

	.total-servers {
		display: flex;
		flex-direction: row;
		align-items: center;
		justify-content: center;
		background-color: #212121;
		text-align: center;
		padding: 2vw;
		margin: 0;
		width: 70vw;
		border-radius: 12px;
		margin-left: 10.5vw;
	}

	.total-servers svg {
		width: 2rem;
		height: 2rem;
		padding-right: 4vh;
	}

	.total-servers h1 {
		padding: 0;
		margin: 0;
		font-size: 2rem;
	}

	.total-servers p {
		padding: 0;
		margin: 0;
		text-align: right;
		font-size: 1.3rem;
		font-weight: 700;
	}
</style>