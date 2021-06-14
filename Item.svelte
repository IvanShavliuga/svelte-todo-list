<p class="item">
	<span class="{select?'item-title-select':'item-title'}">
		Item:
	</span>
	<span class="item-status">
		<span class="{'item-status-'+status}">
			<b style="margin: 0 -2px 0 2px">{status==='yes'?'Y':'N'}</b>
		</span>
	</span>
	(
	<span class="item-number">
		{ id }
	</span>
	,
	<span class="item-color" style="{'color:'+color}">
		{ color }
	</span>
	,
	<span class="item-string">
		{ todo }
	</span>
	)
	<button class="item-btn" on:click={chStatus}>
		{status==='yes'?'N':'Y'}
	</button>
	<button class="item-btn" on:click={chSelect}>
		{select?'O':'X'}
	</button>
</p>
<style>
  .item {
    margin: 2px 0;
    padding: 0 15px;
    color: white;
  }
  .item span {
    display: inline-block;
    padding: 0;
    margin: 0;
    font-family: "Courier New", Courier, monospace;
  }
  .item-color {
    min-width: 3em;
  }
  .item-title {
    color: #158ec6;
    background-color: blue;
    font-weight: bold;
  }
  .item-title-select {
    color: red;
    background-color: white;
    font-weight: bold;
  }
  .item-number {
    color: yellow;
    font-weight: bold;
  }
  .item-string {
    width: 10em;
    text-align: center;
    color: rgb(247, 19, 247);
  }
  .item-prop {
    color: white;
  }
  .item-status {
    width: 1em;
    height: 20px;
    padding: 0 20px;
    background-color: transparent;
  }

  .item-status-yes {
    width: 1em;
    height: 18px;
    padding: 0 20px;
    background-color: #0a0;
    border: 3px solid blue;
    border-radius: 40%;
    color: rgba(250, 250, 250, 0.7);
    font-size: 14px;
    letter-spacing: 6px;
  }
  .item-status-no {
    width: 1em;
    height: 18px;
    padding: 0 20px;
    background-color: #a00;
    border: 3px solid blue;
    border-radius: 40%;
    color: rgba(250, 250, 250, 0.7);
    font-size: 14px;
    letter-spacing: 6px;
  }
  .item-btn {
    border: 1px solid rgb(247, 19, 247);
    background-color: transparent;
    color: rgb(247, 19, 247);
    outline: none;
    width: 1.8em;
  }
  .item-btn:focus {
    background-color: rgba(247, 19, 247, 0.5);
  }
</style>
<script>
	export let id = 0;
	export let color = "#158ec6";
	export let todo = "Hello";
	export let status = "yes";
	export let select = false;
	function chSelect() {
	  select = !select;
	}
	function chStatus() {
	  status = status === "yes" ? "no" : "yes";
	}
</script>