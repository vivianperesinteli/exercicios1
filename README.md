# Exercícios_Programacao_Semana 5

Lista de exercícios 1 área de programação Inteli

# Questões objetivas
1) Considerando a execução do código abaixo, indique a alternativa correta e justifique sua resposta.**
```javascript
console.log(x);
var x = 5;
console.log(y);
let y = 10;
```

Resposta:
a) A saída será undefined seguido de erro 

No caso desse código, a variável x, e também a y, não tinham sido declaradas no momento em que console.log foi chamado. Ou seja, não havia valor declarado para imprimir o valor da variável, como uma chamada fantasma. Nesta ordem gera-se um valor indefinido, pois o ítem existe, mas não é declarado, e gera-se assim o erro.

///////////////////////////////////////////

2) O seguinte código JavaScript tem um erro que impede sua execução correta. Analise e indique a opção que melhor corrige o problema. Justifique sua resposta.**

```javascript
function soma(a, b) {
    if (a || b === 0) {
        return "Erro: número inválido";
    }
    return a + b;
}
console.log(soma(2, 0));
```

Resposta: 

a) Substituir if (a || b === 0) por if (a === 0 || b === 0)


O código proposta contém um problema na expressão if (a || b === 0). No contexto da linguagem javascript empregada, o operador || utilizado tem como regra de retorno o primeiro valor real que encontra no código, e nesse caso, a expressão b === 0 já tinha sido enviada ainda antes de ser implementada como comparação com a. Ou seja, esse comportamento siginifica o mesmo que codar (a) (b === 0), sem conexão, e erroneamente. 

Para corrigirmos essa funcionalidade no nosso código utilizamos a função a === 0 || b === 0, relacionando corretamente os dois ítens a comparação de maneira correta.

//////////////////////////////

3) Ao executar esse código, qual será a saída no console? Indique a alternativa correta e justifique sua resposta.**
```javascript
function calcularPreco(tipo) {
    let preco;

    switch(tipo) {
        case "eletrônico":
            preco = 1000;
        case "vestuário":
            preco = 200;
            break;
        case "alimento":
            preco = 50;
            break;
        default:
            preco = 0;
    }

    return preco;
}

console.log(calcularPreco("eletrônico"));
```
Resposta:

b) O código imprime 200.

O código como um todo está certinho, tirando a ausência do comando break após a declaração do case eletrônico - isso porque o switch vai continuar executando o caso infinitamente até achar algum break ou fechar o switch. Como não tem break, o switch continua executando o outro caso, vestuário. Então como definimos a variável preço como 200, a execução do switch é interrompida, e retorna o valor de 200. Caso o break fosse incluido, o valor retornado seria 1000. 

/////////////////////////

4) Ao executar esse código, qual será a saída no console? Indique a alternativa correta e justifique sua resposta.**
```javascript
let numeros = [1, 2, 3, 4, 5];

let resultado = numeros.map(x => x * 2).filter(x => x > 5).reduce((a, b) => a + b, 0);

console.log(resultado);
```

Resposta: 

c) 18


Com o array original do código, o método map multiplica os elementos do array por 2, gerando [2, 4, 6, 8, 10], seguindo como filter, que filtra os maiores que 5 do array [6, 8, 10]. O próximo reduce age somando esses elementos já filtrados, iniciando com o valor inicial de 0, fechando em 24, que é a saída final. 


/////////////////////////////

5) Qual será o conteúdo do array lista após a execução do código? Indique a alternativa correta e justifique sua resposta.**

```javascript
let lista = ["banana", "maçã", "uva", "laranja"];
lista.splice(1, 2, "abacaxi", "manga");
console.log(lista);
```

Resposta: 

Resposta:

c) ["banana", "abacaxi", "manga", "laranja"]

Justificativa:

Utilizamos o splice para tirar e colocar elementos no erray. Inciando no índice 1, remove maça e uva. Adicionamos então abacaxi e manga no lugar dos removidos. O array lista após executar o splice vira banana, abacaxi, manga e laranja, chegando a alternativa certa. 
```
////////////////////////////////////

6) Abaixo há duas afirmações sobre herança em JavaScript. Indique a alternativa correta e justifique sua resposta**

I. A herança é utilizada para compartilhar métodos e propriedades entre classes em JavaScript, permitindo que uma classe herde os métodos de outra sem a necessidade de repetir código.  
II. Em JavaScript, a herança é implementada através da palavra-chave `extends`.

Resposta:

a) As duas afirmações são verdadeiras, e a segunda justifica a primeira.

Utilizamos no código a herança, que compartilha propriedades entre diferentes classes em JS. Já na segunda afirmação, tratando sobre a palavra de implementação da herança, também é verdadeiro.

////////////////////////

7) Dado o seguinte código. Indique a alternativa correta e justifique sua resposta.**

```javascript
class Pessoa {
  constructor(nome, idade) {
    this.nome = nome;
    this.idade = idade;
  }

