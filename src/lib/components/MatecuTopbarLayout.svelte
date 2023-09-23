<script lang="ts"></script>

<div class="matecu-topbar-layout">
	<div class="matecu-topbar-layout__bar">
		<div class="matecu-topbar-header-row">
			<div class="matecu-topbar-left-items">
				<div class="matecu-topbar-action">A</div>
				<div class="matecu-topbar-action">B</div>
				<div class="matecu-topbar-fab">FabIcon</div>
				<div class="matecu-topbar-title">Título</div>
			</div>

			<div class="matecu-topbar-right-items">
				<div class="matecu-topbar-search">
					<input type="text" placeholder="Buscar" />
				</div>
				<div class="matecu-topbar-action">A</div>
				<div class="matecu-topbar-action">A</div>
			</div>
		</div>
	</div>
</div>

<style lang="scss">
	.matecu-topbar-layout {
		box-sizing: border-box;
		border: var(--border, none);
		* {
			box-sizing: border-box;
		}
		margin: var(--margin, 0px);
		padding: 0px;
		display: flex;
		width: var(--width, 100%);
		height: var(--heigth, 100vh);
		&__bar {
			display: flex;
			flex-direction: column;
			align-items: center;
			justify-content: flex-start;
			background-color: var(--primary-color, blue);
			height: var(--bar-height, 64px);
			border: 1px solid red;
			width: 100%;
			padding: 0px;
			margin: 0px;
		}
	}
	.matecu-topbar-header-row {
		display: flex;
		align-items: center;
		justify-content: flex-start;
		border: 1px solid green;
		box-sizing: border-box;
		width: 100%;
		height: var(--bar-height, 64px);
	}
	.matecu-topbar-left-items {
		display: flex;
		height: 100%;
	}
	.matecu-topbar-right-items {
		display: flex;
		height: 100%;
		margin-left: auto;
	}
	.matecu-topbar-action {
		height: 100%;
		display: flex;
		align-items: center;
		border: 1px solid blue;
	}
	.matecu-topbar-search {
		display: flex;
		align-items: center;
		* {
			box-sizing: border-box;
			outline: none;
		}
		input {
			height: var(--search-heigth, 35px);
			padding: var(--search-pading, 3px 30px);
			border-radius: 4px;
			border: 1px solid;
			border: var(--search-border, none);
			background-color: var(--search-background-color, #ffffff4d);
			color: var(--search-text-color, #fff);
			&::placeholder {
				color: var(--search-text-color, #fff);
				opacity: 1; /* Firefox */
			}
		}
	}
	.matecu-topbar-title {
		display: flex;
		height: 100%;
		align-items: center;
	}
	.matecu-topbar-fab {
		display: flex;
		align-items: flex-start;
		transform: translateY(50%);
	}
</style>
