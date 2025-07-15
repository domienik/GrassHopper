# GrassHopper
Todos as soluções propostas por Laura Holmes em PT

Dicas e truques

## Alguns Putts

Aqui iremos apenas usar uma função para calcular a diferença entre dois números.

``` Javascript
function diferenca(num1, num2) {
    return num2 - num1;
}

console.log(diferenca(9,10))
```

<p style="font-size: 12px;">Este código acima iria imprimir o número 1.</p>

## Auxiliar da conta

Neste desafio iremos usar uma função auxiliar para incluir impostos.

Aqui iremos dividir a conta de 76 reais para 4 pessoas. Porém o exercício quer que cobramos um imposto de 15%, então primeiramente criamos uma função auxiliar de seta e depois adicionamos na outra função.


``` Javascript
let calculateTax = total => {
    return total * 0.15;
}

function splitBill(total, people) {
    let tax = calculateTax(total);
    total += tax;
    return total / people;
}

console.log(splitBill(76, 4));
```

## Tudo ou nada

O exercício a seguir irá imprimir `false` se algum elemento de uma array for "false."

``` Javascript
function check(results) {
    for (let i of results) {
        if (i === "fail") {
            return "Failed"
        }
    }
    return results.length + " Passed"
}

console.log(check(ranlist));
```

Separei anteriormente 4 listas com valores entre "pass" e "fail", elas estão armazenadas na var `ranlist`

A função vai iterar a lista verificando valor por valor, e ai adicionei uma condicional que verifica se o valor é "fail", caso for, ele retornara "failed".

Caso não for, a função retornará o número de acertos + "passed".

## Variáveis de saída

Em muitas funções, é útil declarar uma variável para a função para depois retornar. Por exemplo:

``` Javascript
function calculateSum(numberArray) {
    let sum = 0;
    for (let num of numberArray) {
        sum += num;
        }
    return sum;
}

let array = [0, 1, 2, 3, 4, 5]
console.log(calculateSum(array))
}
```

<p style="font-size: 12px;">Este código acima iria imprimir o número 15.</p>

Declaramos a variável ``sum`` com antecedência sem valor apenas para manter o código mais conciso e sem erros.


## Saída interna  
  
Aqui precisamos fazer uma função que pega todos os itens de uma array e soma eles em uma variável.  
  
- Primeiro vamos definir a array que vamos usar:  
  
`let array = [1, 2, 7, 5];`  
  
- Após isso criamos nossa função, perceba que antes de fazer o laço iterativo eu criei uma variável vazia para armazenar os futuros valores  
```Javascript
function getSum(numbers) {  
let sum = 0;  
for (let element of numbers) {  
sum += element  
}  
return sum  
}  
  
console.log(getSum(array));  
  ```

<p style="font-size: 12px;">Este código acima iria imprimir o número 15.</p>
## Dados ruins  
  
Esse código a seguir requer que depuramos ele para descobrirmos qual é o erro. A função do código é imprimir quantas letras tem cada palavra no console.  

```Javascript
let array = ["yay", "oh no", "spaguete", "", "cola"];  
  
function getlength(list) {  
for (let element of list) {  
console.log(element)  
console.log(element.length + " Letters")  
}  
}  
  
getlength(array);  
  ```

Repare que adicionamos um `console.log` no meio do laço for para descobrir o que está de errado no código (o problema é que tem uma string vazia). 
  
## Veracidade  
  
Em Javascript, existem 6 tipos de valores booleanos considerados "false"  
  
- o número "0" é um deles  
- uma string vazia, sem caractere algum -> ""  
- false -> o valor booleano padrao false  
- NaN -> erro causado por erros matemáticos tbm retorna false  
- undefined --> um valor de uma variavel antes de ser atribuído algum valor a ela  
- null --> um valor em branco que pode ser atribuído a uma variável  
  
## Números diferentes de zero  
  
Esse código irá percorrer um laço e imprimir no console os números de -3 a 3.  
  
Porém o número 0 não será impresso pois ele tem um valor booleano false.  

 ```Javascript
for (let i = -3; i <= 3; i++) {  
if (i) {  
console.log(i);  
};  
};
```

<p style="font-size: 12px;">Ele irá imprimir seguintes números: -3, -2, -1, 1, 2, 3.</p>


Acesse e atualize




Para acessar um item especifico em uma array, pode ser usada a indexação da array.

