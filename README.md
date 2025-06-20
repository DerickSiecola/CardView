# CardView

## Descrição

Este projeto é responsável por exibir as cartas de cada jogador em um jogo de cartas de Pokémon. A aplicação consulta serviços de distribuição de cartas e de jogadores para recuperar as informações necessárias sobre os jogadores e suas cartas. Além disso, a aplicação consulta a PokéAPI para recuperar as informações necessárias sobre os Pokémon.

## Padrão de Arquitetura

O padrão de arquitetura escolhido foi o SPA (Single Page Application). Essa abordagem se encaixa perfeitamente no projeto, pois permite o desenvolvimento de um frontend em que as páginas não precisam ser recarregadas a cada interação. Dessa forma, conseguimos garantir uma navegação mais fluida, rápida e dinâmica para o usuário, melhorando significativamente a experiência de uso da aplicação.

## Padrão de Arquitetura

O projeto faz uso de três Design Patterns clássicos de Engenharia de Software para melhorar a organização, manutenção e escalabilidade do código.

1. Factory Pattern

O Factory Pattern foi utilizado para centralizar a lógica de criação das cartas Pokémon no projeto. Em vez de criar objetos de carta diretamente em várias partes do código, a aplicação conta com uma classe de Fábrica (PokemonCardFactory) responsável por produzir instâncias completas de cartas, incluindo detalhes como id, nome, sprite e outros atributos.

Benefícios:

Centralização da lógica de criação das cartas.

Otimização do código.

2. Observer Pattern (Padrão Observador)

O Observer Pattern foi aplicado para gerenciar o sistema de notificações da aplicação. O NotificationBell atua como um Observador, enquanto um NotificationObserver central armazena a lista de notificações e notifica automaticamente todos os componentes inscritos quando um novo evento acontece (como uma troca de cartas).

3. Facade Pattern (Padrão Fachada)

A Facade foi criada para simplificar e centralizar todas as interações com a PokéAPI, a API pública que fornece informações detalhadas sobre cada Pokémon. Em vez de espalhar requisições HTTP diretas pelo código, o projeto conta com uma camada de fachada (PokemonFacade) que expõe métodos simples para consulta de dados.

Benefícios:

Isola as dependências externas (como a PokéAPI).

Garante um único ponto de controle para tratamento de erros relacionados a chamadas externas.

## Funcionalidades

- **Consulta de Jogadores:** Recupera informações sobre os jogadores.
- **Consulta de Cartas:** Consulta o serviço de distribuição de cartas para obter as cartas de cada jogador.
- **Consulta de Pokémons:** Utiliza a PokéAPI para obter informações detalhadas sobre os Pokémon nas cartas.
- **Exibição de Cartas:** Exibe as cartas de cada jogador com as informações obtidas.

## Tecnologias Utilizadas
- **Front-end:** React
- **APIs:** PokéAPI

## Estrutura de Pastas

Abaixo está a organização das pastas e arquivos do projeto **CardView**:

```bash
CARDVIEW/
├── node_modules/                # Dependências do projeto
├── public/                      # Arquivos públicos (favicon, index.html, etc.)
├── src/                         # Código-fonte da aplicação
│   ├── api/                     # Funções para comunicação com a API
│   ├── assets/                  # Imagens e recursos estáticos
│   ├── auth/                    # Lógica de autenticação
│   ├── components/              # Componentes reutilizáveis da interface
│   │   ├── Details/             # Detalhes dos pokémon
│   │   ├── NotificationBell/    # Componente de notificações
│   │   ├── PokemonCard/         # Componente de exibição de cartas Pokémon
│   │   └── TradeModal/          # Componente modal para trocas
│   ├── pages/                   # Páginas principais da aplicação
│   │   ├── Collection/          # Página da coleção de cartas do jogador
│   │   ├── Login/               # Página de login
│   │   └── Register/            # Página de cadastro
│   ├── App.css                  # Estilos globais do App
│   ├── App.js                   # Componente principal da aplicação
│   ├── index.css                # Estilos globais do index
│   ├── index.js                 # Ponto de entrada da aplicação React
│   └── reportWebVitals.js       # Métricas de performance
├── .gitignore                   # Arquivos e pastas ignorados pelo Git
├── package-lock.json            # Lockfile do npm
├── package.json                 # Informações e dependências do projeto
└── README.md                    # Documentação do projeto
```

## UML
### Fluxograma
<img src="https://github.com/user-attachments/assets/d3666ccb-460c-46e1-a619-71e2740a1b9a" width="600">

#### Descrição  
O fluxograma descreve o funcionamento da tela do jogo, desde o início até a interação do usuário e a atualização da interface.

#### Explicação do Fluxograma  

- **Inicialização**: O jogo começa com o **carregamento de recursos** e a **configuração das interfaces**.  
- **Carregamento dos Dados**: O sistema verifica se os dados foram carregados corretamente.  
  - Se **SIM**, o processo segue para a renderização.  
  - Se **NÃO**, o sistema tenta **obter os dados das cartas**. Caso falhe, uma **mensagem de erro** é exibida.  
- **Renderização e Interação**: Se os dados foram carregados corretamente, a **tela é renderizada** e a **interatividade é ativada**.  
- **Loop de Interação**: O sistema monitora a interação do usuário:  
  - Se houver interação, a **tela é atualizada**.  
  - Caso contrário, o sistema **aguarda uma ação**.  
  - O sistema verifica se o usuário deseja sair:  
    - Se **SIM**, o jogo termina.  
    - Se **NÃO**, o loop continua.  

#### Conclusão  
O fluxograma garante uma **interação contínua** e uma **experiência de jogo fluida**, assegurando o carregamento correto dos recursos e o tratamento adequado de erros. Dessa forma, o sistema mantém uma interface responsiva e funcional.

#### Representação visual do fluxograma
https://www.figma.com/proto/KBulNzYqjDY3G5JKUM9EzH/Untitled?node-id=0-1&t=GX8Ta6zdOw1MqnI2-1

### Diagrama de Caso de Uso  
<img src="https://github.com/user-attachments/assets/4bec9fbc-ee45-4c71-bdaf-df2ae5a23f8c" width="600">

### Diagrama de Classe  
<img src="github.com/user-attachments/assets/e5fbdc78-777a-4dfc-a697-19eaa5cb6c9e" width="600">
