<script lang="ts">
	export let display = true;
</script>

{#if display}
	<div class="matecu-topbar-search">
		<span class="matecu-topbar-search__icon matecu-topbar-search__icon--search">
			<span class="material-symbols-outlined"> search </span>
		</span>
		<button class="matecu-topbar-search__icon matecu-topbar-search__icon--clear">
			<span class="material-symbols-outlined"> close </span>
		</button>

		<input type="text" placeholder="Buscar" />
	</div>
{/if}

<style lang="scss">
	.matecu-topbar-search {
		&,
		* {
			box-sizing: border-box;
			outline: none;
		}
		position: relative;
		display: flex;
		align-items: center;
		color: var(--search-text-color, #fff);
		max-height: var(--bar-height, 64px);

		input {
			width: var(--search-width, 200px);
			min-width: var(--search-width, 200px);
			height: var(--search-heigth, 35px);
			padding: var(--search-pading, 3px 35px);
			border-radius: 4px;
			border: 1px solid;
			border: var(--search-border, none);
			background-color: var(--search-background-color, #ffffff4d);
			color: currentColor;
			transition: all 300ms ease-in-out;
			&::placeholder {
				color: var(--search-text-color, #fff);
				opacity: 1; /* Firefox */
			}
			&:focus {
				min-width: var(--search-width-large, 290px);
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
</style>
