<script lang="ts">
</script>

<div class="matecu-topbar-body">
	<slot />
</div>

<style lang="scss">
	.matecu-topbar-body {
		&,
		* {
			box-sizing: border-box;
			outline: none;
		}
		padding: var(--mtb-body-padding, 30px);
		background-color: var(--mtb-body-background, auto);
		overflow-y: auto;
		padding-bottom: var(--mtb-body-padding-button, 60px);
	}
</style>
