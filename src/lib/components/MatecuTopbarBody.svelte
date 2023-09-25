<script lang="ts">
</script>

<div class="matecu-topbar-body">
	<slot />
</div>

<style lang="scss">
	.matecu-topbar-body {
		padding: var(--body-padding, 30px);
		background-color: var(--body-background, auto);
		overflow-y: auto;
		padding-bottom: var(--body-padding-button, 60px);
	}
</style>
