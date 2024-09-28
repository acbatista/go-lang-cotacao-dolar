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

## Como Executar

### Passo 1: Clonar o repositório

```bash
git clone https://github.com:acbatista/go-lang-cotacao-dolar.git
cd go-lang-cotacao-dolar
