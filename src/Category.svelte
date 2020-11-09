<script>
    import Subcategory from "./Subcategory.svelte";
    export let category;
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

<div class="category">
    <h2 on:click={toggleCategoryCollapse}>{category.name}</h2>
    <div class={categoryCollapse}>
        {#each category.children as subcategory}
            <Subcategory {subcategory} />
        {/each}
    </div>
</div>
