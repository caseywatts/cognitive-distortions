<script>
	import cognitiveDistortions from "./cognitive_distortions.json";
	import Category from "./Category.svelte";
</script>

<style>
</style>

<div>
	<h1>Cognitive Distortions Reference</h1>
	<p>
		Data from
		<a href="https://www.twitter.com/buster">Buster Benson</a>
		<a
			href="https://github.com/busterbenson/public/blob/master/cognitive-bias-cheat-sheet.json">on
			github</a>
	</p>
	{#each cognitiveDistortions.children as category}
		<Category {category} />
	{/each}
</div>
