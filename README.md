# Interfaces_Design_Android
Esta es una recopilación de los temas vistos en el Curso Básico de diseño de interfaces con Android Studio


# Tabla de contenido
- [Interfaces_Design_Android](#interfaces_design_android)
  - [1. UI en Android: ¿Por qué? ¿Cómo?](#1-ui-en-android-por-que-como)
    - [1.1. ¿Qué es XML?](#11-que-es-xml)
    - [1.2. Tags (etiquetas) en XML](#12-tags-etiquetas-en-xml)
    - [1.3. Los namespaces y su importancia en las tags de XML](#13-los-namespaces-y-su-importancia-en-las-tags-de-xml)
    - [1.4. ¿Como saber de donde proviene el namespace en AS?](#14-como-saber-de-donde-proviene-el-namespace-en-as)
## 1. UI en Android: ¿Por que? ¿Como?
### 1.1. ¿Que es XML?

**XML** (eXtensible Markup Language): es un lenguaje de etiquetas, es decir, cada paquete de información está delimitado por dos

***etiquetas/tags*** como se hace también en el lenguaje HTML, pero XML separa el contenido de la presentación.

```xml
<H1>Mateo</H1> <--- HTML
<Nombre>Mateo</Nombre> <--- XML
```

`<H1`> y `<Nombre>` son **etiquetas/tags**. Ambas encierran el texto o paquete de información *Mateo*. <br>

- La etiqueta `<H1>` es de HTML, y se encarga de mostrar visualmente el texto *Mateo* en la página web en un tamaño determinado, pero no dice nada del significado de *Mateo*: si es una ciudad o un nombre, por ejemplo. `<br>`

- En cambio, la etiqueta `<Nombre>` es de XML y nos dice que *Mateo* es un nombre de persona, por lo tanto, XML se preocupa del significado del texto que encierra y no de la apariencia de cómo se muestre el texto en la página web.

Por lo anterior, se dice que XML es un lenguaje de etiquetas, que como hemos dicho anteriormente, separa el contenido de la presentación.`<br><br>`

### 1.2. Tags (etiquetas) en XML

**Pueden tener atributos**, que son una manera de incorporar características o propiedades a las etiquetas de un documento.

El atributo **consta de dos partes**:

1. La **propiedad** del elemento
2. El **valor** de la propiedad,

que siempre va entre comillas dobles (“) o simple (‘).

```xml
<TAG atributo="valor">
    Contenido
</TAG>

<TAG-2 atributo="valor"/>

```

⇒ Ejemplo práctico:

```xml
<Datos-Nacimiento>
    <Persona>
       <Nombre>Mateo</Nombre>
       <Fecha>15.10.2012</Fecha>
       <Ciudad>Madrid</Ciudad>
       <Peso>3.1Kg</Peso>
       <Estatura>45cm</Estatura>
    </Persona>
    <Persona>
       <Nombre>Maribel</Nombre>
       <Fecha>11.09.2012</Fecha>
       <Ciudad>Sevilla</Ciudad>
       <Peso>3Kg</Peso>
       <Estatura>40cm</Estatura>
    </Persona>
</Datos-Nacimiento>
```


### 1.3. Los namespaces y su importancia en las tags de XML

Es una forma de dar un *contexto, o* (scope), a un tag.

> Es definir donde un elemento tiene un valor definido.
>

```xml
<NAMESPACE:TAG atr="val">
    Contenido
</NAMESPACE:TAG>

```

En otras palabras, es un medio para organizar clases dentro de un entorno, agrupándolas de un modo más lógico y jerárquico.

**⇒ Ejemplo:**

```xml
<Profesor:Luis
    trabajo:horario="9-11"
    trabajo:email="luisprof@uni.com"
    persona:id="@user9283">
</Profesor:Luis>
```

- En Android veremos mucho el ***namespace*** de Androd en la siguiente forma:

```xml
<TextView android:text="Hola mundo" />
```

### 1.4. **¿Como saber de donde proviene el namespace en AS?**

Con la palabra reservada `xmlns` y con un **URI/dirección** que hará a entender de donde un XML tiene su procedencia, de esa manera XML va a poder entender cuando un valor tiene o no tiene un contexto y cuando puede darle o asignarle un comportamiento.

Siguiendo el ejemplo anterior:

```xml
<... xmlns:android="http://schemas.android.com/apk/res/android"/>

```

> [!NOTE]
> 
> `android` es un alias asignado por nosotros. 
> Podemos ver esto como una forma de encapsular otra etiqueta dentro una clase *Android*.