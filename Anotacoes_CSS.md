## CSS Básico


Existem 3 maneiras de criar o CSS:
* Inline
* Online
* Externo

### CSS inline


Inserimos o código css dentro da tag que queremos modificar a partir do atributo **style**. A forma básica é:  
"propriedade:estilo da propriedade"

```css
<p style="color:red"> Texto </p>
```

### CSS interno


O CSS interno é inserido dentro da tag **style** dentro da tag **head** do HTML, ele serve para separar o estilo do elemento em si. Tem a vantagem de poder usar o mesmo estilo em todas as tags iguais de um mesmo tipo. Repare que para usar dessa forma, após o nome do elemento usamos chaves ({ }):

```css
<head>
    <style>
        p{
            color:red;
            background-color: yellow;
            }
    </style>
</head>

<body>
    <p> Texto </p>
</body>
```

### CSS externo


O CSS externo também permite que selecionemos os elementos através de seletores mas dessa forma teremos um arquivo externo, geralmente chamado de **style.css**. A vatangem de usar o css externo é que podemos ter um style para todas as página da nossa aplicação, ao passo que o css interno aplica somente ao código html em que estiver inserido e isso força a termos que copiar o estilo em todos os arquivos html. Para usar o estilo separado, dentro da tag **head** de todos os arquivos **html** fazemos:


```css
<head>
    <link rel="stylesheet" href="./style.css">
</head>
```
Lembrando que o href deve levar ao caminho que está o arquivo css! 


### Propriedades CSS

Podemos ver a lista de todas as propriedades do CSS em:  
w3schools.com/cssref/  
Podemos (e devemos) passar várias propriedades para um elemento, separendo cada atributo por ponto e vírgula (;)
```css
<p style="background-color: yellow ; color: red;"> Texto </p>
```

Para que usemos o seletor de elementos (ids e classes), temos duas estruturas possíveis:
* A estrutura #id, onde o # indica para o css que estamos nos referindo a um id de um elemento html, depois passamos o nome do id,
* A estrutura .nome-classe, onde o . indica que estamos nos referindo a uma classe, e o nome-classe é o nome da classe. No exemplo abaixo, vamos criar dois elementos html, o primeiro usando id e o segundo vamos dar o nome da classe e após vamos criar o estilo da classe:


```html
<p id="paragrafo1"> Texto </p>
<p class="paragrafo-2"> Texto 2 </p>
```


```css
#paragrafo1{
    color: blue;
    background-color: yellow
}

.paragrafo-2{
    color: red;
    background-color: yellow
}
```

A diferença da classe para um id é que o id só pode ser usado uma vez na página, seria como um nome. A classe pode aparecer quantas vezes o desenvolvedor quiser, serve para generalizar. Além disso, o CSS funciona da maior especificidade para a menor especificidade, veja da maior especificidade para a menor:  
id > classe > tag  

Além disso, podemos ter, na mesma tag, uma classe e um id e até mesmo mais de uma classe. Quando temos mais de uma classe em um elemento, basta separar com um espaço ( ):


```html
<p class="classe-1 classe-2"> Texto </p>
```

