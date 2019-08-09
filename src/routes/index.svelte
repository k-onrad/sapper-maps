<svelte:head>
	<title>Map</title>
	<link rel='stylesheet' href='leaflet.css'>
	<link rel='stylesheet' href='leaflet-sidebar.css'>
	<link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/font-awesome/4.1.0/css/font-awesome.min.css">
</svelte:head>

<script>
	import Leaflet from '../components/Leaflet.svelte'
</script>

<Leaflet lat={-27.59} long={-48.54} zoom={12}/>