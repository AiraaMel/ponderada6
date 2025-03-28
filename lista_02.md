# Instruções

- Faça uma cópia deste arquivo .md para um repositório próprio
- Resolva as 6 questões objetivas assinalando a alternativa correta
- Resolva as 4 questões dissertativas escrevendo no próprio arquivo .md
  - lembre-se de utilizar as estruturas de código como ``esta aqui com ` `` ou
```javascript
//esta aqui com ```
let a = "olá"
let b = 10
print(a)
```
- Resolva as questões com uso do Visual Studio Code ou ambiente similar.
- Teste seus códigos antes de trazer a resposta para cá.
- Cuidado com ChatGPT e afins: entregar algo só para ganhar nota não faz você aprender e ficar mais inteligente. Não seja dependente da máquina! (E não se envolva em plágio!)
- ao final, publique seu arquivo lista_02.md com as respostas em seu repositório, e envie o link pela Adalove. 

# Questões objetivas

**1)** Considere o seguinte código JavaScript:

```javascript
//EX01
let p = 10;
let q = 3;
let r = 6;

// (p % q === 1) quando divide 10 por 3 sobra 1
// (r * 2 > p) p é menor que r multiplicado por 2
// (q + r < p) q mais r menor que p
let resultado = (p % q === 1) && (r * 2 > p) || (q + r < p);
console.log(resultado);

// multiplica valores no array em loop, de modo semlhante ao reduce
const valores = [3, 6, 9, 12, 15];
// começa multiplicando por 1
let produto = 1;

// começa multiplicando por 1 e em seguida multiplica cada elemento do array pelo resultado da multiplicação anterior 
// ex: 1*3=3; 3*6=18; 18*9=162
// for (inicialização; condição; atualização)
for (let j = 0; j < valores.length; j++) {
  produto *= valores[j];
  // let j = 0: inicia array no 0
  // j < valores.length: O loop continua enquanto j for menor que o tamanho do array valores.length
  // j++: Após cada iteração, j é incrementado em 1, avançando para o próximo índice do array.
}

console.log("O produto dos valores é:", produto);


```
```javascript
    // No caso, quando p dividido por q tem resto 1 e 2r é maior que p ou q+r é menor que p o resultado é possível.
    // O primeiro consol.log imprime um resultado true ou false
    // O segundo console.log imprime o resultado do produto feito com os elementos do array
```

Qual das seguintes alternativas melhor descreve o que o código faz?

``A) O código avalia a expressão booleana, imprime `true`, calcula o produto dos números na lista e imprime o resultado no console.``

B) O código avalia a expressão booleana, imprime `false`, calcula o produto dos números na lista e imprime o resultado no console.

C) O código avalia a expressão booleana, imprime `true` e, em seguida, verifica se o número 6 está na lista.

D) O código avalia a expressão booleana, imprime `false` e ordena os valores em ordem crescente.


______

**2)** O código a seguir contém duas funções que calculam o limite de crédito de um cliente com base nos seus gastos e na renda mensal.

```javascript
// Versão 1 da função de análise de crédito
function analisarCredito1() {
    var compras = [2500, 1200, 800, 100];
    // começa com o primeiro array na posição 0
    var totalCompras = compras[0];
    var limite = 5000;
    // Inicia com status aprovado
    var status = 'aprovado';
    var saldoDisponivel = 0;
    // Um índice para percorrer o array de compras, começando em 1.
    var i = 1;

    do {
        totalCompras += compras[i];
        i++;
    // Percorre um array de compras e soma os valores, parando quando atinge o limite
    // Adiciona valores quando limite é maior ou igual o total de compras e quando ainda possui intens no array, no caso, o limite seria 4
    } while (limite >= totalCompras && i < compras.length);

    // Calculo de saldo
    saldoDisponivel = limite - totalCompras;

    // se o saldo disponível for menor que 0 o status será negado
    if (saldoDisponivel < 0) {
        status = 'negado';
    }
    // imprime se o status é negado ou aprovado
    console.log(`Seu crédito foi ${status}. Saldo disponível: ${saldoDisponivel}.`);
}
```

```javascript
// Versão 2 da função de análise de crédito
function analisarCredito2() {
    var compras = [2500, 1200, 800, 100];
    // começa com o primeiro array na posição 0
    var totalCompras = compras[0];
    // Defini limite disponível
    var limite = 5000;
    // Inicia com status aprovado
    var status = 'aprovado';
    var saldoDisponivel = 0;
    // Um índice para percorrer o array de compras, começando em 1.
    var i = 1;

    // liimite maior ou igual ao total de compras e i menor que números de elementos no array
    while (limite >= totalCompras && i < compras.length) {
        totalCompras += compras[i];
        i++;
    }

    // Calculo de saldo disponível
    saldoDisponivel = limite - totalCompras;

    // 
    if (saldoDisponivel < 0) {
        status = 'negado';
    }
    console.log(`Seu crédito foi ${status}. Saldo disponível: ${saldoDisponivel}.`);
}
```
Se ambas as funções forem executadas com os valores fornecidos, qual será a saída exibida no console?

A) Ambas as funções exibirão: 'Seu crédito foi negado. Saldo disponível: -600.'

B) analisarCredito1() exibirá: 'Seu crédito foi negado. Saldo disponível: -600.', enquanto analisarCredito2() exibirá: 'Seu crédito foi negado. Saldo disponível: -200.'

``C) analisarCredito1() exibirá: 'Seu crédito foi negado. Saldo disponível: -200.', enquanto analisarCredito2() exibirá: 'Seu crédito foi negado. Saldo disponível: -600.'``

D) Ambas as funções exibirão: 'Seu crédito foi negado. Saldo disponível: -200.'

```javascript
    // While verifica antes de executar, se for false, o loop nunca será executado. Ddados são obtidos antes de processá-los
    // do...while é executado pelo menos 1 vez antes da condição ser testada, depois da primeira continua apenas se for verdadeira
