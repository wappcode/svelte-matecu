<div class="matecu-topbar-action">
	<slot />
</div>

<style lang="scss">
	:root {
		--mtb-bar-height: 64px;
		--mtb-action-padding: 10px;
		--mtb-action-margin: 0px;
	}
	.matecu-topbar-action {
		&,
		* {
			box-sizing: border-box;
			outline: none;
		}
		height: 100%;
		display: flex;
		align-items: start;
		max-height: var(--mtb-bar-height);
		padding: var(--mtb-action-padding);
		margin: var(--mtb-action-margin);
	}
</style>
