<script>
	import '../app.css';
	import Header from '../components/Header/header.svelte';
	import BrowserContent from '../components/Browser/BrowserContent.svelte';
</script>

<Header />
<BrowserContent />
<main>
	<slot />
</main>
<footer>
	Created by&nbsp;<a target="_blank" href="https://github.com/SergioFernandezJimenez"
		>Sergio Fernández</a
	>
</footer>
