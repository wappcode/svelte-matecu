<script lang="ts">
	export let display = true;
</script>

{#if display}
	<div class="matecu-topbar-header-row">
		<div class="matecu-topbar-header-row__column matecu-topbar-header-row__column--left">
			{#if $$slots['left-column']}
				<slot name="left-column" />
			{/if}
		</div>

		<div class="matecu-topbar-header-row__column matecu-topbar-header-row__column--right">
			{#if $$slots['right-column']}
				<slot name="right-column" />
			{/if}
		</div>
	</div>
{/if}

<style lang="scss">
	:root {
		--mtb-row-padding: 0px;
		--mtb-row-margin: 0;
		--mtb-row-max-width: 100%;
		--mtb-row-min-width: 320px;
	}
	.matecu-topbar-header-row {
		&,
		* {
			box-sizing: border-box;
			outline: none;
		}
		padding: var(--mtb-row-padding);
		margin: var(--mtb-row-margin);
		display: flex;
		align-items: flex-start;
		justify-content: flex-start;
		box-sizing: border-box;
		width: 100%;
		height: 100%;
		max-width: var(--mtb-row-max-width);
		min-width: var(--mtb-row-min-width);
		&__column {
			display: flex;
			height: 100%;
			min-height: var(--mtb-bar-height, 64px);
			align-items: flex-start;
			&--right {
				margin-left: auto;
				justify-content: flex-end;
			}
		}
	}
</style>
