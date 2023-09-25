<script lang="ts">
	export const scrollTop = () => {
		const element: HTMLElement | null = document.querySelector('.matecu-topbar-layout__body');
		if (!element) {
			return;
		}
		element.scroll({
			top: 0,
			behavior: 'smooth'
		});
	};
	export let prominent = false;
</script>

<div class="matecu-topbar-layout" class:prominent>
	<div class="matecu-topbar-layout__bar">
		{#if $$slots['header-row-first']}
			<slot name="header-row-first" />
		{/if}
		{#if $$slots['header-row-second']}
			<slot name="header-row-second" />
		{/if}
	</div>
	<div class="matecu-topbar-layout__body">
		{#if $$slots['body']}
			<slot name="body" />
		{/if}
	</div>
</div>

<style lang="scss">
	.matecu-topbar-layout {
		display: grid;
		grid-template-rows: auto 1fr;
		box-sizing: border-box;
		border: var(--border, none);
		margin: var(--margin, 0px);
		padding: 0px;
		width: var(--width, 100%);
		height: var(--heigth, 100vh);
		overflow: hidden;
		* {
			box-sizing: border-box;
		}
		&__bar {
			display: flex;
			flex-direction: column;
			align-items: center;
			justify-content: flex-start;
			background-color: var(--primary-color, rgb(85, 0, 255));

			width: 100%;
			padding: 0px;
			margin: 0px;
			min-height: var(--bar-height, 64px);
			transition: all 300ms;
		}
		&__body {
			padding: 0px;
			margin: 0px;
			overflow-y: auto;
		}
		&.prominent {
			.matecu-topbar-layout__bar {
				min-height: var(--prominent-height, 128px);
			}
		}
	}
</style>
