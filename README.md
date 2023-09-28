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

### MatecuTopbarLayout:

Componente principal

#### Variables de estilos

- --mtb-border : Borde
- --mtb-margin : Margen
- --mtb-width : Ancho
- --mtb-height : Alto
- --mtb-primary-color : Color principal (Color de la barra)
- --mtb-bar-height : Alto de la barra
- --mtb-bar-prominent-height : Alto de la barra en modo prominente

### Properties

- prominent : Valor boolean que indica si la barra es prominente

### Binds

- scrollTop : Funcion que se puede llamar desde el componente padre y hace scroll del contenido hacia la parte superior

### MatecuTopbarHeaderRow

Crea una fila para agregar contenido en el encabezado, pueden agregarse hasta 2 filas y es necesario agregar el nombre del slot (first-row, second-row)

### MatecuTopbarHeaderColumn

Crea una columna para agregar contenido a una fila del encabezado es necesario agregar el nombre del slot (left-column,right-column)

### MatecuTopbarAction

Crea un contenedor para agregar acciones como links o botones preferentemente en formato de iconos

### MatecuTopbarFab

Crea un contenedor para agregar un boton (FAB)

### Variables de estilos

--mtb-fab-mobile-bottom-position : Posición relativa a la parte inferior del componente pricipal que se aplica cuando estan activos los estilos para dispositivos móviles.

--mtb-fab-mobile-right-position: Posición relativa a la parte i

#### Propiedades

- mobileStyle: Valor boolaneo que indica si se ajustan los estilos para dispositivos móviles

### MatecuTopbarSearch

Crea un campo de texto para hacer búsquedas

#### Eventos

- valueChanges: Emite un evento con el valor del texto ingresado en el campo de búsqueda

#### Propiedades

- mobileStyle: Valor boolaneo que indica si se ajustan los estilos para dispositivos móviles

### MatecuTopbarTitle

Crea un contenedor para agregar un título a la página.

### MatecuTopbarBody

Crea un contenedor para agregar el contenido de la página

#### Variables de estilos

--mtb-body-padding: Padding para el contenido
--mtb-body-background: Fondo del contenido;
--mtb-body-padding-button: Padding inferior (Es utilizado para asignar un espacio al Botón principal (FAB) cuando tiene asignados los estilos para dispositivos móviles)
