<div class="matecu-topbar-action">
	<slot />
</div>

<style lang="scss">
	.matecu-topbar-action {
		&,
		* {
			box-sizing: border-box;
			outline: none;
		}
		height: 100%;
		display: flex;
		align-items: center;
		border: 1px solid blue;
		max-height: var(--bar-height, 64px);
	}
</style>
