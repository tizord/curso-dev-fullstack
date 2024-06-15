## HTML básico

O conteúdo html tem que estar entre tags.  

```html  
<tag> Conteúdo </tag> = Elemento HTML  
```
  
O primeiro passo é dizer para o navegador qual é o tipo do documento:  

```html
<!DOCTYPE html>
```
E a estrutura básica é:  

```html
<!DOCTYPE html>
<html lang=pt-BR>
    A tag <b>html</b> diz onde começa e onde termina o documento html

    <head>
        A tag <b>head</b> diz para o navegador, tudo que ele precisa saber para carregar a página corretamente
    </head>

    <body>
        A tag <b>body</b> mostra tudo que você deseja exibir para o usuário, na página.
    </body>

</html>

```
Repare no atributo **lang='pt-BR'** dentro da tag html.

Agora, vamos colocar alguns valores e tags, a explicação será feita a posterior:  


```html
<!DOCTYPE html>
<html>
    <head>
        <title> Minha Página </title>
        <meta charset='UTF-8'/>
    </head>

    <body>
        
        <h1> Esse é o meu título </h1>
        <h2> Esse é o meu subtítulo </h2>
        <p> Esse é o meu parágrafo</p>
        <!-- Isso é um comentário.-->


        <h2> Tags de texto </h2>
        <p>
            Esse <del>texto</del> <ins> parágrafo </ins> serve para <b>aprender</b> e <strong>explicar</strong> as <i>tags</i> de <mark>formatação de texto</mark>.<br>
            Por isso, <small>estamos</small> escrevendo coisas sem relevância, para podermos ver como que faz isso em html.<br>
            É isso! Um exemplo das tag small e sub juntas pode ser um exemplo matemático: E<sub><small>n</small></sub> ou até de forma sobrescrita: E<sup><small>n</small></sup>
        </p>

        <h2> Tag de Link </h2>
        <p>
            Navegando entre páginas. Imagine que temos os arquivos "pagina1.html", "pagina2.html" e estamos no "index.html", onde todas estão na mesma pasta e, vamos upor que queremos ir para uma página externa. Para navegar entre as páginas vamos usar:
            <a href='pagina1.html'> Página 1 </a>
            <br>
            <a href='pagina2.html'> Página 2 </a>
            <br>
            <a href='www.pagina.com/pagina'> Página externa </a>
            <br>
            <a href='/'> Link página principal </a>

            Temos, também, outras opções, como:
                Abrir o link em uma nova janela (1),
                Redirecionar para uma ligação (2),
                Link para o zap (3, 4),
                Link para o app do instagram (5),
                Link de e-mail (6), vamos explorar abaixo:
            <a href='link' target='_blank'> Esse link abre em uma nova aba (1)</a>
            <a href='tel:numero'> Esse link redireciona para uma ligação (2)</a>
            <a href='https://wa.me/'+numero target='_blank'> Esse link abre no zap, mas passa na janelinha (3)</a>
            Tambem temos a opção:
            <a href='whatsapp://numero' target='_blank'> Esse link abre direto no zap, não passa na janelinha de abrir (4) </a>
            <a href='instagram://user?username=nome_usuario' target='_blank'> Esse link abre direto no app do Instagram (5) </a>
            <a href='mailto:email@email.com' target='_blank'> Esse link leva para o serviço de email (6) </a>




        <h2> Tag de Imagem img e figure </h2>
        <p>
            Para colocar imagem, usamos a tag "img" com o atributo src (source):
            <img src='site.com/imagem.png'>
            <br>
            E para imagens que estão local:
            <img src='/pasta_imagens/imagem.jpg'>
            Aqui, deixa-se claro que, sempre que queremos mudar o formato/tamanho de qualquer coisa, a gente usa o CSS. Mas o html dá essa possibilidade, por exemplo:
            <img src='/pasta_imagens/imagem.jpg' width='100' height='100'>
            Temos também o atributo alt que diz o que é a imagem (alternative):
            <img alt='Imagem fictícia em uma pasta fictícia' src='/pasta_imagens/imagem.jpg' width='100' height='100'>
            Para colocar uma legenda em uma foto, precisamos envolver tanto a tag img quanto a legenda (figcaption), na tag figure:
            <figure>
                <img alt='Imagem fictícia em uma pasta fictícia' src='/pasta_imagens/imagem.jpg' width='100' height='100'>
                <figcaption> Foto ficticia, e sua legenda verdadeira </figcaption>
            </figure>


        <h2> Listas </h2>
        Temos as listas não ordenadas (unordered list ou ul) e as ordenadas (ordered list ou ol)
        <ul>
            <li> Item número 1</li>
            <li> Item número 2</li>
            <li> Item número 3</li>
        </ul>

        <ol>
            <li> Item número 1</li>
            <li> Item número 2</li>
            <li> Item número 3</li>
        </ol>

        As listas ordenadas tem alguns atributos como:
        reversed: Traz a lista na ordem inversa,
        start=n: diz em qual número a lista deve começar. (começa em n)
        type=a: o tipo de lista, pode ser (1,2,3), (a,b,c), entre outras opções. (classifica pelo alfabeto)

        <h2> DIV e ID </h2>
        A tg div é extremamente importante, mas sua importância é melhor vista quando usamos o CSS. A tag div serve para separar os blocos de código enquanto o atributo id serve para dar uma identificação ao elemento. Repare que a função da div, é poder além de dividir o código em elementos, e também dar um nome a um determinado elemento para criar estilos para cada elemento separadamente. Exemplo:
        <div id='bloco-branco'>
            Elementos do bloco
        </div>
        <div id='bloco-amarelo'>
            Elementos do bloco
        </div>

        Agora poderemos ter o seguinte recurso: Nas tags de link, podemos usar o identificador do elemento para navegar até ele:
        <a href='#bloco-branco'> Bloco branco </a>
        <a href='#bloco-amarelo'> Bloco amarelo </a>


    </body>

</html>

```

Explicação das tags:  
* **title**>**: Traz o título da página, lá na aba do navegador,
* **meta**: Uma tag selfclose, ou seja, ela não necessita o fechamento pois é fechada nela mesmo. Essa tag traz informações relevantes sobre características da página, por exempplo:
* **chartset="UTF-8"**: O charset é um atributo que traz o encoding da página. UTF-8 permite acentos.
* **h1**: É a tag de título. Essa tag varia de h1 até h6. É importante usar de maneira correta pois isso afeta, por exemplo, as pequisas do google sobre o conteúdo da sua página.
* **<!--**  : Essa a estrutura do comentário. O comentário não é exibido pelo navegador, nem processado. Ela precisa ser fechada!
* **b**: Tag para colocar em negrito (bold)
* **strong**: Também da um destaque ao texto, tem função semântica para os buscadores.
* **i**: Itálico
* **em**: Similar ao strong para o itálico. Emphasis 
* **mark**: Marcação de texto.
* **small**: Serve para reduzir o tamanho da letra.
* **sub**: Subescrito.
* **sup**: Sobrescrito.
* **del**: Risca o texto, para indicar que foi excluído,
* **ins**: Sublinha o texto para indicar que foi inserido.
* **br**: Quebra de linha. Uma tag de autofechamento. Não é muito utilizada pois a quebra de linha é feita usando o css.
* 