<script>
	import Header from "./components/Header.svelte";
	import Footer from "./components/Footer.svelte";
	import Tabs from "./shared/Tabs.svelte";
	import Profile from "./pages/Profile.svelte";

	//Tabs
	let items = ['Profile', 'Projects', 'Blogs'];
	let activeItem = 'Profile';



</script>
<Header>

</Header>

<main>
	<Tabs {activeItem} {items} on:tabChange = {(e) => {activeItem = e.detail}}/>
	{#if activeItem === 'Profile'}
		<Profile />
	{:else if activeItem == 'Projects'}
		<p>Projects Page</p>
	{:else if activeItem == 'Blogs'}
		<p>Blogs</p>
	{/if}
</main>

<Footer>

</Footer>
<style>
	main{
		max-width: 960px;
		margin: 40px auto;
	}
</style>