# Instruções
- Faça uma cópia deste arquivo .md para um repositório próprio
- Resolva as 8 questões objetivas assinalando a alternativa correta e **justificando sua resposta.**
- Resolva as 2 questões dissertativas escrevendo no próprio arquivo .md
- Lembre-se de utilizar as estruturas de código como ``esta aqui com ` `` ou
```javascript
//esta aqui com ```
let a = "olá"
let b = 10
print(a)
```
- Resolva as questões com uso do Visual Studio Code ou ambiente similar.
- Teste seus códigos antes de trazer a resposta para cá.
- Cuidado com o uso de ChatGPT (e similares), pois entregar algo só para ganhar nota não fará você aprender. Não seja dependente da máquina!
- Ao final, publique seu arquivo lista_01.md com as respostas em seu repositório, e envie o link pela Adalove. 

# Questões objetivas
**1) Considerando a execução do código abaixo, indique a alternativa correta e justifique sua resposta.**
```javascript
console.log(x);
var x = 5;
console.log(y);
let y = 10;
```
a) A saída será undefined seguido de erro 

temos que o valor dentro da variavel x será impresso como indefinido devido a ele ter sido declarado com "var", o que permite que a variável, mesmo após estar definida no código depois do "console.log", seja lida como undefined (indefinida). Já o valor da variavel y mostra erro o porque foi declarado usando "let", o que não permite acesso ao valor de y, em outros blocos de código, ou quando declarada depois do "console.log".


**2) O seguinte código JavaScript tem um erro que impede sua execução correta. Analise e indique a opção que melhor corrige o problema. Justifique sua resposta.**

```javascript
function soma(a, b) {
    if (a || b === 0) {
        return "Erro: número inválido";
    }
    return a + b;
}
console.log(soma(2, 0));
```

b) Substituir if (a || b === 0) por if (a === 0 && b === 0)

Se qualquer um dos valores for zero, o operador "||" dispara um erro de número inválido. O operador "&&", por sua vez, exige que ambos os valores sejam zero para gerar o mesmo erro.
______
**3) Ao executar esse código, qual será a saída no console? Indique a alternativa correta e justifique sua resposta.**
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

b) O código imprime 200.
O código inicia o caso "eletrônico" com valor 1000, mas sem "break", assim o código prossegue para o próximo caso, alterando o valor para 200, e então interrompe a execução, resultando na impressão de do número 200.
______
**4) Ao executar esse código, qual será a saída no console? Indique a alternativa correta e justifique sua resposta.**
```javascript
let numeros = [1, 2, 3, 4, 5];

let resultado = numeros.map(x => x * 2).filter(x => x > 5).reduce((a, b) => a + b, 0);

