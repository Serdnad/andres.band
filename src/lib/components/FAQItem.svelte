<script lang="ts">
  export let question: string;
  export let answer: string;

  let expanded = false;
</script>

<div class={expanded ? "expanded" : ""} on:click={() => (expanded = !expanded)}>
  <p class="question">{question}</p>
  <hr />
  <p class="answer">{answer}</p>
</div>

<style lang="scss">
  div {
    transition: all 0.25s ease-in-out;
    cursor: pointer;

    height: 32px;
    overflow: hidden;

    p {
      margin: 0;
    }

    .question {
      font-weight: bold;
    }

    &.expanded {
      height: fit-content;
    }
  }
</style>
