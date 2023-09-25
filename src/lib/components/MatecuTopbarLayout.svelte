<script lang="ts">
	export const scrollTop = () => {
		console.log('scrolling matecu-topbar-body');
		const element: HTMLElement | null = document.querySelector('.matecu-topbar-layout__body');
		if (!element) {
			return;
		}
		element.scroll({
			top: 0,
			behavior: 'smooth'
		});
	};
</script>

<div class="matecu-topbar-layout">
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
			background-color: var(--primary-color, orangered);
			height: var(--bar-height, 64px);
			width: 100%;
			padding: 0px;
			margin: 0px;
		}
		&__body {
			padding: 0px;
			margin: 0px;
			overflow-y: auto;
		}
	}
</style>