```
______

**3)** Considere o seguinte trecho de código em JavaScript:
```javascript
//EX03
const idade = 21;

// idade maior ou igual a 18 e menor que 60
if (idade >= 18 && idade < 60) {
  console.log("Você é um adulto!");
  // se a idade é menor que 18, imprime que a pessoa é menor de idade
} else if (idade < 18) {
  console.log("Você é menor de idade!");
} else {
  // Caso não esteja entre essas idades, aparece que está na melhor idade
  console.log("Você está na melhor idade!");
}
```
Qual das seguintes alternativas melhor descreve o comportamento do código?

A) O código verifica se a idade indica um adulto ou um idoso e exibe a mensagem correspondente.

``B) O código verifica se a idade pertence à faixa adulta. Se for, exibe "Você é um adulto!". Caso contrário, verifica se é menor de idade e exibe "Você é menor de idade!". Se nenhuma das condições anteriores for verdadeira, exibe "Você está na melhor idade!".``

C) O código verifica se a idade está entre 18 e 60 anos e, se for, imprime "Você é um adulto!". Se não estiver nesse intervalo, imprime "Você está na melhor idade!".

D) O código verifica se a idade é menor de 18, entre 18 e 60 ou acima de 60, imprimindo uma mensagem específica para cada caso.
______

**4)** Qual será o resultado impresso no console após a execução do seguinte código?
```javascript
//EX04
// Cada dispositivo da lista consome uma quantidade específica de energia. O código verifica se há energia suficiente para ligá-lo.
// energia principal
var energiaDisponivel = 1200;
// energia extra
var bateriaExtra = 400;
// array de consumo
var consumoDispositivos = [300, 600, 500, 200, 400];

