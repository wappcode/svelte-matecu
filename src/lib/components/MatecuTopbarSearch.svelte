<script lang="ts">
	import { createEventDispatcher } from 'svelte';
	export let display = true;
	export let delyValueChanges = 300; // miliseconds
	export let placeholder = '';
	export let mobileStyle = false;

	export let value: string = '';
	let timeoutInstance: ReturnType<typeof setTimeout>;
	let activeMobileSearch = false;
	$: hasValue = value?.length;

	const dispatch = createEventDispatcher();
	const valueChanges = () => {
		if (timeoutInstance) {
			clearTimeout(timeoutInstance);
		}
		timeoutInstance = setTimeout(() => {
			dispatch('valueChanges', { value: value });
		}, delyValueChanges);
	};
	const clearSearch = () => {
		value = '';
		dispatch('valueChanges', { value: value });
		activeMobileSearch = false;
	};
	const toggleActiveMobileSearch = () => {
		activeMobileSearch = !activeMobileSearch;
	};
</script>

{#if display}
	<button
		class="matecu-topbar-search-mobile-only"
		class:mobile-style={mobileStyle}
		on:click={toggleActiveMobileSearch}
	>
		<slot name="search-icon">
			<span class="material-symbols-outlined"> search </span>
		</slot>
	</button>
	<div
		class="matecu-topbar-search"
		class:mobile-style={mobileStyle}
		class:active-mobile={activeMobileSearch}
	>
		<span class="matecu-topbar-search__icon matecu-topbar-search__icon--search">
			<slot name="search-icon">
				<span class="material-symbols-outlined"> search </span>
			</slot>
		</span>
		{#if hasValue || mobileStyle}
			<button
				class="matecu-topbar-search__icon matecu-topbar-search__icon--clear"
				on:click={clearSearch}
			>
				<slot name="clear-icon">
					<span class="material-symbols-outlined"> close </span>
				</slot>
			</button>
		{/if}
		<input type="text" {placeholder} bind:value on:input={valueChanges} />
	</div>
{/if}

<style lang="scss">
	$search-text-color: var(--mtb-bar-color, #fff);
	$mtb-search-margin: var(--mtb-search-margin, 10px);

	.matecu-topbar-search-mobile-only {
		display: none;
		border: none;
		background: none;
		cursor: pointer;
		color: var(--mtb-search-color, $search-text-color);
		margin: $mtb-search-margin;
		&.mobile-style {
			display: block;
		}
	}
	.matecu-topbar-search {
		&,
		* {
			box-sizing: border-box;
			outline: none;
		}
		margin: $mtb-search-margin;
		position: relative;
		display: flex;
		align-items: center;
		color: var(--mtb-search-color, $search-text-color);
		max-height: var(--bar-height, 64px);

		input {
			width: var(--mtb-search-width, 200px);
			min-width: var(--mtb-search-width, 200px);
			height: var(--mtb-search-height, 40px);
			padding: var(--mtb-search-pading, 3px 35px);
			border-radius: 4px;
			border: 1px solid;
			border: var(--mtb-search-border, none);
			background-color: var(--search-background-color, #ffffff4d);
			color: currentColor;
			transition: all 300ms ease-in-out;
			&::placeholder {
				color: var(--mtb-search-color, $search-text-color);
				opacity: 1; /* Firefox */
			}
			&:focus {
				min-width: var(--mtb-search-width-large, 290px);
			}
		}

		&__icon {
			position: absolute;
			top: 50%;
			transform: translateY(-50%);
			padding: 0px;
			&--search {
				left: 6px;
			}
			&--clear {
				border: 0px;
				background: 0px;
				cursor: pointer;
				color: currentColor;
				right: 6px;
			}
		}
	}
	.mobile-style.matecu-topbar-search {
		position: absolute;
		top: 0px;
		left: 0px;
		right: 0px;
		border-bottom: 1px solid;
		border-bottom-color: var(--mtb-search-border-bottom-color, #ededed);
		z-index: 3;
		padding: 0px;
		margin: 0px;
		height: 64px;
		color: var(--mtb-search-mobile-color, #000);
		transform: translateY(-120%);
		transition: all 300ms ease-in-out;
		&.active-mobile {
			transform: translateY(0);
		}
		input {
			background-color: #fff;
			height: 100%;
			width: 100%;
			border-radius: 0px;
			&::placeholder {
				color: var(--mtb-search-mobile-color, #000);
			}
		}
	}
</style>