por exemplo:

```Javascript
let supplies = ['dive mask', 'water shoes', 'fins', 'scuba tank'];
let fins = supplies[2];
/// supplies[2] acessa o 3° item em supplies.
```

Indexação também pode ser usado para adicionar ou alterar o valor de uma array.

Por exemplo, alterar o 2° item em `supplies` de `'water shoes'` para `'wetsuit'` seria semelhante a:

```Javascript
let supplies = ['dive mask', 'water shoes', 'fins', 'scuba tank'];
supplies[1] = 'wetsuit'
/// supplies[1] acessa o 2° item em supplies e permite a manipulação do seu valor dentro da array.
```

Quando `.length` é anexado em uma array, ele retorna o numero de itens dessa array.

Por exemplo, `[4, 5].length` retornará o número 2, porque a array contém 2 itens.

Para acessar o ultimo item de uma array devemos usar `.length - 1`, pois assim ele irá pegar o número correto da indexação pois toda array começa a indexação com o número 0.

## Dar forma

```JavaScript
let shapes = ["triangle", "square", "circle", "rectangle"];

/// Simples código para imprimir item um a um da array.
for (let item of shapes) {
    console.log(item);
};

/// Aqui é quebra de linha
console.log("");

///Função que vai mudar o ultimo item da array.
function setLastValue(values, newlastvalue) {
    let last = values.length - 1;
    values[last] = newlastvalue;
}

/// Acionamos a função (ela é aplicada)
setLastValue(shapes, "hexagon");

/// Simples código para imprimir item um a um da nova array modificada.
for (let item of shapes) {
    console.log(item);
};
```

## Acessar itens adjacentes

Podemos acessar vizinhos de um índice de uma array usando ``i + 1`` ou ``i - 1``.

```JavaScript
let array = ["a", "b", "c"];
let index = 0;
let vizinhoIndex = index + 1;

array[index];
array[vizinhoIndex]

///Esse código iria selecionar o item de índice "0" e o item de índice "1" dentro da array. Poderíamos posteriormente printar na tela os valores que seriam:

// a, b

```

## Seja meu vizinho

Nesse desafio iremos criar uma função que pega os itens vizinhos do lado da direita numa array.

```JavaScript
///Primeiro criamos uma array com elementos
let array = ["primeiro_item,", "segundo_item", "terceiro_item", "quarto_item", "quinto_item", "sexto_item"];

///Após isso definimos a indexação aleatóriamente
let randomIndex = Math.floor(Math.random()*5);

/// Agora iremos criar uma função que seleciona a indexação vizinha do Index selecionado
function pegueVizinho(array, i) {
	let vizinho = array[i + 1];
	return vizinho;
}

/// Por fim imprimimos na tela o Index selecionado + o seu vizinho.

console.log("O vizinho do " + array[randomIndex] + " é o " + pegueVizinho(array, randomIndex))
```
## Fora dos limites

Podemos usar indexação de vizinhos em um laço, porém devemos ter cuidado com o elemento final. Para não imprimir ``undefined``

```JavaScript
let array = ['a', 'b', 'c', 'd', 'e'];

for (let i = 0; i < array.length; i++) {
	let vizinho = array[i + 1];
	console.log(vizinho)
}
```

O código acima vai sair o erro ``undefined``, pois o elemento de índice 5 não existe.

Para resolver isso, podemos mudar o limite da iteração para -1, isso faria com que o código funcionasse adequadamente.

```JavaScript
let array = ['a', 'b', 'c', 'd', 'e'];

for (let i = 0; i < array.length - 1; i++) {
	let vizinho = array[i + 1];
	console.log(vizinho)
}
```

Agora de o laço verifica os elementos vizinhos antes do índice atual (lado direito), certifica-se de que o laço não começa no número 0, pois isso desencadearia um erro também.

```JavaScript
let array = ['a', 'b', 'c', 'd', 'e'];

for (let i = 1; i < array.length; i++) {
	let vizinho = array[i - 1];
	console.log(vizinho)
}

///Imprimiria no console: a, b, c, d
```

## Strings

Essa próxima etapa ensina passo por passo de como fazer tudo anteriormente porém dessa vez com caracteres de strings:

```JavaScript
let string = "uau"

for (let i = 1; i < string.length; i++) {
	let vizinho = string[i - 1];
	console.log(vizinho)
}

/// O resultado no console seria u, a.
```

