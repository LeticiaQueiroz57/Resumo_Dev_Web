Conteúdo da prova: 
- [x] Seletores Css 
- [x] URL
- [x] método HTTP
- [x] internet geral (Primeiros Slides)
- [x] Organização HTML
- [x] variáveis em JS
- [x] status 
- [x] true pra false em JS
- [x] Cookies e eventos

## O caminho por trás de uma requisição
- **Modelo Cliente-Servidor:** O cliente requisita serviços e o servidor realiza serviços entre dois elementos. 
	- Necessidade de uma rede (Internet)
	- Necessidade de um protocolo de comunicação (HTTP)
	- Necessidade de um mecanismo de localização (URL)

- **Internet:** Coleção de redes que utilizam protocolos abertos para se comunicar e formar a 'world wide web'
- Intranet: Rede de comunicação restrita a um domínio, como uma rede interna de uma empresa.
- Extranet: Extensão da intranet, que utiliza protocolos abertos para usar a internet como acesso para alguns usuários restritos à intranet.

Caminho de uma requisição:
	- Cliente --> URL --> HTTP --> DNS (Domínio) e TCP (Interface de rede) --> IP (Internet) --> HTTP (Servidor)
	- Após isso, a requisição retorna do servidor para o cliente.

- Componentes cliente-servidor:
	- Browser / Navegador
	- URL: Endereço de recursos na web
	- Servidor Computador que responde a uma requisição
	- Internet Sequência de redes interconectada
	- Protocolos: Padrões para a transmissão de informações entre dois pontos

- URI X URL:
	- URI: Uniform Resource Indentifier
	- URL: Uniform Resource Locator --> É uma URI que consegue chegar até o recurso.

![[Pasted image 20241124133918.png]]
- http: Esquema - Informa o protocolo
- www.impacta.edu.br: Indica o domínio, obedecendo às regras DNS (Domain Name System)
- graduaçao: Path / Caminho até o recurso
- exemplo.html: Recurso

- Sistema de domínios no Brasil: NIC.br

- Cliente: HTML5, CSS3 e JS.
- Servidor: Servidores de aplicação/HTTP, Banco de dados e Linguagem de programação da aplicação.

### Front-end
- **HTML:** HyperText Markup Language
	- Tagged Language
	- As tags definem a apresentação do conteúdo.

- **CSS:** Cascading Style Sheets
	- Formatação e estilização
	- Redução do tamanho das páginas HTML com redução, centralização e organização de definições necessárias.

- **Javascript:** 
	- É dinâmico
	- Eventos

### Back-end
- **Servidores de Aplicação/HTTP:**
	- Burocracia: Quem mandou o pedido, qual a língua, IP
	- Apache, Nginx, ISS
	- Para que o computador que receberá a requisição possa interpretá-la, precisa entender o protocolo HTTP.


### Protocolo HTTP
- Protocolo de comunicação / troca de informações na internet.
- Utilizado para navegaçãoes na internet e integrações de sistemas via web (REST)

- Composição: Requisições e respostas entre cliente e servidor.

- Requisição: Pedido de um recurso.
	- Cabeçalho (Request Headers)
	- Identificador (URL)

- É *stateless*
	- Ciclo de vida baseado na resposta.
	- Após retorno do servidor as informações sobre a requisição são perdidas.
	- É preciso usar recursos para manter informações sobre as requisições como Cookies e Sessão

- *Cookies*: Conjunto de pares chave-valor em texto que ficam armazenados no cliente e são enviadas em cada requisição de um mesmo domínimo
- *Sessão*: Objeto em memória guardando dados específicos sobre a origem da requisição (Dentro do servidor)

- **Métodos HTTP:** 
	- GET: Obter recurso
	- POST: Envia dados
	- DELETE: Remove recurso
	- PUT: Atualiza informações
	- PATCH: Atualiza parte das informações

- Categoria dos métodos HTTP: 
	- *Não alteram estado*: GET, HEAD, CONNECT, OPTIONS, TRACE
	- *Podem alterar estado*: POST, PUT, DELETE, PATCH

- **Resposta do servidor:**
	- Cabeçalho de resposta (Response headers): Metadados da resposta
	- status: Situação da resposta
	- Corpo da resposta: Informações - Recurso pedido ou confiramação de execução

