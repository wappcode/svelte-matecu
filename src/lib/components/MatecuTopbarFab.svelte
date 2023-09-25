<script lang="ts">
	export let display = true;
</script>

{#if display}
	<div class="matecu-topbar-fab">
		<slot />
	</div>
{/if}

<style lang="scss">
	.matecu-topbar-fab {
		display: flex;
		align-items: flex-start;
		transform: translateY(50%);
	}
</style>
