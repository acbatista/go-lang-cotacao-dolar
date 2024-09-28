# Aplicação de Cotação do Dólar

Este projeto consiste em dois sistemas em Go: `client.go` e `server.go`, que simulam uma comunicação entre cliente e servidor para obter a cotação do dólar e salvar as informações no banco de dados e em um arquivo.

## Funcionalidades

- O `server.go` faz uma requisição à API de câmbio do Dólar e Real na URL: [https://economia.awesomeapi.com.br/json/last/USD-BRL](https://economia.awesomeapi.com.br/json/last/USD-BRL) e retorna a cotação atual.
- O servidor registra cada cotação recebida no banco de dados SQLite.
- O `client.go` faz uma requisição HTTP ao servidor para obter a cotação e a salva em um arquivo `cotacao.txt`.
- A aplicação utiliza `context` para gerenciar timeouts nas operações.

## Tecnologias Utilizadas

- **Go**: Linguagem de programação usada para o desenvolvimento da aplicação.
- **SQLite**: Banco de dados leve utilizado para armazenar as cotações.
- **HTTP**: Protocolo de comunicação entre o cliente e o servidor.
- **Context**: Usado para gerenciar timeouts e deadlines.

## Requisitos

- Go 1.23+ instalado
- Acesso à internet para consultar a API de câmbio

## Estrutura de diretorio
A estrutura de diretório para o seu projeto pode ser organizada da seguinte forma:

```bash
Copiar código
├── client.go         # Código do cliente
├── server.go         # Código do servidor
├── cotacao.txt       # Arquivo gerado pelo cliente com a cotação do dólar
├── cotacoes.db       # Banco de dados SQLite criado pelo servidor
├── README.md         # Instruções do projeto
├── go.mod            # Arquivo de módulo Go para gerenciar dependências
└── go.sum            # Checksum das dependências do projeto
```

Descrição dos Arquivos

- **client.go**: Código que implementa o cliente, responsável por fazer a requisição HTTP ao servidor para obter a cotação do dólar.

- **server.go**: Código que implementa o servidor, responsável por consumir a API de câmbio, salvar os dados no banco de dados SQLite e responder ao cliente.

- **cotacao.txt**: Arquivo gerado pelo cliente, que contém o valor atual da cotação do dólar no formato Dólar: {valor}.

- **cotacoes.db**: Banco de dados SQLite criado pelo servidor, onde as cotações obtidas são armazenadas.

- **README.md**: Arquivo de documentação que explica o projeto, como configurá-lo e executá-lo.

- **go.mod**: Arquivo que define o módulo Go e especifica as dependências do projeto, permitindo controle de versões de pacotes.

- *go.sum**: Arquivo que armazena o checksum (verificação de integridade) das dependências gerenciadas pelo Go.



## Como Executar

### Passo 1: Clonar o repositório

```bash
git clone https://github.com:acbatista/go-lang-cotacao-dolar.git
cd go-lang-cotacao-dolar

