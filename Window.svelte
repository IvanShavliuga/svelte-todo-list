<script>
  import Item from "./Item.svelte";
  let btnok = "ok";
  let count = 0;
  let txt = "";
  /* Входные параметры :?) */
  export let id = 1;
  export let text = "This text for test";
  export let title = "test";
  export let author = "iv2";
  export let isCompleted;
  export let curr = 1;
  export let todosData = [
    {
      id: 1,
      color: "#239860",
      todo: "Test",
      select: false,
      status: "no"
    },
    {
      id: 2,
      color: "#2358b0",
      todo: "Fast",
      select: true,
      status: "yes"
    },
    {
      id: 3,
      color: "#b398d0",
      todo: "Last",
      select: false,
      status: "yes"
    },
    {
      id: 4,
      color: "#a328a0",
      todo: "Nuxt",
      select: false,
      status: "no"
    },
    {
      id: 5,
      color: "#a39840",
      todo: "Real",
      select: "no",
      status: "yes"
    },
    {
      id: 6,
      color: "#43e8d0",
      todo: "Less",
      select: false,
      status: "no"
    }
  ];
  function handleChange(e) {
    txt = e.target.value;
    count = txt.length;
  }
  function handleClick() {
    count += 1;
  }
  function chPrev() {
    if (curr > 1) curr--;
  }
  function chNext() {
    if (curr < todosData.length) curr++;
  }
</script>

<style>
  article {
    width: 100%;
    margin: 15px auto;
    padding: 0;
    border: none;
  }
  article > * {
    padding: 2px 5px;
    font-size: 16px;
  }
  .title {
    background: red;
    color: yellow;
    border: 1px solid gray;
    margin: 0;
    text-align: justify;
  }
  .body {
    text-align: justify;
    background: blue;
    color: white;
    margin-top: 0;
    margin-bottom: 0;
  }
  .info {
    text-align: justify;
    background: green;
    color: white;
    margin-top: 0;
    margin-bottom: 0;
  }
  .bar {
    text-align: justify;
    background: black;
    color: white;
    margin-top: 0;
    margin-bottom: 0;
  }
  .btn {
    color: white;
    background: transparent;
    border: none;
    outline: none;
  }
  .input {
    background: transparent;
    border: none;
    color: yellow;
    outline: none;
  }
  .input:focus,
  .btn:focus {
    background: rgba(128, 128, 128, 0.5);
  }
</style>

<article>
  <h3 class="title">{id} {author} {title}</h3>
  <p class="body">
    {text} {txt}
    {#each todosData as todos}
      <Item id={todos.id} color={todos.color} todo={todos.todo} select={todos.id===curr} status={todos.status}/>
    {/each}
  </p>
  <p class="info">
    All items: {todosData.length}
    Current item: {curr}
    <input class="input" type="text" on:input={handleChange}/>
  </p>
  <p class="bar">
    <button class="btn" on:click={handleClick}>{btnok}</button>
    <button class="btn" on:click={chPrev}>Prev</button>
    <button class="btn" on:click={chNext}>Next</button>
  </p>
</article>