## Letra por letra

Esse desafio apenas iremos imprimir todos os caracteres de uma dada string no console.

```JavaScript
function printCaracters(string) {
	for (let i = 0; i < string.length; i++) {
		console.log(string[i]);
	}
}

printCaracters("Grasshopper")
```

## Notação de colchetes com objetos

Preste bastante atenção nessa página!!!

Podemos acessar uma propriedade de um objeto em JS usando notação de ponto:

```JavaScript
let cat = {
	name: "Moo",
	age: 4
}

console.log(cat.name)
/// Isso imprimiria "Moo" no console, pois é o que a propriedade "name" armazena.
```

Porém podemos acessar a mesma propriedade usando a ==notação de colchetes==, para isso precisaríamos apenas colocar o nome da propriedade entre aspas.

```JavaScript
let cat = {
	name: "Moo",
	age: 4
}

console.log(cat['name'])
/// Isso também imprimiria "Moo" no console.
```

Podemos também usar variáveis na notação de colchetes desde que a variavel faça referência a uma string 

```JavaScript
let cat = {
	name: "Moo",
	age: 4
}

let name = "name"
// Imprimimos agora a notação de colchetes, pórem, com a váriavel dentro dos parênteses, repare que a váriavel faz referência a string por isso o código é aceito.
console.log(cat[name])
```

Propriedades também podem ser <mark style="background: #D2B3FFA6;">criadas</mark> usando notação de colchetes.

Por exemplo, vamos criar um objeto vazio chamado animal:

``let animal = {}``

Esse objeto atualmente não contém nenhuma propriedade. Entretanto, a notação de colchetes (bem como a notação de ponto) pode ser usada para criar propriedades. Vamos adicionar uma propriedade chamada <mark style="background: #ABF7F7A6;">type</mark> para animal:

``animal[type] = 'Super Furry';

Esse código acima adicionaria uma propriedade contendo o valor 'Super Furry' para o objeto ``animal``

## Bracketball

```Javascript
/// Esse código abaixo nos selecionará uma palavra aleatória da array

let words = ['cat', 'dog', 'gather', 'juice'];
let ran = Math.floor(Math.random() * words.length);
let word = words[ran];
console.log(word);

/// Esse código abaixo criara um objeto vazio.
let obj = {};

/// Esse código armazenará letra por letra no nosso objeto.

for (let i = 0; i < word.length; i++) {
    /// Primeiro armazenamos cada letra na váriavel "letra"
    let letter = word[i];
    /// Após isso criamos uma propriedade com o valor de "i" para cada iteração do nosso laço
    obj[letter] = i;
}

/// Agora imprimimos o nosso objeto usando o laço for, iremos imprimir tanto as propriedades quanto seus valores.

for (let element in obj) {
    console.log(element + " : " + obj[element])
```

Esse código acima selecionara um item aleatória da array "words" e depois será transformado em um objeto e impresso no console.

<mark style="background: #ABF7F7A6;">Importante:</mark> "Lembre-se que sempre que estamos usando ``obj[letter] = i``, estamos criando uma nova propriedade com um valor dentro dela no objeto.




Divisão de problemas


## A palavra mais longa

Neste desafio, iremos comparar duas palavras e retornar a mais longa de ambas.

```JavaScript
/// Primeiro criamos uma função com dois parâmetros
function getLonger(word1, word2) {
    /// Após isso verificamos qual dos parâmetros tem um maior comprimento
    if (word1.length > word2.length) {
        return word1
    } else {
        return word2
    }
}

/// Por fim chamamos a função e colocamos duas palavras diferentes nos argumentos.
console.log(getLonger("Minecraft", "Roblox"))
```

<p style="font-size: 12px;">O resultado acima seria: Minecraft
</p>
## Café da manhã ou almoço

Neste desafio, iremos selecionar a array com mais itens entre duas escolhas, no caso, seriam dois cardápios de um restaurante no período da manha e da tarde.

```JavaScript
/// Criei duas arrays com uma quantidade de strings diferentes

let cardapio_manha = ["churros", "Panquecas", "Suco", "Ovo", "Pão"];
let cardapio_tarde = ["Feijoada", "Arroz", "Feijão", "Bife", "Legumes", "Salada"];

/// Inicie a função que vai analisar ambas as arrays e retornar a mim a com mais itens
function compararMaior(array1, array2) {
    if (array1.length > array2.length) {
        return array1
    } else {
        return array2
    }
}

console.log(compararMaior(cardapio_manha, cardapio_tarde))
```