// inicia no array 0 e percorre todos os dispositivos da lista
for (var i = 0; i < consumoDispositivos.length; i++) {
    var consumo = consumoDispositivos[i];
    
    // se o consumo for menor ou igual a energia disponivel, é ligado sem energia extra
    if (consumo <= energiaDisponivel) {
        // imprime que foi ligado e mostra energia restante
        console.log("Dispositivo " + (i+1) + " ligado. Energia restante: " + (energiaDisponivel - consumo));
        // energia principal é reduzida
        energiaDisponivel -= consumo;
    // se o consumo for menor ou igual a energia disponivel mais a extra, é ligado usando a extra
    } else if (consumo <= energiaDisponivel + bateriaExtra) {
        // imprime que é ligado com bateria extra e mostra que a energia principal é 0 e reduz da extra o valor que faltava
        console.log("Dispositivo " + (i+1) + " ligado com bateria extra. Energia restante: " + ((energiaDisponivel + bateriaExtra) - consumo));
        energiaDisponivel = 0;
        bateriaExtra -= (consumo - energiaDisponivel);
    // se não imprime que o dispositivo não pode ser ligado
    } else {
        console.log("Dispositivo " + (i+1) + " não pode ser ligado. Energia insuficiente.");
    }
}
```

Escolha a opção que responde corretamente:

A)
Dispositivo 1 ligado. Energia restante: 900

Dispositivo 2 ligado com bateria extra. Energia restante: 700

Dispositivo 3 ligado. Energia restante: 200

Dispositivo 4 ligado com bateria extra. Energia restante: 0

Dispositivo 5 ligado. Energia restante: -200

B)
Dispositivo 1 ligado. Energia restante: 900

Dispositivo 2 ligado com bateria extra. Energia restante: 700

Dispositivo 3 ligado. Energia restante: 200

Dispositivo 4 não pode ser ligado. Energia insuficiente.

Dispositivo 5 não pode ser ligado. Energia insuficiente.

C)
Dispositivo 1 ligado. Energia restante: 900

Dispositivo 2 ligado com bateria extra. Energia restante: 700

Dispositivo 3 ligado. Energia restante: 400

Dispositivo 4 não pode ser ligado. Energia insuficiente.

``D)``
Dispositivo 1 ligado. Energia restante: 900

Dispositivo 2 ligado. Energia restante: 300

Dispositivo 3 ligado com bateria extra. Energia restante: 200

Dispositivo 4 não pode ser ligado. Energia insuficiente.

Dispositivo 5 não pode ser ligado. Energia insuficiente.

``` javascript
// Obs. 
```

______

**5)** Qual é a principal função do método update() em um jogo desenvolvido com Phaser.js?

Escolha a opção que melhor descreve seu propósito:

A) O método update() é responsável por carregar os assets do jogo antes da cena ser exibida.

``B) O método update() é chamado continuamente a cada quadro (frame) do jogo, sendo usado para atualizar a lógica, movimentação e interações dos objetos na cena.``

C) O método update() renderiza todos os sprites na tela e garante que a física do jogo seja processada corretamente.

D) O método update() é chamado apenas uma vez após a criação da cena, sendo utilizado para configurar variáveis iniciais do jogo.
______

**6)** Qual é o principal objetivo do módulo Matter.js Physics em Phaser.js?

Escolha a opção que responde corretamente:

``A) Simular física avançada, incluindo corpos rígidos, colisões complexas e interação entre objetos com gravidade e forças. ``


B) Gerenciar eventos de entrada do usuário, como cliques e toques na tela, permitindo movimentação de personagens.``Input System``

C) Renderizar gráficos otimizados para jogos 2D e garantir uma taxa de quadros estável.``WebGl e Canvas, feito pelo propio motor de renderização``

D) Criar animações automáticas para sprites e objetos interativos sem necessidade de programação de movimentação.
``frames``

______

# Questões dissertativas

**7)** Uma loja online deseja implementar um sistema de classificação de pedidos com base no valor total da compra. O sistema deve determinar a categoria de um pedido com as seguintes regras:

```

Pedidos abaixo de R$50,00 → "Frete não disponível!"

Pedidos entre R$50,00 e R$199,99 (inclusive) → "Frete com custo adicional!"

Pedidos de R$200,00 ou mais → "Frete grátis!"
```
Implemente um pseudocódigo que receba o valor total da compra e exiba a classificação correta do frete para o cliente.

``` javascript
// array com valores do pedido
// array com valores do pedido
var pedidos = [350, 44, 50, 200]

// função para verificar qual o tipo de frete
function calcularFrete(pedido) {
// Se o pedido for menor que R$50, o frete não está disponível
if (pedido < 50) {
    console.log(`Pedido de R$${pedido}: Frete não disponível`);
// Se o pedido estiver entre R$50 e R$199, o frete tem custo adicional
} else if (pedido >= 50 && pedido < 200) {
    console.log(`Pedido de R$${pedido}: Frete com custo adicional!`)
// Se o pedido for R$200 ou mais, o frete é grátis
} else
    console.log(`Pedido de R$${pedido}: Frete grátis`)
}

