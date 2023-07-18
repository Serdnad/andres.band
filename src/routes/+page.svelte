<script>
  import FaqItem from "$lib/components/FAQItem.svelte";
  import SongCard from "$lib/components/SongCard.svelte";

  const songs = [
    "cacoph1.1.mp3",
    "embers.mp3",
    "heavy_air.mp3",
    "meld1.mp3",
    "lily.mp3",
    "pjzz1.mp3",
    "deepgroove2.mp3",
    "vib.mp3",
    "drone.mp3",
    "beachmeh1.mp3",
    "bubbles01.mp3",
    "keyboardfunk.mp3",
  ];
</script>

<div>
  <h1>Andres' Music</h1>

  <p class="tagline">Like SoundCloud but less convenient</p>

  <p>
    Here's some noodling I've recorded. None of them are finished, but some of
    them I like enough I thought I'd share.
  </p>

  <p>
    P.S. I'm still learning how to mix, they'll sound _much_ better on
    headphones.
  </p>
</div>

<div class="grid">
  {#each songs as song}
    <SongCard {song} />
  {/each}
</div>

<h1>Frequently Asked Questions</h1>

<div class="faq-section">
  <FaqItem
    question="Which andres?"
    answer="Andres, the one from Miami, now in San Francisco."
  />
  <FaqItem
    question="It is just you playing all these instruments?"
    answer="Unfortunately."
  />
  <FaqItem
    question="I like your sound, what DAW do you use?"
    answer="I use BitWig, cause it runs on linux."
  />
  <FaqItem
    question="Can I meet you?"
    answer="Uhh, pretty unlikely, but, you can text me if you want. 786 266 0300, just tell me where you got this number from."
  />
</div>

<style lang="scss">
  .tagline {
    color: rgb(175, 35, 175);
  }

  .grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(180px, 1fr));
    gap: 16px;
  }

  .faq-section {
    display: flex;
    flex-direction: column;
    gap: 16px;
  }
</style>