<p style="font-size: 12px;">O resultado acima seria: [ 'Feijoada', 'Arroz', 'Feijão', 'Bife', 'Legumes', 'Salada' ]
.</p>

Repare que o método ``length`` também funciona com arrays e pode ser usado dentro de condicionais.

## Procurando informações importantes

<mark style="background: #ABF7F7A6;">Pensamento computacional</mark> trata-se de enquadrar problemas do mundo real para que os computadores possam resolvê-los e é uma maneira útil de chegar a uma solução ao enfrentar um desafio.

## Tamanho da tela

Maria acabou de comprar um novo computador com monitor 4k e ela se pergunta quantos pixels tem.

```javascript
/// Apneas criamos uma função que multiplica a largura pela altura.

function totalPixels(a, b) {
    let total = a * b;
    return total
}

// Depois inserimos os valores nos argumentos da função.
console.log(totalPixels(1920, 3240))
```

## Hora do Ingresso

```JavaScript
/// Aqui está uma array com objetos contendo nomes e idades de alunos

let estudantes = [
  { nome: 'Ana', idade: 12 },
  { nome: 'Pedro', idade: 10 },
  { nome: 'Maria', idade: 14 },
  { nome: 'JoÃ£o', idade: 8 },
  { nome: 'Carla', idade: 13 },
  { nome: 'Lucas', idade: 11 },
  { nome: 'Julia', idade: 9 },
  { nome: 'Matheus', idade: 15 },
  { nome: 'Beatriz', idade: 12 },
  { nome: 'Gabriel', idade: 10 },
  { nome: 'Larissa', idade: 14 },
  { nome: 'Rafael', idade: 8 },
  { nome: 'Isabela', idade: 13 },
  { nome: 'Eduardo', idade: 11 },
  { nome: 'Amanda', idade: 9 },
  { nome: 'Fernando', idade: 15 },
  { nome: 'Camila', idade: 12 },
  { nome: 'Felipe', idade: 10 },
  { nome: 'VitÃ³ria', idade: 14 },
  { nome: 'Guilherme', idade: 8 },
];

///agora iremos criar uma função que itera sobre a array, e os itens que ele vai acessar serão todos objetos.

function getOlderStudents(lista) {
	/// O laço for "of" nao pode ser usado em objetos!!!
	for (let estudante of lista) {
		/// Para cada estudante da lista que tiver + de 12 anos, a função nos informará no console.
		if (estudante.idade > 12) {
			console.log(estudante.nome)
		}
	}
}

getOlderStudents(estudantes)
```

## Modelagem de informação

No pensamento computacional existem várias formas de resolver problemas.

Duas famosas delas seriam Abstração e Decomposição.

Enquanto Abstração olha o problema de maneira geral focando nos pontos importantes, a decomposição diminui o problema em etapas pequenas.

Um exemplo de Decomposição seria criar várias funções e reutilizar em uma nova função, enquanto na Abstração seria olhar para o código ignorando elementos irrelevantes complexos e focando no essencial. Porém a solução da abstração seria direta.

## Auxiliar de palavras cruzadas

Esse desafio requer que criemos uma função que retorne a última letra de uma palavra.

```Javascript
/// Primeiro definimos uma array com strings aleatórias  
array = ["leao", "macaco", "esquilo", "tamandua", "elefante"];

/// Após isso definimos pegamos uma string aleatória da array.  
let randomWord = array[Math.floor(Math.random()*array.length)];

///Printamos essa palavra.  
console.log(randomWord);

/// Agora criamos uma função que captura a ultima letra de uma palavra e retorna ela de volta a onde foi chamada.  
function getLastLetter(word) {  
let last = word[word.length - 1];  
return last;  
};

console.log(getLastLetter(randomWord));
```

## Verificador de palavras

Este exercício requer que comparemos duas palavras juntas e, ver se ela se encaixa em dado espaço.

Regras:

- Ambas strings devem ter o mesmo número de caracteres
- As strings só podem ter os caracteres diferentes no número de indexação que está o outro caractere, que seria``"-"`` .
- Se tiver um caractere diferente da outra string sendo comparada no lugar onde não há traço, então a string deve retornar false.

