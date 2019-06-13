<style lang="scss">
  $color: violet;

  button {
    background-color: $color;
    font-size: 1.2rem;
    padding: 0.25rem 1rem;
  }
</style>

<button on:click>
  <slot />
</button>
