<script>
	import Hero from "../lib/components/Hero.svelte"
	import ServerGroups from "../lib/components/ServerGroups.svelte"
	import Footer from "../lib/components/Footer.svelte"

	import {config} from "../config/config"
</script>

{#if config.showTitle}
	<Hero/>
{/if}
<ServerGroups/>
{#if config.showFooter}
	<Footer/>
{/if}
