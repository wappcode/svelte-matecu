<script lang="ts">
	import MatecuTopbarAction from '../lib/components/MatecuTopbarAction.svelte';
	import MatecuTopbarBody from '../lib/components/MatecuTopbarBody.svelte';
	import MatecuTopbarColumn from '../lib/components/MatecuTopbarColumn.svelte';
	import MatecuTopbarHeaderRow from '../lib/components/MatecuTopbarHeaderRow.svelte';
	import MatecuTopbarLayout from '../lib/components/MatecuTopbarLayout.svelte';
	import MatecuTopbarSearch from '../lib/components/MatecuTopbarSearch.svelte';
	import MatecuTopbarTitle from '../lib/components/MatecuTopbarTitle.svelte';

	let scrollTop: () => void;
</script>

<div>
	<h1>Matecu Topbar Layout</h1>
	<button on:click={scrollTop}>Scroll top</button>
	<!-- <div class="matecu-topbar-layout">a</div> -->
	<MatecuTopbarLayout
		--heigth="500px"
		--width="500px"
		--primary-color="red"
		--border="1px solid blue"
		bind:scrollTop
	>
		<MatecuTopbarHeaderRow slot="header-row-first">
			<MatecuTopbarColumn slot="left-column">
				<MatecuTopbarAction>A</MatecuTopbarAction>
				<MatecuTopbarAction>B</MatecuTopbarAction>
				<MatecuTopbarTitle>Título de la página</MatecuTopbarTitle>
			</MatecuTopbarColumn>
			<MatecuTopbarColumn slot="right-column">
				<MatecuTopbarSearch />
				<MatecuTopbarAction>A</MatecuTopbarAction>
				<MatecuTopbarAction>B</MatecuTopbarAction>
			</MatecuTopbarColumn>
		</MatecuTopbarHeaderRow>
		<MatecuTopbarBody slot="body">
			Lorem ipsum dolor sit amet consectetur, adipisicing elit. Cupiditate incidunt architecto unde
			aliquam. Sit veritatis odit recusandae, officiis unde ipsa iusto fugit aspernatur placeat
			omnis magnam, maiores dolor maxime sunt. Lorem ipsum dolor sit amet consectetur, adipisicing
			elit. Cupiditate incidunt architecto unde aliquam. Sit veritatis odit recusandae, officiis
			unde ipsa iusto fugit aspernatur placeat omnis magnam, maiores dolor maxime sunt. Lorem ipsum
			dolor sit amet consectetur, adipisicing elit. Cupiditate incidunt architecto unde aliquam. Sit
			veritatis odit recusandae, officiis unde ipsa iusto fugit aspernatur placeat omnis magnam,
			maiores dolor maxime sunt. Lorem ipsum dolor sit amet consectetur, adipisicing elit.
			Cupiditate incidunt architecto unde aliquam. Sit veritatis odit recusandae, officiis unde ipsa
			iusto fugit aspernatur placeat omnis magnam, maiores dolor maxime sunt. Lorem ipsum dolor sit
			amet consectetur, adipisicing elit. Cupiditate incidunt architecto unde aliquam. Sit veritatis
			odit recusandae, officiis unde ipsa iusto fugit aspernatur placeat omnis magnam, maiores dolor
			maxime sunt. Lorem ipsum dolor sit amet consectetur, adipisicing elit. Cupiditate incidunt
			architecto unde aliquam. Sit veritatis odit recusandae, officiis unde ipsa iusto fugit
			aspernatur placeat omnis magnam, maiores dolor maxime sunt. Lorem ipsum dolor sit amet
			consectetur, adipisicing elit. Cupiditate incidunt architecto unde aliquam. Sit veritatis odit
			recusandae, officiis unde ipsa iusto fugit aspernatur placeat omnis magnam, maiores dolor
			maxime sunt. Lorem ipsum dolor sit amet consectetur, adipisicing elit. Cupiditate incidunt
			architecto unde aliquam. Sit veritatis odit recusandae, officiis unde ipsa iusto fugit
			aspernatur placeat omnis magnam, maiores dolor maxime sunt. Lorem ipsum dolor sit amet
			consectetur, adipisicing elit. Cupiditate incidunt architecto unde aliquam. Sit veritatis odit
			recusandae, officiis unde ipsa iusto fugit aspernatur placeat omnis magnam, maiores dolor
			maxime sunt. Lorem ipsum dolor sit amet consectetur, adipisicing elit. Cupiditate incidunt
			architecto unde aliquam. Sit veritatis odit recusandae, officiis unde ipsa iusto fugit
			aspernatur placeat omnis magnam, maiores dolor maxime sunt. Lorem ipsum dolor sit amet
			consectetur, adipisicing elit. Cupiditate incidunt architecto unde aliquam. Sit veritatis odit
			recusandae, officiis unde ipsa iusto fugit aspernatur placeat omnis magnam, maiores dolor
			maxime sunt. Lorem ipsum dolor sit amet consectetur, adipisicing elit. Cupiditate incidunt
			architecto unde aliquam. Sit veritatis odit recusandae, officiis unde ipsa iusto fugit
			aspernatur placeat omnis magnam, maiores dolor maxime sunt. Lorem ipsum dolor sit amet
			consectetur, adipisicing elit. Cupiditate incidunt architecto unde aliquam. Sit veritatis odit
			recusandae, officiis unde ipsa iusto fugit aspernatur placeat omnis magnam, maiores dolor
			maxime sunt. Lorem ipsum dolor sit amet consectetur, adipisicing elit. Cupiditate incidunt
			architecto unde aliquam. Sit veritatis odit recusandae, officiis unde ipsa iusto fugit
			aspernatur placeat omnis magnam, maiores dolor maxime sunt. Lorem ipsum dolor sit amet
			consectetur, adipisicing elit. Cupiditate incidunt architecto unde aliquam. Sit veritatis odit
			recusandae, officiis unde ipsa iusto fugit aspernatur placeat omnis magnam, maiores dolor
			maxime sunt. Lorem ipsum dolor sit amet consectetur, adipisicing elit. Cupiditate incidunt
			architecto unde aliquam. Sit veritatis odit recusandae, officiis unde ipsa iusto fugit
			aspernatur placeat omnis magnam, maiores dolor maxime sunt. Lorem ipsum dolor sit amet
			consectetur, adipisicing elit. Cupiditate incidunt architecto unde aliquam. Sit veritatis odit
			recusandae, officiis unde ipsa iusto fugit aspernatur placeat omnis magnam, maiores dolor
			maxime sunt. Lorem ipsum dolor sit amet consectetur, adipisicing elit. Cupiditate incidunt
			architecto unde aliquam. Sit veritatis odit recusandae, officiis unde ipsa iusto fugit
			aspernatur placeat omnis magnam, maiores dolor maxime sunt. Lorem ipsum dolor sit amet
			consectetur, adipisicing elit. Cupiditate incidunt architecto unde aliquam. Sit veritatis odit
			recusandae, officiis unde ipsa iusto fugit aspernatur placeat omnis magnam, maiores dolor
			maxime sunt. Lorem ipsum dolor sit amet consectetur, adipisicing elit. Cupiditate incidunt
			architecto unde aliquam. Sit veritatis odit recusandae, officiis unde ipsa iusto fugit
			aspernatur placeat omnis magnam, maiores dolor maxime sunt. Lorem ipsum dolor sit amet
			consectetur, adipisicing elit. Cupiditate incidunt architecto unde aliquam. Sit veritatis odit
			recusandae, officiis unde ipsa iusto fugit aspernatur placeat omnis magnam, maiores dolor
			maxime sunt. Lorem ipsum dolor sit amet consectetur, adipisicing elit. Cupiditate incidunt
			architecto unde aliquam. Sit veritatis odit recusandae, officiis unde ipsa iusto fugit
			aspernatur placeat omnis magnam, maiores dolor maxime sunt. Lorem ipsum dolor sit amet
			consectetur, adipisicing elit. Cupiditate incidunt architecto unde aliquam. Sit veritatis odit
			recusandae, officiis unde ipsa iusto fugit aspernatur placeat omnis magnam, maiores dolor
			maxime sunt. Lorem ipsum dolor sit amet consectetur, adipisicing elit. Cupiditate incidunt
			architecto unde aliquam. Sit veritatis odit recusandae, officiis unde ipsa iusto fugit
			aspernatur placeat omnis magnam, maiores dolor maxime sunt. Lorem ipsum dolor sit amet
			consectetur, adipisicing elit. Cupiditate incidunt architecto unde aliquam. Sit veritatis odit
			recusandae, officiis unde ipsa iusto fugit aspernatur placeat omnis magnam, maiores dolor
			maxime sunt. Lorem ipsum dolor sit amet consectetur, adipisicing elit. Cupiditate incidunt
			architecto unde aliquam. Sit veritatis odit recusandae, officiis unde ipsa iusto fugit
			aspernatur placeat omnis magnam, maiores dolor maxime sunt. Lorem ipsum dolor sit amet
			consectetur, adipisicing elit. Cupiditate incidunt architecto unde aliquam. Sit veritatis odit
			recusandae, officiis unde ipsa iusto fugit aspernatur placeat omnis magnam, maiores dolor
			maxime sunt. Lorem ipsum dolor sit amet consectetur, adipisicing elit. Cupiditate incidunt
			architecto unde aliquam. Sit veritatis odit recusandae, officiis unde ipsa iusto fugit
			aspernatur placeat omnis magnam, maiores dolor maxime sunt. Lorem ipsum dolor sit amet
			consectetur, adipisicing elit. Cupiditate incidunt architecto unde aliquam. Sit veritatis odit
			recusandae, officiis unde ipsa iusto fugit aspernatur placeat omnis magnam, maiores dolor
			maxime sunt. Lorem ipsum dolor sit amet consectetur, adipisicing elit. Cupiditate incidunt
			architecto unde aliquam. Sit veritatis odit recusandae, officiis unde ipsa iusto fugit
			aspernatur placeat omnis magnam, maiores dolor maxime sunt. Lorem ipsum dolor sit amet
			consectetur, adipisicing elit. Cupiditate incidunt architecto unde aliquam. Sit veritatis odit
			recusandae, officiis unde ipsa iusto fugit aspernatur placeat omnis magnam, maiores dolor
			maxime sunt. Lorem ipsum dolor sit amet consectetur, adipisicing elit. Cupiditate incidunt
			architecto unde aliquam. Sit veritatis odit recusandae, officiis unde ipsa iusto fugit
			aspernatur placeat omnis magnam, maiores dolor maxime sunt.
		</MatecuTopbarBody>
	</MatecuTopbarLayout>
</div>

<style lang="scss">
	div {
		border: 1px solid green;
		min-height: 100vh;
	}
</style>
