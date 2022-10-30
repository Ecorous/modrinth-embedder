<!--
 Copyright 2022 Ecorous System
 
 Licensed under the Apache License, Version 2.0 (the "License");
 you may not use this file except in compliance with the License.
 You may obtain a copy of the License at
 
     http://www.apache.org/licenses/LICENSE-2.0
 
 Unless required by applicable law or agreed to in writing, software
 distributed under the License is distributed on an "AS IS" BASIS,
 WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
 See the License for the specific language governing permissions and
 limitations under the License.
-->
<script>
	import { browser } from '$app/environment';

	let left = '<';
	let right = '>';
	let url = 'https://m.ecorous.org';

    if (browser) {
        url = window.location.protocol + "//" + window.location.host
    }
</script>

<h1>Examples</h1>
<p>
	To use these examples, you must replace the slug/id from the url with the project you wish's
	slug/id. <br /> Despite the url saying <code>mod</code>, it should work (untested) with modpacks,
	plugins and resourcepacks as well
</p>
<div id="example1">
	<h4 style="font-size: x-large;">Example - using a project's slug</h4>
	<p>
		<code
			>{left}iframe style="border: none; height: 200px;" seamless src="{url}/mod/rmscore"{right}{left}/iframe{right}</code
		>
	</p>
	<iframe style="border: none; height: 200px;" seamless src="{url}/mod/rmscore" />
	<p>To remove the scrollbars (this is unrecommended as it's deprecated) use this:</p>
	<p>
		<code
			>{left}iframe style="border: none; height: 200px;" scrolling="no" seamless src="{url}/mod/rmscore"{right}{left}/iframe{right}</code
		>
	</p>
	<iframe
		style="border: none; height: 200px;"
		scrolling="no"
		seamless
		src="{url}/mod/rmscore"
	/>
</div>
<br />
<br />
<br />
<div id="example2">
	<h4 style="font-size: x-large;">Example - using a project's id</h4>
	<p>Using a project's id works in just the same way - see below</p>
	<p>
		<code
			>{left}iframe style="border: none; height: 200px;" seamless src="{url}/mod/aRooc1Sw"{right}{left}/iframe{right}</code
		>
	</p>
	<iframe style="border: none; height: 200px;" seamless src="http://m:5173/mod/aRooc1Sw" />
	<p>Again, to remove the scrollbars (again, deprecated) use this:</p>
	<p>
		<code
			>{left}iframe style="border: none; height: 200px;" scrolling="no" seamless src="{url}/mod/aRooc1Sw"{right}{left}/iframe{right}</code
		>
	</p>
	<iframe
		style="border: none; height: 200px;"
		scrolling="no"
		seamless
		src="{url}/mod/aRooc1Sw"
	/>
</div>

<style>
	:root {
		color: rgb(211, 211, 211);
		background-color: rgb(17, 22, 41);
		font-family: Arial, Helvetica, sans-serif;
	}
	* {
		color: rgb(211, 211, 211);
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
