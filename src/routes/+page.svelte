<h1>modrinth-embedder</h1>
<p>A simple <code>iframe</code>-based modrinth embed creator</p>
<button on:click={() => {window.location.href += "examples"}}>View Examples</button>

<style>
	:root {
		color: white;
		background-color: rgb(17, 22, 41);
		font-family: Arial, Helvetica, sans-serif;
	}
	* {
		color: white;
		text-align: center;
	}
	code {
		background-color: rgb(17, 22, 42);
	}
	h1 {
		margin-top: 20vh;
		font-size: 7vh;
	}
	button {
		margin: 0;
		position: absolute;
		top: 50%;
        cursor: pointer;
		left: 50%;
		-ms-transform: translate(-50%, -50%);
		transform: translate(-50%, -50%);
        background-color: rgb(22, 50, 162);
        border: none;
        padding: 20px;
        font-size: larger;
        border-radius: 15px;
	}
</style>
