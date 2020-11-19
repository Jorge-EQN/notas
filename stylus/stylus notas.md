# Notas de Stylus

crear variables

```stylus
$variable = 500px
variable = 600px

div
	width $variable
    height (@width / 2) // divide la variable width
div
    width variable
	article
    	height (@width / 2) // divide la variable width mas cercana

```

Mixins

```stylus
body 
    backgroud white
center()//mixin
	position relative
	margin 0 auto 0 auto 0
    
border-radius(n)//nos ayuda compilar para todos los navegadores
    border-radius n
    -webkit-border-radius n
    -moz-border-radius n
.box
    center()//se llama mixin y compila
    background white
    border-radius(5px)
    border 1px solid red
    width 250px
    height 150px
.container
    background blue
    color white
    width 200px
    border 1px solid white
    center()//el mixin se puede llamar cuatas veces quieras
    border-radius(5px)
    
```