// Percorre o array "pedidos" 
for (let i = 0; i < pedidos.length; i++) {
    calcularFrete(pedidos[i]);
}
```
______

**8)** Considere a implementação da classe base Veiculo em um sistema de modelagem de veículos. Sua tarefa é implementar, utilizando pseudocódigo, as classes derivadas Carro e Moto, que herdam da classe Veiculo, adicionando atributos específicos e métodos para calcular o consumo de combustível de um carro e de uma moto, respectivamente.

```
Classe Veiculo:
Atributos:

modelo
ano
Método Construtor(modelo, ano):

Define os valores dos atributos modelo e ano com os valores passados como parâmetro.
Método CalcularConsumo():
```
Implementação genérica para cálculo de consumo, a ser sobrescrita pelas subclasses.
Agora, implemente as classes Carro e Moto, garantindo que ambas herdem de Veiculo e possuam métodos específicos para calcular o consumo de combustível com base na quilometragem e eficiência do veículo.

``` javascript
// Classe mãe
class Veiculo {
    constructor (modelo, ano) {
        // atributos
        this.modelo = modelo;
        this.ano = ano;
    }
    // Método para caucúlo de consumo 
    CalcularConsumo() {
        console.log(`Modelo: ${this.modelo}, Ano: ${this.ano}`)
    }
}

// Classe filha carro herda de veiculo
class Carro extends Veiculo {
    constructor(modelo, ano, eficiencia) {
        // atributos herdados por super
        super(modelo, ano);
        // adiciona variavel eficiencia
        this.eficiencia = eficiencia;
    }
    
    // método para calcular o consumo do carro com base na distância
    CalcularConsumo(distancia) {
        let consumo = distancia / this.eficiencia;
        console.log(`O carro ${this.modelo} consumiu ${consumo} litros em ${distancia} km.`);
    }
}

// Classe filha moto herda de veiculo
class Moto extends Veiculo {
    constructor(modelo, ano, eficiencia) {
        super(modelo, ano);
        this.eficiencia = eficiencia; 
    }

    // método para calcular o consumo do carro com base na distância
    CalcularConsumo(distancia) {
        let consumo = distancia / this.eficiencia;
        console.log(`A moto ${this.modelo} consumiu ${consumo} litros em ${distancia} km.`);
    }
}

// exemplo teste
let carro1 = new Carro("Porshe", 2016, 30);
carro1.CalcularConsumo(240);

let moto1 = new Moto("Bros", 2023, 25);
moto1.CalcularConsumo(100);
```

______

**9)** Você é um cientista da NASA e está ajudando no desenvolvimento de um sistema de pouso para sondas espaciais em Marte. Seu objetivo é calcular o tempo necessário para que a sonda reduza sua velocidade até um nível seguro para pouso, considerando uma velocidade inicial de entrada na atmosfera marciana e uma taxa de desaceleração constante causada pelo atrito atmosférico e retrofoguetes.

Entretanto, a sonda não pode ultrapassar um tempo máximo de descida para evitar desvios orbitais, nem pode desacelerar além de um limite mínimo, pois isso poderia causar instabilidade no pouso.

Implemente a lógica dessa simulação em pseudocódigo, considerando a seguinte equação para atualização da velocidade:

Considere a fórumla de atualização velocidade:
```
    velocidade = velocidadeInicial - desaceleracao * tempo
```
Seu programa deve determinar quanto tempo será necessário para que a sonda atinja uma velocidade segura de pouso, sem ultrapassar os limites estabelecidos.

``` javascript
function calcularTempoPouso(velocidadeInicial, desaceleracao, velocidadeSegura, limiteMinimo, tempoMaximo) {
    // velocidadeInicial: velocidade de entrada na atmosfera
    // desaceleracao: desacelera devido ao atrito
    // velocidadeSegura: velocidade necessária para pouso seguro
    // limiteMinimo: minimo para velocidade não cair
    // tempoMaximo: tempo maximo permitido para descida

    for (let tempo = 0; tempo <= tempoMaximo; tempo++) {
        // Calcula a velocidade da sonda no tempo atual usando a equação da velocidade
        let velocidade = velocidadeInicial - desaceleracao * tempo;

        // Se a velocidade está dentro da faixa segura para pouso, exibe o tempo necessário e encerra a simulação
        if (velocidade <= velocidadeSegura && velocidade >= limiteMinimo) {
            console.log(`Tempo necessário para atingir a velocidade segura: ${tempo} segundos.`);
            return;
        }

        // Se a velocidade ficar abaixo do limite mínimo, significa que desacelerou demais, o que pode causar instabilidade
        if (velocidade < limiteMinimo) {
            console.log("Atingiu desaceleração excessiva: velocidade abaixo do limite mínimo.");
            return;
        }
    }

    // Se a simulação terminar sem atingir a velocidade segura, exibe uma mensagem de erro
    console.log("Tempo máximo de descida excedido. Ajuste os parâmetros de desaceleração.");
}

