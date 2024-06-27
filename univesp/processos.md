# Processos

## Definição de um Processo

Um processo é caracterizado por um programa em execução. Um processo é uma instância de um programa e possui dados de entrada,  dados de saída e um estado (executando, bloqueando, pronto).

## Programa vs processo

 - Um programa pode ter várias instâncias em execução (em diferentes processos).
 - É um algoritimo codificado.
 - Forma como o programador vê a tarefa a ser executada.

 - Um processo é único.
 - Código acompanhado de dados e estado.
 - Forma pela qual o SO vê um programa e possibilita a sua execução.

## Processo em primeiro plano

Interage com o usuário.

 - Ler um arquivo
 - Iniciar um programa (linha de comando ou um duplo clique no mouse).

## Processo em segundo plano

Processos com funções específicas que independem de usuários - daemons:

 - Recepção e envio de emails.
 - Serviços de impressão.

## Cada processo possui

1. Conjunto de instruções
2. Espaço de endereçamento (espaço reservado para que o processo possa ler e escrever - 0 até max)
3. Contexto de hardware (valores nos registradores, como PC, ponteiro de pilha, e reg. de prop gerais)
4. Contexto de software (atributos em geral, como lista de arquivos abertos, variáveis, etc. )

## Espaço de endereçamento

1. Texto: Código executável do(s) programa(s);
2. Dados: As variáveis;
3. Pilha de execução:
   - Controla e xecução do processo;
   - Empilhando chamadas a procedimentos, e seus parâmetros e variáveis locais, etc.

## Tabela de processos

1. Também chamada de BCP (Bloco de controle de Processo)
2. Contém informações de contexto de cada prpcesso (ex. ponteiros de arquivos abertos, posição do próximo byte a ser lido em cada arquivo, etc.)
3. Contém informações necessárias para trazer o processo de volta, caso o SO tenha que tirálo de execução.
4. Contém estados de um processo em um determinado tempo.

O BPC só não guarda o conteúdo do espaço de endereçamento do processo.

Assim, um processo é constituído de seu espaço de endereçamento e BPC (com seus registradores, etc.), representando uma entrada na tabela de processos.

## Características de processo

1. Processos CPU-bound (orientados á CPU): processos que utilizam muito o processador;
    - Tempo de xecução é definido pelos ciclos de processador;
2. Processos I/O-bound (orientado á E/S): processos que realizam muito E/S;
    - Tempo de execução é definido peça duração das operações de E/S;

Ideal: Existir um balanceamento entre processos CPU-bound e I/O-bound;

### Situação Ideal

Processos de surto curto preenchem as lacunas de uso da CPU deixadas por processos mais longos

## Criação de processos

 - Inicialização do sistema.
 - Execução de uma chamada de sistema para criação de processo, realizada por algum processo em execução.
 - Requisição de usuário para criar um novo processo (duplo clique do mouse, etc.).
 - Inicialização de um processo em batch ( em sistemas mainframes com proc. em batch ).

## Processos criando outros processos

1. No UNIX com a função fork()
   - Cria clone do proceso pai: cópias exatas na memória, mas com identificadores diferentes.
2. No Windows com createProcess
   - Cria processo Filho, já carregando novo programa nele.

## Finalizando processos

1. Término normal (voluntário):
   - A tarefa a ser executada é finalizada;
   - Ao terminar, o processo executa uma chamada (comunicando ao SO que terminou): exit (UNIX) e ExitProcess (Windows).

2. Término por erro (Voluntário):
   - O processo sendo executado não pode ser finalizado. Ex: gcc filename.c; o arquivo filename.c não existe.

3. Término com erro fatal (involuntário);
   - Erro causado por algum erro no programa (bug); EX: Divisão po 0; Referência á memória inexistente; Execução de uma instrução ilegal.

4. Término (involuntário) causado por algum outro processo, via chamada a:
   - kill (UNIX)
   - TerminateProcess (Windows)

## Estados de processos

1. Executando: Realmente usando a CPU naquele momento.
2. Bloqueando: Incapaz de executar enquanto um evento externo não ocorrer.
3. Pronto: Em memória, pronto para executar (ou para continuar sua execução) apenas aguardando a disponibilidade do processador.