- Status mais comuns:
	- 200: ok
	- 403: Não tem permissão para usar o recurso
	- 404: Não encontrado
	- 405: Método bloqueado no servidor
	- 500: Problema interno 

- Faixas de código de status:
	- 1xx: Informações da requisição (Usados pelo servidor)
	- 2xx: Requisição retornou com sucesso
	- 3xx: Ação que será tomada para término da requisição
	- 4xx: Erro no cliente ao construir e executar a requisição
	- 5xx Erro no servidor ao processar a requisição ou construir a resposta

- HTTPS (HTTP Secure): Adiciona criptografia dos dados
	- Apenas servidor e cliente conseguem ler
	- Protocolo de segurança TLS (Transfer Layer Security) e SSL (Secure Socket Layer)

-- Ler sobre as versões do HTTP (final do slide 1)


## Javascript
Colocando o código js dentro do html:
```html
<script type = "text/javascript" src="arquivo.js">
</script>
```

- Atributos: 
	- type: Informa que o script é JS (Não é obrigatório no HTML5)
	- src: Localização
	- async: Execução assíncrona ativa
	- charset: Codificação
	- defer: Se o script executa apenas quando a páina acabar de carregar.

Ex: 
```html
<script src="arquivo.js" defer async charset="utf-8">
</script>
```

Variáveis:
```js
var x = "abc";
let y = 123;
const z = true;
w = 5.0 //Sem var, let ou const
```
- var: Escopo global
- let: Variáveis com escopo em bloco. Só é acessível no bloco em que foi declarada
- const: Não mudam (Constantes)

- Valor *undefined*: Valor primitivo vazio --> Variável declarada mas não foi atribuído um valor.
- null: Usado para zerar a referência

- Operadores:
	- Aritméticos: +, -, * , /, %, **
	- Lógicos: &&(and), || (or), !(not)
	- Comparação: == , != , === , !== , <= , < , >= , >
	- Incremento e decremento: ++ e --

- === --> Faz a comparação estrita entre os valores (5 e '5' não são iguais)
- == --> Tenta fazer a conversão do tipo para comparar (5 e '5' são iguais e 0 e false também)

- false, 0, "", null, undefined, NaN são sempre tratados como falsos em booleanos
- Coerção de tipos: JS converte valores automaticamente em alguns casos.

Arrays:
```js]
let alunos = new Array(); //Evitar essa forma
let alunos = [];

// Inserir valores
alunos[0] = "Aluno 1";
alunos[1] = "Aluno 2";

let alunos = ["Aluno1","Aluno2"]

let tamanho = alunos.length; // Tamanho do array
```

Arquivos JSON --> Coleçaõ de pares chave-valor:
```js
let objeto1 = new Object();
let objeto2 = {};

// Acessando os valores:
objeto1.atributo
objeto2["atributo"]
```

Funções: 
```js
function func(){
	alert("Hello World!");
}

function func(arg1,arg2) //Argumento
{
	alert(arg1);
	alert(arg2);
}

//Uma função pode ser parâmetro de outra
const minhaFunc = function(a,b,c) {
	return a(c) + b(c)
}
let valor = minhaFuncao(Math.sin,Math.cos,Math.PI);
```

Estrutura de repetição:
```js
// For
for (let i = 0; i < n; i++) {
  console.log(`índice ${i} tem o valor ${x[i]}`);
}

// for in 
let x = [10,20,30]
for (let j in x) {
  console.log(j); //0,1,2
}

// for of
for (let k of x) {
  console.log(k); //10, 20, 30
}
```

Operador ternário:
```js
let x = 15;

let y = x>10 ? "maior" : "não é maior";
```

Método .map --> É usado para criar um array a partir de outro, transformando seus valores de acordo com a função fornecida.
```js
const numeros = [1,2,3,4,5];
const dobros = numeros.map(num => num*2);

console.log(dobros) //[2,4,6,8,10]
```

### Manipulação do DOM 
- DOM = Document Object Model --> Modelo de objetos que representa a página.
- É construído como uma árvore de objetos
Ex:
![[Pasted image 20241124184632.png]]