  apresentar() {
    console.log(`Olá, meu nome é ${this.nome} e tenho ${this.idade} anos.`);
  }
}

class Funcionario extends Pessoa {
  constructor(nome, idade, salario) {
    super(nome, idade);
    this.salario = salario;
  }

  apresentar() {
    super.apresentar();
    console.log(`Meu salário é R$ ${this.salario}.`);
  }
}
```

I) A classe Funcionario herda de Pessoa e pode acessar os atributos nome e idade diretamente.  
II) O método `apresentar()` da classe Funcionario sobrepõe o método `apresentar()` da classe Pessoa, mas chama o método da classe pai usando `super`.  
III) O código não funciona corretamente, pois Funcionario não pode herdar de Pessoa como uma classe, já que o JavaScript não suporta herança de classes.

Quais das seguintes afirmações são verdadeiras sobre o código acima?

Resposta: 

Resposta:

a) I e II são verdadeiras.

Justificativa:

A classe Funcionario herda de Pessoa usando a palavra-chave extends, que permite o acesso direto aos atributos nome e idade.
O método apresentar() da classe Funcionario sobrepõe o método apresentar() da classe Pessoa, mas chama o método da classe pai usando super.apresentar(). Portanto, a afirmação II é verdadeira. Já a afirmação III é falsa, pois o JavaScript suporta herança de classes usando a palavra-chave extends.

//////////////////////////////

8) Analise as afirmações a seguir. Indique a alternativa correta e justifique sua resposta.**

**Asserção:** O conceito de polimorfismo em Programação Orientada a Objetos permite que objetos de diferentes tipos respondam à mesma mensagem de maneiras diferentes. 
**Razão:** Em JavaScript, o polimorfismo pode ser implementado utilizando o método de sobrecarga de métodos em uma classe.

Resposta:

b) A asserção é verdadeira e a razão é falsa.

Em JavaScript, o polimorfismo pode ser implementado utilizando o método de sobrecarga de métodos em uma classe.
Isso é falso. JavaScript não suporta sobrecarga de métodos da mesma forma que linguagens como Java ou C++. Em vez disso, o polimorfismo em JavaScript é geralmente implementado através de herança e substituição de métodos (overriding).

/////////////////////////////////

# Questões dissertativas
9) O seguinte código deve retornar a soma do dobro dos números de um array, mas contém erros. Identifique os problema e corrija o código para que funcione corretamente. Adicione comentários ao código explicado sua solução para cada problema.

```javascript
function somaArray(numeros) {

    for (i = 0; i < numeros.size; i++) {
        soma = 2*numeros[i];
    }
    return soma;
}
console.log(somaArray([1, 2, 3, 4]));
```

Resposta:

function somaArray(numeros) {
    // Inicializa a variável soma com 0
    let soma = 0;

    // Corrige a declaração da variável i e usa a propriedade length
    for (let i = 0; i < numeros.length; i++) {
        // Acumula o dobro de cada número na variável soma
        soma += 2 * numeros[i];
    }

    // Retorna a soma acumulada
    return soma;
}

// Testa a função com um array de exemplo
console.log(somaArray([1, 2, 3, 4])); // Saída esperada: 20
______

////////////////////////////////

10) Crie um exemplo prático no qual você tenha duas classes:

- Uma classe `Produto` com atributos `nome` e `preco`, e um método `calcularDesconto()` que aplica um desconto fixo de 10% no preço do produto.
- Uma classe `Livro` que herda de `Produto` e modifica o método `calcularDesconto()`, aplicando um desconto de 20% no preço dos livros.

Explique como funciona a herança nesse contexto e como você implementaria a modificação do método na classe `Livro`.

Resposta:

// Classe Produto
class Produto {
    constructor(nome, preco) {
        this.nome = nome;
        this.preco = preco;
    }

    // Método para calcular desconto de 10%
    calcularDesconto() {
        return this.preco * 0.90;
    }
}

// Classe Livro que herda de Produto
class Livro extends Produto {
    constructor(nome, preco, autor) {
        super(nome, preco);
        this.autor = autor;
    }

    // Método para calcular desconto de 20%
    calcularDesconto() {
        return this.preco * 0.80;
    }
}

// Exemplo de uso
const produto = new Produto("Genérico", 100);
console.log(`Preço do produto com desconto: R$ ${produto.calcularDesconto()}`);

const livro = new Livro("JavaScript Avançado", 100, "Autor Desconhecido");
console.log(`Preço do livro com desconto: R$ ${livro.calcularDesconto()}`);
