<script>
    export let subcategory;
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
    .hide {
        display: none;
    }
</style>

<div class="subcategory">
    <h3 on:click={toggleSubCategoryCollapse}>{subcategory.name}</h3>
    <div class={subCategoryCollapse}>
        {#each subcategory.children as distortion}
            <div class="cognitive-distortion">
                <a href={`https://en.wikipedia.org/wiki/${distortion.name}`}>
                    <div>{distortion.name}</div>
                </a>
            </div>
        {/each}
    </div>
</div>
