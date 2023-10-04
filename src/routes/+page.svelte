<script lang="ts">
	import MatecuTopbarAction from '../lib/components/MatecuTopbarAction.svelte';
	import MatecuTopbarBody from '../lib/components/MatecuTopbarBody.svelte';
	import MatecuTopbarFab from '../lib/components/MatecuTopbarFab.svelte';
	import MatecuTopbarHeaderColumn from '../lib/components/MatecuTopbarHeaderColumn.svelte';
	import MatecuTopbarHeaderRow from '../lib/components/MatecuTopbarHeaderRow.svelte';
	import MatecuTopbarLayout from '../lib/components/MatecuTopbarLayout.svelte';
	import MatecuTopbarSearch from '../lib/components/MatecuTopbarSearch.svelte';
	import MatecuTopbarTitle from '../lib/components/MatecuTopbarTitle.svelte';

	let scrollTop: () => void;
	let dobuleRow = false;
	let prominent = false;
	let mobileStyle = false;

	const handleSearching = (event: any) => {
		console.log('event searching', event);
	};
	const handleResize = (event: any) => {
		console.log('event resizing', event);
	};
</script>

<div>
	<h1>Matecu Topbar Layout</h1>
	<button on:click={scrollTop}>Scroll top</button>
	<MatecuTopbarLayout
		--mtb-height="500px"
		--mtb-width="100%"
		--mtb-border="1px solid blue"
		{prominent}
		mobileWidth={768}
		bind:scrollTop
		bind:mobileStyle
		on:resize={handleResize}
	>
		<MatecuTopbarHeaderRow slot="first-row" --mtb-row-max-width="600px">
			<MatecuTopbarHeaderColumn slot="left-column">
				<MatecuTopbarAction>A</MatecuTopbarAction>
				<MatecuTopbarAction>B</MatecuTopbarAction>
				<MatecuTopbarFab {mobileStyle}
					><button type="button" class="fabbtn">+</button></MatecuTopbarFab
				>
				<MatecuTopbarTitle>El titulo de la página puede estar en dos lineas</MatecuTopbarTitle>
			</MatecuTopbarHeaderColumn>
			<MatecuTopbarHeaderColumn slot="right-column">
				<MatecuTopbarSearch
					{mobileStyle}
					on:valueChanges={handleSearching}
					placeholder="Buscando..."
				>
					<span slot="search-icon">B</span>
					<span slot="clear-icon">X</span>
				</MatecuTopbarSearch>
				<MatecuTopbarAction>C</MatecuTopbarAction>
				<MatecuTopbarAction>D</MatecuTopbarAction>
			</MatecuTopbarHeaderColumn>
		</MatecuTopbarHeaderRow>

		<MatecuTopbarHeaderRow slot="second-row" display={dobuleRow}>
			<MatecuTopbarHeaderColumn slot="left-column">
				<MatecuTopbarAction>E</MatecuTopbarAction>
				<MatecuTopbarAction>F</MatecuTopbarAction>
			</MatecuTopbarHeaderColumn>
		</MatecuTopbarHeaderRow>
		<MatecuTopbarBody slot="body">
			<div><label><input type="checkbox" bind:checked={dobuleRow} /> Dos filas</label></div>
			<div><label><input type="checkbox" bind:checked={prominent} /> Prominente</label></div>
			Lorem ipsum dolor sit amet consectetur, adipisicing elit. Cupiditate incidunt architecto unde aliquam.
			Sit veritatis odit recusandae, officiis unde ipsa iusto fugit aspernatur placeat omnis magnam,
			maiores dolor maxime sunt. Lorem ipsum dolor sit amet consectetur, adipisicing elit. Cupiditate
			incidunt architecto unde aliquam. Sit veritatis odit recusandae, officiis unde ipsa iusto fugit
			aspernatur placeat omnis magnam, maiores dolor maxime sunt. Lorem ipsum dolor sit amet consectetur,
			adipisicing elit. Cupiditate incidunt architecto unde aliquam. Sit veritatis odit recusandae, officiis
			unde ipsa iusto fugit aspernatur placeat omnis magnam, maiores dolor maxime sunt. Lorem ipsum dolor
			sit amet consectetur, adipisicing elit. Cupiditate incidunt architecto unde aliquam. Sit veritatis
			odit recusandae, officiis unde ipsa iusto fugit aspernatur placeat omnis magnam, maiores dolor
			maxime sunt. Lorem ipsum dolor sit amet consectetur, adipisicing elit. Cupiditate incidunt architecto
			unde aliquam. Sit veritatis odit recusandae, officiis unde ipsa iusto fugit aspernatur placeat
			omnis magnam, maiores dolor maxime sunt. Lorem ipsum dolor sit amet consectetur, adipisicing elit.
			Cupiditate incidunt architecto unde aliquam. Sit veritatis odit recusandae, officiis unde ipsa
			iusto fugit aspernatur placeat omnis magnam, maiores dolor maxime sunt. Lorem ipsum dolor sit amet
			consectetur, adipisicing elit. Cupiditate incidunt architecto unde aliquam. Sit veritatis odit
			recusandae, officiis unde ipsa iusto fugit aspernatur placeat omnis magnam, maiores dolor maxime
			sunt. Lorem ipsum dolor sit amet consectetur, adipisicing elit. Cupiditate incidunt architecto
			unde aliquam. Sit veritatis odit recusandae, officiis unde ipsa iusto fugit aspernatur placeat
			omnis magnam, maiores dolor maxime sunt. Lorem ipsum dolor sit amet consectetur, adipisicing elit.
			Cupiditate incidunt architecto unde aliquam. Sit veritatis odit recusandae, officiis unde ipsa
			iusto fugit aspernatur placeat omnis magnam, maiores dolor maxime sunt. Lorem ipsum dolor sit amet
			consectetur, adipisicing elit. Cupiditate incidunt architecto unde aliquam. Sit veritatis odit
			recusandae, officiis unde ipsa iusto fugit aspernatur placeat omnis magnam, maiores dolor maxime
			sunt. Lorem ipsum dolor sit amet consectetur, adipisicing elit. Cupiditate incidunt architecto
			unde aliquam. Sit veritatis odit recusandae, officiis unde ipsa iusto fugit aspernatur placeat
			omnis magnam, maiores dolor maxime sunt. Lorem ipsum dolor sit amet consectetur, adipisicing elit.
			Cupiditate incidunt architecto unde aliquam. Sit veritatis odit recusandae, officiis unde ipsa
			iusto fugit aspernatur placeat omnis magnam, maiores dolor maxime sunt. Lorem ipsum dolor sit amet
			consectetur, adipisicing elit. Cupiditate incidunt architecto unde aliquam. Sit veritatis odit
			recusandae, officiis unde ipsa iusto fugit aspernatur placeat omnis magnam, maiores dolor maxime
			sunt. Lorem ipsum dolor sit amet consectetur, adipisicing elit. Cupiditate incidunt architecto
			unde aliquam. Sit veritatis odit recusandae, officiis unde ipsa iusto fugit aspernatur placeat
			omnis magnam, maiores dolor maxime sunt. Lorem ipsum dolor sit amet consectetur, adipisicing elit.
			Cupiditate incidunt architecto unde aliquam. Sit veritatis odit recusandae, officiis unde ipsa
			iusto fugit aspernatur placeat omnis magnam, maiores dolor maxime sunt. Lorem ipsum dolor sit amet
			consectetur, adipisicing elit. Cupiditate incidunt architecto unde aliquam. Sit veritatis odit
			recusandae, officiis unde ipsa iusto fugit aspernatur placeat omnis magnam, maiores dolor maxime
			sunt. Lorem ipsum dolor sit amet consectetur, adipisicing elit. Cupiditate incidunt architecto
			unde aliquam. Sit veritatis odit recusandae, officiis unde ipsa iusto fugit aspernatur placeat
			omnis magnam, maiores dolor maxime sunt. Lorem ipsum dolor sit amet consectetur, adipisicing elit.
			Cupiditate incidunt architecto unde aliquam. Sit veritatis odit recusandae, officiis unde ipsa
			iusto fugit aspernatur placeat omnis magnam, maiores dolor maxime sunt. Lorem ipsum dolor sit amet
			consectetur, adipisicing elit. Cupiditate incidunt architecto unde aliquam. Sit veritatis odit
			recusandae, officiis unde ipsa iusto fugit aspernatur placeat omnis magnam, maiores dolor maxime
			sunt. Lorem ipsum dolor sit amet consectetur, adipisicing elit. Cupiditate incidunt architecto
			unde aliquam. Sit veritatis odit recusandae, officiis unde ipsa iusto fugit aspernatur placeat
			omnis magnam, maiores dolor maxime sunt. Lorem ipsum dolor sit amet consectetur, adipisicing elit.
			Cupiditate incidunt architecto unde aliquam. Sit veritatis odit recusandae, officiis unde ipsa
			iusto fugit aspernatur placeat omnis magnam, maiores dolor maxime sunt. Lorem ipsum dolor sit amet
			consectetur, adipisicing elit. Cupiditate incidunt architecto unde aliquam. Sit veritatis odit
			recusandae, officiis unde ipsa iusto fugit aspernatur placeat omnis magnam, maiores dolor maxime
			sunt. Lorem ipsum dolor sit amet consectetur, adipisicing elit. Cupiditate incidunt architecto
			unde aliquam. Sit veritatis odit recusandae, officiis unde ipsa iusto fugit aspernatur placeat
			omnis magnam, maiores dolor maxime sunt. Lorem ipsum dolor sit amet consectetur, adipisicing elit.
			Cupiditate incidunt architecto unde aliquam. Sit veritatis odit recusandae, officiis unde ipsa
			iusto fugit aspernatur placeat omnis magnam, maiores dolor maxime sunt. Lorem ipsum dolor sit amet
			consectetur, adipisicing elit. Cupiditate incidunt architecto unde aliquam. Sit veritatis odit
			recusandae, officiis unde ipsa iusto fugit aspernatur placeat omnis magnam, maiores dolor maxime
			sunt. Lorem ipsum dolor sit amet consectetur, adipisicing elit. Cupiditate incidunt architecto
			unde aliquam. Sit veritatis odit recusandae, officiis unde ipsa iusto fugit aspernatur placeat
			omnis magnam, maiores dolor maxime sunt. Lorem ipsum dolor sit amet consectetur, adipisicing elit.
			Cupiditate incidunt architecto unde aliquam. Sit veritatis odit recusandae, officiis unde ipsa
			iusto fugit aspernatur placeat omnis magnam, maiores dolor maxime sunt. Lorem ipsum dolor sit amet
			consectetur, adipisicing elit. Cupiditate incidunt architecto unde aliquam. Sit veritatis odit
			recusandae, officiis unde ipsa iusto fugit aspernatur placeat omnis magnam, maiores dolor maxime
			sunt. Lorem ipsum dolor sit amet consectetur, adipisicing elit. Cupiditate incidunt architecto
			unde aliquam. Sit veritatis odit recusandae, officiis unde ipsa iusto fugit aspernatur placeat
			omnis magnam, maiores dolor maxime sunt. Lorem ipsum dolor sit amet consectetur, adipisicing elit.
			Cupiditate incidunt architecto unde aliquam. Sit veritatis odit recusandae, officiis unde ipsa
			iusto fugit aspernatur placeat omnis magnam, maiores dolor maxime sunt. Lorem ipsum dolor sit amet
			consectetur, adipisicing elit. Cupiditate incidunt architecto unde aliquam. Sit veritatis odit
			recusandae, officiis unde ipsa iusto fugit aspernatur placeat omnis magnam, maiores dolor maxime
			sunt. Lorem ipsum dolor sit amet consectetur, adipisicing elit. Cupiditate incidunt architecto
			unde aliquam. Sit veritatis odit recusandae, officiis unde ipsa iusto fugit aspernatur placeat
			omnis magnam, maiores dolor maxime sunt.
		</MatecuTopbarBody>
	</MatecuTopbarLayout>
</div>

<style lang="scss">
	.fabbtn {
		border: none;
		width: 45px;
		height: 45px;
		border-radius: 50%;
		background-color: pink;
	}
</style>