console.log(resultado);
```

d) 24

Primeiro, o código multiplica por 2 cada elemento da lista. Depois, ele filtra a lista, mantendo apenas os valores maiores que 5. Finalmente, ele soma esses valores filtrados, e o resultado final é 24.
6 + 8 + 10 = 24
______
**5) Qual será o conteúdo do array lista após a execução do código? Indique a alternativa correta e justifique sua resposta.**

```javascript
let lista = ["banana", "maçã", "uva", "laranja"];
lista.splice(1, 2, "abacaxi", "manga");
console.log(lista);
```

c) ["banana", "abacaxi", "manga", "laranja"]

A lista original, que continha "maçã" e "uva" nas posições 1 e 2, foi modificada. Esses elementos foram excluídos e "abacaxi" e "manga" foram adicionados, resultando na seguinte sequência ["banana", "abacaxi", "manga", 'laranja"].
______
**6) Abaixo há duas afirmações sobre herança em JavaScript. Indique a alternativa correta e justifique sua resposta**

I. A herança é utilizada para compartilhar métodos e propriedades entre classes em JavaScript, permitindo que uma classe herde os métodos de outra sem a necessidade de repetir código.  
II. Em JavaScript, a herança é implementada através da palavra-chave `extends`.


b) As duas afirmações são verdadeiras, mas a segunda não justifica a primeira.

As 2 informações são verdadeiras, porém existem outras maneiras de implementar herança dentro do Javascript.
___
**7) Dado o seguinte código. Indique a alternativa correta e justifique sua resposta.**

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

a) I e II são verdadeiras.



______

**8) Analise as afirmações a seguir. Indique a alternativa correta e justifique sua resposta.**

**Asserção:** O conceito de polimorfismo em Programação Orientada a Objetos permite que objetos de diferentes tipos respondam à mesma mensagem de maneiras diferentes.  
**Razão:** Em JavaScript, o polimorfismo pode ser implementado utilizando o método de sobrecarga de métodos em uma classe.

b) A asserção é verdadeira e a razão é falsa.

O conceito de polimorfismo na POO(Programação Orientada a Objetos) permite objetos que são de classes diferentes à responderem a mesma mensagem de uma forma diferente, de acordo com seus atributos. A sobrecarga de métodos, entretanto, não implementa o polimorfismo, pois resolve invocações de método com base na assinatura,já que ele considera somente a última declaração lida que foi associada ao nome.           

______

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

Novo código, já comentado:

```javascript
//definimos a nossa função 
function somaArray(numeros) {

    //definimos a variável soma
    var soma = 0;

    //o intervalo é definido, até onde a soma vai e que o valor de i vai aumentar em 1
    for (var i = 0; i < numeros.length; i++) {
        //definimos a soma de elementos do array depois que os multiplicamos por 2
        soma += 2*numeros[i];
    }
    //nos é retornado o valor da soma
    return soma;
}
//define os elementos do array a serem inicializados e impressos
console.log(somaArray([1, 2, 3, 4]));
```
______
10) Crie um exemplo prático no qual você tenha duas classes:

- Uma classe `Produto` com atributos `nome` e `preco`, e um método `calcularDesconto()` que aplica um desconto fixo de 10% no preço do produto.
- Uma classe `Livro` que herda de `Produto` e modifica o método `calcularDesconto()`, aplicando um desconto de 20% no preço dos livros.

Explique como funciona a herança nesse contexto e como você implementaria a modificação do método na classe `Livro`.

```javascript
class Produto {
    constructor(nome, preco) {
        this.nome = nome;
        this.preco = preco;
    }

    // Método para calcular um desconto padrão de 10%
    calcularDesconto() {
        return this.preco * 0.9; // 10% de desconto
    }

    // Método para exibir as informações do produto
    mostrarDetalhes() {
        console.log(Produto: ${this.nome} | Preço: R$${this.preco});
    }
}

class Livro extends Produto {
    constructor(nome, preco, autor) {
        super(nome, preco); // Aproveitando o construtor da classe Produto
        this.autor = autor;
    }

    // Aqui, os livros têm um desconto maior (20%)
    calcularDesconto() {
        return this.preco * 0.8; // 20% de desconto
    }

    // Método para exibir os detalhes do livro
    mostrarDetalhes() {
        console.log(Livro: ${this.nome} | Autor: ${this.autor} | Preço: R$${this.preco});
    }
}
  
  ```
Usamos a palavra-chave "extends" para estabelecer a relação de herança entre "Livro" e "Produto". Nos mostra que "Livro" é uma subclasse de "Produto".
O "super()" é usado no construtor da classe "Livro" para chamar o construtor da classe "Produto". Isso nos garante que as propriedades "nome" e "preco" sejam inicializadas corretamente na classe pai.
A classe "Livro" herda as propriedades "nome" e "preco" e os métodos "calcularDesconto()" e "mostrarDetalhes()" da classe "Produto".
A modificação dos métodos "calcularDesconto()" e "mostrarDetalhes()" na classe "Livro" é feita definindo novos métodos com os mesmos nomes na subclasse. O JavaScript automaticamente usará a versão modificada dos métodos quando forem chamados em um objeto "Livro."