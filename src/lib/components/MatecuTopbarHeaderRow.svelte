<script lang="ts">
	export let display = true;
</script>

{#if display}
	<div class="matecu-topbar-header-row">
		<div class="matecu-topbar-header-row__left-column">
			{#if $$slots['left-column']}
				<slot name="left-column" />
			{/if}
		</div>

		<div class="matecu-topbar-header-row__right-column">
			{#if $$slots['right-column']}
				<slot name="right-column" />
			{/if}
		</div>
	</div>
{/if}

<style lang="scss">
	.matecu-topbar-header-row {
		&,
		* {
			box-sizing: border-box;
			outline: none;
		}
		display: flex;
		align-items: center;
		justify-content: flex-start;
		border: 1px solid green;
		box-sizing: border-box;
		width: 100%;
		height: 100%;
		min-height: var(--bar-height, 64px);
		&__left-column {
			display: flex;
			height: 100%;
		}
		&__right-column {
			display: flex;
			height: 100%;
			margin-left: auto;
		}
	}
</style>