``` Javascript 
/// Aqui definimos uma string aleatória em uma array de 3 strings.
let words = ["heat", "last", "clat"];
let random = Math.floor(Math.random()*words.length);
let word = words[random];

/// Aqui iremos comparar se ambas strings possuem o mesmo length.
function compareWords(string, word) {
	if (word.length !== string.length) {
		return false
	}
	/// Aqui iremos fazer um laço for que ira comparar se o priemiro caractere é diferente de "-", se for ele retorna true no teste, 
	
	/// ele também testa de o caractere atual é diferente do outro caractere da outra string, caso for, ele retorna true
	
	/// por fim se ambos testes retornarem "true", o teste total retornara false
	for (let i = 0; i < word.length; i++) {
		if (string[i] !== "-" && word[i] !== string[i]) {
			return false
		}
	}
	return true
}



console.log(compareWords("-a-t", word));
 ```

## Decompor Problema

- Atenção, o desafio é criar uma função que recebe como argumento uma palavra gigante (stringsequence), e retorna a maior subsequência dessa strings pesquisando dentro da array de strings (dictionary).


<img width="1043" height="606" alt="image" src="https://github.com/user-attachments/assets/a76ac8bf-4186-4601-abd6-dadeca280468" />

## A palavra mais longa

Neste exercício iremos comparar uma array de palavras e retornar a palavra com mais caracteres dentro dela.

Iremos precisar de um laço for e uma condicional para fazer isso.

```javascript
///Primeiro definimos os valores da array(dictionary)
let stringsequence = 'abppplee';

let dictionary = ["apple", "ale", "able"];

///Após isso criamos a função que irá iterar e passar por uma condicional.
function findLongest(dictionary) {
   //Note que precisamos criar uma variável do tipo string vazia para armazenar o maior valor atual da indexação.
   let longest = "";  
    for (word of dictionary) {  
        if (word.length > longest.length) {  
            longest = word;  
            }  
        }  
    return longest  
    }  
     
console.log(findLongest(dictionary));
```

A cada iteração, a variável "longest" vai recebendo o maior valor que foi aprovado pela condicional anterior. Assim obtemos a palavra "Apple".

## Cartografia de strings

Esse exercício requer que criemos um objeto utilizando uma string.
Basicamente será uma mapa para ajudar em um próximo código.

```JavaScript
/// Primeiro definimos as palavras que iremos usar como argumentos (elas serao selecionadas de forma aleatória)  
let words = ["cat", "banana", "plane"];  
let random = Math.floor(Math.random()*words.length);  
let randomWord = words[random];  
console.log(randomWord)

///Ao obter a string, criamos uma função que transformará a string em um objeto.

function makeMap(word) {  
   let map = {};  
    for (let i = 0; i < word.length; i++) {  
    let wIn = word[i];  
    if (map[wIn]) {  
        map[wIn].push(i);  
        } else {  
        map[wIn] = [i]  
        }  
    }  
    return map  
}

///Armazenamos então nosso objeto em uma variável

let stringMap = makeMap(randomWord);

///Imprimimos no console usando o "laço for in"  
for (let element in stringMap) {  
    console.log(element + " : " + stringMap[element])  
}
```

- Ao declarar a função criamos uma variável com um objeto vazio. (Ele será útil para armazenar os futuros valores).

``map = {0}``

- Após isso criamos um ``laço for`` e armazenamos cada iteração (caractere) da string em uma variável chamada ``wIn``

