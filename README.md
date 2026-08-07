Sistema de Controle de Estufa Inteligente

Sistema desenvolvido em Python para simular o monitoramento e o controle automatizado de uma estufa inteligente.

O projeto realiza a aquisição simulada de dados de temperatura, umidade do ar e umidade do solo, aplicando regras de controle para irrigação e geração de alertas. As informações são armazenadas em banco de dados SQLite e podem ser exportadas em formato JSON.

Objetivo

O projeto tem como objetivo demonstrar conceitos de automação, programação orientada a objetos, persistência de dados e processamento periódico de informações utilizando Python.

O sistema foi desenvolvido inicialmente como uma simulação computacional, permitindo que futuramente os sensores simulados possam ser substituídos por dispositivos físicos.

Funcionalidades

- Simulação de sensores de temperatura;
- Simulação de umidade relativa do ar;
- Simulação de umidade do solo;
- Controle automático da bomba de irrigação;
- Configuração de limites de temperatura e umidade;
- Geração automática de alertas;
- Registro de medições em banco SQLite;
- Armazenamento de configurações no banco de dados;
- Execução contínua utilizando threads;
- Registro de eventos utilizando logging;
- Exportação das medições para JSON;
- Configurações modificáveis sem alteração direta do código.

Tecnologias utilizadas

- Python
- SQLite
- SQL
- JSON
- Threading
- Logging
- Programação Orientada a Objetos

O projeto utiliza apenas bibliotecas disponíveis na biblioteca padrão do Python.

Arquitetura

flowchart TD

A[Sensores simulados] --> B[ControleEstufa]

B --> C{Análise das condições}

C --> D[Controle da irrigação]
C --> E[Geração de alertas]

D --> F[Banco SQLite]
E --> F

B --> F

F --> G[Exportação JSON]

Estrutura do projeto

estufa-inteligente-python/
│
├── README.md
├── .gitignore
├── LICENSE
│
├── src/
│   ├── __init__.py
│   ├── main.py
│   ├── banco.py
│   └── controle.py
│
├── tests/
│   └── test_controle.py
│
└── docs/
    └── arquitetura.md

Banco de dados

O sistema utiliza SQLite para persistir as informações.

São utilizadas três tabelas principais.

medicoes

Armazena as leituras realizadas pelo sistema:

- temperatura;
- umidade do ar;
- umidade do solo;
- estado da bomba;
- data e horário da medição.

alertas

Registra situações identificadas pelo sistema, como:

- temperatura elevada;
- temperatura abaixo do limite;
- baixa umidade do solo;
- baixa umidade do ar;
- erros durante a execução.

configuracoes

Permite armazenar parâmetros utilizados pelo sistema, incluindo:

- intervalo entre medições;
- temperatura mínima;
- temperatura máxima;
- umidade mínima do solo;
- umidade mínima do ar;
- ativação do controle automático da bomba.

Lógica de funcionamento

O sistema executa ciclos periódicos de monitoramento.

Em cada ciclo:

1. Os sensores simulados geram uma nova leitura.
2. Os valores são comparados aos limites configurados.
3. O sistema verifica a necessidade de irrigação.
4. Alertas são registrados quando necessário.
5. A medição é armazenada no banco SQLite.
6. O processo é repetido automaticamente em segundo plano.

Execução

Clone o repositório:

git clone URL_DO_REPOSITORIO

Entre na pasta:

cd estufa-inteligente-python

Execute:

python -m src.main

O sistema iniciará a aquisição simulada dos dados.

Para interromper:

Ctrl + C

Ao finalizar, as últimas medições poderão ser exportadas para um arquivo JSON.

Exemplo de saída

Sistema de Controle de Estufa Inteligente iniciado.

2026-08-07 15:30:10 [INFO] Loop de aquisição iniciado
2026-08-07 15:30:10 [INFO] Medição: T=24.31°C, UA=49.82%, US=44.10%, Bomba=Inativa
2026-08-07 15:30:15 [INFO] Medição: T=23.91°C, UA=50.27%, US=43.85%, Bomba=Inativa

Possíveis evoluções

O projeto foi estruturado de forma que possa futuramente receber novas funcionalidades, como:

- integração com sensores físicos;
- utilização de ESP32 ou Raspberry Pi;
- sensores de temperatura e umidade;
- sensores capacitivos de umidade do solo;
- controle de bombas e relés;
- comunicação MQTT;
- dashboard para visualização dos dados;
- API REST;
- interface web;
- gráficos históricos;
- integração com sistemas IoT;
- notificações automáticas;
- aprendizado de máquina para previsão das necessidades de irrigação.

Status

Projeto em desenvolvimento.

Atualmente o sistema utiliza sensores simulados para validar a lógica de aquisição de dados, persistência e automação.

Autora

Jenniffer Karla da Silva Araújo