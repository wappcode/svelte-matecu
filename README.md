# Svelte-Matecu

Libreria con complementos y utilidades para el desarrollo de aps

## Instalar

    npm install svelte-matecu

Agregar estilos para la fuente de los iconos

```
<link rel="stylesheet" href="https://fonts.googleapis.com/css2?family=Material+Symbols+Outlined:opsz,wght,FILL,GRAD@20..48,100..700,0..1,-50..200"/>
```

## MatecuTopbarLayout

Crea la estructura para una página que contiene un topbar en posición fija a la que se le pueden agregar botones de acciones, titulo y buscador.

El contenido de la página tiene una función que se puede llamar para realizar un desplazamiento hacia arriba.

## Ejemplo básico

```
<script lang="ts">

    // imports ...
    let scrollTop: () => void;
    let mobileStyle = false;

    // Detecta cambios en el input de búsqueda
	const handleSearching = (event: any) => {
		console.log('event searching', event);
	};
    // Detecta cambios al redimencionar el compontente principal
	const handleResize = (event: any) => {
		mobileStyle = event.detail.width < 768;
	};
</script>
<MatecuTopbarLayout
		bind:scrollTop
		on:resize={handleResize}
	>
		<MatecuTopbarHeaderRow slot="first-row">
			<MatecuTopbarHeaderColumn slot="left-column">
				<MatecuTopbarAction>NAV_MENU</MatecuTopbarAction>
				<MatecuTopbarFab {mobileStyle}>
                    <button type="button" class="fabbtn">+</button>
                </MatecuTopbarFab>
				<MatecuTopbarTitle>
                    El titulo de la página
                </MatecuTopbarTitle>
			</MatecuTopbarHeaderColumn>
			<MatecuTopbarHeaderColumn slot="right-column">
				<MatecuTopbarSearch
					{mobileStyle}
					on:valueChanges={handleSearching}
					placeholder="Buscando..."
				/>
				<MatecuTopbarAction>PAGE_MENU</MatecuTopbarAction>
			</MatecuTopbarHeaderColumn>
		</MatecuTopbarHeaderRow>


		<MatecuTopbarBody slot="body">
			Contenido de la página ...
		</MatecuTopbarBody>
	</MatecuTopbarLayout>
    <style >
	    .fabbtn {
		    border: none;
		    width: 45px;
		    height: 45px;
		    border-radius: 50%;
		    background-color: pink;
	    }
    </style>

```

## Componentes

MatecuTopbarLayout: Componente principal
MatecuTopbarHeaderRow: Crea una fila para agregar contenido en el encabezado, pueden agregarse hasta 2 filas y es necesario agregar el nombre del slot (first-row, second-row)
MatecuTopbarHeaderColumn
MatecuTopbarAction
MatecuTopbarFab
MatecuTopbarSearch
MatecuTopbarTitle
MatecuTopbarBody
