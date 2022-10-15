<script>
	import Hero from "../lib/components/Hero.svelte"
	import ServerGroups from "../lib/components/ServerGroups.svelte"
	import Footer from "../lib/components/Footer.svelte"

	import {config} from "../config/config"
</script>

<svelte:head>
	<title>{config.title}</title>
    <meta name="description" content="{config.description}">
    <meta name="og:description" content="{config.description}">
    <meta property="og:title" content="{config.title}" />
    <meta property="og:type" content="website" />
    <meta name="keywords" content="Minecraft Status, Status Page, Status, Minecraft, {config.title}">
    <meta name="author" content="Baezor">
    <meta name="theme-color" content="#323c39" />
</svelte:head>

{#if config.showTitle}
	<Hero/>
{/if}
<ServerGroups/>
{#if config.showFooter}
	<Footer/>
{/if}

<style>
	.abc {
		background-color: lime;
	}
</style>
