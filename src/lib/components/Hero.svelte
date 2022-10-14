<script>
	import {config} from "../../config/config"
</script>

<div class="hero">
	<h1>{config.title}</h1>
	<p>{config.description}</p>
</div>

<style>
	
	.hero {
		width: 100vw;
		padding-top: 3rem;
		padding-bottom: 5rem;
		text-align: center;
		background-color: #181818;
		margin-bottom: 6vh;
	}

	.hero h1 {
		font-size: 6rem;
		margin: 0;
		padding: 0;
	}
	.hero p {
		font-size: 1.5rem;
		margin: 0;
		padding: 0;
	}

</style>