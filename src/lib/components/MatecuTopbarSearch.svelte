<div class="matecu-topbar-search">
	<span class="matecu-topbar-search__icon matecu-topbar-search__icon--search">
		<span class="material-symbols-outlined"> search </span>
	</span>
	<button class="matecu-topbar-search__icon matecu-topbar-search__icon--clear">
		<span class="material-symbols-outlined"> close </span>
	</button>

	<input type="text" placeholder="Buscar" />
</div>

<style lang="scss">
	.matecu-topbar-search {
		position: relative;
		display: flex;
		align-items: center;
		color: var(--search-text-color, #fff);
		* {
			box-sizing: border-box;
			outline: none;
		}
		input {
			height: var(--search-heigth, 35px);
			padding: var(--search-pading, 3px 35px);
			border-radius: 4px;
			border: 1px solid;
			border: var(--search-border, none);
			background-color: var(--search-background-color, #ffffff4d);
			color: currentColor;
			&::placeholder {
				color: var(--search-text-color, #fff);
				opacity: 1; /* Firefox */
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
