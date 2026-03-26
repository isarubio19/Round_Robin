# Simulação de Escalonamento Round Robin com Fila Circular em C

## Descrição do Projeto

Este projeto implementa uma simulação do algoritmo de escalonamento **Round Robin**, amplamente utilizado em sistemas operacionais para gerenciamento de processos.

O programa utiliza uma **fila circular (Queue)** para armazenar processos representados por seus tempos de execução. A cada iteração, um processo é retirado da fila, executado por um tempo fixo (quantum) e, caso não seja finalizado, retorna ao final da fila com seu tempo restante atualizado.

O objetivo é demonstrar, na prática, o funcionamento de filas e do algoritmo Round Robin.

---

## Estruturas Utilizadas

### Fila Circular (Queue)

A fila é implementada com:

* Um vetor dinâmico de inteiros
* Índices de controle (`inicio` e `fim`)
* Tamanho atual (`curr_size`)
* Capacidade máxima (`max_size`)

Características:

* Estrutura FIFO (First In, First Out)
* Uso de aritmética modular para comportamento circular

Operações disponíveis:

* `enqueue`: insere elemento no final
* `dequeue`: remove elemento do início
* `front`: acessa o primeiro elemento
* `rear`: acessa o último elemento
* `isEmpty`: verifica se está vazia
* `isFull`: verifica se está cheia

---

## Funcionamento

### Entrada do Programa

1. O usuário informa o tamanho da fila (quantidade de processos)
2. Insere os tempos de execução de cada processo
3. Define o valor do quantum

### Execução dos Processos

* O programa executa os processos em ordem de chegada
* A cada ciclo:

  * Remove um processo da fila
  * Subtrai o valor do quantum
  * Se ainda restar tempo, o processo volta ao final da fila
  * Caso contrário, o processo é finalizado
* A fila é exibida a cada etapa

---

## Exemplos de Execução

### Entrada:

tamanho da fila: 3
10 5 8
3

### Saída:

[10,5,8]

10-3 = 7
Executando o processo 10...
Nao finalizado! Novo valor: 7.
[5,8,7]

5-3 = 2
Executando o processo 5...
Nao finalizado! Novo valor: 2.
[8,7,2]

8-3 = 5
Executando o processo 8...
Nao finalizado! Novo valor: 5.
[7,2,5]

... (continua até todos finalizarem)

---

## Observações Importantes

* O algoritmo segue o modelo Round Robin, garantindo divisão justa de tempo entre processos
* A fila é circular, permitindo reaproveitamento de posições no vetor
* O uso do operador `%` (módulo) é essencial para o funcionamento circular
* O programa exibe o estado da fila após cada operação
* Quando um processo termina, ele não retorna à fila
* O valor `-1` pode ser retornado em casos de erro (fila vazia)
* O programa utiliza alocação dinâmica de memória (`malloc` e `free`)



---

## Conceitos Praticados

* Estrutura de Dados: Fila (Queue)
* Fila Circular
* Algoritmo de Escalonamento Round Robin
* Alocação dinâmica de memória
* Manipulação de arrays
* Controle de fluxo e repetição
