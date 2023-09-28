<script lang="ts">
	import { onMount } from 'svelte';
	import { createEventDispatcher } from 'svelte';
	let layoutElement: HTMLElement | null | undefined;
	let bodyElement: HTMLElement | null | undefined;
	export let prominent = false;
	let scrolled = false;
	export const scrollTop = () => {
		if (!bodyElement) {
			return;
		}
		bodyElement.scroll({
			top: 0,
			behavior: 'smooth'
		});
	};
	const dispatchResize = createEventDispatcher();
	const spyScroll = (scrollabe: HTMLElement) => {
		if (!scrollabe) {
			return;
		}
		const maxScrollHeight = scrollabe.scrollHeight;
		const screenHeight = screen.availHeight;
		if (screenHeight > maxScrollHeight) {
			return;
		}
		const scrollPosition = scrollabe.scrollTop;
		scrolled = scrollPosition > 20;
	};
	onMount(() => {
		const resizeObserver = new ResizeObserver(() => {
			dispatchResize('resize', { width: layoutElement?.clientWidth });
		});
		bodyElement!.addEventListener('scroll', (ev) => {
			spyScroll(bodyElement!);
		});
		resizeObserver.observe(layoutElement!);
		return () => {
			bodyElement!.removeEventListener('scroll', () => {});
			resizeObserver.disconnect();
		};
	});
</script>

<div class="matecu-topbar-layout" class:prominent class:scrolled bind:this={layoutElement}>
	<div class="matecu-topbar-layout__bar">
		{#if $$slots['first-row']}
			<slot name="first-row" />
		{/if}
		{#if $$slots['second-row']}
			<slot name="second-row" />
		{/if}
	</div>
	<div class="matecu-topbar-layout__body" bind:this={bodyElement}>
		{#if $$slots['body']}
			<slot name="body" />
		{/if}
	</div>
</div>

<style lang="scss">
	.matecu-topbar-layout {
		position: relative;
		box-sizing: border-box;
		* {
			box-sizing: border-box;
		}
		display: grid;
		grid-template-rows: auto 1fr;
		box-sizing: border-box;
		border: var(--mtb-border, none);
		margin: var(--mtb-margin, 0px);
		padding: 0px;
		width: var(--mtb-width, 100%);
		height: var(--mtb-height, 100vh);
		overflow: hidden;

		&__bar {
			display: flex;
			flex-direction: column;
			align-items: center;
			justify-content: flex-start;
			background-color: var(--mtb-primary-color, #3f51b5);
			color: var(--mtb-bar-color, #fff);
			width: 100%;
			padding: 0px;
			margin: 0px;
			min-height: var(--mtb-bar-height, 64px);
			transition: all 300ms;
		}
		&__body {
			padding: 0px;
			margin: 0px;
			overflow-y: auto;
		}
		&.prominent {
			.matecu-topbar-layout__bar {
				min-height: var(--mtb-bar-prominent-height, 128px);
			}
		}
		&.scrolled {
			.matecu-topbar-layout__bar {
				box-shadow: 0px 3px 5px -1px rgba(0, 0, 0, 0.2), 0px 6px 10px 0px rgba(0, 0, 0, 0.14),
					0px 1px 18px 0px rgba(0, 0, 0, 0.12);
				min-height: var(--mtb-bar-height, 64px);
			}
		}
	}
</style>
