<!-- App.svelte -->
<script>
  import Clock from "./components/Clock.svelte"

  let time = new Date()
  setInterval(() => {
    time = new Date()
  }, 1000)
</script>

<div class="container">
  <Clock {time} />
</div>

<style>
  .container {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    height: 100vh;
  }
</style>
