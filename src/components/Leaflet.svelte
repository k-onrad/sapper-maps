<script>
	import { onMount } from 'svelte'
	import Sidebar from './Sidebar.svelte'
	
	export let lat 
	export let long
	export let zoom

	let container
	let map

	onMount(async () => {
		try {
			const L = await import('leaflet')
			const lsv2 = await import('leaflet-sidebar-v2')
			
			const geoObj = await fetch('https://gist.githubusercontent.com/k-onrad/ce16960cbdfe45bd14d7c9272981e4b6/raw/71f50c3246fe8eca51eb76f08772085ddce68f3d/map.geojson')
			const geoData = await geoObj.json()
			console.log(geoData)
		} catch (e) {
			console.error(e)
		}
		
		map = L.map(container).setView([lat, long], zoom)
		L.tileLayer('https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png').addTo(map)
		L.geoJSON(geoData).addTo(map)
		
		const sidebar = L.control.sidebar({
			autopan: false,       // whether to maintain the centered map point when opening the sidebar
			closeButton: true,    // whether to add a close button to the panes
			container: 'sidebar', // the DOM container or #ID of a predefined sidebar container that should be used
			position: 'left',     // left or right
		}).addTo(map)

		return () => {
			map.remove()
		}
	})
</script>

<style>
	div {
		height: 100%;
		width: 100%;
	}
</style>

<Sidebar/>

<div bind:this={container}/>