``for (let i = 0; i < word.length; i++) { 
   `` let wIn = word[i];``

- Agora iremos entrar para parte mais complexa, a condicional, ela nos irá dizer aonde o código deve armazenar as propriedades e valores no mapa.
- Verificamos usando a condicional ``if``, e dentro dessa condicional ela testa se já existe uma propriedade com o mesmo nome da indexação atual, se existir ele é inserido dentro da array da propriedade usando o método ``push``

```javascript
if (map[wIn]) {  
        map[wIn].push(i);  
```

- Agora se essa propriedade não existir no objeto, iremos criar uma com o nome do caractere atual na iteração, e o valor dessa propriedade será o próprio índice dela mesma dentro de uma array.

```javascript
} else {  
        map[wIn] = [i]  
        }  
```

- Após isso conseguimos extrair o objeto da nossa função usando o comando ``return``
- após extrair o objeto, devemos imprimir ele no console, para isso usaremos o ``laço for in`` que irá nos entregar cada propriedade do objeto, porém se quisermos o valor dessas propriedades teremos que usar outro comando.
- como armazenamos nosso objeto dentro da variável ``stringMap``, para imprimir os valores das propriedades podemos usar ``stringMap[element]``

```javascript
///Imprimimos no console usando o "laço for in"
for (let element in stringMap) {
    console.log(element + " : " + stringMap[element])
}
```

Finalmente, no console teremos:

```
banana
b : 0
a : 1,3,5
n : 2,4
```

- Notas importantes: caso não exista uma propriedade identificada na condicional igual mostrado no primeiro if: 
```javascript
if (map[wIn])
```

O resultado da ``if`` será automaticamente o ==número zero==. E o número 0 será considerada como o booleano ``false``

- Por fim um curto código que criei para estudarmos melhor as funcionalidades dos objetos:

```javascript
let meuObjeto = {
  propriedade1: "Valor1",
  propriedade2: 42,
  propriedade3: true
};

meuObjeto['panquecas'] = [3];

meuObjeto['panquecas'].push(2, 1, 0)

console.log(meuObjeto['panquecas'])

for (let element in meuObjeto) {
	console.log(element + " : " + meuObjeto[element])
};
```

Console:

```

[
  3,
  2,
  1,
  0
]
propriedade1 : Valor1
propriedade2 : 42
propriedade3 : true
panquecas : 3,2,1,0
```

## Pesquisa de letra

Neste desafio iremos comparar uma string com um objeto e conferir se todos os caracteres da string estão no objeto como propriedades.

```JavaScript
//Primeiro iremos criar uma string que virou um objeto

// iremos usar a subfunção "makeMap" da cartografia de strings.

  

let stringSequence = {

c : [0],

a : [1, 8],

r : [2],

t : [3, 7],

i : [4, 8],

f : [5],

l : [9]

}

//Agora definimos a palvra que queremos saber se é uma subsequencia.

let dictionaryWord = "car";
///A função vai comparar se cada caractere existe no objeto, caso não exista, a função já retorna false.

function testWords(word, map) {

for (let element of word) {

if (map[element]) {

} else {

return false

}

}

///Se todos caracteres aparecem nas propriedades do objeto então o código pode retornar true

return true

};

console.log(testWords(dictionaryWord, stringSequence));


```

## Subsequência

Aqui iremos incrementar uma etapa no código que fizemos anteriormente para verificar se existem números repetidos, já que, ele já verificava se existia ou não todos os respectivos caracteres da subsequência na ``stringSequence``.

- Vamos imaginar primeiramente que temos uma dada ``stringSequence``

| C | A | R | T | I | F | I | T | A | L |
| ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- |
| 0 | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 |

- Queremos verificar se a palavra ``AFTA`` é uma subsequência dessa string.
- Para isso é importante transformar a ``stringSequence`` em um dicionário.

| C | 0 |
| ---- | ---- |
| A | 1, 8 |
| R | 2 |
| T | 3, 7 |
| I | 4, 6 |
| F | 5 |
| L | 9 |
- Agora que temos nosso mapa, ficará mais fácil de visualizar nosso procedimento para encontrar caracteres repetidos.

- A função ``findNextIndex()`` vai ter a seguinte codificação:

```javascript
findNextIndex(array, minIndex) {
for (var element of array) {
if (element >= minIndex) {
return element + 1;
}
}
return false
}
```

- A função em resumo ``findNextIndex()`` vai verificar se cada caractere sem repetições da palavra ``afta`` esteja dentro da palavra da ``stringSequence``.

<img width="984" height="535" alt="image" src="https://github.com/user-attachments/assets/9af5d8dd-c444-4acd-8a91-bb13d6301430" />

 A função então vai verificar cada array da palavra <mark style="background: #ABF7F7A6;">mapeada</mark> ``cartifical`` de acordo com os caracteres da string do dictionary.
- Por exemplo, acima demos a subsequência "AFTA", então iriamos verificar 3 possíveis arrays dentro do objeto ``stringSequence``, essas arrays seriam:

| A | 1, 8 |
| ---- | ---- |
| F | 5 |
| T | 3, 7 |
- No final da subfunção ``findNextIndex``, nosso código iria retornar ``minIndex === 9``, o que faria com que a função aprovasse que a palavra verificada a ser uma subsequência fosse aprovada com ``true``.

```javascript

// Primeiro iremos criar uma string que virou um objeto

// iremos usar a subfunção "makeMap" da cartografia de strings.

  

let stringSequence = {

c : [0],

a : [1, 8],

r : [2],

t : [3, 7],

i : [4, 8],

f : [5],

l : [9]

}

//Agora definimos a palvra que queremos saber se é uma subsequencia.

let dictionaryWord = "car";

// Criamos agora a função minIndex para saber se a palavra não possui caracteres repetidos.

findNextIndex(array, minIndex) {
for (var element of array) {
if (element >= minIndex) {
return element + 1;
}
}
return false
}



///A função vai comparar se cada caractere existe no objeto, caso não exista, a função já retorna false.

//Perceba que agora iremos implementar a função, portanto é recomendavél já usarmos com antecedência um nome novo para ela, seu nome novo será: getSubsequence.

function getSubsequence(word, map) {
/// Perceba que iremos definir anteriormente o minIndex como seu valor atual de zero. Isso será util apenas para incrementarmos posteriormente
minIndex = 0;

for (let element of word) {

if (map[element]) {
/// aqui iremos implementar a função "findNextIndex".
/// map[element] vai acessar dentro do nosso mapa, a array que contem os indices dos caracteres que vamos verificar.
minIndex = findNextIndex(map[element], minIndex)
/// Aqui caso a função não retorne nenhum numero e apenas o ``false``, já saberemos que a palavra em questão não é uma subSequencia.
if (minIndex === false) {
return false
}
} else {

return false

}

}

///Se todos caracteres aparecem nas propriedades do objeto então o código pode retornar true

return true

};

console.log(testWords(dictionaryWord, stringSequence));
```

## Juntando tudo

``` javascript

let dictionaryWords = ["ton", "maton", "matmo", "mon", "on", "mato", "matoon", "aton", "llkkkkkkkkk", "matmioc"];

/// achar subsequencia mais longa

function getLongest(words) {  
let longestWord = "";  
for (let word of words) {  
if (word.length > longestWord.length) {  
longestWord = word;  
}  
}  
return longestWord;  
}  

/// retornar mapa

let stringSequence = 'matoatomico'  

console.log(stringSequence)

function mapString(string) {  
let map = {};  
for (let i = 0; i < string.length; i++) {  
let letter = string[i];  
if (map[letter]) {  
map[letter].push(i);  
} else {  
map[letter] = [i];  
}  
}  
return map  
}

/// Encontrar próximo index

function findNextIndex(array, minIndex) {  
for (let element of array) {  
if (element >= minIndex) {  
return element + 1  
}  
}  
return false  
}

///Função para verificar se a string é uma subsequencia

function isSubsequence(word, map) {  
minIndex = 0;  
for (let car of word) {  
if (map[car]) {  
minIndex = findNextIndex(map[car], minIndex)  
  if (minIndex === false) {  
  return false  
  }  
} else {  
return false  
}  
}  
return true  
}

/// Juntando tudo

function all(string, array) {

let subSequences = [];

let map = mapString(string);

for (let word of array) {  
if (isSubsequence(word, map)) {  
subSequences.push(word)  
}  
}

let longest = getLongest(subSequences)

return longest  
}

console.log(all(stringSequence, dictionaryWords))



```


o resultado então:

<img width="283" height="100" alt="image" src="https://github.com/user-attachments/assets/cd62b7a1-a8f8-485a-bc53-1d71dcc6f43c" />

- Ao juntar todos os elementos, precisamos começar pensando em criar uma função.
- Nessa função vão ter 2 parâmetros: ``stringSequence`` e ``array de strings do dicionario``, podemos simplificar apenas chamando de ``string`` e ``array``.
- Então definimos uma array vazia na primeira linha de código dentro da nossa função para armazenar as futuras subsequências: ``let subSequences = [];``
- Depois disso criamos a variável ``map`` e iremos armazenar a ``stringSequence`` transformada em um ``objeto`` pela função ``mapString``.
- Após isso, iremos percorrer todas as strings dentro do ``array de strings do dicionario`` e conferir quais strings são ou não uma subsequência, caso forem, serão armazenadas na variável criada anteriormente ``subSequences``, para isso iremos usar um laço ``for`` e um ``if statment``.
- Por fim usamos a função ``getLongest`` e passamos a array que criamos de subsequências como argumento para achar a maior subsequência de todas.









