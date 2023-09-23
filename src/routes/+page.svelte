<script lang="ts">
	import MatecuTopbarLayout from '../lib/components/MatecuTopbarLayout.svelte';
</script>

<div>
	<h1>Matecu Topbar Layout</h1>
	<!-- <div class="matecu-topbar-layout">a</div> -->
	<MatecuTopbarLayout
		--heigth="500px"
		--width="500px"
		--primary-color="red"
		--border="1px solid blue"
	/>
</div>

<style lang="scss">
	div {
		border: 1px solid green;
		min-height: 100vh;
	}
	.matecu-topbar-layout {
		display: flex;
		width: 100%;
		height: 100%;
		border: 1px solid red;
	}
</style>
