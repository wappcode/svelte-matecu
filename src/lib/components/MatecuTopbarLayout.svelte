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
	<div class="matecu-topbar-body">
		<h1>inicio de la página</h1>
		contenido de la página Lorem ipsum, dolor sit amet consectetur adipisicing elit. Accusamus, sed distinctio
		deleniti nihil laboriosam, at unde mollitia sit aliquam molestias nobis omnis, suscipit numquam voluptatibus
		esse maiores a quos quasi. Lorem ipsum dolor sit amet consectetur adipisicing elit. Magnam consequuntur,
		aliquid nesciunt nam quisquam ullam culpa asperiores temporibus omnis dolor et quam itaque? Doloremque
		pariatur deserunt velit nam! Ea, impedit. Lorem ipsum dolor sit amet consectetur, adipisicing elit.
		Non rerum laboriosam necessitatibus quam minus adipisci ut culpa totam nihil iusto esse, distinctio
		ducimus. Maxime culpa voluptatem obcaecati quos, recusandae accusamus. Lorem ipsum dolor sit, amet
		consectetur adipisicing elit. Repudiandae quo dolor illum est dolore architecto ex! Magni aut provident
		corporis suscipit excepturi, laboriosam porro architecto ullam minus laudantium, saepe recusandae?
		Lorem ipsum dolor sit amet, consectetur adipisicing elit. Dolores ipsum ipsam expedita, esse fugit
		reiciendis, animi quo deserunt in eligendi provident impedit ratione quos voluptatem molestiae labore
		sit eaque ab. Lorem, ipsum dolor sit amet consectetur adipisicing elit. Aut laudantium omnis consequatur.
		In temporibus ullam saepe expedita debitis architecto qui optio dicta fugiat. Nobis commodi unde
		nemo nostrum cumque veritatis? Lorem ipsum dolor sit amet consectetur adipisicing elit. Temporibus
		quam molestias voluptatem odio sed vitae quo voluptatum aperiam consequuntur est tempore fuga provident
		maxime distinctio optio, odit neque iure sequi.
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
	.matecu-topbar-body {
		padding: var(--body-padding, 30px);
		border: 1px solid yellow;
		background-color: #ededed;
		overflow-y: auto;
		padding-bottom: var(--body-padding-button, 60px);
	}
</style>