- Manipular DOM para:
	- Mudar o conteúdo de elementos HTML
	- Mudar estilo de elementos
	- Trabalhar com eventos
	- Adicionar e remover elementos HTML

- Acessando HTML pelo JS:
	- **document.getElementById(id)** --> Pelo ID
	- **document.getElementsByTagName("p")** --> pelo marcador (tag). Retorna TODOS os elementos com nome do argumento, onde cada elemento é acessado na forma de uma array.
	- **document.getElementsByClassName("abc")** --> Retorna todos os elementos com esse atributo(class = "abc") na forma de array.
	- **document.querySelectorAll("p.especial")** --> Retorna todos elementos que satisfaçam o seletor escolhido.
	- **document.querySelector("div.titulo")** --> Retorna o primeiro elemento.
	- **document.forms["form1"];

- Alterando elementos da página:
	- **document.write("...")** --> Escrever no documento HTML
	- **.innerHTML = "..."** --> Mudar conteúdo HTML de um elemento.
	- **.src = "imagem.jpg"** --> Muda o valor de um atributo
```js
document.write("<p>Parágrafos</p>");

document.getElementById("id").innerHTML = "texto";

document.getElementById("id").src = "imagem.jpg";
```

- Modificando o CSS:
	- **elemento.style.propriedade**
Ex:
```js
const e = document.getElementById("id1");
e.style.background = "#F0D";
e.style.margin = "10px";

document.getElementById("id2").style.marginTop = "10px";
```

### Eventos
- São ações que podem ser detectadas pelo JS.
	- .onclick() --> Clique com mouse
	- onmouseover() --> Passar o mouse em cima
	- onmouseout() --> Tirar o mouse de cima
	- onfocus
	- onblur
	- onchange
	- onsubmit

Promises 

fetchAPI

Manipulação do form

## HTML
- Os atributos definem propriedades dos marcadores, como tamanho, nome, identificador, classes CSS e valores.
```HTML
<marcador atributo='valor'>Texto</marcador>
```
- Existem atributos comuns e especificos de um marcador.

- Estrutura básica de uma página HTML:
```html
1<!DOCTYPE html>
2<html>
3  <head>
4<meta charset="UTF-8" />
5<link rel="favicon" type="image/x-icon" href="favicon.ico" />
6<title>Título da Página</title>
7  </head>
8  <body>
9    Conteúdo da página
10  </body>
11</html>
```

- <!DOCTYPE html> --> Indica que o arquivo é um documento HTML.
- 2 --> Inicia o documento HTML
- 3 --> Delimita a área de cabeçalho
	- Engloba marcadores de metadados, scripts, folhas de estilo, título
- 4 --> Codificação dos caracteres
- 5 --> Define o ícone da página (aba do navegador)
- 6 --> Título


- Tipos de marcadores:
	- Marcadores de texto
	- de Multimídia
	- de Estrutura
	- de Divisão

- **Marcadores de texto:**
	- p --> Parágrafo
	- em --> Texto em itálico
	- strong --> Em negrito
	- br --> Quebra de linha
	- h1, h2, h3... --> Vários níveis de título
	- a --> Link(âncora) junto com o atributo href e pode ser referenciada a uma região da página web pelo seu id usando '#'

- **Atributo ID:** Identificador único para cada elemento.
```html
<ul id="lista_1"></ul>
```

- **Marcadores de mídia:**
	- img src="" --> Define uma imagem <img/>
	- Outros atributos: alt (Texto alternativo), width (Largura), height (Altura)

- **Marcadores de mídia:**
	- audio src="" 
	- video src=""

- **Marcadores de estrutura:**
	Listas
	- ul --> Define uma lista não ordenada
	- li --> Define um item da lista
	- ol --> Define uma lista ordenada
	Tabelas
	- table --> Delimita espaço para a tabela
	- tr --> Linha
	- td --> Célula
	- th --> Cabeçalho

- **Marcadores de divisão:**
	- Em bloco: div --> Divisões de página
	- Em linha: span --> Criar regiões (Sua criação não implica em uma nova linha)

Organização HTML
- header, footer, section, article, aside, nav, blockquote

