# SD-PrioridadeThreadsJava

Este repositório contém um programa em Java que demonstra o uso de prioridades em threads. Ele cria duas threads com diferentes prioridades para mostrar como o sistema as gerencia.

## Descrição do Código

O programa define duas classes de threads:

**BaixaPrioridade**:
   - É uma thread configurada com prioridade mínima.
   - Executa continuamente, imprimindo a mensagem:
     ---
     Thread de baixa prioridade executando -> 1
     ---
   - Por ter prioridade baixa, pode ser preterida por outras threads com prioridade maior.

**AltaPrioridade**:
   - É uma thread configurada com prioridade máxima.
   - Executa com pausas curtas (10 milissegundos) e imprime a mensagem:
     ```
     Thread de alta prioridade executando -> 10
     ```
   - Por ter prioridade alta, tende a receber mais tempo de execução do sistema.

**Gerenciador de Threads (`LancadorPrioridade`)**:
   - Inicia as duas threads (`start()`).
   - Inclui um "Shutdown Hook" para encerrar as threads quando o programa for encerrado.
   - As threads são interrompidas (`interrupt()`) para evitar loops infinitos.

### Como o programa funciona:
- Ao iniciar, as threads começam a executar:
  - A thread de alta prioridade tende a imprimir suas mensagens mais frequentemente.
  - A thread de baixa prioridade imprime suas mensagens, mas é menos priorizada.
- Quando o programa é encerrado, o "Shutdown Hook" interrompe as threads de forma limpa.
