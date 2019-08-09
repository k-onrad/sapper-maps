<script>
  import FormREP from './FormREP.svelte'
</script>

<div id="sidebar" class="leaflet-sidebar collapsed">
	
	<!-- nav tabs -->
	<div class="leaflet-sidebar-tabs">
		
		<!-- top aligned tabs -->
		<ul role="tablist">
			<li><a href="#formrep" role="tab"><i class="fa fa-bars active"></i></a></li>
		</ul>
		
		<!-- bottom aligned tabs -->
		<ul role="tablist">
			<li><a href="https://github.com/nickpeihl/leaflet-sidebar-v2"><i class="fa fa-github"></i></a></li>
		</ul>
	
	</div>

	<!-- panel content -->
	<div class="leaflet-sidebar-content">
		<FormREP/>
	</div>

</div>