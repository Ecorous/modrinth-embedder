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
<script lang="ts">
	import { browser } from '$app/environment';
	import { onMount } from 'svelte';
    import { page } from '$app/stores';
	if (browser) {
		//@ts-ignore
		document.getElementsByTagName('body').item(0).style.display = 'flex';
	}
	let name = 'Example Mod';
	let iconUrl = 'https://cdn.modrinth.com/placeholder.svg';
	let author = 'My uncle!';
	let summary = 'This is a very real mod';
	let modSlug = $page.params.mod;

	onMount(async () => {
		let resp = await fetch('https://api.modrinth.com/v2/project/' + modSlug);
		let json = await resp.json();
		name = json.title;
		iconUrl = json.icon_url;
		let resp2 = await fetch('https://api.modrinth.com/v2/project/' + modSlug + '/members');
		let json2 = await resp2.json();
		author = "";
		json2.forEach(e => {
			if (e == json2[json2.length]) {
				author += e.user.username
			} else {
				author += e.user.username + ", "
			}
		});
		summary = json.description;
	});
</script>

<div class="mainDiv">
	<div class="mainDiv" style="display: flex;">
		<img src={iconUrl} />
		<p style="font-size:large;margin-right:15px;">{name}</p>
		<div>
			<p style="display: block;"><a style="font-weight: bold"> By </a>{author}</p>
		</div>
	</div>
	<p>{summary}</p>
</div>

<style>
	* {
		color: white;
		font-family: Arial, Helvetica, sans-serif;
		justify-content: flex-start;
	}
	*:link {
		color: white;
	}
	*:link:visited {
		color: white;
	}
	.mainDiv {
		padding: 15px;
		border-radius: 15px;
		max-width: 36vw;
		flex-grow: true;
		display: block;
		max-height: fit-content;
		max-width: fit-content;
		justify-content: center;
		background-color: #18191a;
	}
	.mainDiv > img {
		margin-right: 12px;
		width: 64px;
		border-radius: 15px;
		height: 64px;
	}
</style>
