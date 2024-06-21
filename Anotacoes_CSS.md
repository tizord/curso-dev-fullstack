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


#### Tamanho relativo de fonte

Se não passarmos nada para a fonte, ela terá o tamanho padrão da tag (por exemplo uma tag parágrafo tem tamanho padrão 16px enquanto a tah h1 tem atamanho padrão 32px). O tamanho relativo de fontes é dado pelo parâmetro **em** e **rem** onde o **em** é relativo a classe pai e o **rem** é relativo a classe raiz. Vejamos um exemplo:

```html
<html>
    <head></head>
    <body>
        <div class="container">
            <p class="exemplo1"> Esse é um exemplo de texto </p>
            <p class="exemplo2"> Esse é outro exemplo de texto</p>
        </div>
        <p class="exemplo3"> Esse é um novo exemplo de texto </p>
    </body>
```

No exemplo acima, temos a div de classe **container** e dentro dela temos duas tags parágrafos com classes diferentes. Fora da div temos outro parágrafo com outra classe. Agora, supondo o seguinte código css:

```css
.container{
    font-size: 15px;
}

.exemplo1{
    
}

.exemplo2{
    font-size: 2em;
}

html{
    font-size: 20px;
}

.exemplo3{
    font-size: 1.5rem
}
```
Repare que a classe container tem tamanho de 15px, portanto:
* O exemplo1 tem 15px por estar dentro da div que tem essa classe.
* O exemplo2 tem 2em, ou seja, 2* o tamanho da classe pai, logo tem: 2*15px = 30px.
* O html, classe raiz, tem tamanho de fonte de 20px. Todo o documento, se não for definido, terá 20px.
* O exemplo3 tem 1.5rem, ou seja, 1.5 o tamanho do elemento raiz, logo: 1.5*20px = 30px.

#### Transformação de texto

Vamos ver os principais atributos para transformar o texto. Considere o trecho de código html a seguir:

```html
<body>
    <p id="p1"> Texto 1 </p>
</body>
```

Agora:

```css
#p1{
    text-transform: capitalize;
    text-decoration: underline;
    text-align: center;
    letter-spacing: 0px;
    word-spacing: 0px;
    line-height: 1em;
    text-indent: 30px;
    text-shadow: 5px 5px 10px black; (distância para o lado, distancia para baixo, esfumaçamento da sobra e cor da sombra)
}
    
```

#### Fontes

As famílias de fonte são:
* Com serifa (as voltinhas)
* Sem serifa (sem as voltinhas)
* Monospace (o espaço de todas as letras é igual)

Como podemos mudar as fontes? Vamos ver. Considere o pedaço de código html abaixo:
```html
<body>
    <div>
        <h1> texto </h1>
            <p id="paragrafo1"> texto texto texto </p>
            <p > texto texto texto </p>
    </div>
</body>
```

Agora:

```css
body{
    font-family: sans-serif;
    font-style: italic;
}

h1{
    font-family: monospace;
    font-weight: bold;
}

#paragrafo1{
    font-family: "Comic Sans MS", "Arial";
    font-size: larger;
    font-variant: small-caps;
}
```

No último caso, o que acontece é:
* Escolhemos a fonte Comic Sans. Mas e se o usuários não tiver essa fonte? Exibe a Arial. É um recurso de backup.

E como podemos customizar nossas fontes?

1) Primeiro precisamos ter acesso a fonte. Um exemplo é o fonts.google.com. Nesse caso, ele disponibiliza um link que devemos importar na tag head.
2) Podemos baixar a fonte (otf, tff ou woff). Tem-se que atentar para o peso das fontes. Depois devemos criar um font-face:
```css
@font-face{
    font-family: NomeDaFonte;
    src: url(caminho_da_fonte/fonte.otf);
}
```
3) O site fontsquirrel transforma o arquivo com as fontes em arquivo.tff, para poder ser usado.

#### Border

São as bordas de um elemento. Para criar uma borda, deve-se definir algumas propriedas:
* border-width: Espessura da borda. Lembrando que é top, right, bottom left
* border-style: Estilo da borda. O padrão é none
* border-color: Cor da borda
* border-radius: Deixa os cantos arredondados

Imagine uma div com id "primeira" e uma tag parágrafo:

```css
#primeira{
    height: 100px;
    width: 100px;
    background-color: red;
    border-width: 5px 10px 15px 20px;
    border-style: dashed;
    border-color: blue green red yellow;
    border-radius: 50%
}

p{
    border: 3px solid green;
}
```

O estilo da tag parágrafo é short-hand.

#### Margin e Padding
