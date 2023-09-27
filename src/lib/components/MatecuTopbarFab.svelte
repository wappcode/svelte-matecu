<script lang="ts">
	export let display = true;
	export let movileStyle = false;
</script>

{#if display}
	<div class="matecu-topbar-fab" class:movile-style={movileStyle}>
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
		&.movile-style {
			position: absolute;
			transform: translate(0);
			bottom: 20px;
			right: 20px;
		}
	}
</style>
