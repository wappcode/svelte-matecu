<script lang="ts">
	export let display = true;
</script>

{#if display}
	<div class="matecu-topbar-title"><slot /></div>
{/if}

<style lang="scss">
	:root {
		--mtb-title-padding: 6px;
		--mtb-title-margin: 0px;
	}
	.matecu-topbar-title {
		&,
		* {
			box-sizing: border-box;
			outline: none;
		}
		font-weight: bold;
		display: flex;
		height: 100%;
		align-items: center;
		align-self: center;
		padding: var(--mtb-title-padding);
		margin: var(--mtb-title-margin);
	}
</style>