// Exemplo de uso
calcularTempoPouso(200, 10, 5, 4, 50);
```
______

**10)** Em um sistema de análise financeira, as operações de investimento de uma empresa podem ser representadas por matrizes, onde cada linha representa um tipo de investimento e cada coluna representa um período de tempo.

A seguir, é fornecida a implementação da função SomarMatrizesInvestimento(matrizA, matrizB), que soma os valores de duas matrizes de investimento. Sua tarefa é implementar uma função semelhante, porém que realize a multiplicação das matrizes de investimento, determinando como os investimentos afetam os resultados ao longo do tempo.

```
Função SomarMatrizesInvestimento(matrizA, matrizB):  
    # Verifica se as matrizes têm o mesmo número de linhas e colunas  
    Se tamanho(matrizA) ≠ tamanho(matrizB) então:  
        Retornar "As matrizes não podem ser somadas. Elas têm dimensões diferentes."  
    Senão:  
        linhas <- tamanho(matrizA)  
        colunas <- tamanho(matrizA[0])  
        matrizResultado <- novaMatriz(linhas, colunas)  

        # Loop para percorrer cada elemento das matrizes e calcular a soma  
        Para i de 0 até linhas-1 faça:  
            Para j de 0 até colunas-1 faça:  
                matrizResultado[i][j] <- matrizA[i][j] + matrizB[i][j]  

        Retornar matrizResultado  

# Exemplo de uso da função  
investimentosAno1 <- [[1000, 2000], [1500, 2500]]  
investimentosAno2 <- [[1200, 1800], [1300, 2700]]  

totalInvestimentos <- SomarMatrizesInvestimento(investimentosAno1, investimentosAno2)  
Escrever("Total de investimentos acumulados:")  
ImprimirMatriz(totalInvestimentos)  
```
Agora, implemente a função MultiplicarMatrizesInvestimento(matrizA, matrizB), que multiplica as duas matrizes, simulando o efeito de diferentes fatores de crescimento e impacto financeiro nos investimentos ao longo do tempo.

``` javascript
    //O número de colunas da primeira matriz deve ser igual ao número de linhas da segunda matriz.
// O resultado terá o mesmo número de linhas da primeira matriz e o mesmo número de colunas da segunda matriz.
function multiplicarMatrizesInvestimento(matrizA, matrizB) {

    // numero de linhas de A
    let linhasA = matrizA.length;
    // numero de colunas de A
    let colunasA = matrizA[0].length;
    // numero de linhas de B
    let linhasB = matrizB.length;
    // numero de colunas de B
    let colunasB = matrizB[0].length;

    // Verifica se a multiplicação é possível (número de colunas de A == número de linhas de B)
    if (colunasA !== linhasB) {
        return "As matrizes não podem ser multiplicadas. Número de colunas de A deve ser igual ao número de linhas de B.";
    }

    // Inicializa a matriz resultado com valores zerados
    let matrizResultado = [];
    for (let i = 0; i < linhasA; i++) {
        // Cria uma nova linha na matriz resultado
        matrizResultado[i] = [];
        for (let j = 0; j < colunasB; j++) {
            // Inicializa cada posição da matriz com 0
            matrizResultado[i][j] = 0;
        }
    }

    // percorre cada linha da matriz A
    for (let i = 0; i < linhasA; i++) { 
        // percorre cada coluna da matriz B
        for (let j = 0; j < colunasB; j++) { 
            // percorre cada elemento da linha de A e coluna de B
            for (let k = 0; k < colunasA; k++) { 
                matrizResultado[i][j] += matrizA[i][k] * matrizB[k][j];
            }
        }
    }

    // retorna a matriz resultante da multiplicação
    return matrizResultado;

}

```