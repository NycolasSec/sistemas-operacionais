# Tipos e estruturas de SO

## Contextualizando

 - Tipos de SO
 - Como os SOs podem ser estruturados

## Tipos de SOs

Classificação quanto ao **compartilhamento de HW**:

### Sistemas operacionais Monoprogramados ou monotarefa:

 - Só permitem um programa ativo em um dado período, o qual permanece na RAM até o seu fim (Ex.: MS-DOS)

### Sistemas operacionais Multiprogramados ou multitarefa:

 - Mantêm mais de um programa na memória, para permitir o compartilhamento de tempo de CPU e demais recursos (Ex.: UNIX, Windows)

## SOs Monoprogramados ou Monotarefa

1. Caracterizam-se por permitir que o processador, a memória e os periféricos permaneçam exclusivamente dedicados á execução de um único programa.
2. Recursos mal utilizados, entretanto, são implementados com facilidade.
3. São simples de serem programados.

## SOs Multiprogramados ou Multitarefa

1. Aideia é manter **vários programas** em memória ao mesmo tempo.
2. Há várias tarefas simultâneas, em um únivo processador: enquanto uma espera, a outra roda.
3. Demandam mecanismo de trocas rápidas de processos.

### Podem ser classificados quanto á interação permitida com as aplicações

 - Sistemas Batch.
 - Sistemas de tempo compartilhado (Time Sharing).
 - Sistemas de tempo real.

## SO Multitarefa em Batch

1. Sistemas Batch (Lote) consiste em submeter ao computador **um lote (batch) de progamas de uma só vez.**
2. Os jobs (script com lote de programas) do usuárioa são submetidos em ordem sequencial para a execução.
3. Não existe interação entre o usuário e o job durante sua execução.

## SO multitarefa interativo

1. O sistema permite que os usuários interajam com suas computações na forma de diálogo.
2. Pode ser projetado como sistemas monousuário ou multiusuário (usando conceitos de multiprogrmação e time sharing)

## Estrutura de SOs

SOs são normalmente grandes e complexas coleções de rotinas de software.

Projetistas devem dar grande ênfase á sua organização interna e estrutura:

1. Monolítica
2. Micronúcleo (microkernel)
3. Camadas
4. Máquina virtual

## Estrutura monolítica

SO é um único módulo.

Consiste de um conjunto de programas que executam sobre o hardware, como se fosse um único programa.

Os programas de usuário invocam rotinas de SO.

## Estrutura Microkernel

Busca se tornar o núcleo do SO o menor possível.

A principal função do núcleo é gerenciar a comunicação entre esees processos.

Núcleo fornece serviços de alocação de CPU e de comunicação aos processos (IPC).

## Estrutura de Camadas

A ideia é criar um SO:

1. Modular - Divisão de um programa complexo em módulos de menor complexidade.
2. Hierárquico - A cada nível, os detalhes de operação dos níveis inferiores podem ser ignorados.

As interfaces são definidas para facilitar a interação entre os módulos hierárquixos.

## Estrutura de Máquina Virtual

Essa estrutura cria um nível intermediário entre o hardware e o SO, denominado Gerência de VM.

Esse nível cria diversas VMs independentes.

Cada VM oferece uma cópia virtual do Hardware, incluindo modod=s de acesso, interrupções, dispositivos de E/S, etc.

