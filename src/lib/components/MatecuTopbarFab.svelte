<script lang="ts">
	export let display = true;
	export let mobileStyle = false;
</script>

{#if display}
	<div class="matecu-topbar-fab" class:mobile-style={mobileStyle}>
		<slot />
	</div>
{/if}

<style lang="scss">
	* {
		box-sizing: border-box;
		outline: none;
	}
	.matecu-topbar-fab {
		display: flex;
		align-self: flex-end;
		align-items: flex-start;
		transform: translateY(50%);
		transition: all 300ms ease-in-out;
		&.mobile-style {
			position: absolute;
			transform: translate(0);
			bottom: var(--mtb-fab-mobile-bottom-position, 20px);
			right: var(--mtb-fab-mobile-right-position, 20px);
		}
	}
</style>
