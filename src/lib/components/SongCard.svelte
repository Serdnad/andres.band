<script lang="ts">
  import { onMount } from "svelte";

  export let song: string;

  let playing = false;
  let audio: HTMLAudioElement;
  let trackProgress = 0;

  onMount(() => {
    audio = new Audio(`/music/${song}`);
  });

  function togglePlaying() {
    if (playing) {
      audio.pause();
    } else {
      audio.play();

      setInterval(() => {
        trackProgress = (100 * audio.currentTime) / audio.duration;
      }, 100);
    }

    playing = !playing;
  }
</script>

<div class="container {playing ? 'playing' : ''}" on:click={togglePlaying}>
  <div>
    <p>{song}</p>
  </div>

  <div class="progress" style="width: {trackProgress}%;" />
</div>

<style lang="scss">
  * {
    color: white;
  }

  .container {
    cursor: pointer;
    transition: all 0.25s ease-in-out;
    position: relative;
    background: black;
    border: 0.5px solid #dddddd;
    padding: 4px 8px;

    height: 48px;

    &.playing {
      background: rgb(74, 7, 98);
    }

    .progress {
      position: absolute;
      bottom: 0;
      left: 0;

      transition: all 0.25s ease-in-out;
      background: green;

      height: 4px;
    }
  }
</style>