### Formulários
- Tag form --> Campos de coletas de dados (inputs) e etiquetas (labels)
```html
<form>
	<label for="primeiroNome">Primeiro Nome</label>:<br>
	<input type="text" name="primeiroNome" id="primeiroNome"><br>
	<label for="ultimoroNome">Primeiro Nome</label>:<br>
	<input type="text" name="ultimoNome" id="ultimoNome">
</form>
```
![[Pasted image 20241124212958.png]]

- fieldset --> Dividir os campos do formulário em categorias

- Propriedades do formulário:
	- action --> Para onde envia os dados
	- method --> Como deve enviar 
	- enctype --> Como empacotar
	- name --> Nome para identificar o form

- Propriedades dos campos (inputs):
	- type --> Tipo do atributo (text ou checkbox)
	- name --> Nome do atributo
	- value --> Valor inicial
	- readonly --> Apenas leitura
	- disabled --> Campo não pode ser usado
	- etc
## CSS
- CSS = Cascading Style Sheets (Folha de estilo em cascata)
	- Define como os elementos HTML são exibidos

- Como as folhas de estilo podem ser especificadas:
	- Inline: Dentro de um elemento HTML
	- Dentro do elemento head da página HTML
	- Arquivo CSS externo

- **Estilo Inline**: 
	- Apenas para uma tag de uma página específica
	- Propriedade style da tag

```html
<body style="background: yellow;">
  <h1> Olá Mundo! </h1>
</body>
```

- **Folha de estilo interna**: 
	- Dentro do próprio HTML
	- Definido na seção head ou usando a tag style

```html
<head>
   <style type="text/css">
       body {
           background: yellow;
       }
   </style>
</head>
```

- **Folha de estilo externa:**
	- Ideal quando aplicado em várias páginas
	- Muda todo o visual de uma página mudando apenas um arquivo
	- Cada página deve ter um vínculo com a folha de estilo

```html
<head>
   <link rel="stylesheet"
         type="text/css"
         href="meuestilo.css" />
</head>
```

- Atributos do marcador <link>:
	- rel: Relacionamento entre o documento HTML e o documento ligado. (stylesheet)
	- type: Tipo do documento (text/css)
	- href: Localização do arquivo CSS

### Sintaxe CSS
- 3 partes:
	- Seletor: Pode ser um marcador HTML, uma classe ou id
	- propriedade
	- valor
```css
seletor {
	propriedade: valor;
}

body {
	background: yellow;
}
```

- Classe de estilo:
	- Permitem definir diferentes estilos para o mesmo elemento.

```css
p.right {
	text-align: right; /*Alinhado à direita*/
}

p.center {
	text-align:center; /*Alinhado no centro*/
}
```

- Também é possível omitir o nome do elemento no seletor:
```css
.center { text-align: center; }
/* Todo marcador HTML com a classe center será o estilo aplicado.
```

- Um marcador HTML pode receber mais de uma classe no atributo class.

- É possível definir o estilo usando o seletor id definido por um #
```HTML
<p id="para1"> Vermelho </p>
```
```css
p#para1 {
	color: red;
}
```

- Agrupando seletores:
	- Para agrupar é só separar por vírgula.
	- O estilo é aplicado a todos seletores declarados
```css
h1, h2, h3, h4 {
	color:green;
}
```

- Pseudo-classes e pseudo-elementos são usados para adicionar efeitos especiais em alguns seletores
	- São essas: link, active, focus, first-line, before, lang(language), visited, hover, first-letter, first-child, after

- Unidades de tamanho: Especificar tamanho
	- px  (padrão)
	- em
	- rem
	- %

- Os atributos que permitem mudar a forma como o texto é representado:
	- font-family: Fonte
	- font-size: Tamanho da fonte
	- font-weight: Negrito ou não (normal, bold, bolder, lighter)
	- font-style: Itálico ou não (normal, italic, oblique)
	- text-decoration: Sublinhado ou não (none, underline, overline, line-through)
	- text-transform: Capitalização das letras (none, capitalize, uppercase, lowercase)

- text-align (Alinhar): center, left, right ou justify
- text-indent (Indentar): Valores em comprimento ou porcentagem

- border: Aplica borda ao model box
	- width: Largura
	- Style: Tipo
	- Color

- display: Define como diversos elementos são exibidos

Modelo de caixa

display flex e grid

Animações
