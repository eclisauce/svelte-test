<style>
  button {
    font: inherit;
    padding: 0.15rem 0.5rem;
    background: #d10057;
    border: 1px solid #d10057;
    color: #fff;
    cursor: pointer;
  }

  button:hover,
  button:active {
    box-shadow: 0 2px 2px rgba(0, 0, 0, 0.26);
  }
</style>

<button on:click>
  <slot />
</button>
