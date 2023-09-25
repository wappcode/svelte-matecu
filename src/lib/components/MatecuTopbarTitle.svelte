<script lang="ts">
	export let display = true;
</script>

{#if display}
	<div class="matecu-topbar-title"><slot /></div>
{/if}

<style lang="scss">
	.matecu-topbar-title {
		display: flex;
		height: 100%;
		align-items: center;
	}
</style>
