<script>
  export let time = new Date()
  $: hours = time.getHours()
  $: minutes = time.getMinutes()
  $: seconds = time.getSeconds()

  $: mfive = (minutes >= 5 && minutes < 10) || (minutes >= 55 && minutes <= 59)
  $: mten = (minutes >= 10 && minutes < 15) || (minutes >= 50 && minutes < 55)
  $: quarter =
    (minutes >= 15 && minutes < 20) || (minutes >= 45 && minutes < 50)
  $: twenty =
    (minutes >= 20 && minutes < 30) || (minutes >= 40 && minutes <= 45)
  $: half = minutes >= 30 && minutes < 45

  $: to = minutes >= 40
  $: past = minutes >= 5 && minutes < 40
  $: oclock = minutes < 5

  $: one = hours === 1 || hours === 13
  $: two = hours === 2 || hours === 14
  $: three = hours === 3 || hours === 15
  $: four = hours === 4 || hours === 16
  $: five = hours === 5 || hours === 17
  $: six = hours === 6 || hours === 18
  $: seven = hours === 7 || hours === 19
  $: eight = hours === 8 || hours === 20
  $: nine = hours === 9 || hours === 21
  $: ten = hours === 10 || hours === 22
  $: eleven = hours === 11 || hours === 23
  $: twelve = hours === 12 || hours === 0

  const pad = (val) => (val >= 10 ? val : "0" + val)
</script>

<div class="clock">
  <div class="wordClock">
    <span class="on_pre">it</span><span>t</span><span class="on_pre">is</span
    ><span>v</span><span class:on_num={twenty}>twenty</span><br />
    <span class:on_num={quarter}>quarter</span><span class:on_num={half}
      >half</span
    ><span>m</span><br />
    <span class:on_num={mten}>ten</span><span class:on_num={mfive}>five</span
    ><span>e</span><span class:on_ins={past}>past</span><br />
    <span class:on_ins={to}>to</span><span>a</span><span class:on_num={twelve}
      >twelve</span
    ><span class:on_num={one}>one</span><br />
    <span class:on_num={two}>two</span><span class:on_num={three}>three</span
    ><span class:on_num={four}>four</span><br />
    <span class:on_num={five}>five</span><span class:on_num={six}>six</span
    ><span class:on_num={seven}>seven</span><br />
    <span class:on_num={eight}>eight</span><span class:on_num={nine}>nine</span
    ><span class:on_num={ten}>ten</span><br />
    <span>nd</span><span class:on_num={eleven}>eleven</span><span>dtiw</span><br
    />
    <span>ti</span><span class:on_ins={oclock}>o'clock</span><span>mea</span><br
    />
  </div>
</div>

<style>
  @import url("https://fonts.googleapis.com/css2?family=Major+Mono+Display&display=swap");
  .clock {
    font-family: "Major Mono Display", monospace;
    font-size: 1.5rem;
    font-style: normal;
    font-weight: 400;
    text-shadow: none;
    text-decoration: none;
    text-transform: none;
    letter-spacing: 0.5em;
    word-spacing: 0em;
    line-height: 1.2;
    text-align: center;
    background: black;
  }

  @media (min-width: 45rem) {
    .clock {
      font-size: 2rem;
    }
  }

  @media (min-width: 64rem) {
    .clock {
      font-size: 2.625rem;
    }
  }
  .clock span {
    transition: all 300ms ease-in-out;
  }

  .wordClock {
    clear: both;
    color: #212121;
  }

  .on_num {
    color: #e336b6;
    text-shadow: 0 0 5px #e336b6, 0 0 10px #e336b6, 0 0 20px #e336b6,
      0 0 40px #e336b6, 0 0 80px #e336b6, 0 0 90px #e336b6, 0 0 100px #e336b6,
      0 0 150px #e336b6;
  }

  .on_pre {
    color: #4eb0f1;
    text-shadow: 0 0 5px #4eb0f1, 0 0 10px #4eb0f1, 0 0 20px #4eb0f1,
      0 0 40px #4eb0f1, 0 0 80px #4eb0f1, 0 0 90px #4eb0f1, 0 0 100px #4eb0f1,
      0 0 150px #4eb0f1;
  }

  .on_ins {
    color: #70f3f0;
    text-shadow: 0 0 5px #70f3f0, 0 0 10px #70f3f0, 0 0 20px #70f3f0,
      0 0 40px #70f3f0, 0 0 80px #70f3f0, 0 0 90px #70f3f0, 0 0 100px #70f3f0,
      0 0 150px #70f3f0;
  }
</style>
