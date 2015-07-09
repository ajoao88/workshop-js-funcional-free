![Logo da Webschool e do Curso JS Funcional](https://cldup.com/bn_CJFPZce-2000x2000.png)

#JS Funcional

Possuimos 2 grandes paradigmas de programação: 

- funcional
- imperativo

A Funcional é a mais antiga, sua primeira linguagem foi criada em 1955 (IPL) e posteriomente a mais popular LISP foi criada em 1958. Fortran e COBOL foram criadas respectivamentes em 1956 e 1959, são imperativas.

[Explicar como ira funcionar o curso]


##O que é programação funcional?

Programação funcional é um paradigma de programação que trata a computação como uma avaliação de funções matemáticas e evita estados ou dados mutáveis. Utiliza a aplicação de funções, em contraste da programação imperativa, que enfatiza mudanças no estado do programa.

Uma função pode ter ou não ter parâmetros e um simples valor de retorno. Os parâmetros são os valores de entrada da função, e o valor de retorno é o resultado da função. A definição de uma função descreve como a função será avaliada em termos de outras funções.

Assim como na orientação a objetos a menor parte de um sistema é um objeto, você pode atribuir objetos a variáveis, pode passá-los por parâmetro e ter métodos retornando objetos, na programação funcional, a menor parte do seu sistema é uma função.

Por exemplo, a função f(x) = x^2 + 5 é definida utilizando funções de exponenciação e adição. Do mesmo modo, a linguagem deve oferecer funções básicas que não requerem definições adicionais.

[ESCREVER MAIS SOBRE]

###Por que usar programação funcional?

####Onde usar?

####Quem está usando?

###Linguagens funcionais

Hoje em dia com o aumento na necessidade de sistemas concorrentes as linguagens funcionais estão voltando para o mercado comercial. Vemos muito grandes empresas usares: Erlang, Haskell, Scala, etc.

Linguagens mais conhecidas:

- Erlang
- F#
- Haskell
- Lisp
- OCaml
- R
- Scala
- Scheme

LISP introduziu a maioria das características hoje encontradas nas modernas linguagens de programação funcional. Scheme foi uma tentativa posterior de simplificar e melhorar LISP. Haskell foi lançada no fim dos anos 1980 numa tentativa de juntar muitas ideias na pesquisa de programação funcional.

###Lambda
O cálculo lambda pode ser considerado a primeira linguagem de programação funcional, embora nunca tenha sido projetada para ser realmente executada em um computador. É um modelo de computação projetado por [Alonzo Church](https://pt.wikipedia.org/wiki/Alonzo_Church) nos anos 1930 que oferece um modo muito formal de descrever um cálculo de uma função.

A ideia de Church era usar a noção de “processo” ou “transformação” (função) como essencial para fundamentar a matemática, ao invés da noção de conjunto de Cantor. O lambda cálculo não deu muito certo para isso na época, mas acabou sendo importante em outra questão do tempo: a busca pela definição formal do que vem a ser um procedimento efetivo. Em termos atuais, diríamos que essa busca tentava definir formalmente o que é “computação”.

(A ideia de usar o conceito de transformação como central na matemática retornou na segunda metade do século XX através da Teoria das Categorias, mas isso é outra história.)

####Notação

Essa notação pode parecer um pouco confusa no início, mas veremos que não é nenhum bicho de sete cabeças.

![](https://cldup.com/gov3Q0J67O-1200x1200.jpeg)

*Queria ter colocado o Tiamat,  mas ele tem 5 cabeças apenas :(*

```
(λx.x) y
```

Basicamente (λx.x) tem como resultado a expressão y.

Onde (E = x, F = y), guardem bem essa informação E é o resultado onde x é substituído pela expressão[função?] F.

Agora se F (λx.x)(λx.y) tem como resultado (λx.y), então (E = x, F = (λx.y)). E é só isso, substituição textual.

A sintaxe das expressões-lambda é determinada por duas operações: abstração e aplicação (sendo que a aplicação envolve uma operação de substituição chamada conversão-β). Uma expressão-lambda pode ser uma variável, uma abstração de uma expressão, ou uma aplicação de duas expressões:

- Variáveis: x, y, z, um conjunto qualquer de nomes de variáveis.
- Abstrações: dada uma expressão-lambda E, podemos formar uma abstração de E usando λ + variável + ‘.’ + E. Por exemplo: λx.x
- Aplicações: dadas duas expressões-lambda E e F, a expressão da aplicação é formada pela justaposição de uma ao lado da outra: E F

A conversão-β é a regra de substituição que diz como a aplicação deve funcionar. 

Analisemos essa expressão `(λ x. + x 1) 4` a conversão-β é:

```
+ 4 1
```

**Fácil não?**

![meme jackie chan](https://cldup.com/EZEjcYdurI-1200x1200.jpeg)

Zuerinha vou explicar é claro, vamos lá:

```
(λ x. + x 1) 4 → + 4 1
// (λ"variável"."E") "F"
// variável = x
// E = + x 1
// F = 4
```

Nesse caso a conversão-β resulta na expressão[?] `+ 4 1` onde substituímos a variável `x` da função[?] `E` pelo valor de `F`, agora ficou fácil né?

![meme meme-yeah-we-will-sse-about-that](https://cldup.com/9dhGMxmsQW-1200x1200.jpeg)


[Falar mais]

###Teoria das Categorias

A teoria das categorias é uma teoria matemática que trata de forma abstrata das estruturas matemáticas e dos relacionamentos entre elas. Ela pode ser entendida como um "jogo de setas", em que se abstrai o significado das construções.

As aplicações da teoria das categorias estendem-se por áreas como álgebra, teoria da recursividade, semântica formal, etc.

Uma única operação exigida em uma categoria é a **composição**. Ouviremos falar muito disso ainda.

- uma classe de objetos a, b, c, ...
- para cada par de objetos a,b, uma classe de morfismos ou setas de a para b, denotados por f:a -> b (e neste caso se diz que a é o objeto origem e b é o objeto destino da seta);
- para cada objeto a, um morfismo chamado identidade em a, id_a:a\rightarrow a que tem origem e destino em a;
- uma operação de composição que associa a cada par de morfismos.

![imagem de uma função gigante de matemática apenas porque a zuera não tem limites](https://cldup.com/DgAjKvXx7W-1200x1200.png)

####Functor

> A functor is a function, given a value and a function, unwraps the values to get to its inner value(s), calls the given function with the inner value(s), wraps the returned values in a new structure, and returns the new structure.

Vamos entender parte por parte:

- *functor* é uma função que irá receber um valor e uma função
- desembrulha? os valores para chegar a seu(s) valor(es) interno(s)
- chama a função dada com o(s) valor(es) interno(s)
- envolve os valores devolvidos em uma nova estrutura
- e retorna a nova estrutura.

![meme realy?](https://cldup.com/ERM06kh3ki-2000x2000.jpeg)

Sim eu sei que é basicamente a tradução do texto acima, bom então vamos aqo que interessa, *códigoooooooooooo*:

```js
function plus1(value) {
    return value + 1
};

function plus2(value) {
    return value + 2
};
```

Criamos duas funções simples, `plus1` adiciona 1 ao `value` e `plus2` adiciona 2, agora vamos escrever uma função ara que possamos usar qualquer uma dessas funções como e quando necessário:

```js
function F(value, fn) {
    return fn(value)
};

F(1, plus1); // 2
```

Essa função irá funcionar enquanto passarmos um inteiro, vamos tentar passar um *Array*:

```js
F([1, 2, 3], plus1); // '1,2,31'
```

![meme shit happens](https://cldup.com/g-9ZGuT22B-1200x1200.jpeg)

E que bela **merda** aconteceu hein, passamos um *Array*, somamos com um inteiro e recebos uma *String*!!!

![meme pode isso Arnaldo?](https://cldup.com/5sahDi-dC0-1200x1200.jpeg)

Nós queremos que F faça o trabalho "do jeito certo" e o "jeito certo" é manter a estrutura durante a operação. Mas o que significa "manter a estrutura"?

Significa que nossa função precisa "desembrulhar?" o *Array* passado e pegar seus elementos. Depois precisa chamar a função passada para cada elemento. Então "embrulhar?" os valores retornados em um novo *Array* e retorná-lo.

Isso não te lembra nenhuma funçãozinha não?

![meme pensando](https://cldup.com/bYyOR0OQpS-1200x1200.png)

SIM! A função `map` é um *functor*!

```js
[1, 2, 3].map(plus1); // [2, 3, 4]
```

No caso do Jasvascript, *filter* é um *functor* porque retorna um *Array*, entretando o *forEach* não é pois retorna *undefined*, ou seja, ele não mantém a estrutura.

*Functors* são definidos como "[homomorfismos](https://pt.wikipedia.org/wiki/Homomorfismo) entre categorias", vamos entender melhor esse significado:

- homo = mesmo, igual
- morfismos = funções que mantém estrutura
- categoria = tipo

De acordo com a teoria, a função `F` é um *functor* quando as duas funções comuns combináveis f e g, como no exemplo abaixo:

```
F(f . g) = F(f) . F(g)
```

Onde `.` indicam composição, ou seja, *functors* precisam preservar a composição.

#####Array Functor

Como disse que o `map` é um *functor* então vamos provar isso.

```js
function compose(f, g) {
    return function(x) {return f(g(x))}
}
```

Fazer composição de funções é criar uma chamada de um conjunto de funções, chamando a função seguinte, com resultados da função anterior. Note que a nossa função de composição acima funciona da direita para a esquerda. g é chamado pela primeira vez, em seguida, f.

```js
[1, 2, 3].map(compose(plus1, plus2)) // [ 4, 5, 6 ]

```

É o mesmo que compor usando 2 funções `map`:

```js
[1, 2, 3].map(plus2).map(plus1) // [ 4, 5, 6 ]
```

[Quando mostrar a composição]
Isso lembra alguma coisa pra você? Bom logo logo verá um exemplo mais conhecido.

[ESCREVER MAIS SOBRE]

###Por que JavaScript é funcional?

##Funções

No JavaScript uma função nada mais é que um objeto que possui atributos como:

- arguments
- name
- length

E funções importantes como:

- apply
- call

Para criarmos uma função no JavaScript é muito simples, como já vimos anteriormente, precisamos apenas utilizar a palavra `function`:

![Homer fazendo Doh](https://cldup.com/CVvUx6Uswo.gif)

```js
function add(a, b) {
  return a + b;
};
```

Podemos usar um exemplo mais simples ainda, uma função que duplica *Strings*:

```js
var repeat = function(s) {
  return s + s;
};

repeat('Na');
// NaNA
```

Então se chamamos apenas a função `repeat` dessa forma, teremos um resultado indesejado.

![Meme WAT](https://cldup.com/BOagKEB49C.gif)

Sim meu caro aluno, prete atenção no exemplo abaixo:

```js
repeat(10);
// 4
```

Aí encontramos o problema!

Nesse caso ele não está mais repetindo a *String* como desejado inicialmente, agora ela está multiplicando o valor por 2 caso seja um *Number*. Isso porque não temos um contrato com uma função que retorne apenas *Strings*. Para resolver esse problema é fácil, criamos essa função abaixo:

```js
var str = function(s) {
  if(typeof s !== 'string') {
    throw new TypeError('Expected a string');
  }
  else {
    return s;
  }
}
```

Agora você passa uma *String* para a função, como valor de entrada, e espera-se que seu retorno também seja uma *String*, como valor de saída.

Refatorando nossa função `repeat`:

```js
var repeat = function(s) {
  var s = str(s)
  return s + s;
};

repeat('Na');
// NaNA
repeat(1)
// TypeError: Expected a string
```


[EXPLICAR MAIS]

###Função anônima

###First-class Functions

No JavaScript a função é first-class citizen, assim como objeto, entidade ou valor, porque ela suporta todas as operações comuns às outras entidades.

![Hein!?](https://cldup.com/Oul_G5l7FB.gif)

Essas operações incluem:

- assinada a uma variável
- retornada de uma função
- ser passada por parâmetro

Vamos mostrar cada uma dessas operações com o exemplo anterior:

```js
// assinada a uma variável
var add = function (a, b) {
  return a + b;
}

add(400, 20); // 420
```

```js
// retornada de uma função
function adder(a) {
  return function(b) {
    return a + b;
  }
}

var _add =  adder(20);
_add(400) // 420
_add(646) // 666
```

Podemos melhorar esse exemplo e criarmos a função de multiplicar.

```js
// retornada de uma função
function multiply(a) {
  var sum = 0;
  return function(b) {
    sum = b;
    for(i=1; i<a; i++){
      sum += b;
    }
    return sum;
  };
}

multiply(2)(333); //666
```

Você deve ter percebido que podemos utilizar 2 formas de passagem de parâmetros, correto?

Vamos entender melhor como isso funciona, vamos analisar o exemplo coma soma por sem mais simples, porém desta vez vendo os valores dos parâmetros.

```js
// retornada de uma função
function adder(a) {
  console.log('a', a);
  return function(b) {
    console.log('b', b);
    return a + b;
  }
}

var _add =  adder(20);
_add(400) // 420
_add(646) // 666
```

Na linha:

```js
var _add =  adder(20);
// a 20
```

Basicamente a função está apenas instanciando o valor de `a` e retornando a função com a soma já usando o `a`, falaremos mais disso posteriormente, logo `_add` não recebe o valor de `a`, mas sim a funçao da soma:

```js
function adder(a) {
  var a = a; // 20
  return function(b) {
    return a + b;
  }
}
```

Depois quando chamamos a função `_add` passando `400` como parâmetro 
```js
_add(400)
// b 420
// 440
```

Estamos passando o `400` para a função que recebe `b` desse jeito retornando o valor da nossa soma:

```js
function(b) { //400
  return a + b; //420
}
```

Para entender melhor como isso acontece falarei mais adiante sobre *closures*.

###High-order function

- recebe uma ou mais funções como parâmetro
- retorna uma função

###Closures

###Currying

###Monads

> "As monads vieram para resolver um problema que não tínhamos antes." - Douglas Crockford

![](https://cldup.com/S5tC18Ab_x-2000x2000.jpeg)

Normalmente esse assunto *Monads* é tratado com certa "obscuridade" para quem não está familiarizado com Teoria das Categorias, mas bem na verdade ela só parece complexa na matemática.

Na verdade *Monad* é um padrão de design usado para descrever computações como um série de passos. Elas são extensivamente usadas em linguagens de programação puramente funcional para gerenciar efeitos colaterais, mas também são usadas em linguagens multiparadigmas para controlar complexidade.

*Monad* "empacotam" tipos dando-les um comportamento adicional. Entenderemos isso melhor com código na sequência, porém antes precisamos conhecer quais são os componentes de uma *monad*:

- unit: função que "envolve" um valor em um tipo aceitado pelas funções compostas
- bind: função que transforma qualquer função para que aceite o mesmo tipo que ela retorna, deixando-a pronta para composição

> Nota: A função bind function não é a mesma que a função Function.prototype.bind  Essa última é nativa do ES5 e é usada para criar uma série de funções ou funções parcialmente aplicadas com esse valor vinculado.

####Leis da *monad*

Uma *monad* deve obedecer as seguintes leis para ser válida:

1. bind(unit(x), f) === f(x)
2. bind(monad, unit) === monad
3. bind(bind(monad, f), g) === bind(monad, function(x) { return bind(f(x), g); })

Vamos começar com um [exemplo de *monad* do Douglas Crockford](https://gist.github.com/JackNova/4339141):
[COLOCAR LINK OFICIAL DO ARTIGO]

```js
function MONAD() {
  return function unit(value) {
    var monad = Object.create(null);
    monad.bind = function (func) {
      return func(value);
    };
    return monad;
  };
}
```

Vamos entender como esse código funciona.

1. a função `MONAD` retorna a função `unit` passando `value` como parâmetro
2. cria uma `monad` que não herda nada
3. adiciona o método `bind` na *monad* que recebe uma função `func` como parâmetro 
4. e retorna a chamada dessa função `func` 
5. passando `value` para ela que foi passada na função construtora `unit`
6. retorna a *monad*

A *monad* mais simples é a identidade, a qual não adiciona nenhuma informação ao valor, o valor é passado para a função `unit` que passará para as funções ligadas.

```js
var identity = MONAD();
var monad = identity("JS FTW!" );
monad.bind(alert);
```


[MOSTRAR OUTROS EXEMPLOS DE MONADS]



