# FénecFox
Mis pensamientos acerca del diseño que le daría al lenguage de programación **Fénec Fox**, el zorro que habita en el desierto del sahara.

# Introducción
Fui un programador de Visual FoxPro por 12 años y por eso le tengo un aprecio enorme a este noble lenguaje, debe ser así pues me dio de comer por más de una década y lo menos que puedo hacer por él es evolucionarlo.

[**Fénec Fox**](https://es.wikipedia.org/wiki/Vulpes_zerda) encaja perfectamente con **Fox** porque es un pequeño zorro que habita en el desierto del **Sahara**; casi se podría decir que es el mismo **Visual FoxPro** desterrado al desierto por **Microsoft**. Esta coincidencia hizo *clic* en mi cabeza y he decidido darle un paso evolutivo a nuestro amado zorro, no será un paso enorme pues no tendrá muchas de sus cualidades originales *(por eso encaja con fénec)* pero si que tendrá nuevas habilidades que lo ayudarán a adaptarse a su nuevo entorno *(suena poético con Fénec)*.

Tal vez no te guste **Fénec** pero creeme que el diseño que vas a ver aquí es lo más parecido a un **Visual FoxPro** evolucionado, así que comencemos a ver lo que deja, lo que hereda y lo que adquiere. Este diseño es meramente subjetivo así que la evolución de **Fox** está en mi mano pero no te preocupes porque conozco la gramática de Fox y la gramática de los lenguajes *"modernos"* por lo tanto me aseguraré que sus nuevos poderes lo ayuden a sobrevir en este nuevo ecosistema.


## Limando asperezas en el proceso evolutivo

- **Literales Booleanos:** honestamente **.T.** y **.F.** no me molestan pero he decidido tender una rama hacía el árbol **ALGOL** por lo que ahora serán **true** y **false**. La vieja versión es incluso mejor ya que escribes menos *(3 letras contra 4)* pero esto lo hago para que Fénec sea bien visto por la comunidad cuya raíz desde luego parte de **ALGOL**.
```Javascript
   verdad = true
   mentira = false
```
- **Literales Arrays:** debo admitir que la sintaxis **DIMENSION arrayName()** nunca me gustó así que esta exclusión es personal *(al igual que todas)* 😋. Fénec adoptará la forma simplística que muchos lenguajes tienen pero que fue popularizada por **Javascript**.

```Javascript
   numeros = [1, 2, 3]
   frutas = ["Manzana", "Mango", "Mora"]
```
- **Funciones Builtins:** estas son las funciones que un lenguaje tiene integradas en su núcleo y que por lo tanto podemos utilizar en cualquier script. Visual FoxPro tiene montones de ellas clasificadas por tipos de datos. Aunque particularmente me gusta trabajar con ellas pienso que es mejor adherirlas a su tipo correspondiente y así *limitar* la cantidad de funciones integradas que Fénec debe cargar en sus hombros. Esto tiene un coste que aún sigo sopesando pero creo que al final me decantaré por este diseño. 

Veamos algunos ejemplos:
```xBase
   && Version VFP
   nombre = "Fenec   "
   ?LEN(nombre) && 8
   ?LEN(ALLTRIM(nombre)) && 5
```
El ejemplo anterior está escrito en Visual FoxPro y muestra el uso de 2 funciones integradas: **ALLTRIM()** y **LEN()** donde la primera trabaja con Characters o String y la segunda con números.

Ahora veamos la versión en Fénec:
```Javascript
   // version fénec
   nombre = "Fenec   "
   ?nombre.len() // 8
   ?nombre.trim().len() // 5
```
Como habrás notado **ALLTRIM()** ha perdido parte de su pelaje y ahora es solo **TRIM()** que es una versión resumida y significa lo mismo, esta nueva versión quizá no te agrade mucho pero es una forma de mantener las funciones integradas adheridas a sus tipos. Es verdad que no previenen los errores porque si invocas la función **trim()** sobre un tipo numérico obtendrás un error de incompatibilidad de tipos pero esto tampoco tiene que ser una desventaja porque para eso existen los **[linters]**(https://es.wikipedia.org/wiki/Lint) que ayudan a detectar errores en tiempo de diseño. De esto no tienes que preocuparte porque un linter se puede desarrollar e incrustar dentro de un editor bien sea propio de **Fénec** o un tercero como **VsCode, Atom, etc.**

**ALLTRIM()** y **LEN()** son solo el abrebocas de todo el cambio que sufrirán las funciones integradas. Algunas las agradecerás y otras las lamentarás pero es por el bien de Fénec y su nuevo ecosistema.

**SUBSTR()** está sentenciada a muerte porque lo mismo se puede lograr de la siguiente manera:
```Javascript
   // Versión Fox
   nombre = "Fenec"
   ?SUBSTR(nombre, 1, 3) // fen
   // Versión Fénec
   ?nombre[0:3]
```
¿Qué? ¿Quiere decir que Fénec será basado en cero? La respuesta corta es Sí. No vale la pena agregar más complejidad a la máquina virtual de Fénec para que trate los enumarables basados en 1 en lugar de cero que es su forma natural *(al menos en el lenguaje implementado).*



