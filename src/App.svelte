<script>
  import Product from "./Product.svelte";
  import Button from "./Button.svelte";
  let title = "";
  let price = 0;
  let description = "";

  let products = [];

  function createProduct() {
    const newProduct = {
      title,
      price,
      description
    };
    products = products.concat(newProduct);
  }
</script>

<style>
  section {
    width: 30rem;
    margin: auto;
  }

  label,
  input,
  textarea {
    width: 100%;
  }
</style>

<section>
  <div>
    <label for="title">Title</label>
    <input type="text" id="title" placeholder="Title" bind:value={title} />
  </div>

  <div>
    <label for="price">Price</label>
    <input type="number" id="price" placeholder="20kr" bind:value={price} />
  </div>

  <div>
    <label for="description">Description</label>
    <textarea
      rows="3"
      id="description"
      placeholder="A nice description of item"
      bind:value={description} />
  </div>

  <Button on:click={createProduct}>Create product</Button>
</section>

<section>
  {#if products.length === 0}
    <p>No products were added yet!</p>
  {:else}
    {#each products as product}
      <Product
        productTitle={product.title}
        productPrice={product.price}
        productDescription={product.description} />
    {/each}
  {/if}
</section>
