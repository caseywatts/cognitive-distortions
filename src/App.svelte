<script>
	import cognitiveDistortions from "./cognitive_distortions.json";
	let categoryCollapse = "";
	function toggleCategoryCollapse() {
		if (categoryCollapse === "") {
			categoryCollapse = "hide";
		} else {
			categoryCollapse = "";
		}
	}
	let subCategoryCollapse = "hide";
	function toggleSubCategoryCollapse() {
		if (subCategoryCollapse === "") {
			subCategoryCollapse = "hide";
		} else {
			subCategoryCollapse = "";
		}
	}
</script>

<style>
	h2,
	h3 {
		margin: 0;
		cursor: pointer;
	}
	.category {
		background: #ddd;
		border-radius: 0.5rem;
		padding: 1rem;
		margin: 1rem;
	}
	/* .category:nth-child(1) {
		background: red;
	}
	.category:nth-child(2) {
		background: orange;
	}
	.category:nth-child(3) {
		background: yellow;
	}
	.category:nth-child(4) {
		background: green;
	} */
	.subcategory {
		background: #eee;
		border-radius: 0.5rem;
		padding: 0.5em;
		margin: 0.5rem;
	}
	.cognitive-distortion {
		background: #fff;
		border-radius: 0.5rem;
		padding: 1rem;
		margin: 1rem;
		display: inline-block;
		min-width: 15rem;
		text-align: center;
	}
	/* .cognitive-distortion:nth-child(1) {
		background: #ddd;
	}
	.cognitive-distortion:nth-child(7n + 2) {
		background: #ccc;
	}
	.cognitive-distortion:nth-child(7n + 3) {
		background: #bbb;
	} */
	.hide {
		display: none;
	}
</style>

<div>
	{#each cognitiveDistortions.children as category}
		<div class="category">
			<h2 on:click={toggleCategoryCollapse}>{category.name}</h2>
			<div class={categoryCollapse}>
				{#each category.children as subcategory}
					<div class="subcategory">
						<h3 on:click={toggleSubCategoryCollapse}>
							{subcategory.name}
						</h3>
						<div class={subCategoryCollapse}>
							{#each subcategory.children as distortion}
								<div class="cognitive-distortion">
									<a
										href={`https://en.wikipedia.org/wiki/${distortion.name}`}>
										<div>{distortion.name}</div>
									</a>
								</div>
							{/each}
						</div>
					</div>
				{/each}
			</div>
		</div>
	{/each}
</div>