Quando trabalhamos com cores no css, podemos fazer:  
* Usando o nome da cor (red, blue, green, aquamarine),
* Usando o atributo "rgb" dentro do parênteses (rgb(255,0,0), rgb(0,0,255)...),
* Usando o código hexadecimal (#ffffff, #000000, #660099)
* Temos também o rgba, onde o a indica a opacidade, variando de 0 a 1 (rgba(255,0,0,0.5))


```css
#id{
    color: red;
    color: rgb(255, 0, 0);
    color: #FF0000;
    color: rgba(255, 0, 0, 0.5)
}
```

Podemos, também, acessar a página w3schools.com/cssref/css_colors.asp para ver as cores (limitada a 140 cores), seus nomes e seus códigos hexadecimal.

Podemos adicionar uma imagem de fundo em um elemento, por exemplo, imagina uma div que será o banner do nosso site. Fazemos isso usando o atributo **background-image**:

```css
div{
    background-image: url('./caminho_imagem/imagem.jpg')
}
```
Porém, se não passarmos nenhum outro parâmetro, ele repete a imagem inteira. Precisamos passar mais um parâmetro, como o **background-size** que assume alguns valores:
* contain,
* cover,
* auto,  
Podemos também usar o atributo background-repeat que assume os valores:  
* repeat-x,
* repeat-y,
* no-repeat
O background tem muitos atributos, outro atributo importante é **background-position** que tem valores como:  
* right,
* top left,
* etc
Podemos ter o efeito de "fundo fixo" enquanto rola a página, que é usando o atributo **background-attachment**.

```css
div{
    background-color: yellow;
    background-image: url('./caminho_imagem/imagem.jpg');
    background-repeat: no-repeat;
    background-size: cover;
    background-attachment: fixed;
    background-position: right;
}
```

Por fim, outra forma de fazer tudo isso é usando o short-hand, que é passar todos os parâmetros de uma vez mas, nesse caso, existe uma ordem que se deve seguir:  
cor, url, repeat, attachment, position  
fazendo:

```css
div{
    background yellow url('./caminho_imagem/imagem.jpg') no-repeat right;
    background-size: cover; 
}
```

Agora, vamos ver como criar um gradiente de cor. Para isso, vamos super que existe uma div com classe "gradiente". Para podermos fazer esse efeito, temos que usar uma **função css** que será visto mais pra frente. Por hora, vamos ver que o gradiente:
* Pode ter mais de uma cor,
* Pode ter um ângulo definido (passando o angulo (deg) ou passando a direção do gradiente (to bottom right)),
* Podemos definir onde vai começar o grandiente de cada dor (x% cor),
* Podemos definir onde vai estar a parte com a cor que definimos mais forte (meio do gradiente) (x%)
No código abaixo vamos ver essas possibilidades todas juntas:

```css
.grandiente{
    height: 100px;
    background: linear-gradiente(90deg, red, blue 25%, 40%, green);
}

```

Agora vamos olhar as **unidades** de medidas. No CSS temos as **unidades fixas** e as **unidades relativas**. De forma geral, as **unidades fixas** não dependem de outros elementos, possuem valor próprio e é necessáio alterar esses valores para alterar o tamanho do elemento. As **unidades relativas** possuem tamanho relativo ao elemento pai logo, se o elemento pai sofre uma variação no seu tamanho, o elemento filho também sofrerá. Se não utilizarmos nenhuma unidade, a unidade padrão é pixel (px). As unidade de medidas são:
* cm: centímetros
* mm: milímetros
* in: polegadas (1in = 96px = 2.54cm)
* px: pixels (low dpi)
* pt: pontos (1pt = 1/72 in)
* pc picas (1pc = 12pt)

Porém, quando falamos em telas, supondo uma mesma dela de 29", elas podem ter propriedades como FullHD ou 4K, que determina a quantidade de pixels da tela e, por isso, a quantidade de pixels é diferente para cada tela.

Para podermos ver melhor a diferença entre as unidade fixas e relativas, vamos considerar o código html abaixo:  

```html
<div id="codigo1">
    <img class="imagem1" src="./imagem.jpg">
</div>

<div id="codigo2">
    <img class="imagem2" src="./imagem.jpg">
</div>

```
O código acima cria duas divs que vão conter a mesma imagem. Em uma vamos usar a medida fixa e na outra a medida relativa. As unidades de medida relativa são:  
* % (porcentagem de um elemento)
* vw (viewport width - largura do tamanho da tela)
* vh (viewport height - altura da tela)
Vamos mostrar todas:

```css
#codigo-1{
    width: 500px;
    height: 30vh;
}

#codigo-2{
    width: 70vw;
    height: 400px;

}

.imagem1{
    width: 300px;
}

.imagem2{
    width: 50%
}
```

No primeiro caso, a imagem vai ocupar 300px dentro da div. Se o tamanho da div for alterado, a imagem continuará a ocupar 300px. No segundo caso, a imagem vai ocupar 50% do tamanho da div que ela está inserida, ou seja, 350px. Se aumentarmos o tamanho da div, a imagem também aumentará, mas sempre correspondendo 50% do tamanho da div.
