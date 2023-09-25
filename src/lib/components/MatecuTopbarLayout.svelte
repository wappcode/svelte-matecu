<script lang="ts">
	import { onDestroy, onMount } from 'svelte';

	export let prominent = false;
	let scrolled = false;
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
		const scrollabe: HTMLElement | null = document.querySelector('.matecu-topbar-layout__body');
		if (!scrollabe) {
			return;
		}
		scrollabe.addEventListener('scroll', (ev) => {
			spyScroll(scrollabe);
		});
	});

	onDestroy(() => {
		const scrollabe: HTMLElement | null = document.querySelector('.matecu-topbar-layout__body');
		if (!scrollabe) {
			return;
		}
		scrollabe.removeEventListener('scroll', () => {});
	});
</script>

<div class="matecu-topbar-layout" class:prominent class:scrolled>
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
		box-sizing: border-box;
		* {
			box-sizing: border-box;
		}
		display: grid;
		grid-template-rows: auto 1fr;
		box-sizing: border-box;
		border: var(--border, none);
		margin: var(--margin, 0px);
		padding: 0px;
		width: var(--width, 100%);
		height: var(--heigth, 100vh);
		overflow: hidden;

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
		&.scrolled {
			.matecu-topbar-layout__bar {
				box-shadow: 0px 3px 5px -1px rgba(0, 0, 0, 0.2), 0px 6px 10px 0px rgba(0, 0, 0, 0.14),
					0px 1px 18px 0px rgba(0, 0, 0, 0.12);
				min-height: var(--bar-height, 64px);
			}
		}
	}
</style>
